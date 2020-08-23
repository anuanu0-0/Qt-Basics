# Qt-Basics
## Layouts
----------------
----------------
### FORM LAYOUT
--------------
![form](https://github.com/anuanu0-0/Qt-Basics/blob/master/img/form.png)
<pre>
```cpp
    QApplication app(argc, argv);
    QWidget *window = new QWidget;
    QLineEdit *firstNameLineEdit = new QLineEdit;
    QLineEdit *lastNameLineEdit = new QLineEdit;
    QSpinBox *ageSpinBox = new QSpinBox;
    ageSpinBox->setRange(1, 100);
    QComboBox *employmentStatusComboBox = new QComboBox;
    QStringList employmentStatus = {"Unemployed", "Employed", "NA"};
    employmentStatusComboBox->addItems(employmentStatus);
    QFormLayout *personalInfoFormLayout= new QFormLayout;
    personalInfoFormLayout->addRow("First Name:", firstNameLineEdit);
    personalInfoFormLayout->addRow("Lat Name:" ,lastNameLineEdit);
    personalInfoFormLayout->addRow("Age:" ,ageSpinBox);
    personalInfoFormLayout->addRow("Employemnt Status:", employmentStatusComboBox);
    window->setLayout(personalInfoFormLayout);
    window->show();
    return app.exec();
```
</pre>
    
### QVLAYOUT
--------------------
![Qvbox](https://github.com/anuanu0-0/Qt-Basics/blob/master/img/Qvbox.png)
 <pre>
        QApplication app(argc, argv);
        QWidget *window = new QWidget;
        QLabel *label1 = new QLabel("Username");
        QLabel *label2 = new QLabel("Password");
        QLineEdit *usernameLineEdit = new QLineEdit;
        usernameLineEdit->setPlaceholderText("Enter your username");
        QLineEdit *passwordLineEdit = new QLineEdit;
        passwordLineEdit->setEchoMode(QLineEdit::Password);
        passwordLineEdit->setPlaceholderText("Enter your password");
        QPushButton *loginBtn = new QPushButton("&Login");
        QPushButton *registerBtn = new QPushButton("&Register");
        QVBoxLayout *layout = new QVBoxLayout;
        layout->addWidget(label1);
        layout->addWidget(usernameLineEdit);
        layout->addWidget(label2);
        layout->addWidget(passwordLineEdit);
        layout->addWidget(loginBtn);
        layout->addWidget(registerBtn);
        window->setLayout(layout);
        window->show();
        return app.exec();
</pre>

###  QHLAYOUT
--------------------
![QHbox](https://github.com/anuanu0-0/Qt-Basics/blob/master/img/QHbox.png)
<pre>
        QApplication app(argc, argv);
        QWidget *window = new QWidget;
        QLineEdit *urlLineEdit = new QLineEdit;
        QPushButton *exportButton = new QPushButton("Export");
        urlLineEdit->setPlaceholderText("Enter URL to export. Eg, https://www.google.com");
        urlLineEdit->setFixedWidth(400);
        QHBoxLayout *layout = new QHBoxLayout;
        layout->addWidget(urlLineEdit);
        layout->addWidget(exportButton);
        window->setLayout(layout);
        window->show();
        return app.exec();
</pre>

### Signals and Slots
--------------------------
------------------------
#### Quit Application
--------------
<pre>
        QApplication app(argc, argv);
        QPushButton *quitButton = new QPushButton("Quit");
        QObject::connect(quitButton, SIGNAL(clicked()), &app, SLOT(quit()));
        quitButton->show();
        return app.exec();
</pre>

#### Dials
-----------------
![QHbox](https://github.com/anuanu0-0/Qt-Basics/blob/master/img/dials.png)
<pre>
        QApplication app(argc, argv);
        QWidget *window = new QWidget;
        QVBoxLayout *layout = new QVBoxLayout;
        QLabel *volumeLabel = new QLabel("0");
        QDial *volumeDial = new QDial;
        layout->addWidget(volumeDial);
        layout->addWidget(volumeLabel);
        QObject::connect(volumeDial, SIGNAL(valueChanged(int)), volumeLabel, SLOT(setNum(int)));
        window->setLayout(layout);
        window->show();
        return app.exec();
</pre>

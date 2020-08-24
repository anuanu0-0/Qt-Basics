# Qt-Basics
### Layouts
----------------

#### FORM LAYOUT

![form](https://github.com/anuanu0-0/Qt-Basics/blob/master/img/form.png)

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

    
#### QVLAYOUT

![Qvbox](https://github.com/anuanu0-0/Qt-Basics/blob/master/img/Qvbox.png)

```cpp
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
```

####  QHLAYOUT

![QHbox](https://github.com/anuanu0-0/Qt-Basics/blob/master/img/QHbox.png)
```cpp
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

```

### Signals and Slots
--------------------------

####  Quit Application


```cpp
        QApplication app(argc, argv);
        QPushButton *quitButton = new QPushButton("Quit");
        QObject::connect(quitButton, SIGNAL(clicked()), &app, SLOT(quit()));
        quitButton->show();
        return app.exec();

```

#### Dials

![QHbox](https://github.com/anuanu0-0/Qt-Basics/blob/master/img/dials.png)

```cpp
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

```

#### One Signal Multiple Slots eg-1
![multipleSlots](https://github.com/anuanu0-0/Qt-Basics/blob/master/img/multipleSlots.png)

```cpp
    QApplication app(argc, argv);
    QWidget *window = new QWidget;
    QVBoxLayout *layout = new QVBoxLayout;
    QLabel *volumeLabel = new QLabel("0");
    QDial *volumeDial = new  QDial;
    QLCDNumber *volumeLCD = new QLCDNumber;
    volumeLCD->setPalette(Qt::green);
    volumeLabel->setAlignment(Qt::AlignHCenter);
    volumeDial->setNotchesVisible(true);
    volumeDial->setMinimum(0);
    volumeDial->setMaximum(100);
    layout->addWidget(volumeDial);
    layout->addWidget(volumeLabel);
    layout->addWidget(volumeLCD);
    QObject::connect(volumeDial, SIGNAL(valueChanged(int)), volumeLabel, SLOT(setNum(int)));
    QObject::connect(volumeDial, SIGNAL(valueChanged(int)), volumeLCD, SLOT(display(int)));
    window->setLayout(layout);
    window->show();
    return app.exec();

```

#### Multiple slots eg-2

![mSlots](https://github.com/anuanu0-0/Qt-Basics/blob/master/img/mslots.png)

```cpp
    QApplication app(argc, argv);
    QWidget *window = new QWidget;
    QVBoxLayout *layout = new QVBoxLayout;
    QDial *volumeDial = new  QDial;
    QSlider *lengthSlider = new QSlider(Qt::Horizontal);
    QLCDNumber *volumeLCD = new QLCDNumber;
    volumeLCD->setPalette(Qt::green);
    volumeDial->setNotchesVisible(true);
    volumeDial->setMinimum(0);
    volumeDial->setMaximum(100);
    lengthSlider->setTickPosition(QSlider::TicksAbove);
    lengthSlider->setTickInterval(10);
    lengthSlider->setSingleStep(1);
    lengthSlider->setMinimum(0);
    lengthSlider->setMaximum(100);
    layout->addWidget(volumeDial);
    layout->addWidget(lengthSlider);
    layout->addWidget(volumeLCD);
    QObject::connect(volumeDial, SIGNAL(valueChanged(int)), volumeLCD, SLOT(display(int)));
    QObject::connect(lengthSlider, SIGNAL(valueChanged(int)), volumeLCD, SLOT(display(int)));
    window->setLayout(layout);
    window->show();
    return app.exec();
```


#### MenuBars

![menuBar](https://github.com/anuanu0-0/Qt-Basics/blob/master/img/menuBar.png)
![menuBar2](https://github.com/anuanu0-0/Qt-Basics/blob/master/img/menuBar2.png)



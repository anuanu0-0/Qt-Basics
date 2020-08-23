# Qt-Basics
![form](https://github.com/anuanu0-0/Qt-Basics/blob/master/img/form.png)
<pre>
FORM LAYOUT
--------------
    ![form](https://github.com/anuanu0-0/Qt-Basics/blob/master/img/form.png)

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
</pre>

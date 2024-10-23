# Proyecto De Interfaces

## Primer proyecto 

En este repositorio se manejan dos ramas la *master* y la *hotflix*. Y tiene ya tres actividades.

Las tres actividades son el **Login**, el **Sign Up** y el **Main**.


### LOGIN:

![LOGIN_ACTIVITY](img/Login.png)

Se consigue relacionar con **SignUp** mediante el siguiente código:

**En el Login.java :**

    public void openSignup(View view) {
        Intent intent = new Intent(Login.this, SignUp.class);
        startActivity(intent);
    }

**Y en el activity_login.xml :**

     <Button
        android:id="@+id/signup"
        android:text="SIGN UP"
        android:onClick="openSignup" <!--Desde aqui se llama al metodo para que
                                        al presionar el boton te mande a Sign Up-->
        app:cornerRadius="8dp"
        app:layout_constraintEnd_toEndOf="@id/guideline5"
        app:layout_constraintStart_toStartOf="@+id/guideline4"
        app:layout_constraintTop_toBottomOf="@id/login"
        style="@style/buttonStyle">
    </Button>



También se relacionan **Login** y **Main** por un codigo similar :

**En el Login.java :**

    public void openMain(View view) {
        Intent intent = new Intent(Login.this, Main.class);
        startActivity(intent);
    }

**Y en el activity_login.xml :**

        android:onClick="openMain"


### SIGN UP:

![SIGNUP_ACTIVITY](img/SignUp.png)

El SignUp cuenta con dos botones, *Confirm* y *Cancel* .El primero te mandara al **Main** y el segundo al **Login**
El código es el siguiente:

**Para ir al Login**

*SignUp.java*
        
    public void returnLogin(View view) {
        Intent intent = new Intent(SignUp.this, Login.class);
        startActivity(intent);
    }
    
*activity_signup.xml*
    
    android:id="@+id/cancelar"
    android:text="@string/cancel"
    android:onClick="returnLogin"

**Para ir al Main**

*SignUp.java*

     public void returnMain(View view) {
        Intent intent = new Intent(SignUp.this, Main.class);
        startActivity(intent);
    }

*activity_signup.xml*

    android:id="@+id/confirm"
    android:text="CONFIRM"
    app:cornerRadius="0dp"
    android:onClick="returnMain"


### MAIN:

![MAIN_ACTIVITY](img/Main.png)

El main todavia no tiene ningun boton por lo que solo es una pantalla.
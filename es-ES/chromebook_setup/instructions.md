Puedes [saltarte esta sección](http://tutorial.djangogirls.org/en/installation/#install-python) en caso de que no estés usando un Chromebook. Si lo eres, tu instalación sera un poco diferente. Puedes ignorar el resto de las instrucciones de instalación.

### Cloud IDE (PaizaCloud Cloud IDE, AWS Cloud9)

Cloud IDE es una herramienta que te da un editor de código y acceso a un ordenador conectado a internet en el que puedes instalar, escribir y ejecutar software. Durante este tutorial, el IDE en la nube te servirá como tu *máquina local*. Seguirás corriendo comandos en una interfaz de terminal justo como tus compañeros de clase en OS X, Ubuntu, o Windows, pero tu terminal será conenctada a una computadora corriendo en algún otro lugar que cloud IDE establecerá por tí. Aquí están las instrucciones para cloud IDEs (PaizaCloud Cloud IDE, AWS CLoud9). Puedes elegir uno de los IDEs en la nube, y seguir sus instrucciones.

#### PaizaCloud Cloud IDE

1. Ve a [PaizaCloud Cloud IDE](https://paiza.cloud/)
2. Crea una cuenta
3. Haga clic en *New Server* y elija la aplicación Django
4. Haga clic en el botón Terminal (al lado izquierdo de la ventana)

Ahora deberías ver una interfaz con una barra y botones en la izquierda. Haz click en al botón "Terminal" para abrir la ventana de la terminal con un símbolo de sistema como este:

{% filename %}Terminal{% endfilename %}

    $
    

La terminal en el Cloud IDE de PaizaCloud está preparada para ejecutar tus instrucciones. Puedes redimensionar o maximizar la ventana para hacerla un poco más grande.

#### AWS Cloud9

Actualmente Cloud 9 requiere que te registres con AWS e ingreses la información de una tarjeta de crédito.

1. Instala Cloud 9 desde la [Chrome web store](https://chrome.google.com/webstore/detail/cloud9/nbdmccoknlfggadpfkmcpnamfnbkmkcp)
2. Ve a [c9.io](https://c9.io) y haz clic en *Get started with AWS Cloud9*
3. Regístrate en una cuenta AWS (requiere información de tarjeta de crédito, pero puedes usar gratis)
4. En el panel de control AWS, introduzca *Cloud9* en la barra de búsqueda y haga clic en ella
5. En el panel de control de Cloud 9, haga clic en *Create environment*
6. Nómbralo *django-girls*
7. Mientras configura los ajustes, seleccione *Create a new instance for environment (EC2)* para "Environment Type" y seleccione el valor *t2.micro* para "Instance type" (debería decir "Free-tier eligible."). La configuración por defecto de ahorro de costes está bien y puede mantener los otros valores por defecto.
8. Haz clic en *Next step*
9. Haz clic en *Create environment*

Ahora deberías ver una interfaz con una barra, una gran ventana principal con algún texto y una ventana pequeña en la parte inferior que se vería así:

{% filename %}bash{% endfilename %}

    yourusername:~/workspace $
    

El área de abajo es tu terminal. Puedes usar el terminal para enviar instrucciones al ordenador remoto Cloud 9. Puedes redimensionar la ventana para hacerla un poco mas grande

### Entorno Virtual

Un entorno virtual (también llamado "virtualenv" o "vitual environment" en inglés) es un tipo de caja privada donde podemos introducir código para el proyecto en el cual estemos trabajando. Lo usamos para mantener separados los varios trozos de código de nuestros varios proyectos separados de este modo las cosas no se mezclan entre proyectos.

Ejecutar:

{% filename %}Cloud 9{% endfilename %}

    mkdir djangogirls
    cd djangogirls
    python3 -m venv myvenv
    source myvenv/bin/activate
    pip install django~={{ book.django_version }}
    

(nota que en la última línea usamos una virgulilla seguido de un signo igual `~=`).

### GitHub

Haz una cuenta de [GitHub](https://github.com).

### PythonAnywhere

El tutorial de Django Girls incluye una sección en lo que se conoce como Despliegue, lo cual se refiere al proceso de tomar el código que da vida a tu nueva aplicación web y moverlo a un ordenador de acceso publico (llamado servidor) para que otras personas puedan ver tu trabajo.

Esta parte del tutorial es algo extraña usando un Chromebook, pues ya estamos usando un computador conectado a Internet (contrario a, por ejemplo, una laptop). Sin embargo, aún es útil, ya que podemos pensar que nuestro espacio de trabajo en Cloud 9 como un lugar para nuestro trabajo "en progreso" y Python Anywhere como un lugar donde mostrar nuestro trabajo mientras se va haciendo más completo.

Por lo tanto, regístrate en una nueva cuenta de Python Anywhere en [www.pythonanywhere.com](https://www.pythonanywhere.com).
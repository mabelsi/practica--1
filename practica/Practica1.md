Universidad Pública de El Alto
Ingenieria de Sistemas  
Tecnologias Emergentes II  

**UNIV.:** Siñani Chavez Mabel  
**C.I.:** 9935027 L.P.
- - -
# PRACTICA N° 1 / Sistemas Empresariales
1. Explique que son los sistemas empresariales.
>Un sistema empresarial es un sistema central de la organización, que garantiza que la información se pueda transmitir atraves de todas las funciones empresariales, y todos los niveles de gestión, para soportar la operación y administración de una empresa.

>Está formado por muchos grupos. Cada tarea asignada a un grupo representará un elemento dinámico del sistema. Para la correcta operación de este sistema deben establecerse métodos de realimentación para informar de los logros de cada grupo. El acoplamiento cruzado entre los grupos funcionales debe reducirse a un mínimo para evitar retardos de tiempo que no son deseables en el sistema.
2. Describa cuales son las características más importantes de una aplicación empresarial.
 
- Acceso a **bases de datos**, usualmente a bases de datos relacionales 
- Operaciones **transaccionales**, cumple con las propiedades ACID.
- **Escalables**, permiten escalabilidad vertical y horizontal.
- **Disponibles**, idealmente prestan servicios de forma continua.
- **Seguras**, no todos los usuarios acceden con la misma funcionalidad.
- Permiten **integración** con otras tecnologías.
- Arquitectura **multicapa**.
- **Valida** los resultados del sistema o una entrada de usuario.
- Capacidad de **extender** la funcionalidad del sistema.
- **Flexibilidad** en realizar cambios de configuracion, manteniendo la integridad del sistema.
  
3. Investigue y proponga cinco (5) instituciones que requerirían aplicaciones de misión crítica. Justifique su respuesta.

4. Explique cuáles son las diferencias entre la escalabilidad horizontal y escalabilidad vertical.
>La ***escalabilidad vertical*** o hacia arriba, este es el **más simple**, pues significa crecer el hardware de uno de los nodos, es decir aumentar el hardware por uno más potente, como disco duro, memoria, procesador, etc. pero también puede ser la migración completa del hardware por uno más potente. El esfuerzo de este crecimiento es mínimo, pues no tiene repercusiones en el software, ya que solo será respaldar y migrar los sistemas al nuevo hardware.

>La ***escalabilidad horizontal*** es sin duda el **más potente**, pero también el **más complicado**. Este modelo implica tener varios servidores (conocidos como Nodos) trabajando como un todo. Se crea una red de servidores conocida como Cluster, con la finalidad de repartirse el trabajo entre todos nodos del cluster, cuando el performance del cluster se ve afectada con el incremento de usuarios, se añaden nuevos nodos al cluster, de esta forma a medida que es requeridos, más y más nodos son agregados al cluster.
   
5. Que es un servidor Web y que es un servidor de aplicaciones.

>El **servidor web** (también llamado webserver) es el software que se encarga de despachar el contenido de un sitio web al usuario.
Este proceso de despacho, que a simple vista parece muy simple, es en realidad más complejo de lo que parece, pues toda la «magia» de un webserver ocurre fuera de quien está navegando por un sitio web.

>Un **servidor de aplicaciones** es un programa de servidor en un equipo en una red distribuida que proporciona la lógica de negocio para un programa de aplicación. El servidor de aplicaciones se ve frecuentemente como parte de una aplicación de tres niveles, que consta de un servidor gráfico de interfaz de usuario (GUI), un servidor de aplicaciones (lógica empresarial) y un servidor de bases de datos y transacciones. De manera más descriptiva, se puede visualizar como la división de una aplicación.

6. Con un gráfico explique cómo funciona el protocolo HTTP.

   ![img](..\practica\protocolo.png)

7. Explique los elementos importantes de REQUEST en HTTP.

- Una línea de request para obtener el recurso, por ejemplo un request con el método GET /content/page1.html está requiriendo el recurso llamado /content/page1.html del servidor.
- Encabezados. Indican cosas como el lenguaje, codificación, tipo de datos (XML,JSON, etc). (Por ejemplo– Accept-Language: EN).
- Una línea vacía.
- Un cuerpo del mensaje que es opcional. Entre aplicaciones esta es la parte mas importante. Por ejemplo, yo puedo enviar un XML o un JSON  a otra máquina, y el servidor web interpretara la información que yo le mando.

8. Explique los elementos importantes de RESPONSE en HTTP.

- HTTP Status Code (Por ejemplo HTTP/1.1 301 Movido Permanentemente, significa que el recurso requerido fue movido permanentemente y redirigido a otro recurso).
- Encabezados. Igual que en el request, describen el contenido del response (Example – Content-Type: html)
- Una línea vacía.
- Un cuerpo de mensaje, que es opcional. Cuando trabajamos con aplicaciones, aquí puede venir la respuesta en XML u otro formato. Cuando es una página del navegador, contiene el código HTML que forma nuestra página.
9.  Describa con un gráfico la arquitectura Java EE.

    ![img](..\practica\arquitectura.png)

10.   Explique cuáles son los contenedores, componentes y servicios de Java EE.
>Un **contenedor** es un entorno de ejecución que provee al componente una serie de servicios.
Java EE define los siguientes tipos de contenedores: 
- Contenedor web.
- Contenedor de negocio (o de EJBs).

>Un **componente** es una unidad de software que forma parte de una aplicación. Java EE define los siguientes tipos de componentes:
- Componente cliente: Cliente AWT, Swing, Applety navegador Web.
- Componente web: Servlet, JSP y JSF.
- Componente de negocio: EJB.
Cada tipo cubre necesidades concretas y se basan en APIs especificas.

> Son los **servicios** que deben ofrecer los contenedores Java EE. Java EE define los siguientes servicios:
- De directorio: para la indexación y búsqueda de componentes y recursos.
- De despliegue: para poder personalizar los componentes y recursos.
- De transaccionalidad: para poder ejecutar distintas acciones en una misma unidad transaccional.
- De seguridad: para poder autenticar y autorizar a los usuarios de la aplicación.
- De acceso a datos: para facilitar el acceso a Bases de Datos.
- De conectividad: para poder acceder fácilmente a distintos EIS.
- De mensajería: para poder comunicarse con otros componentes, aplicaciones o EIS.
1.    Investigue los métodos más utilizados de las clases HttpServlet, HttpServletRequest y HttpServletResponse, y para cada uno de los métodos muestre un ejemplo.

**METODOS UTILIZADOS:**   
- doGet()
- getWriter()
- setContentType (tipo de cadena)
~~~
package hall;
import java.io.*; 
import javax.servlet.*; 
import javax.servlet.http.*;
public class HelloWorld extends HttpServlet {  
   public void doGet(HttpServletRequest request,         
   HttpServletResponse response)      
   throws ServletException, IOException {   
      PrintWriter out = response.getWriter();    
      out.println("Hello World");  } 
      }
~~~
~~~
public class SimpleServlet extends HttpServlet {
    public void doGet (HttpServletRequest request, HttpServletResponse response)
    throws ServletException, IOException {    
       PrintWriter out;    
       String title = "Simple Servlet Output";
    response.setContentType("text/html");   
    out = response.getWriter();    
    out.println("<HTML><HEAD><TITLE>");    
    out.println(title);    
    out.println("</TITLE></HEAD><BODY>");    
    out.println("<H1>" + title + "</H1>");    
    out.println("<P>This is output from SimpleServlet.");    
    out.println("</BODY></HTML>");    
    out.close();    
    } 
}
~~~

~~~
  import java.io.*;
  import javax.servlet.*;
  import javax.servlet.http.*;
  import java.util.*;

  public class Refresh extends HttpServlet {
 
   public void doGet(HttpServletRequest request, HttpServletResponse response)
      throws ServletException, IOException {
      response.setIntHeader("Refresh", 5);
      response.setContentType("text/html");
      Calendar calendar = new GregorianCalendar();
      String am_pm;
      int hour = calendar.get(Calendar.HOUR);
      int minute = calendar.get(Calendar.MINUTE);
      int second = calendar.get(Calendar.SECOND);
      if(calendar.get(Calendar.AM_PM) == 0)
         am_pm = "AM";
      else
         am_pm = "PM";
      String CT = hour+":"+ minute +":"+ second +" "+ am_pm;
      PrintWriter out = response.getWriter();
      String title = "Auto Refresh Header Setting";
      String docType =
         "<!doctype html public \"-//w3c//dtd html 4.0 " + "transitional//en\">\n";
      out.println(docType +
         "<html>\n" +
         "<head><title>" + title + "</title></head>\n"+
         "<body bgcolor = \"#f0f0f0\">\n" +
         "<h1 align = \"center\">" + title + "</h1>\n" +
         "<p>Current Time is: " + CT + "</p>\n"
      );
   }
   public void doPost(HttpServletRequest request, HttpServletResponse response)
      throws ServletException, IOException {
      doGet(request, response);
   }
  }
~~~


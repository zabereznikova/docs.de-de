---
title: Entwickeln von ASP.NET Core MVC-Apps
description: Entwerfen moderner Webanwendungen mit ASP.NET Core und Azure | Entwickeln von ASP.NET Core-Apps
author: ardalis
ms.author: wiwagn
ms.date: 12/04/2019
ms.openlocfilehash: a18b4dfc60c7d3971136f73f333b7225735710b3
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503943"
---
# <a name="develop-aspnet-core-mvc-apps"></a>Entwickeln von ASP.NET Core MVC-Apps

> „Sie müssen nicht schon beim ersten Mal alles richtig machen, aber unbedingt beim letzten Mal.“  
> _– Andrew Hunt and David Thomas_

ASP.NET Core ist ein plattformübergreifendes Open-Source-Framework zum Erstellen moderner cloudoptimierter Webanwendungen. ASP.NET Core-Apps sind einfach und modular aufgebaut. Sie verfügen über integrierte Unterstützung für Dependency Injection, wodurch ihre Testfähigkeit und Verwaltbarkeit verbessert wird. In Kombination mit MVC (einem Muster, das neben ansichtsbasierten Apps das Erstellen von modernen Web-APIs unterstützt) stellt ASP.NET Core ein leistungsstarkes Framework zum Erstellen von Unternehmenswebanwendungen dar.

## <a name="mvc-and-razor-pages"></a>MVC und Razor Pages

ASP.NET Core MVC enthält viele Features, die für das Erstellen von webbasierten APIs und Apps nützlich sind. MVC bedeutet „Model View Controller“. Dabei handelt es sich um ein Benutzeroberflächenmuster, das die Zuständigkeit für die Reaktion auf Anforderungen von Benutzern aufteilt. Wenn Sie dieses Muster verwenden, können Sie ebenfalls Features als sogenannte Razor Pages in Ihre ASP.NET Core-Apps implementieren. Razor Pages werden in ASP.NET Core MVC integriert und verwenden die gleichen Features für Vorgänge wie das Routing oder die Modellbindung. Dafür werden jedoch nicht wie üblich verschiedene Ordner und Dateien für Controller oder Ansichten und auch kein attributbasiertes Routing verwendet. Razor Pages werden in einem einzelnen Ordner (/Pages) gespeichert, das Routing basiert auf deren relativen Speicherort in diesem Ordner, und Anforderungen werden mit Handlern anstatt mit Controlleraktionen verarbeitet.

Wenn Sie eine neue ASP.NET Core-App erstellen, sollten Sie sich zuvor genau überlegen, was die erstellte App leisten soll. In Visual Studio können Sie aus mehreren Vorlagen auswählen. Am häufigsten werden die drei Projektvorlagen „Web-API“, „Webanwendung“ und „Webanwendung (Model View Controller)“ verwendet. Sie können sich zwar nur beim Erstellen des Projekts für eine Vorlage entscheiden, aber die Entscheidung ist nicht endgültig. Ein Projekt für Web-APIs verwendet Standard-MVCs, enthält aber standardmäßig keine Ansichten. Die Standardvorlage für Webanwendungen verwendet Razor Pages, enthält aber ebenfalls keinen Ordner für Ansichten. Sie können einen entsprechenden Ordner im Nachhinein zu diesen Projekten hinzufügen, um auf Ansichten basierendes Verhalten zu unterstützen. Web-API- und Model View Controller-Projekte enthalten standardmäßig keinen Pages-Ordner. Sie können diesen jedoch im Nachhinein hinzufügen, um Razor Pages zu unterstützen. Diese drei Vorlagen unterstützen drei verschiedene Arten der Standardbenutzerinteraktion: datenbasierte (Web-API), seitenbasierte und ansichtsbasierte Interaktionen. Sie können diese jedoch nach Bedarf alle in einem Projekt verwenden.

### <a name="why-razor-pages"></a>Was spricht für Razor Pages?

Razor Pages werden standardmäßig für neue Webanwendungen in Visual Studio verwendet. Mithilfe von Razor Pages können Sie seitenbasierte Anwendungsfeatures (wie Nicht-Single-Page-Formulare) einfacher erstellen. Wenn Controller und Ansichten verwendet werden, enthalten Anwendungen häufig sehr große Controller, die mit mehreren Abhängigkeiten und Ansichtsmodellen arbeiten und viele unterschiedliche Ansichten zurückgeben. Dadurch wird die Anwendung komplexer, und häufig sind Controller vorhanden, die das Single Responsibility Principle (Prinzip der eindeutigen Verantwortlichkeit) oder das Offen-Geschlossen-Prinzip nicht befolgen. Dieses Problem wird durch Razor Pages behoben, indem die serverseitige Logik für eine bestimmte lokale Seite in einer Webanwendung mit entsprechendem Razor-Markup gekapselt wird. Eine Razor Page ohne serverseitige Logik kann aus einer Razor-Datei bestehen (z.B. „Index.cshtml“). Den meisten nicht trivialen Razor Pages ist jedoch eine Seitenmodellklasse zugeordnet, die üblicherweise genauso wie die Razor-Datei benannt wird, aber die Erweiterung „.cs“ aufweist (z.B. „Index.cshtml.cs“).

Das Seitenmodell einer Razor Page kombiniert die Zuständigkeit eines MVC und eines Ansichtsmodells. Anforderungen werden nicht mit Controlleraktionsmethoden verarbeitet, sondern Seitenmodellhandler wie OnGet() werden ausgeführt, um die zugehörige Seite standardmäßig zu rendern. Durch Razor Pages wird das Erstellen einzelner Seiten in einer ASP.NET Core-App vereinfacht, während alle Architekturfeatures von ASP.NET Core MVC genutzt werden können. Diese sind für neue seitenbasierte Funktionen gut geeignet.

### <a name="when-to-use-mvc"></a>Wann sollten Sie MVC verwenden?

Wenn Sie Web-APIs erstellen, ist das MVC-Muster besser als Razor Pages geeignet. Wenn Ihr Projekt nur Web-API-Endpunkte verfügbar macht, sollten Sie idealerweise mit der Web-API-Projektvorlage beginnen. Andernfalls ist es auch ganz einfach, Controller und zugehörige API-Endpunkte zu einer beliebigen ASP.NET Core-App hinzuzufügen. Verwenden Sie den ansichtsbasierten MVC-Ansatz, wenn Sie eine vorhandene Anwendung mit geringem Aufwand von ASP.NET Core MVC 5 oder früher zu ASP.NET Core MVC migrieren möchten. Nach der Migration können Sie überprüfen, ob Razor Pages für neue Feature oder als gesamte Migration sinnvoll eingesetzt werden können.

Die Leistung Ihrer Web-App hängt nur geringfügig davon ab, ob Sie Razor Pages oder MVC-Ansichten verwenden, außerdem werden bei beiden Methoden Features wie Abhängigkeitsinjektion, Filter, Modellbindung, Validierung usw. unterstützt.

## <a name="mapping-requests-to-responses"></a>Zuordnen von Anforderungen zu Antworten

Im Wesentlichen dienen ASP.NET Core-Apps dazu, eingehende Anforderungen ausgehenden Antworten zuzuordnen. Auf niedriger Ebene wird dazu Middleware verwendet. Daher kann es sein, dass ASP.NET Core-Apps und -Microservices ausschließlich aus benutzerdefinierter Middleware bestehen. Wenn Sie ASP.NET Core MVC verwenden, können Sie auf einer allgemeineren Ebene arbeiten und _Routen_, _Controller_ und _Aktionen_ hinzufügen. Jede eingehende Anforderung wird mit der Routingtabelle der Anwendung verglichen, und wenn eine übereinstimmende Route gefunden wird, wird die zugewiesene Aktionsmethode (des Controllers) aufgerufen, um die Anforderung zu verarbeiten. Wenn keine übereinstimmende Route gefunden wird, wird ein Fehlerhandler aufgerufen und das Ergebnis „NotFound“ zurückgegeben.

ASP.NET Core MVC-Apps können entweder herkömmliche Routen oder Attributrouten oder beides gleichzeitig verwenden. Herkömmliche Routen werden als Code definiert und geben unter Verwendung einer wie im Folgenden dargestellten Syntax _Routingkonventionen_ an:

```csharp
app.UseEndpoints(endpoints =>
{
    endpoints.MapControllerRoute(name: "default", pattern: "{controller=Home}/{action=Index}/{id?}");
});
```

In diesem Beispiel wurde eine Route mit dem Namen „Standard“ der Routingtabelle hinzugefügt. Sie definiert eine Routenvorlage mit Platzhaltern für den _Controller_, die _Aktion_ und die _ID_. Für die Platzhalter für den Controller und die Aktion ist „Standard“ angegeben („Home“ bzw. „Index“). Der Platzhalter für die ID ist hingegen optional, da ein Fragezeichen („?“) hinzugefügt wurde. Die hier definierte Konvention drückt aus, dass der erste Teil einer Anforderung dem Namen eines Controllers und der zweite Teil der Aktion entsprechen soll. Außerdem kann wenn nötig ein dritter Teil den ID-Parameter darstellen. Herkömmliche Routen werden in der Regel an einer bestimmten Stelle wie der Methode „Configure“ in der Klasse „Startup“ für die Anwendung definiert.

Attributrouten gelten für Controller und Aktionen direkt und werden nicht global angegeben. Das hat den Vorteil, dass sie besser zu finden sind, wenn Sie eine bestimmte Methode betrachten. Andererseits bedeutet dies aber auch, dass die Routinginformationen nicht an einer bestimmten Stelle in der Anwendung gespeichert sind. Sie können mit Attributrouten problemlos mehrere Routen für eine bestimmte Aktion festlegen und gleichzeitig aber auch Routen zwischen Controllern und Aktionen kombinieren. Zum Beispiel:

```csharp
[Route("Home")]
public class HomeController : Controller
{
    [Route("")] // Combines to define the route template "Home"
    [Route("Index")] // Combines to define route template "Home/Index"
    [Route("/")] // Does not combine, defines the route template ""
    public IActionResult Index() {}
}
```

Routen können über [HttpGet] und ähnliche Attribute angegeben werden, weshalb keine separaten [Route]-Attribute hinzugefügt werden müssen. Ebenso können wie folgt Token von Attributrouten verwendet werden, damit die Namen von Controllern oder Aktionen seltener wiederholt werden müssen:

```csharp
[Route("[controller]")]
public class ProductsController : Controller
{
    [Route("")] // Matches 'Products'
    [Route("Index")] // Matches 'Products/Index'
    public IActionResult Index() {}
}
```

Für Razor Pages wird kein Attributrouting verwendet. Sie können in der `@page`-Anweisung einer Razor Page jedoch zusätzliche Informationen zu Routingvorlagen angeben:

```csharp
@page "{id:int}"
```

Im vorherigen Beispiel hat die Seite Routen mit einem ganzzahligen `id`-Parameter abgeglichen. Die Seite *Products.cshtml*, die sich im Stamm von `/Pages` befindet, würde beispielsweise folgende Route aufweisen:

```csharp
"/Products/123"
```

Nachdem eine bestimmte Anforderung einer Route zugeordnet wurde, aber noch bevor die Aktionsmethode aufgerufen wird, führt ASP.NET Core MVC Vorgänge zur [Modellbindung](/aspnet/core/mvc/models/model-binding) und [Modellvalidierung](/aspnet/core/mvc/models/validation) für die Anforderung aus. Die Modellbindung ist notwendig, um eingehende HTTP-Daten in .NET-Typen zu konvertieren, die als Parameter der aufzurufenden Aktionsmethode angegeben wurden. Wenn z.B. die Aktionsmethode einen int-ID-Parameter erwartet, versucht die Modellbindung, diesen Parameter über einen Wert bereitzustellen, der Teil der Anforderung ist. Dafür sucht die Modellbindung nach bereitgestellten Formularwerten, Werten in der Route selbst und Werten von Abfragezeichenfolgen. Wenn ein ID-Wert gefunden wird, wird dieser in eine ganze Zahl konvertiert, bevor dieser an die Aktionsmethode übergeben wird.

Nach der Modellbindung, aber noch vor dem Aufruf der Aktionsmethode, wird eine Modellvalidierung vorgenommen. Die Modellvalidierung verwendet optionale Attribute für den Modelltyp. In diesem Zusammenhang kann ggf. sichergestellt werden, dass das bereitgestellte Modellobjekt mit bestimmten Anforderungen an Daten konform ist. Bestimmte Werte sind möglicherweise entsprechend den Anforderungen angegeben oder auf eine bestimmte Länge bzw. einen bestimmten numerischen Bereich beschränkt. Wenn Validierungsattribute angegeben sind, das Modell aber nicht deren Anforderungen entspricht, wird für die Eigenschaft „ModelState.IsValid“ FALSE zurückgegeben. Dann können die fehlerhaften Validierungsregeln an den Client gesendet werden, von dem die Anforderung ausgeht.

Wenn Sie die Modellvalidierung verwenden, sollten Sie stets überprüfen, ob das Modell gültig ist, bevor Sie einen Befehl ausführen, der Einfluss auf den Status haben kann. Dadurch stellen Sie sicher, dass die App nicht durch ungültige Daten beschädigt wird. Sie können einen [Filter](/aspnet/core/mvc/controllers/filters) verwenden, damit Sie nicht für jede Aktion Code für die Modellvalidierung hinzufügen müssen. Mithilfe von ASP.NET Core MVC-Filtern können Sie Gruppen von Anforderungen abfangen, damit allgemeine Richtlinien und übergreifende Aspekte gezielt angewendet werden können. Filter können sowohl auf individuelle Aktionen als auch auf vollständige Controller oder global auf eine ganze Anwendung angewendet werden.

Im Hinblick auf Web-APIs unterstützt ASP.NET Core MVC die [_Inhaltsaushandlung_](/aspnet/core/mvc/models/formatting). Dadurch können Anforderungen angeben, wie Antworten formatiert werden sollen. Auf der Grundlage von in Anforderungen enthaltenen Headern formatieren Aktionen, die Daten zurückgeben, die Antworten in XML, JSON oder einem beliebigen anderen unterstützten Format. Mithilfe dieses Features kann dieselbe API in mehreren Clients mit unterschiedlichen Anforderungen an das Datenformat verwendet werden.

Für Web-API-Projekte sollte das `[ApiController]`-Attribut verwendet werden, das auf einzelne Controller, eine Basiscontrollerklasse oder die gesamte Assembly angewendet werden kann. Durch dieses Attribut wird eine automatische Modellüberprüfung hinzugefügt, und jede Aktion, bei der ein ungültiges Modell verwendet wird, gibt den Fehler „BadRequest“ mit Details zu den Überprüfungsfehlern zurück. Wenn dieses Attribut verwendet wird, müssen alle Aktionen eine Attributroute anstelle einer konventionellen Route aufweisen. Das Attribut gibt zudem ausführlichere Informationen zu aufgetretenen Fehlern zurück.

> ### <a name="references--mapping-requests-to-responses"></a>Ressourcen: Zuordnen von Anforderungen zu Antworten
>
> - **Routing to Controller Actions (Routing zu Controlleraktionen)** 
 > <https://docs.microsoft.com/aspnet/core/mvc/controllers/routing>
> - **Modellbindung in ASP.NET Core**
 > <https://docs.microsoft.com/aspnet/core/mvc/models/model-binding>
> - **Model Validation (Modellvalidierung)** 
 > <https://docs.microsoft.com/aspnet/core/mvc/models/validation>
> - **Filter in ASP.NET Core**
 > <https://docs.microsoft.com/aspnet/core/mvc/controllers/filters>
> - **ApiController Attribute (ApiController-Attribut)** 
 > <https://docs.microsoft.com/aspnet/core/web-api/>

## <a name="working-with-dependencies"></a>Arbeiten mit Abhängigkeiten

Die Technik [Dependency Injection](/aspnet/core/fundamentals/dependency-injection) wird von ASP.NET Core unterstützt und intern verwendet. Es handelt sich dabei um eine Technik, die die lose Kopplung von unterschiedlichen Teilen einer Anwendung ermöglicht. Eine losere Kopplung stellt einen Vorteil dar, da dadurch verschiedene Teile der Anwendung besser isoliert voneinander getestet oder ersetzt werden können. Außerdem wird es dadurch unwahrscheinlicher, dass eine Änderung eines Teils der Anwendung zu unerwarteten Auswirkungen auf die restliche Anwendung führen kann. Dependency Injection basiert auf dem Prinzip der Dependency Inversion und stellt häufig ein wichtiges Mittel dar, um das Offen/Geschlossen-Prinzip durchzusetzen. Wenn Sie auswerten, wie die Anwendung mit ihren Abhängigkeiten funktioniert, sollten Sie schlecht strukturierten Code im [statischen Zusammenhang](https://deviq.com/static-cling/) vermeiden und den Leitsatz [New is Glue](https://ardalis.com/new-is-glue) („New“ ist klebrig) beachten.

Es entsteht ein statischer Zusammenhang, wenn Ihre Klassen statische Methoden aufrufen oder auf statische Eigenschaften zugreifen, die Nebenwirkungen oder Abhängigkeiten von der Infrastruktur umfassen. Wenn Sie z.B. über eine Methode verfügen, die eine statische Methode aufruft, die wiederum in eine Datenbank schreibt, wird Ihre Methode eng an die Datenbank gekoppelt. Jegliches Element, das den Datenbankaufruf unterbricht, unterbricht auch die Methode. Es ist bekannt, dass es sehr schwierig ist, diese Methode zu testen, da dafür entweder kommerzielle Testbibliotheken erforderlich sind, die statische Aufrufe testen, oder die Tests nur mit einer aktiven Testdatenbank ausgeführt werden können. Statische Aufrufe, bei denen keine Abhängigkeiten von der Infrastruktur bestehen, insbesondere die vollständig zustandslosen, können ohne Bedenken aufgerufen werden und haben (abgesehen von Kopplungscode und statischen Aufrufen an sich) keine Auswirkung auf die Kopplung oder Testfähigkeit.

Viele Entwickler kennen zwar das Risiko von statischen Zusammenhängen und globalen Status, koppeln ihren Code aber dennoch über direkte Instanziierung eng an bestimmte Implementierungen. Der Leitsatz „new is glue“ („new“ fungiert als Klebstoff) soll an diese Kopplung erinnern und stellt keine generelle Verurteilung der Verwendung des Schlüsselworts `new` dar. Genauso wie statische Methodenaufrufe koppeln neue Instanzen von Typen ohne externe Abhängigkeiten Code nicht eng an die Implementierungsdetails, und sie erschweren auch nicht den Testvorgang. Sie sollten aber jedes Mal, wenn eine Klasse instanziiert wird, überlegen, ob es sinnvoll ist, vordefinierten Code für diese Instanz an einem bestimmten Ort zu verwenden, oder ob Sie besser festlegen sollten, dass diese Instanz als eine Abhängigkeit abgefragt wird.

### <a name="declare-your-dependencies"></a>Deklarieren Ihrer Abhängigkeiten

ASP.NET Core ist so konzipiert, dass Methoden und Klassen ihre jeweiligen Abhängigkeiten deklarieren und diese als Argumente anfordern. ASP.NET-Anwendungen werden in der Regel in Startklassen eingerichtet, die so konfiguriert sind, dass sie an mehreren Stellen Dependency Injection unterstützen. Wenn Ihre Startklasse über einen Konstruktor verfügt, kann sie über diesen wie folgt Abhängigkeiten anfordern:

```csharp
public class Startup
{
    public Startup(IHostingEnvironment env)
    {
        var builder = new ConfigurationBuilder()
            .SetBasePath(env.ContentRootPath)
            .AddJsonFile("appsettings.json", optional: false, reloadOnChange: true)
            .AddJsonFile($"appsettings.{env.EnvironmentName}.json", optional: true);
    }
}
```

Die Startklasse ist von Bedeutung, weil es keine expliziten Typanforderungen an sie gibt. Sie erbt weder von einer besonderen Basisstartklasse und implementiert auch keine bestimmte Schnittstelle. Sie können ihr optional einen Konstruktor zuweisen und beliebig viele Parameter für diesen angeben. Wenn der Web-Host, den Sie für Ihre Anwendung konfiguriert haben, startet, ruft dieser die von Ihnen festgelegte Startklasse auf und verwendet Dependency Injection, um jegliche Abhängigkeiten aufzufüllen, die die Startklasse erfordert. Wenn Sie Parameter anfordern, die nicht in den von ASP.NET Core verwendeten Dienstcontainern konfiguriert sind, wird eine Ausnahme ausgelöst. Wenn Sie sich jedoch nur auf die Abhängigkeiten beziehen, die dem Container bekannt sind, können Sie jede beliebige Anforderung senden.

Dependency Injection ist in ASP.NET Core-Apps schon von Beginn an integriert, wenn Sie die Startinstanz erstellen. Dies bezieht sich auch auf die Startklasse. Außerdem können Sie Abhängigkeiten in der Methode „Configure“ anfordern:

```csharp
public void Configure(IApplicationBuilder app,
    IHostingEnvironment env,
    ILoggerFactory loggerFactory)
{

}
```

Die Methode „ConfigureServices“ stellt eine Ausnahme in Bezug auf dieses Verhalten dar, da sie nur einen Parameter des Typs IServiceCollection benötigt. Sie muss nicht unbedingt Dependency Injection unterstützen, da sie einerseits dafür verantwortlich ist, dem Dienstcontainer Objekte hinzuzufügen, und andererseits über den IServiceCollection-Parameter Zugriff auf alle zu diesem Zeitpunkt konfigurierten Dienste hat. Daher können Sie in der gesamten Startklasse mit Abhängigkeiten arbeiten, die in der ASP.NET Core-Dienstauflistung definiert sind, indem Sie entweder den benötigten Dienst als Parameter anfordern oder Sie mit IServiceCollection in der Methode ConfigureServices arbeiten.

> [!NOTE]
> Wenn Sie sicherstellen müssen, dass bestimmte Dienste in Ihrer Startup-Klasse verfügbar sind, können Sie diese mithilfe von WebHostBuilder und der ConfigureServices-Methode innerhalb des Aufrufs von CreateDefaultBuilder konfigurieren.

Bei der Startklasse handelt es sich um ein Modell zur Vorgehensweise bei der Strukturierung anderer Bestandteile Ihrer ASP.NET Core-Anwendung – angefangen bei Controllern über Middleware bis hin zu Filtern Ihrer eigenen Dienste. Auf jeden Fall sollten Sie das [Prinzip der expliziten Abhängigkeiten](https://deviq.com/explicit-dependencies-principle/) beachten und besser Ihre Abhängigkeiten anfordern als sie direkt zu erstellen sowie in der gesamten Anwendung Dependency Injection nutzen. Achten Sie darauf, wo und wie Sie Implementierungen direkt instanziieren, insbesondere wenn es um Dienste und Objekte geht, die mit der Infrastruktur arbeiten und Nebenwirkungen haben. Sie sollten besser mit Abstraktionen arbeiten, die im Anwendungskern definiert sind und als Argumente an vordefinierte Verweise auf bestimmte Implementierungstypen übergeben wurden.

## <a name="structuring-the-application"></a>Strukturieren der Anwendung

Monolithische Anwendungen verfügen in der Regel über einen festgelegten Einstiegspunkt. Bei ASP.NET Core-Webanwendungen stellt das ASP.NET Core-Webprojekt den Einstiegspunkt dar. Das bedeutet jedoch nicht, dass die Projektmappe aus nur einem Projekt bestehen sollte. Sie sollten die Anwendung in verschiedene Schichten unterteilen, um dem Prinzip „Separation of Concerns“ zu folgen. Wenn Sie dies tun, sollten Sie Ordner erstellen, um Projekte voneinander zu trennen und um so die Kapselung zu verbessern. Der beste Ansatz, um diese Ziele mit einer ASP.NET Core-Anwendung zu erreichen, ist eine Abwandlung der in Kapitel 5 erläuterten sogenannten „Clean Architecture“. Wenn Sie diesem Ansatz folgen, besteht die Projektmappe dieser Anwendung aus separaten Bibliotheken für die Benutzeroberfläche, die Infrastruktur und das ApplicationCore-Projekt.

Neben diesen Projekten sind dann auch Testprojekte in der Anwendung enthalten (Informationen zum Testen finden Sie in Kapitel 9).

Das Objektmodell und die Schnittstellen der Anwendung sollten im ApplicationCore-Projekt enthalten sein. Dann hat das Projekt so wenige Abhängigkeiten wie möglich, auf die die anderen Projekte in der Projektmappe verweisen. Sowohl Geschäftsentitäten, die beibehalten werden sollen, als auch Dienste, die nicht direkt von der Infrastruktur abhängig sind, werden im ApplicationCore-Projekt definiert.

Im Infrastrukturprojekt sind Informationen zur Implementierung enthalten. Diese umfassen Hinweise zur Vorgehensweise im Hinblick auf die Persistenz und beim möglichen Senden von Benachrichtigungen an den Benutzer. Dieses Projekt verweist dann zwar auf implementierungsspezifische Pakete wie Entity Framework Core, sollte aber keine Informationen zu diesen Implementierungen außerhalb des Projekts verfügbar machen. Infrastrukturdienste und Repositorys sollten Schnittstellen implementieren, die im ApplicationCore-Projekt definiert sind. Über die Persistenzimplementierungen dieses Projekts werden darin implementierte Entitäten abgerufen und gespeichert.

Das ASP.NET Core-Benutzeroberflächenprojekt ist zwar verantwortlich für jegliche Aspekte im Hinblick auf die Benutzeroberflächenebene, es sollte jedoch keine Geschäftslogik oder Informationen zur Infrastruktur enthalten. Bestenfalls sollte es sogar unabhängig vom Infrastrukturprojekt sein. Dadurch wird sichergestellt, dass nicht versehentlich eine Abhängigkeit zwischen zwei Projekten hergestellt wird. Dies erreichen Sie, indem Sie einen Dependency Injection-Container eines Drittanbieters wie Autofac verwenden. Damit können Sie Regeln für die einzelnen Projekte zu Dependency Injection in Module-Klassen festlegen.

Alternativ können Sie auch festlegen, dass die Anwendung Microservices aufruft, die möglicherweise in individuellen Docker-Containern bereitgestellt werden, um die Anwendung von Informationen zur Implementierung zu entkoppeln. Dadurch wird das Prinzip „Separation of Concerns“ noch deutlicher eingehalten, und es wird eine bessere Entkopplung vorgenommen als bei der Verwendung von Dependency Injection zwischen zwei Projekten. Allerdings ist diese Methode auch komplexer.

### <a name="feature-organization"></a>Organisieren von Features

Standardmäßig stellen ASP.NET Core-Anwendungen ihre eigene Ordnerstruktur her, die Controller, Ansichten und häufig auch ViewModels umfasst. Clientseitiger Code, der diese Strukturen auf Serverseite unterstützen soll, wird in der Regel separat im wwwroot-Ordner gespeichert. Es kann jedoch sein, dass bei größeren Anwendungen im Zusammenhang mit dieser Ordnerstruktur Probleme auftreten, da Sie häufig zwischen diesen Ordnern hin- und herwechseln müssen, wenn Sie an einem bestimmten Feature arbeiten. Je mehr Dateien und Unterordner in einem Ordner gespeichert werden, desto schwieriger wird dies, und desto mehr müssen Sie im Projektmappen-Explorer scrollen. Wenn Sie dieses Problem vermeiden möchten, können Sie Anwendungscode anstatt nach Dateityp nach _Feature_ ordnen. Diese Strukturierung wird häufig als Featureordner oder [Feature Slices](https://docs.microsoft.com/archive/msdn-magazine/2016/september/asp-net-core-feature-slices-for-asp-net-core-mvc) bezeichnet (siehe auch: [Vertical Slices (Vertikale Slices)](https://deviq.com/vertical-slices/)).

In diesem Zusammenhang unterstützt ASP.NET Core MVC die Verwendung verschiedener Bereiche. Wenn Sie verschiedene Bereiche verwenden, können Sie verschiedene separate Ordner für Controller und Ansichten (sowie für jegliche zugeordneten Modelle) in jedem Bereichsordner erstellen. In Abbildung 7-1 wird eine Ordnerstruktur dargestellt, in der Bereiche verwendet werden.

![Beispielstruktur mit Bereichen](./media/image7-1.png)

**Abbildung 7-1**. Beispielstruktur mit Bereichen

Wenn Sie Bereiche verwenden, müssen Sie Attribute verwenden, um Ihre Controller mit den Namen der Bereiche zu versehen, zu denen sie gehören:

```csharp
[Area("Catalog")]
public class HomeController
{}
```

Außerdem müssen Sie die Bereichsunterstützung zu Ihren Routen hinzufügen:

```csharp
app.UseEndpoints(endpoints =>
{
    endpoints.MapControllerRoute(name: "areaRoute", pattern: "{area:exists}/{controller=Home}/{action=Index}/{id?}");
    endpoints.MapControllerRoute(name: "default", pattern: "{controller=Home}/{action=Index}/{id?}");
});
```

Neben der bereits integrierten Unterstützung von Bereichen können Sie auch ihre eigene Ordnerstruktur und Konventionen anstelle von Attributen und benutzerdefinierten Routen verwenden. Dadurch können Sie über Featureordner verfügen, die keine separaten Ordner für Ansichten, Controller usw. umfassen. Dadurch bleibt die Hierarchie flach, und es werden alle verwandten Dateien für ein Feature gleichzeitig an einem Ort angezeigt.

ASP.NET Core verwendet integrierte Konventionstypen, um das Verhalten dieses Frameworks zu kontrollieren. Sie können diese Konventionen verändern oder ersetzen. Sie können beispielsweise eine Konvention erstellen, die automatisch anhand des Namespace, der in der Regel mit dem Ordner korreliert, in dem der Controller platziert ist, den Featurenamen für einen bestimmten Controller abruft:

```csharp
public class FeatureConvention : IControllerModelConvention
{
    public void Apply(ControllerModel controller)
    {
        controller.Properties.Add("feature",
        GetFeatureName(controller.ControllerType));
    }

    private string GetFeatureName(TypeInfo controllerType)
    {
        string[] tokens = controllerType.FullName.Split('.');
        if (!tokens.Any(t => t == "Features")) return "";
        string featureName = tokens
        .SkipWhile(t => !t.Equals("features",
        StringComparison.CurrentCultureIgnoreCase))
        .Skip(1)
        .Take(1)
        .FirstOrDefault();
        return featureName;
    }
}
```

Geben Sie dann diese Konvention als eine Option an, wenn Sie in ConfigureServices zu Ihrer Anwendung MVC-Unterstützung hinzufügen:

```csharp
services.AddMvc(o => o.Conventions.Add(new FeatureConvention()));
```

ASP.NET Core MVC verwendet außerdem eine Konvention, um Ansichten zu finden. Sie können diese Konvention mit einer benutzerdefinierten Konvention überschreiben, indem Sie den obenstehend unter FeatureConvention angegebenen Featurenamen verwenden, damit in Ihren Featureordnern Ansichten gefunden werden. Weitere Informationen zu diesem Ansatz finden Sie im MSDN Magazine-Artikel [ASP.NET Core: Feature Slices für ASP.NET Core MVC](https://docs.microsoft.com/archive/msdn-magazine/2016/september/asp-net-core-feature-slices-for-asp-net-core-mvc). Auf dieser Seite können Sie auch ein Beispiel herunterladen.

### <a name="cross-cutting-concerns"></a>Übergreifende Belange

Je größer die Anwendungen werden, desto wichtiger ist es, übergreifende Belange zu vermeiden, um Duplizierungen zu vermeiden und Konsistenz zu gewährleisten. Unter übergreifenden Belangen für ASP.NET Core-Anwendungen sind u.a. die Authentifizierung, Modellvalidierungsregeln, Ausgabezwischenspeicherung und die Fehlerbehandlung zu verstehen. In ASP.Net Core MVC ermöglichen [Filter](/aspnet/core/mvc/controllers/filters) Ihnen, Code vor oder nach bestimmten Schritten der Anforderungsverarbeitungspipeline auszuführen. Beispielsweise kann ein Filter sowohl vor als auch nach der Modellbindung, einer Aktion oder dem Ergebnis einer Aktion ausgeführt werden. Sie können auch einen Autorisierungsfilter verwenden, um den Zugriff auf die restliche Pipeline zu steuern. In Abbildung 7-2 wird dargestellt, wie Sie über möglicherweise konfigurierte Filter Ausführungsflows anfordern können.

![Die Anforderung wird von Autorisierungsfilter, Ressourcenfilter, Modellbindung, Aktionsfilter, Aktionsausführung sowie Aktionsergebniskonvertierung, Ausnahmefilter, Ergebnisfilter und Ergebnisausführung verarbeitet. Beim Verlassen der Pipeline wird die Anforderung nur von Ergebnisfiltern und Ressourcenfiltern verarbeitet, bevor sie an den Client gesendet wird.](./media/image7-2.png)

**Abbildung 7-2**. Anfordern der Ausführung über Filter und Anforderungspipeline

Filter werden in der Regel als Attribute implementiert, damit Sie sie auf Controller oder Aktionen (oder sogar global) anwenden können. Wenn auf diese Weise Filter hinzugefügt werden, überschreiben die auf Aktionsebene angegebenen Filter entweder die auf Controllerebene angegebenen Filter, oder sie bauen auf diesen Filtern auf, die selbst globale Filter überschreiben. Beispielsweise kann das Attribut \[Route\] verwendet werden, um Routen zwischen Controllern und Aktionen zu erstellen. Genauso kann auch die Autorisierung auf Controllerebene konfiguriert und dann von individuellen Aktionen überschrieben werden. Dies wird im folgenden Beispiel dargestellt:

```csharp
[Authorize]
public class AccountController : Controller

{
    [AllowAnonymous] // overrides the Authorize attribute
    public async Task<IActionResult> Login() {}
    public async Task<IActionResult> ForgotPassword() {}
}
```

Die erste Methode (Login) verwendet den AllowAnonymous-Filter (Attribut), um den auf Controllerebene festgelegten Authorize-Filter zu überschreiben. Die ForgotPassword-Aktion sowie jede andere Aktion in der Klasse, die nicht über ein AllowAnonymous-Attribut verfügt, erfordert eine authentifizierte Anforderung.

Filter können verwendet werden, um Duplizierungen in Form von allgemeinen Richtlinien zur Fehlerbehandlung für APIs zu vermeiden. Eine typische API-Richtlinie soll z.B. eine NotFound-Antwort auf Anforderungen zurückgeben, die auf nicht vorhandene Schlüssel verweisen. Wenn die Modellvalidierung fehlschlägt, soll hingegen eine BadRequest-Anforderung zurückgegeben werden. Das folgende Beispiel veranschaulicht die Verwendung dieser beiden Richtlinien:

```csharp
[HttpPut("{id}")]
public async Task<IActionResult> Put(int id, [FromBody]Author author)
{
    if ((await _authorRepository.ListAsync()).All(a => a.Id != id))
    {
        return NotFound(id);
    }
    if (!ModelState.IsValid)
    {
        return BadRequest(ModelState);
    }
    author.Id = id;
    await _authorRepository.UpdateAsync(author);
    return Ok();
}
```

Vermeiden Sie, dass Ihre Aktionsmethoden mit bedingtem Code wie diesem überladen werden. Pullen Sie die Richtlinien stattdessen in Filter, die nach Bedarf angewendet werden können. In diesem Beispiel kann die Modellvalidierung, die jedes Mal erfolgen sollte, wenn ein Befehl an die API gesendet wird, durch das folgende Attribut ersetzt werden:

```csharp
public class ValidateModelAttribute : ActionFilterAttribute
{
    public override void OnActionExecuting(ActionExecutingContext context)
    {
        if (!context.ModelState.IsValid)
        {
            context.Result = new BadRequestObjectResult(context.ModelState);
        }
    }
}
```

Sie können `ValidateModelAttribute` als NuGet-Abhängigkeit zu Ihrem Projekt hinzufügen, indem Sie das Paket [Ardalis.ValidateModel](https://www.nuget.org/packages/Ardalis.ValidateModel) einfügen. Für APIs können Sie das `ApiController`-Attribut verwenden, um dieses Verhalten zu erzwingen, ohne einen separaten `ValidateModel`-Filter zu verwenden.

Ebenso kann ein Filter verwendet werden, um zu überprüfen, ob ein Datensatz vorhanden ist, und um den Fehler 404 zurückzugeben, bevor die Aktion ausgeführt wird. Deshalb müssen diese Überprüfungen nicht mehr innerhalb der Aktion durchgeführt werden. Wenn Sie häufig verwendete Konventionen entfernt haben und Ihre Projektmappe so geordnet haben, dass Infrastrukturcode und Geschäftslogik von Ihrer Benutzeroberfläche getrennt sind, sollten Ihre MVC-Aktionsmethoden sehr dünn sein:

```csharp
[HttpPut("{id}")]
[ValidateAuthorExists]
public async Task<IActionResult> Put(int id, [FromBody]Author author)
{
    await _authorRepository.UpdateAsync(author);
    return Ok();
}
```

Weitere Informationen zum Implementieren von Filtern und ein Arbeitsbeispiel zum Herunterladen finden Sie im MSDN Magazine-Artikel [ASP.NET Core – ASP.NET Core MVC-Filter in der Praxis](https://docs.microsoft.com/archive/msdn-magazine/2016/august/asp-net-core-real-world-asp-net-core-mvc-filters).

> ### <a name="references--structuring-applications"></a>Ressourcen: Strukturieren von Anwendungen
>
> - **Bereiche**  
>   <https://docs.microsoft.com/aspnet/core/mvc/controllers/areas>
> - **ASP.NET Core: Feature-Slices für ASP.NET Core MVC**  
>   <https://docs.microsoft.com/archive/msdn-magazine/2016/september/asp-net-core-feature-slices-for-asp-net-core-mvc>
> - **Filter**  
>   <https://docs.microsoft.com/aspnet/core/mvc/controllers/filters>
> - **MSDN Magazine: ASP.NET Core MVC-Filter in der Praxis**  
>   <https://docs.microsoft.com/archive/msdn-magazine/2016/august/asp-net-core-real-world-asp-net-core-mvc-filters>

## <a name="security"></a>Sicherheit

Das Sichern von Webanwendungen stellt ein umfangreiches und komplexes Thema dar. Im Grunde genommen müssen Sie beim Thema Sicherheit sicherstellen, dass Sie wissen, wer eine Anforderung sendet. Dann müssen Sie sicherstellen, dass die Anforderung nur Zugriff auf die Ressourcen hat, auf die sie Zugriff haben sollte. Im Rahmen der Authentifizierung werden Anmeldeinformationen miteinander verglichen, die zusammen mit einer Anforderung an die Anmeldeinformationen in einem vertrauenswürdigen Datenspeicher bereitgestellt werden, um zu überprüfen, ob die Anforderung behandelt werden soll, als würde sie von einer bekannten Entität gesendet werden. Bei der Autorisierung wird auf der Grundlage der Benutzeridentität der Zugriff auf bestimmte Ressourcen eingeschränkt. Ein weiterer Punkt im Hinblick auf die Sicherheit ist das Schützen von Anforderungen vor Lauschangriffen durch Drittanbieter. Dafür sollten Sie sicherstellen, dass [Ihre Anwendung zumindest SSL verwendet](/aspnet/core/security/enforcing-ssl).

### <a name="authentication"></a>Authentifizierung

Bei ASP.NET Core Identity handelt es sich um ein Mitgliedschaftssystem, das Sie verwenden können, um die Anmeldefunktionen für Ihre Anwendung zu unterstützen. Dieses System unterstützt sowohl lokale Benutzerkonten als auch die Unterstützung von externen Protokollanbietern wie Microsoft Account, Twitter, Facebook und Google. Neben ASP.NET Core Identity kann Ihre Anwendung auch die Windows-Authentifizierung oder einen Identitätsanbieter eines Drittanbieters wie [Identity Server](https://github.com/IdentityServer/IdentityServer4) verwenden.

ASP.NET Core Identity ist in neuen Projektvorlagen enthalten, wenn die Option „Einzelne Benutzerkonten“ aktiviert ist. Diese Vorlage umfasst die Unterstützung der Registrierung, Anmeldung, von externen Anmeldungen, vergessenen Kennwörtern und von zusätzlichen Funktionen.

![Auswählen einzelner Benutzerkonten zur Vorabkonfiguration von Identity](./media/image7-3.png)

**Abbildung 7-3**. Auswählen einzelner Benutzerkonten zur Vorabkonfiguration von Identity.

Die Unterstützung von Identity wird unter „Startup“ und sowohl in der Methode ConfigureServices als auch in Configure konfiguriert:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    // Add framework services.
    services.AddDbContext<ApplicationDbContext>(options =>
    options.UseSqlServer(Configuration.GetConnectionString("DefaultConnection")));
    services.AddIdentity<ApplicationUser, IdentityRole>()
    .AddEntityFrameworkStores<ApplicationDbContext>()
    .AddDefaultTokenProviders();
    services.AddMvc();
}

public void Configure(IApplicationBuilder app)
{
    app.UseStaticFiles();
    app.UseIdentity();
    app.UseEndpoints(endpoints =>
    {
        endpoints.MapControllerRoute(name: "default", pattern: "{controller=Home}/{action=Index}/{id?}");
    });
}
```

Es ist wichtig, dass UseIdentity vor UseMvc in der Methode Configure angezeigt wird. Wenn Sie Identity in ConfigureServices konfigurieren, sollte AddDefaultTokenProviders aufgerufen werden. Dies hat nichts mit Token zu tun, die möglicherweise verwendet werden, um die Webkommunikation zu sichern. Stattdessen bezieht es sich auf Anbieter, die Aufforderungen erstellen, die per SMS oder E-Mail an Benutzer gesendet werden können, damit diese ihre Identität bestätigen können.

Weitere Informationen zum [Konfigurieren der zweistufigen Authentifizierung](/aspnet/core/security/authentication/2fa) und zum [Zulassen von externen Anmeldungsanbietern](/aspnet/core/security/authentication/social/) finden Sie in der offiziellen ASP.NET Core-Dokumentation.

### <a name="authorization"></a>Autorisierung

Die einfachste Art der Authentifizierung umfasst die Einschränkung des Zugriffs auf anonyme Benutzer. Wenn Sie diese Art der Authentifizierung durchführen möchten, müssen Sie nur das Attribut \[Authorize\] auf bestimmte Controller oder Aktionen anwenden. Wenn Rollen verwendet werden, kann das Attribut wie im Folgenden dargestellt erweitert werden, um den Zugriff auf Benutzer zu beschränken, denen bestimmte Rollen zugewiesen sind:

```csharp
[Authorize(Roles = "HRManager,Finance")]
public class SalaryController : Controller
{

}
```

In diesem Fall hätten Benutzer, die den Rollen HRManager und/oder Finance zugewiesen sind, Zugriff auf den SalaryController. Wenn Sie erfordern möchten, dass ein Benutzer mehreren Rollen statt nur einer von mehrern Rollen angehört, können Sie das Attribut mehrmals anwenden und dabei jeweils eine erforderliche Rolle angeben.

Wenn Sie in vielen verschiedenen Controllern und Aktionen bestimmte Rollen als Zeichenfolgen festlegen, kann dies zu ungewollten Wiederholungen führen. Sie können Autorisierungsrichtlinien konfigurieren, die Autorisierungsregeln kapseln, und anschließend die Richtlinie anstelle von individuellen Rollen angeben, wenn Sie das Attribut \[Authorize\] anwenden:

```csharp
[Authorize(Policy = "CanViewPrivateReport")]
public IActionResult ExecutiveSalaryReport()
{
    return View();
}
```

Wenn Sie auf diese Weise Richtlinien verwenden, können Sie die Arten von Aktionen unterteilen, die auf bestimmte Rollen und Regeln beschränkt sind, die für diese gelten. Wenn Sie später eine neue Rolle erstellen, die Zugriff auf bestimmte Ressourcen benötigt, können Sie einfach eine Richtlinie aktualisieren und müssen nicht mehr jede Liste mit Rollen für jedes \[Authorize\]-Attribut aktualisieren.

#### <a name="claims"></a>Ansprüche

Ansprüche sind Name-Wert-Paare, die Eigenschaften eines authentifizierten Benutzers darstellen. Möglicherweise möchten Sie die Personalnummer eines Benutzers als Anspruch speichern. Ansprüche können als Bestandteil von Autorisierungsrichtlinien verwendet werden. Daher können Sie eine Richtlinie mit dem Namen „EmployeeOnly“ erstellen, die, wie im folgenden Beispiel dargestellt, einen Anspruch mit dem Namen „EmployeeNumber“ erfordert:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc();
    services.AddAuthorization(options =>
    {
        options.AddPolicy("EmployeeOnly", policy => policy.RequireClaim("EmployeeNumber"));
    });
}
```

Diese Richtlinie kann dann mit dem Attribut \[Authorize\] verwendet werden, um wie obenstehend beschrieben einen Controller und/oder eine Aktion zu schützen.

#### <a name="securing-web-apis"></a>Sichern von Web-APIs

Die meisten Web-APIs sollten ein tokenbasiertes Authentifizierungssystem implementieren. Die Tokenauthentifizierung ist zustandslos und skalierbar. In einem tokenbasierten Authentifizierungssystem muss sich der Client zuerst mit dem Authentifizierungsanbieter authentifizieren. Wenn dies erfolgreich ist, wird für den Client ein Token ausgestellt, bei dem es sich um eine kryptografische, sinnvolle Zeichenfolge handelt. Wenn der Client dann eine Anforderung an eine API durchführen muss, fügt er dieses Token als Header der Anforderung hinzu. Der Server überprüft dann das im Anforderungsheader gefundene Token, bevor er die Anforderung abschließt. Abbildung 7-4 zeigt diesen Vorgang.

![TokenAuth](./media/image7-4.png)

**Abbildung 7-4.** Tokenbasierte Authentifizierung für Web-APIs.

Sie können einen eigenen Authentifizierungsdienst erstellen, Ihre API in Azure AD und OAuth integrieren oder einen Dienst über ein Open-Source-Tool wie z. B. [IdentityServer](https://github.com/IdentityServer) implementieren.

#### <a name="custom-security"></a>Benutzerdefinierte Sicherheit

Gehen Sie insbesondere mit Bedacht vor, wenn Sie eigene Kryptografien, Benutzermitgliedschaften oder Systeme zur Tokengenerierung implementieren. Es gibt viele im Handel erwerbliche oder Open Source-Alternativen, deren Sicherheit die einer benutzerdefinierten Implementierung in den meisten Fällen übertrifft.

> ### <a name="references--security"></a>Ressourcen: Sicherheit
>
> - **Übersicht über die Dokumentation zur Sicherheit**  
>   https://docs.microsoft.com/aspnet/core/security/
> - **Enforcing SSL in an ASP.NET Core App (Erzwingen von SSL in einer ASP.NET Core-App)**  
>   <https://docs.microsoft.com/aspnet/core/security/enforcing-ssl>
> - **Einführung in Identity**  
>   <https://docs.microsoft.com/aspnet/core/security/authentication/identity>
> - **Introduction to Authorization (Einführung in die Authentifizierung)**  
>   <https://docs.microsoft.com/aspnet/core/security/authorization/introduction>
> - **Authentifizierung und Autorisierung in Azure App Service**  
>   <https://docs.microsoft.com/azure/app-service-api/app-service-api-authentication>
> - **IdentityServer**  
>   <https://github.com/IdentityServer>

## <a name="client-communication"></a>Clientkommunikation

ASP.NET Core-Apps können nicht nur Seiten bereitstellen und über Web-APIs auf Anforderungen für Daten antworten, sondern auch direkt mit verbundenen Clients kommunizieren. Für diese ausgehende Kommunikation können verschiedene Transporttechnologien verwendet werden, wobei am häufigsten die Technologie WebSockets verwendet wird. ASP.NET Core SignalR ist eine Bibliothek, mit der Sie Ihren Anwendungen leicht Funktionen für die Echtzeitkommunikation zwischen Server und Client hinzufügen können. SignalR unterstützt verschiedene Transporttechnologien, einschließlich WebSockets, und nimmt dem Entwickler einen Großteil der Implementierungsdetails ab.

Die Clientkommunikation in Echtzeit erweist sich in vielen Anwendungsszenarios als nützlich. Dabei macht es keinen Unterschied, ob Sie WebSockets oder andere Methoden verwenden. Beispiele:

- Anwendungen für Livechats

- Überwachen von Anwendungen

- Updates zum Auftragsstatus

- Benachrichtigungen

- Interaktive Forms-Anwendungen

Wenn Sie die Clientkommunikation in Ihre Anwendungen integrieren, gibt es in der Regel zwei Komponenten:

- Einen serverseitigen Verbindungs-Manager (SignalR-Hub, WebSocketManager und WebSocketHandler)

- Eine clientseitige Bibliothek

Clients sind nicht auf Browser beschränkt, denn auch mobile Apps, Konsolen-Apps und andere native Apps können mithilfe von SignalR/WebSockets kommunizieren. Das folgende einfache Programm ist Bestandteil einer WebSocketManager-Beispielanwendung und gibt jeglichen Inhalt, der an eine Chat-Anwendung gesendet wird, an die Konsole weiter:

```csharp
public class Program
{
    private static Connection _connection;
    public static void Main(string[] args)
    {
        StartConnectionAsync();
        _connection.On("receiveMessage", (arguments) =>
        {
            Console.WriteLine($"{arguments[0]} said: {arguments[1]}");
        });
        Console.ReadLine();
        StopConnectionAsync();
    }

    public static async Task StartConnectionAsync()
    {
        _connection = new Connection();
        await _connection.StartConnectionAsync("ws://localhost:65110/chat");
    }

    public static async Task StopConnectionAsync()
    {
        await _connection.StopConnectionAsync();
    }
}
```

Ziehen Sie Möglichkeiten in Betracht, über die Anwendungen direkt mit Clientanwendungen kommunizieren können, und prüfen Sie, ob die Kommunikation in Echtzeit die Benutzerfreundlichkeit der App verbessern würde.

> ### <a name="references--client-communication"></a>Ressourcen: Clientkommunikation
>
> - **ASP.NET Core SignalR**  
>   <https://github.com/dotnet/aspnetcore/tree/master/src/SignalR>
> - **WebSocket-Manager**  
>   https://github.com/radu-matei/websocket-manager

## <a name="domain-driven-design--should-you-apply-it"></a>Sollten Sie die Methode „Domain-Driven Design“ verwenden?

Bei der Methode Domain-Driven Design (DDD) handelt es sich um einen nützlichen Ansatz zum Erstellen von Software, bei dem sich der Entwickler auf die _Geschäftsdomäne_ konzentriert. Außerdem wird der Fokus auf Kommunikation und Interaktion mit Experten für Geschäftsdomänen gelegt, die den Entwicklern im Zusammenhang erläutern können, wie das System in der Praxis funktionieren soll. Wenn Sie z.B. ein System für den Aktienhandel erstellen, sollten Sie sich an einen erfahrenen Börsenmakler als Experten für die Geschäftsdomäne wenden. DDD soll dazu dienen, große, komplexe Geschäftsprobleme anzugehen und eignet sich häufig nicht für kleinere, einfachere Anwendungen, da es sich für diese nicht lohnt, viel Zeit darein zu investieren, die Domäne zu verstehen und zu modellieren.

Wenn Sie Software anhand der DDD-Technik erstellen, sollte Ihr Team (das auch Projektbeteiligte und Mitwirkende außerhalb des technischen Bereichs umfasst) eine _ubiquitäre Sprache_ für den Problembereich entwickeln. Das bedeutet, das für das praxisorientierte Konzept, das modelliert wird, dessen Softwareäquivalent und jegliche andere Strukturen, die möglicherweise zu dem Konzept beitragen (z.B. Datentabellen), dieselbe Terminologie verwendet werden soll. Die in der ubiquitären Sprache beschriebenen Konzepte sollen die Grundlage für Ihr _Domänenmodell_ darstellen.

Ihr Domänenmodell besteht aus Objekten, die miteinander interagieren, um das Verhalten des Systems darzustellen. Diese Objekte können in die folgenden Kategorien eingeteilt werden:

- [Entitäten](https://deviq.com/entity/), die Objekte mit Identitätsthreads darstellen. Entitäten werden in der Regel dauerhaft mit einem Schlüssel gespeichert, über den sie zu einem späteren Zeitpunkt wieder abgerufen werden können.

- [Aggregate](https://deviq.com/aggregate-pattern/), die Objektgruppen darstellen, die als eine Einheit beibehalten werden sollten.

- [Wertobjekte](https://deviq.com/value-object/), die Konzepte darstellen, die auf der Grundlage der Summe ihrer Eigenschaftswerte miteinander verglichen werden können. Beispielsweise das DateRange-Objekt, das aus einem Start- und einem Enddatum besteht.

- [Domänenereignisse](https://martinfowler.com/eaaDev/DomainEvent.html), die Vorgänge darstellen, die innerhalb des System ausgeführt werden und für andere Bestandteile des Systems von Bedeutung sind.

Ein DDD-Domänenmodell muss komplexes Verhalten innerhalb des Modells kapseln. Insbesondere Entitäten sollten nicht nur Auflistungen von Eigenschaften sein. Wenn das Domänenmodell kein Verhalten aufweist und nur den Status des Systems darstellt, wird es als [anämisches Modell](https://deviq.com/anemic-model/) bezeichnet. Diese Art von Modellen sollten in Verbindung mit DDD nicht auftreten.

Neben diesen Modelltypen verwendet DDD in der Regel verschiedene Muster:

- [Repository](https://deviq.com/repository-pattern/) zum Zusammenfassen von Informationen zur Persistenz.

- [Factory](https://en.wikipedia.org/wiki/Factory_method_pattern) zum Kapseln der Erstellung von komplexen Objekten.

- Domänenereignisse zum Entkoppeln von abhängigem Verhalten von Triggerverhalten

- [Dienste](http://gorodinski.com/blog/2012/04/14/services-in-domain-driven-design-ddd/) zum Kapseln von komplexem Verhalten und/oder Informationen zur Implementierung der Infrastruktur.

- [Kommando](https://en.wikipedia.org/wiki/Command_pattern) zum Entkoppeln von ausgebenden Befehlen und Ausführen des Befehls selbst.

- [Spezifikation](https://deviq.com/specification-pattern/) zum Entkoppeln von Abfragedetails.

Für DDD wird auch die Verwendung der bereits erwähnten Clean Architecture empfohlen, die die lose Kopplung, die Entkopplung und Code umfasst, der problemlos mithilfe von Komponententests überprüft werden kann.

### <a name="when-should-you-apply-ddd"></a>Empfohlene Anwendung von DDD

DDD eignet sich besonders für große Anwendungen mit erheblicher Komplexität im geschäftlichen Bereich (nicht nur im technischen Bereich). Zum Erstellen der Anwendung wird dann das Fachwissen von Domänenexperten benötigt. Das Domänenmodell selbst sollte ein bedeutungsvolles Verhalten aufweisen, indem es Geschäftsregeln und Interaktionen darstellt und nicht nur den aktuellen Status verschiedener Datensätze aus Datenspeichern speichert und abfragt.

### <a name="when-shouldnt-you-apply-ddd"></a>Nicht empfohlene Anwendung von DDD

Wenn Sie die DDD-Methode anwenden möchten, müssen Sie viel Zeit in die Modellierung, die Architektur und die Kommunikation investieren. Dies lohnt sich für kleinere Anwendungen oder CRUD-Anwendungen nicht (create/read/update/delete = Erstellen/Lesen/Aktualisieren/Löschen). Wenn Sie sich für diesen Ansatz entscheiden, dann aber feststellen, dass es sich bei Ihrem Domänenmodell um ein anämisches Modell handelt, das kein Verhalten aufweist, sollten Sie Ihre Wahl noch einmal überdenken. Entweder ist die DDD-Methode für diese Anwendung nicht notwendig, oder Sie benötigen möglicherweise Unterstützung beim Refactoring Ihrer Anwendung, um die Geschäftslogik anstatt in Ihrer Datenbank oder Benutzeroberfläche in das Domänenmodell zu kapseln.

Sie können auch einen hybriden Ansatz auswählen und DDD nur für Transaktionsbereiche bzw. komplexere Bereiche der Anwendung verwenden und für die CRUD-Bestandteile oder die schreibgeschützten Bestandteile der Anwendung eine andere Methode verwenden. Beispielsweise benötigen Sie nicht die Einschränkungen eines Aggregats, wenn Sie Daten abfragen, um einen Bericht abzufragen oder Daten für ein Dashboard zu visualisieren. Dann ist es vollkommen akzeptabel, ein separates, einfaches Lesemodell für solche Anforderungen zu verwenden.

> ### <a name="references--domain-driven-design"></a>Ressourcen: Domain-Driven Design
>
> - **DDD in Plain English (StackOverflow Answer) (Einfache Beschreibung von DDD (StackOverflow-Antwort))**  
>   <https://stackoverflow.com/questions/1222392/can-someone-explain-domain-driven-design-ddd-in-plain-english-please/1222488#1222488>

## <a name="deployment"></a>Bereitstellung

Unabhängig davon, wo die ASP.NET Core-Anwendung gehostet wird, besteht deren Bereitstellung aus einigen Schritten. Als Erstes muss die Anwendung veröffentlicht werden. Dafür können Sie den CLI-Befehl `dotnet publish` verwenden. Dadurch wird die Anwendung kompiliert und alle Dateien, die benötigt werden, um die Anwendung auszuführen, werden in einem festgelegten Ordner platziert. Wenn Sie die Bereitstellung über Visual Studio ausführen, wird dieser Schritt automatisch für Sie ausgeführt. Der Ordner „publish“ enthält EXE- und DLL-Dateien für die Anwendung und ihre Abhängigkeiten. Unabhängige Anwendungen umfassen außerdem eine Version der .NET-Runtime. Außerdem enthalten ASP.NET Core-Anwendungen Konfigurationsdateien, statische Clientobjekte und MVC-Ansichten.

Bei ASP.NET Core-Anwendungen handelt es sich um Konsolenanwendungen, die gestartet werden müssen, wenn der Server startet, und die neugestartet werden müssen, wenn die Anwendung bzw. der Server abstürzt. Wenn Sie diesen Vorgang automatisieren möchten, können Sie einen Prozess-Manager verwenden. Die am häufigsten verwendeten Prozess-Manager für ASP.NET Core sind Nginx und Apache unter Linux und IIS oder Windows Service unter Windows.

Zusätzlich zu einem Prozess-Manager können ASP.NET Core-Anwendungen einen Reverseproxyserver verwenden. Ein Reverseproxyserver empfängt HTTP-Anforderungen aus dem Internet und leitet diese nach einer vorbereitenden Verarbeitung an Kestrel weiter. Reverseproxyserver stellen eine Sicherheitsebene für die Anwendung bereit. Kestrel unterstützt das Hosten von mehreren Anwendungen auf einem Port nicht. Daher können Techniken wie Hostheader nicht verwendet werden, um das Hosten von mehreren Anwendungen auf einem Port und einer IP-Adresse zu ermöglichen.

![Von Kestrel zum Internet](./media/image7-5.png)

**Abbildung 7-5**. ASP.NET in Kestrel hinter einem Reverseproxyserver gehostet

Ein Reverseproxyserver kann sich außerdem als nützlich erweisen, um mehrere Anwendungen unter Verwendung von SSL/HTTPS zu sichern. In diesem Zusammenhang muss SSL nur für den Reverseproxy konfiguriert sein. Wie in Abbildung 7-6 dargestellt kann die Kommunikation zwischen dem Reverseproxyserver und Kestrel über HTTP hergestellt werden.

![ASP.NET hinter einem über HTTPS gesicherten Reverseproxyserver gehostet](./media/image7-6.png)

**Abbildung 7-6**. ASP.NET hinter einem über HTTPS gesicherten Reverseproxyserver gehostet

Ein immer häufiger verwendeter Ansatz ist das Hosten Ihrer ASP.NET Core-Anwendung in einem Docker-Container, der anschließend lokal gehostet oder in Azure für cloudbasiertes Hosting bereitgestellt werden kann. Dann kann der Docker-Container wie oben dargestellt Ihren Anwendungscode enthalten, der auf Kestrel ausgeführt und hinter einem Reverseproxyserver bereitgestellt wird.

Wenn Sie Ihre Anwendung auf Azure hosten, können Sie Microsoft Azure Application Gateway als reservierte virtuelle Anwendung verwenden, um verschiedene Dienste bereitzustellen. Application Gateway dient nicht nur als Reverseproxy für einzelne Anwendungen, sondern bietet auch die folgenden Features:

- HTTP-Lastenausgleich

- SSL-Offload (SSL nur für Internet)

- End-to-End-SSL

- Routing über mehrere Websites (Konsolidieren von bis zu 20 Websites für eine Application Gateway-Version)

- Firewall der Webanwendung

- WebSocket-Unterstützung

- Erweiterte Diagnose

_Weitere Informationen zu den Bereitstellungsoptionen für Azure finden Sie in [Kapitel 10](development-process-for-azure.md)._

> ### <a name="references--deployment"></a>Ressourcen: Bereitstellung
>
> - **Hosten und Bereitstellen von ASP.NET Core**  
>   <https://docs.microsoft.com/aspnet/core/publishing/>
> - **Verwenden von Kestrel mit einem Reverseproxy**  
>   <https://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel#when-to-use-kestrel-with-a-reverse-proxy>
> - **Hosten von ASP.NET Core in Docker-Containern**  
>   <https://docs.microsoft.com/aspnet/core/publishing/docker>
> - **Übersicht über Application Gateway**  
>   <https://docs.microsoft.com/azure/application-gateway/application-gateway-introduction>

>[!div class="step-by-step"]
>[Zurück](common-client-side-web-technologies.md)
>[Weiter](work-with-data-in-asp-net-core-apps.md)

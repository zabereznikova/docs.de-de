---
title: Entwicklung von MVC-Apps mit ASP.NET Core
description: Innovative Webanwendungen mit ASP.NET Core und Azure Architekt | Entwickeln von ASP.NET Core MVC-Apps
author: ardalis
ms.author: wiwagn
ms.date: 10/07/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: 54e7ed6fff9ac709e411d0ac1e345c63fd753201
ms.sourcegitcommit: 43c656811dd38a66a6672084c65d10c0cbbf2015
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2017
---
# <a name="develop-aspnet-core-mvc-apps"></a>Entwickeln von ASP.NET Core MVC-Apps

> "Es ist nicht wichtig, die es richtig erstmalig machen. Es ist äußerst wichtig zum richtigen Zeitpunkt der letzten abrufen."  
> _-Andrew Jagd und David Thomas_

## <a name="summary"></a>Zusammenfassung

ASP.NET Core ist eine plattformübergreifende und Open Source-Framework zum Erstellen von modernen cloudoptimiertes Webanwendungen. ASP.NET Core-apps sind einfache und modulare, mit integrierter Unterstützung für zielabhängigkeit, in größere Prüfbarkeit und verwaltbarkeit zu aktivieren. Kombiniert mit MVC, das Erstellen von modernen Web-APIs zusätzlich zum Anzeigen von datenbasierten apps unterstützt, ist ASP.NET Core ein leistungsfähiges Framework mit dem Enterprise-Webanwendungen erstellen.

## <a name="mapping-requests-to-responses"></a>Zuordnen von Anforderungen zu Antworten

ASP.NET Core apps wird der ausgehenden Antworten im Wesentlichen eingehende Anforderungen zuordnen. Auf einer unteren Ebene Dies erfolgt mit Middleware und einfache ASP.NET Core-apps und Microservices ausschließlich aus benutzerdefinierten Middleware umfassen kann. Bei Verwendung von ASP.NET Core MVC können Arbeit auf einer etwas höheren Ebene im Sinne von denken *Routen*, *Controller*, und *Aktionen*. Jede eingehende Anforderung ist mit der Anwendung Routingtabelle verglichen, und wenn eine übereinstimmende Route gefunden wird, wird die zugeordnete Aktionsmethode (gehört zu einem Domänencontroller) aufgerufen, um die Anforderung zu verarbeiten. Wenn keine übereinstimmende Route gefunden wird, wird ein Fehlerhandler (in diesem Fall wird ein Ergebnis NotFound zurückgegeben) aufgerufen.

ASP.NET Core MVC-apps können herkömmliche Routen, attributenrouten oder beides verwenden. Herkömmliche Routen werden im Code angeben, routing definiert *Konventionen* mithilfe von Syntax wie im folgenden Beispiel:

```csharp
app.UseMvc(routes =>;
{
    routes.MapRoute("default","{controller=Home}/{action=Index}/{id?}");
});
```

In diesem Beispiel wurde der Routingtabelle eine Route mit dem Namen "Default" hinzugefügt. Definiert eine routenvorlage mit Platzhaltern für *Controller*, *Aktion*, und *Id*. Die Platzhalter für Controller und Aktion Standardwert vorhanden sein ("Startseite" und "Index" bzw.), und die Platzhalter-Id ist optional (-ASP.NET-Kompatibilitätsmodus ein "?" angewendet wird). Die Konvention hier definierten Status, in denen der erste Teil einer Anforderung zu entsprechen, sollten auf den Namen des Controllers an, der zweite Teil der Aktion, und klicken Sie dann bei Bedarf eine dritte Teil repräsentiert einen Id-Parameter. Herkömmliche Routen werden in der Regel an einem Ort für die Anwendung z. B. in der Methode konfigurieren, in der Start-Klasse definiert.

Attributenrouten werden direkt auf Controllern und Aktionen angewendet, anstatt Global angegeben. Dies hat den Vorteil, somit viel leichter auffindbar, wenn Sie sehen eine besondere Methode bedeutet, dass die Routinginformationen nicht an einer Stelle in der Anwendung beibehalten wird. Mit attributenrouten können Sie problemlos mehrere Routen für eine bestimmte Aktion angeben sowie Routen zwischen Controllern und Aktionen zu kombinieren. Zum Beispiel:

```csharp
[Route("Home")]
public class HomeController : Controller
{
    [Route("")] // Combines to define the route template "Home"
    [Route("Index")] // Combines to define route template "Home/Index"
    [Route("/")] // Does not combine, defines the route template ""
    public IActionResult Index() {}
```

Routen auf [HttpGet] angegeben werden können, und Trennen von ähnliche Attributen entfällt die Notwendigkeit hinzufügen [Route\] Attribute. Attributenrouten können Token auch um die Notwendigkeit der Controller bzw. die Aktionsmethode Namen wiederholt zu verringern, wie unten dargestellt:

```csharp
[Route("[controller\]")]
public class ProductsController : Controller
{
    [Route("")] // Matches 'Products'
    [Route("Index")] // Matches 'Products/Index'
    public IActionResult Index()
}
```

Core ASP.NET-MVC wird ausgeführt, sobald eine bestimmte Anforderung verfügt über eine Route zugeordnet wurde, aber bevor die Aktion wird aufgerufen, [modellbindung](https://docs.microsoft.com/aspnet/core/mvc/models/model-binding) und [modellüberprüfung](https://docs.microsoft.com/aspnet/core/mvc/models/validation) in der Anforderung. Wurden die modellbindung ist verantwortlich für das Konvertieren von eingehender HTTP-Daten in die Typen als Parameter der Aktionsmethode angegeben, die aufgerufen wird. Beispielsweise, wenn die Aktionsmethode einen Int-Id-Parameter erwartet, versucht wurden die modellbindung, geben Sie diesen Parameter aus einem Wert, der als Teil der Anforderung bereitgestellt. Sucht zu diesem Zweck wurden die modellbindung für Werte in ein bereitgestelltes Formular, Werte in der Route selbst und Abfragezeichenfolgen-Werte. Angenommen, ein Id-Wert gefunden wird, wird es in eine ganze Zahl konvertiert werden vor der Aktionsmethode übergeben wird.

Nach dem Binden des Modells, jedoch vor dem Aufrufen der Aktionsmethode erfolgt die modellüberprüfung. Modellvalidierung optionale Attribute auf den Typ des Modells verwendet und können Sie sicherstellen, dass das angegebene Modellobjekt bestimmte datenanforderungen entspricht. Bestimmte Werte angegeben werden können, als erforderlich sind, oder auf eine bestimmte Länge oder einen numerischen Bereich beschränkt, usw.. Wenn Validierungsattribute angegeben sind, aber das Modell nicht der Anforderungen entspricht, die Eigenschaft ModelState.IsValid wird "false" sein und der Satz von Validierungsregeln fehlschlagen wird zum Senden an die anfordernde Client verfügbar sein.

Bei Verwendung von modellvalidierung sollten Sie darauf achten, überprüfen Sie immer, dass das Modell gültig ist, vor dem Ausführen der Befehle Status ändern, um sicherzustellen, dass Ihre app durch ungültige Daten nicht beschädigt ist. Sie können eine [Filter](https://docs.microsoft.com/aspnet/core/mvc/controllers/filters) neu hinzuzufügenden Code dafür in jeder Aktion zu umgehen. ASP.NET Core MVC-Filter bieten eine Möglichkeit, Gruppen von Anforderungen abfangen, damit allgemeine Richtlinien und querschnittliche Anmerkungen auf Basis eines targeted angewendet werden können. Filter können auf einzelne Aktionen, die gesamte Controller oder global für eine Anwendung angewendet werden.

Für Web-APIs, Core ASP.NET-MVC unterstützt [ *content-Aushandlung*](https://docs.microsoft.com/aspnet/core/mvc/models/formatting), sodass Anforderungen, um anzugeben, wie die Antworten formatiert werden soll. Basierend auf den Header in der Anforderung angegeben, werden Aktionen, die Rückgabe von Daten die Antwort in XML, JSON oder ein anderes unterstütztes Format formatieren. Dieses Feature ermöglicht die gleiche API von mehreren Clients mit verschiedenen datenformatanforderungen verwendet werden.

> ### <a name="references--mapping-requests-to-responses"></a>Verweise – Zuordnen von Anforderungen zu Antworten
> - **Routing zum Controlleraktionen**
> <https://docs.microsoft.com/aspnet/core/mvc/controllers/routing>
> - **Der modellbindung** https://docs.microsoft.com/aspnet/core/mvc/models/model-binding
> - **Modellüberprüfung**
> <https://docs.microsoft.com/aspnet/core/mvc/models/validation>
> - **Filter** https://docs.microsoft.com/aspnet/core/mvc/controllers/filters

## <a name="working-with-dependencies"></a>Arbeiten mit Abhängigkeiten

ASP.NET Core verfügt über integrierte Unterstützung für und intern nutzt eine als bekannte Technik [Abhängigkeitsinjektion](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection). Abhängigkeitsinjektion ist eine Technik, die losen Kopplung zwischen verschiedenen Teilen einer Anwendung aktiviert. Großzügiger ist Kopplung ist wünschenswert, da es leichter, um Teile der Anwendung abfangen, indem zum Testen oder Austausch zu isolieren kann. Außerdem wird auch die Wahrscheinlichkeit, dass eine Änderung in einem Teil der Anwendung keine unerwarteten Auswirkungen, die an anderer Stelle in der Anwendung haben wird. Abhängigkeitsinjektion basiert auf dem Prinzip der Abhängigkeit Umkehrung und häufig Schlüssel zum Erreichen einer das Prinzip geöffnet bzw. geschlossen wird. Beim Auswerten der Funktionsweise der Anwendungsstatus mit seinen Abhängigkeiten, Vorsicht vor der [Fensterdekorationen](http://deviq.com/static-cling/) Geruch code, und speichern Sie die Aphorism "[neuerungen Kleben](http://ardalis.com/new-is-glue)."

Fensterdekorationen tritt auf, wenn Ihre Klassen an statische Methoden Aufrufe oder Zugriff auf statische Eigenschaften, die möglichen Nebeneffekte bzw. Abhängigkeiten aufweisen. Beispielsweise haben eine Methode, die eine statische Methode, die wiederum mit einer Datenbank schreibt aufruft, ist die Methode, eng mit der Datenbank verbunden. Elemente, die diese Datenbankaufruf unterbrochen wird die Methode unterbrochen. Testen von solchen Methoden ist bekanntermaßen schwierig, da es sich bei derartige Tests kommerziellen imitieren Bibliotheken zum Simulieren von statischen Aufrufe erfordern oder können nur mit einer Testdatenbank festliegen getestet werden. Statische aufrufen, deren Abhängigkeit von Infrastruktur, insbesondere solche, die nicht vollständig zustandslos sind sind in Ordnung, aufrufen und haben keinen Einfluss auf die Kopplung oder Prüfbarkeit (hinter Kopplung Code für den Aufruf der statischen selbst).

Viele Entwickler die Risiken einer Fensterdekorationen und globaler Zustand verstehen, aber Codeprobleme an bestimmte Implementierungen über die direkte Instanziierung werden weiterhin eng gekoppelt. "Is Kleben neue" soll eine Erinnerung an diese Kopplung und nicht um eine allgemeine Condemnation die Verwendung des new-Schlüsselwort sein. Ebenso wie mit statischen Methodenaufrufen neue Instanzen von Typen, die keine externen Abhängigkeiten, in der Regel haben nicht eng Code zu verknüpfen, um Details zur Implementierung oder testen schwieriger machen. Aber jedes Mal, wenn eine Klasse instanziiert wird, nehmen nur einen kurzen Moment zu überlegen, ob er zum Programmieren der betreffenden Instanz in der jeweiligen Position sinnvoll ist, oder ob wäre es einen besseren Entwurf, um diese Instanz als Abhängigkeit anzufordern.

### <a name="declare-your-dependencies"></a>Deklarieren Sie die Abhängigkeiten

ASP.NET Core wird erstellt, um Methoden und Klassen deklarieren, ihre Abhängigkeiten, die sie als Argumente anfordern. ASP.NET-Anwendungen werden in der Regel in einer Startklasse eingerichtet. die selbst konfiguriert ist, um die Abhängigkeitsinjektion zu verschiedenen Zeitpunkten zu unterstützen. Wenn die Start-Klasse einen Konstruktor verfügt, können sie Abhängigkeiten über den Konstruktor anfordern wie folgt:

```csharp
public class Startup
{
    public Startup(IHostingEnvironment env)
    {
        var builder = new ConfigurationBuilder()
        .SetBasePath(env.ContentRootPath)
        .AddJsonFile("appsettings.json", optional: false, reloadOnChange: true)
        .AddJsonFile(\$"appsettings.{env.EnvironmentName}.json", optional: true);
    }
}
```

Die Startklasse ist interessant, es keine expliziten typanforderungen dafür gibt. Sie erbt nicht von der eine spezielle Autostart-Basisklasse, noch ist es eine bestimmte Schnittstelle implementieren. Kann ihm einen Konstruktor oder nicht, und Sie können angeben, wie viele Parameter für den Konstruktor wie gewünscht. Zu Beginn der Webhost, den Sie für Ihre Anwendung konfiguriert haben, rufen die Start-Klasse, die Sie eingerichtet haben, um die Verwendung und wird Abhängigkeitsinjektion verwenden, um eventuelle weitere Abhängigkeiten zu aufzufüllen benötigten die Startklasse. Natürlich, wenn Sie Parameter, die nicht in der von ASP.NET Core verwendeten Dienstecontainer konfiguriert ist anfordern, erhalten Sie eine Ausnahme, aber solange Sie sich an den Abhängigkeiten halten Container kennt, können Sie alles gewünschte anfordern.

Abhängigkeitsinjektion wird bei Ihren apps ASP.NET Core rechts vom Start und erstellt, wenn Sie die Autostart-Instanz zu erstellen. Es ist nicht für die Startklasse beenden. Sie können auch die Abhängigkeiten in der Methode konfigurieren anfordern:

```csharp
public void Configure(IApplicationBuilder app,
    IHostingEnvironment env,
    ILoggerFactory loggerFactory)
{

}
```

Die ConfigureServices-Methode ist die Ausnahme zu diesem Verhalten. Es muss nur ein Parameter vom Typ IServiceCollection dauern. Er muss nicht wirklich unterstützen die Abhängigkeitsinjektion, da einerseits verantwortlich ist für den Container für Objekte hinzugefügt und auf dem anderen sie Zugriff auf alle derzeit konfigurierten Diensten über den IServiceCollection-Parameter hat. Daher können Sie mit Abhängigkeiten, die in der Auflistung des ASP.NET Core-Dienste in jedem Teil der Start-Klasse, die erforderlichen Dienst als Parameter anfordern oder Arbeiten mit der IServiceCollection in ConfigureServices definierten arbeiten.

> [!NOTE]
> Sie müssen sicherstellen, dass bestimmte Dienste sind auf die Start-Klasse verfügbar, konfigurieren Sie sie mithilfe von WebHostBuilder und der zugehörigen ConfigureServices-Methode.

Die Startklasse ist ein Modell für wie andere Teile der Anwendung ASP.NET Core von Domänencontrollern auf Middleware zu filtern, um eigene Dienste strukturieren werden sollte. In jedem Fall befolgen Sie die [expliziten Abhängigkeiten Prinzip](http://deviq.com/explicit-dependencies-principle/), Ihre Abhängigkeiten anfordern statt direkt erstellen und die Nutzung Abhängigkeitsinjektion in der gesamten Anwendung. Achten Sie darauf, dass der, wo und wie Sie nicht direkt instanziieren Implementierungen, insbesondere Dienste und Objekte, die mit der Infrastruktur arbeiten oder nachteiligen Auswirkungen haben. Bevorzugen Sie arbeiten mit Abstraktionen in Ihrer Anwendung wichtigsten definiert und als Argumente an hartcodierten Verweise auf spezifische Implementierungstypen übergeben werden.

## <a name="structuring-the-application"></a>Strukturieren die Anwendung

Aufgrund eines monolithischen Anwendungen haben normalerweise einen einzigen Einstiegspunkt. Bei einer ASP.NET Core-Web-Anwendung wird der Einstiegspunkt das Webprojekt ASP.NET Core sein. Allerdings impliziert dies nicht, dass die Projektmappe nur ein einzelnes Projekt bestehen sollte. Es ist nützlich, um die Anwendung in den verschiedenen Ebenen um führen die Trennung von Anliegen aufteilen. Sobald in Ebenen unterteilt, ist es hilfreich, die Ordner für Projekte, trennen Sie nützlich sein können, die eine bessere Kapselung zu erzielen, hinausgehen. Der beste Ansatz für diese Ziele mit einer Anwendung ASP.NET Core ist eine Variation der Clean-Architektur in Kapitel 5 erläutert. Nach dieser Ansatz wird die Anwendung Lösung separate Bibliotheken für die UI-Infrastruktur und ApplicationCore bestehen.

Zusätzlich zu diesen Projekten separate Testprojekte sind, enthalten ebenfalls (Test ist im Kapitel 9 erläutert).

Die Anwendung das Objektmodell und Schnittstellen sollten im ApplicationCore Projekt gespeichert werden. Dieses Projekt muss so wenig Abhängigkeiten wie möglich, und andere Projekte in der Projektmappe werden darauf verweisen. Business-Entitäten, die beibehalten werden müssen werden in das Projekt ApplicationCore definiert, ebenso wie Dienste, die nicht direkt von der Infrastruktur abhängen.

Implementierungsdetails wie wie die Persistenz ausgeführt wird oder wie Benachrichtigungen möglicherweise an einen Benutzer gesendet werden, bleiben im Infrastructure-Projekt. Dieses Projekt implementierungsspezifische-Paketen, wie z. B. Entity Framework Core verweist, aber die Details zu dieser Implementierungen außerhalb des Projekts sollten nicht verfügbar machen. Infrastrukturdienste und Repositorys sollten Schnittstellen implementieren, die im Projekt ApplicationCore definiert sind, und ihre Implementierung der Persistenz sind verantwortlich für das Abrufen und Speichern von Entitäten, die in ApplicationCore definiert.

ASP.NET Core-Projekt selbst ist verantwortlich für die Benutzeroberfläche Ebenen bedenken, jedoch sollten keine Details zu Business Logic und Infrastruktur. In der Tat darf nicht im Idealfall es auch eine Abhängigkeit auf Infrastructure-Projekt verfügen, das hilft sicherzustellen, dass keine Abhängigkeit zwischen den zwei Projekten versehentlich eingeführt wird. Dies kann erreicht werden, mit einem Drittanbieter-DI-Container wie StructureMap, dadurch können Sie DI-Regeln in der Registrierung von Klassen in jedem Projekt definieren.

Einen anderen Ansatz für die Anwendung von Implementierungsdetails zu trennen, besteht darin, die Anwendung Aufruf Microservices, vielleicht in einzelne Docker-Container bereitgestellt haben. Dies bietet noch stärkere Trennung von Anliegen und die Entkopplung als DI zwischen zwei Projekte nutzen, hat jedoch zusätzliche Komplexität.

### <a name="feature-organization"></a>Feature-Organisation

Standardmäßig organisieren ASP.NET Core-Anwendungen, deren Ordnerstruktur Controller und Ansichten und häufig ViewModels aufgenommen werden sollen. Clientseitiger Code zur Unterstützung dieser Strukturen serverseitige wird im Ordner "Wwwroot" in der Regel separat gespeichert. Allerdings können große Anwendungen Probleme für diese Organisation auftreten, da arbeiten häufig auf eine gegebene Funktion erforderlich ist, die zwischen diesen Ordnern springen. Dadurch wird mehr schwierig, die Anzahl der Dateien und Unterordner im Ordner "Jeder" wächst, was zu sehr viel systemverarbeitungszeit in einen Bildlauf durch die Projektmappen-Explorer. Eine Lösung für dieses Problem ist, zum Organisieren von Anwendungscode durch *Feature* anstatt von Dateityp. Dieser Organisationseinheit Stil ist in der Regel als Featureordner oder Funktion Slices bezeichnet (Siehe auch: [vertikale Slices](http://deviq.com/vertical-slices/)).

ASP.NET Core MVC unterstützt die Bereiche für diesen Zweck. Bereiche können Sie separate Sätze von Controllern und Ansichten Ordner (sowie alle zugeordneten Modelle) in jedem Bereichsordner erstellen. Abbildung 7 – 1 zeigt eine Beispiel-Ordnerstruktur, die mithilfe von Bereichen.

![](./media/image7-1.png)

Abbildung 7 – 1 Bereich Beispielorganisation

Wenn Sie Bereiche verwenden zu können, müssen Sie Attribute verwenden, auf um Ihren Domänencontrollern mit dem Namen des Bereichs zu ergänzen, zu dem sie gehören:

```csharp
[Area("Catalog")]
public class HomeController
{}
```

Sie müssen auch so Ihre Routen Bereich Unterstützung hinzu:

```csharp
app.UseMvc(routes =>
{
    // Areas support
    routes.MapRoute(
    name: "areaRoute",
    template: "{area:exists}/{controller=Home}/{action=Index}/{id?}");
    routes.MapRoute(
    name: "default",
    template: "{controller=Home}/{action=Index}/{id?}");
});
```

Über die integrierte Unterstützung für Bereiche können Sie auch eigene Schritt die Ordnerstruktur und die Konventionen anstelle von Attributen und benutzerdefinierten Routen. Dies können Sie Featureordner aufweisen, die separate Ordner für Ansichten, Controller, durch die Trennung der Hierarchie flachere und erleichtert es, alle Dateien in einem einzigen Ort für jede Funktion anzuzeigen usw. enthalten waren.

ASP.NET Core werden mit integrierten Konvention Typen um sein Verhalten zu steuern. Sie können ändern oder ersetzen diesen Konventionen. Beispielsweise können Sie eine Konvention erstellen, die automatisch den Namen der Funktion für einen bestimmten Controller basierend auf dessen Namespace erhält (die in der Regel in den Ordner, in dem sich der Controller befindet, korreliert):

```csharp
FeatureConvention : IControllerModelConvention
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

Anschließend geben Sie an dieser Konvention als eine Option, wenn Sie Ihre Anwendung in ConfigureServices Unterstützung für MVC hinzufügen:

```csharp
services.AddMvc(o => o.Conventions.Add(new FeatureConvention()));
```

ASP.NET Core MVC wird auch eine Konvention zum Suchen von Ansichten verwendet. Sie können es mit einer benutzerdefinierten Konvention überschreiben, sodass Ansichten in Ihre Featureordner (mit dem Namen der Funktion durch die FeatureConvention oben aufgeführten) gespeichert werden. Können Sie weitere Informationen zu diesen Ansatz und Herunterladen von ein funktionstüchtiges Beispiel aus dem MSDN-Artikel [Feature Slices für ASP.NET Core MVC](https://msdn.microsoft.com/magazine/mt763233.aspx).

### <a name="cross-cutting-concerns"></a>Querschnittliche Sicherheitsrisiken

Anwendungen hinausgeht, wird es zunehmend wichtig, verlagern Sie querschnittliche Bedenken Beseitigung von Duplikaten und Konsistenz zu gewährleisten. Einige Beispiele für querschnittliche Begriffe in ASP.NET Core-Anwendungen sind Authentifizierung, Modell Validierungsregeln Zwischenspeichern der Ausgabe und Fehler zu behandeln, obwohl es gibt noch viele andere. ASP.NET Core MVC [Filter](https://docs.microsoft.com/aspnet/core/mvc/controllers/filters) ermöglichen es Ihnen, Code vor oder nach der bestimmte Schritte in der Verarbeitungspipeline Anforderung auszuführen. Ein Filter kann z. B. vor und nach der modellbindung, die vor und nach einer Aktion oder vor und nach einer Aktion Ergebnis führen. Einen Autorisierungsfilter können auch zum Steuern des Zugriffs auf den Rest der Pipeline. Abbildung 7 – 2 zeigt fordern wie Ausführung Flüsse gefiltert, wenn konfiguriert.

![Die Anforderung wird über den Autorisierungsfilter, Ressourcenfilter Modell binden, Aktionsfilter, Ausführen von Aktionen und Aktion Ergebniskonvertierung, Ausnahmefilter, Ergebnisfilter und Ergebnis Ausführung verarbeitet. Auf dem Weg heraus wird die Anforderung nur durch Ergebnisfilter und Ressourcenfilter verarbeitet, bevor eine Antwort an den Client gesendet wird.](./media/image7-2.png)

Abbildung 7-2-anforderungsausführung durch Filter und Anforderungspipeline.

Filter werden in der Regel als Attribute implementiert, damit Sie diese Controllern oder Aktionen anwenden können. Wenn auf diese Weise, auf der Ebene überschreiben oder Build auf Filtern auf Controllerebene, angegebene angegebenen Filter hinzugefügt, die selbst globale Filter außer Kraft setzen. Z. B. die \[Route\] Attribut kann verwendet werden, um Routen zwischen Controllern und Aktionen zu erstellen. Ebenso kann Autorisierung werden auf Controllerebene konfiguriert und dann überschrieben, indem einzelne Aktionen, wie im folgende Beispiel veranschaulicht:

```csharp
[Authorize]
public class AccountController : Controller

{
    [AllowAnonymous]
    public async Task<IActionResult> Login() {}
    public async Task<IActionResult> ForgotPassword() {}
}
```

Die erste Methode, Login, verwendet den AllowAnonymous-Filter (Attribut), das Autorisieren Filter auf Controllerebene überschreiben. Die ForgotPassword-Aktion (und eine andere Aktion in der Klasse, die ein AllowAnonymous-Attribut besitzt) ist eine authentifizierte Anforderung erforderlich.

Filter können verwendet werden, um Duplikate in Form von häufige Fehler bei der Verarbeitung von Richtlinien für APIs zu vermeiden. Eine typische API-Richtlinie werden z. B. NotFound Antwort auf Anforderungen mit Verweisen auf die Schlüssel, die nicht vorhanden sind, und eine Antwort BadRequest-Objekts zurück, wenn die modellvalidierung fehlschlägt. Das folgende Beispiel zeigt diese zwei Richtlinien in Aktion:

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

Zulassen Sie nicht die Aktionsmethoden mit einem bedingten Code wie überladen werden. Ziehen Sie stattdessen die Richtlinien in Filtern, die auf einen Bedarf angewendet werden können. In diesem Beispiel kann die Modell-Überprüfung, die einem beliebigen Zeitpunkt erfolgen soll, ein Befehl an der API gesendet wird, durch das folgende Attribut ersetzt werden:

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

Ebenso kann ein Filter zum Überprüfen, ob ein Datensatz vorhanden ist und Fehler 404 zurückgegeben werden, bevor die Aktion ausgeführt wird, entfällt die Erfordernis zum Ausführen dieser Tests in der Aktion verwendet werden. Sobald Sie allgemeine Konventionen herausgezogen und organisiert die Projektmappe Infrastruktur Code und Geschäftslogik von der Benutzeroberfläche getrennt haben, sollte Ihre MVC-Aktionsmethoden sehr dünne sein:

```csharp
// PUT api/authors/2/5
[HttpPut("{id}")]
[ValidateAuthorExists]
public async Task<IActionResult> Put(int id, [FromBody]Author author)
{
    await _authorRepository.UpdateAsync(author);
    return Ok();
}
```

Erfahren Sie mehr zu implementieren von Filtern und Laden Sie ein funktionstüchtiges Beispiel aus dem MSDN-Artikel [Real World ASP.NET Core MVC-Filter](https://msdn.microsoft.com/magazine/mt767699.aspx).

> ### <a name="references--structuring-applications"></a>Verweise – Strukturieren von Anwendungen
> - **Bereiche**  
> <https://docs.Microsoft.com/ASPNET/Core/MVC/Controllers/Areas>
> - **MSDN – Feature Slices für ASP.NET Core MVC**
>  <https://msdn.microsoft.com/magazine/mt763233.aspx>
> - **Filter**  
> <https://docs.Microsoft.com/ASPNET/Core/MVC/Controllers/Filters>
> - **MSDN – realen Core ASP.NET MVC-Filter**  
> <https://msdn.Microsoft.com/magazine/mt767699.aspx>

## <a name="security"></a>Sicherheit

Sichern von Webanwendungen ist ein komplexes Thema, mit dem viele Aspekte zu berücksichtigen. Auf der grundlegendsten Ebene wird die Sicherheit sicherstellen, dass Sie wissen, wer eine gegebene Anforderung stammt, und dann sicherstellen, dass die Anforderung nur auf Ressourcen zugreifen kann, sollten es. Authentifizierung versteht man das Vergleichen von Anmeldeinformationen mit einer Anforderung an die in einem vertrauenswürdigen Datenspeicher, um festzustellen, ob die Anforderung als stammen aus einer bekannten Entität behandelt werden soll. Autorisierung versteht man das Einschränken des Zugriffs auf bestimmte Ressourcen je nach Benutzeridentität. Eine dritte Sicherheitsbedenken schützt Anforderungen auf Abhören von Drittanbietern, die für die sollten Sie mindestens [stellen Sie sicher, dass SSL, von der Anwendung verwendet wird](https://docs.microsoft.com/aspnet/core/security/enforcing-ssl).

### <a name="authentication"></a>Authentifizierung

ASP.NET Core Identität ist eine Mitgliedschaftssystem, das Sie verwenden können, um die Anmeldefunktionalität für Ihre Anwendung zu unterstützen. Es wurde Unterstützung für lokale Benutzerkonten sowie externe Anmeldung anbieterunterstützung von Anbietern wie Microsoft Account, Twitter, Facebook, Google und vieles mehr. Ihre Anwendung kann zusätzlich zu ASP.NET Core Identity, Windows-Authentifizierung verwenden, oder ein Drittanbieter-Identitätsanbieter wie [Identity Server](https://github.com/IdentityServer/IdentityServer4).

ASP.NET Core Identität ist in Vorlagen für neue Projekte enthalten, wenn der einzelne Benutzerkonten-Option ausgewählt ist. Diese Vorlage enthält Unterstützung für die Registrierung, Anmeldung, externer Anmeldungen, vergessene Kennwörter und zusätzliche Funktionen.

![](./media/image7-3.png)

Abbildung 7 – 3 Wählen Sie einzelne Benutzerkonten Identität vorkonfiguriert.

Identity-Support ist in den Starttasks, die sowohl in ConfigureServices "und" Konfigurieren konfiguriert:

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
    app.UseMvc(routes =>
    {
        routes.MapRoute(
        name: "default",
        template: "{controller=Home}/{action=Index}/{id?}");
    });
}
```

Es ist wichtig, dass vor dem UseMvc UseIdentity angezeigt, in der Methode konfigurieren werden. Beim Konfigurieren von Identität in ConfigureServices, sehen Sie einen Aufruf von AddDefaultTokenProviders. Dies hat nichts mit Token zu tun, die zum Sichern der Webkommunikation verwendet werden kann, jedoch bezieht sich stattdessen auf Anbietern, die Anweisungen zu erstellen, die an Benutzer per SMS oder e-Mail in der Reihenfolge dafür, ihre Identität bestätigen gesendet werden können.

Sie können erfahren Sie mehr über [zweistufige Authentifizierung konfigurieren](https://docs.microsoft.com/aspnet/core/security/authentication/2fa) und [aktivieren externer anmeldeanbietern](https://docs.microsoft.com/aspnet/core/security/authentication/social/) aus offizielle ASP.NET Core Dokumente.

### <a name="authorization"></a>Autorisierung

Die einfachste Form der Autorisierung umfasst das Einschränken des Zugriffs für anonyme Benutzer. Dies kann erreicht werden, indem Sie einfach die \[autorisieren\] -Attribut auf bestimmte Domänencontroller oder Aktionen. Wenn Rollen verwendet werden, kann das Attribut erweitert werden, um Beschränken des Zugriffs auf Benutzer, die bestimmten Rollen angehören wie gezeigt:

```csharp
[Authorize(Roles = "HRManager,Finance")]
public class SalaryController : Controller
{

}
```

In diesem Fall würden Benutzer entweder der Rollen HRManager oder Finanzen (oder beides), Zugriff auf die SalaryController haben. So, dass ein Benutzer mehreren Rollen (nicht nur eine von mehreren) angehören, können Sie das Attribut mehrere Male anwenden Geben Sie jedes Mal eine Rolle erforderliche.

Bestimmte Gruppen von Rollen angeben, wie Zeichenfolgen in vielen verschiedenen Controllern und Aktionen zu unerwünschten Wiederholung führen können. Sie können Konfigurieren von Autorisierungsrichtlinien, die Autorisierungsregeln zu kapseln, und geben Sie dann die Richtlinie anstelle einzelner Rollen beim Anwenden der \[autorisieren\] Attribut:

```csharp
[Authorize(Policy = "CanViewPrivateReport")]
public IActionResult ExecutiveSalaryReport()
{
    return View();
}
```

Verwendung von Richtlinien auf diese Weise können Sie die Arten von Aktionen, die aus dem bestimmte Rollen oder die dafür geltenden Regeln eingeschränkt trennen. Später, wenn Sie eine neue Rolle, die auf bestimmte Ressourcen zugreifen muss erstellen, können Sie einfach aktualisieren eine Richtlinie, anstatt jede Liste von Rollen zu aktualisieren, auf jedem \[autorisieren\] Attribut.

#### <a name="claims"></a>Ansprüche

Ansprüche sind Name-Wert-Paaren, die Eigenschaften eines authentifizierten Benutzers darstellen. Beispielsweise können Benutzer Mitarbeiternummer als Anspruch gespeichert werden. Ansprüche können dann im Rahmen von Autorisierungsrichtlinien verwendet werden. Sie können eine Richtlinie namens "EmployeeOnly" erstellen, erfordert das Vorhandensein eines Anspruchs "EmployeeNumber", aufgerufen, wie im folgenden Beispiel gezeigt:

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

Diese Richtlinie kann dann verwendet werden, mit der \[autorisieren\] Attribut, um alle Controller und/oder eine Aktion, wie oben beschrieben zu schützen.

#### <a name="securing-web-apis"></a>Sichern von Web-APIs

Die meisten Web-APIs sollten ein Token-basierter Authentifizierungssystem implementieren. Tokenauthentifizierung ist statusfrei und entworfenen skalierbar sein. In einem System tokenbasierter Authentifizierung authentifizieren des Clients muss zunächst mit dem Authentifizierungsanbieter. Im Erfolgsfall wird der Client ein Token ausgestellt. dabei einfach eine kryptografisch sinnvolle Zeichenfolge von Zeichen. Wenn der Client eine Anforderung an eine API ausgeben, dann benötigt, fügt dieses Token als einen Header für die Anforderung hinzu. Der Server überprüft dann das Token im Anforderungsheader vor Abschließen der Anforderung gefunden. Abbildung 7 – 4 veranschaulicht diesen Prozess.

![TokenAuth](./media/image7-4.png)

**Abbildung 7 – 4.** Tokenbasierte Authentifizierung für Web-APIs.

> ### <a name="references--security"></a>Verweise – Sicherheit
> - **Übersicht über die Containerdokumentation Sicherheit**  
> https://docs.Microsoft.com/ASPNET/Core/Security/
> - **Erzwingen von SSL in einer ASP.NET Core-App**  
> <https://docs.Microsoft.com/ASPNET/Core/Security/Enforcing-SSL>
> - **Einführung in Identity**  
> <https://docs.Microsoft.com/ASPNET/Core/Security/Authentication/Identity>
> - **Einführung in die Autorisierung**  
> <https://docs.Microsoft.com/ASPNET/Core/Security/Authorization/Introduction>
> - **Authentifizierung und Autorisierung für API-Apps in Azure App Service**  
> <https://docs.Microsoft.com/Azure/App-Service-API/App-Service-API-Authentication>

## <a name="client-communication"></a>Clientkommunikation

Zusätzlich zu den Seiten bedient, und reagieren auf Anforderungen von Daten über Web-APIs, können ASP.NET Core-apps direkt verbundenen Clients kommunizieren. Diese ausgehende Kommunikation kann eine Vielzahl von Transport-Technologien, die am häufigsten verwendeten wird WebSockets verwenden. SignalR für ASP.NET Core ist eine Bibliothek, die sie auf die Art von Server-zu-Client-Kommunikation in Echtzeit-Funktion auf Ihre Anwendungen auf einfache Weise. SignalR unterstützt eine Vielzahl von Transport-Technologien, darunter WebSockets, und beseitigen viele Implementierungsdetails seitens des Entwicklers abstrahiert.

SignalR für ASP.NET Core befindet sich derzeit in Bearbeitung und wird in der nächsten Version von ASP.NET Core verfügbar sein. Allerdings andere [Source WebSockets-Bibliotheken öffnen](https://github.com/radu-matei/websocket-manager) sind derzeit verfügbar.

Echtzeit Clientkommunikation, ob mit WebSockets direkt oder andere Techniken in einer Vielzahl von Anwendungsszenarien nützlich sind. Beispiele:

-   Live Chatraum-Anwendungen

-   Überwachen von Anwendungen

-   Auftrag statusaktualisierungen

-   Benachrichtigungen

-   Interaktive Forms-Anwendungen

Wenn die Clientkommunikation in Ihre Anwendungen zu erstellen, sind in der Regel zwei Komponenten:

-   Serverseitige Verbindungs-Manager (SignalR-Hubs, WebSocketManager WebSocketHandler)

-   Die clientseitige-Bibliothek

Clients sind nicht auf Browsern – mobile apps, die Konsolen-apps beschränkt, und andere systemeigene apps können auch mithilfe von SignalR/WebSockets kommunizieren. Das folgende einfache Programm wiederholt alle Inhalte, die an eine Chat-Anwendung in der Konsole als Teil einer beispielanwendung WebSocketManager gesendet:

```csharp
public class Program
{
    private static Connection _connection;
    public static void Main(string[] args)
    {
        StartConnectionAsync();
        _connection.On("receiveMessage", (arguments) =>;
        {
            Console.WriteLine(\$"{arguments\[0\]} said: {arguments\[1\]}");
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
```

Erwägen Sie, die Methoden in denen Anwendung kommunizieren direkt mit Clientanwendungen, und überlegen Sie, ob die Kommunikation in Echtzeit Benutzer Ihrer app verbessern würden auftreten.

> ### <a name="references--client-communication"></a>Verweise – Client-Kommunikation
> - **SignalR für ASP.NET Core**  
> <https://github.com/ASPNET/SignalR>
> - **WebSocket-Manager**  
> https://github.com/Radu-matei/WebSocket-Manager

## <a name="domain-driven-design--should-you-apply-it"></a>Installieren Domain-Driven Design: sollten Sie es?

Domain Driven Design (DDD) ist ein agile Ansatz zum Erstellen von Software, die Fokussierung auf hat vor den *Business-Domäne*. Es wird ein starker Gewichtung von Kommunikation und Interaktion mit Expert(s) von Business-Domäne, die den Entwicklern verknüpft sein kann wie die realen System funktioniert. Wenn Sie ein System, die Aktualität behandelt erstellen, möglicherweise Ihrer Domäne Expert z. B. eine erfahrenen stock-Broker-Instanz sein. DDD dient zum großen, komplexen Geschäftsprobleme zu lösen, und ist häufig nicht für kleinere, einfacher Anwendungen geeignet, wie die Investition zum verstehen und Modellieren der Domänenadministrators nicht Sache ist.

Beim Erstellen von Software, die einen DDD Ansatz folgen, sollte Ihr Team (einschließlich nichttechnische Projektbeteiligten und Mitwirkenden) Entwickeln einer *ubiquitäre Sprache* für das Problemfeld. D. h. sollte dieselbe Terminologie verwendet werden, für die reale Konzept, das modelliert wird, die entsprechende Software und aller Strukturen, die möglicherweise vorhanden, um das Konzept (z. B. die Datenbanktabellen) beizubehalten. Daher sollte in der ubiquitäre Sprache beschriebenen Konzepte bilden die Grundlage für Ihre *Domänenmodell*.

Ihre Domänenmodell besteht aus Objekten, die das Verhalten des Systems darstellen miteinander interagieren. Diese Objekte können in den folgenden Kategorien fallen:

-   [Entitäten](http://deviq.com/entity/), Objekte mit einem Thread-Identität darstellt. Entitäten sind in der Regel in Persistenz mit einem Schlüssel gespeichert mit denen sie später abgerufen werden können.

-   [Aggregate](http://deviq.com/aggregate-pattern/), die darstellen, dass Gruppen von Objekten, die als Einheit beibehalten werden soll.

-   [Wert von Objekten](http://deviq.com/value-object/), die darstellen Konzepte, die auf der Basis der Summe der zugehörigen Eigenschaftswerte enthält verglichen werden können. Beispielsweise besteht ein Anfangs- und Enddatum Datum DateRange.

-   [Domäne Ereignisse](https://martinfowler.com/eaaDev/DomainEvent.html), die Dinge innerhalb des Systems, die von Interesse an anderen Teilen des Systems sind darstellen.

Beachten Sie, dass ein Domänenmodell DDD komplexe Verhalten innerhalb des Modells kapseln sollten. Entitäten sollten insbesondere lediglich Auflistungen von Eigenschaften nicht. Wenn die Domänenmodell verfügt nicht über das Verhalten und lediglich den Zustand des Systems darstellt, es gilt als ein [anemic Modell](http://deviq.com/anemic-model/), im DDD unerwünscht ist.

Zusätzlich zu diesen Modell die folgenden DDD in der Regel einer Vielzahl von Mustern:

-   [Repository](http://deviq.com/repository-pattern/), Abstraktion Persistenz-Details.

-   [Factory](https://en.wikipedia.org/wiki/Factory_method_pattern), für das Erstellen von komplexen Objekten kapseln.

-   Domain-Ereignisse für das entkoppeln abhängige Verhalten unterscheidet sich von Verhalten auslösen.

-   [Services](http://gorodinski.com/blog/2012/04/14/services-in-domain-driven-design-ddd/)für kapselnden komplexe Verhalten und/oder Infrastrukturdetails-Implementierung.

-   [Befehl](https://en.wikipedia.org/wiki/Command_pattern), für die Entkopplung Befehle ausgibt, und den Befehl selbst ausführen.

-   [Spezifikation](http://deviq.com/specification-pattern/), für das Kapseln Abfragedetails.

DDD empfiehlt außerdem die Verwendung der zuvor besprochenen Clean-Architektur ermöglicht lose Verbindung, für die Kapselung und Code, die leicht mit Komponententests überprüft werden kann.

### <a name="when-should-you-apply-ddd"></a>Wann sollten Sie DDD anwenden

DDD eignet sich gut für große Anwendungen mit erheblichen Business (nicht nur technische) Komplexität. Die Anwendung sollte die Domänenexperten sein. Es darf signifikantem Verhalten im Domänenmodell selbst, Geschäftsregeln und Interaktionen hinter einfach speichern und Abrufen von den aktuellen Status der verschiedenen Datensätzen aus Datenspeichern darstellt.

### <a name="when-shouldnt-you-apply-ddd"></a>Sie sollte nicht beim DDD anwenden

DDD umfasst die Investitionen in die Modellierung, Architektur und Kommunikation, die für kleinere Anwendungen oder Anwendungen, die im Wesentlichen nur CRUD (erstellen/lesen/aktualisieren/löschen) sind nicht gerechtfertigt sein kann. Wenn Sie entscheiden, Ihre Anwendung folgende DDD Ansatz, aber feststellen, dass Ihre Domäne ein anemic Modell ohne das Verhalten hat, müssen Sie Ihres Ansatzes überdenken. Ihre Anwendung möglicherweise nicht DDD oder um Unterstützung zu erhalten, die Umgestaltung Ihrer Anwendung zum Kapseln der Geschäftslogik im Domänenmodell und nicht in der Datenbank oder-Benutzeroberfläche möglicherweise.

Ein Hybridansatz wäre nur DDD für die Transaktions- oder komplexeren Bereiche der Anwendung, nicht jedoch für einfacher CRUD oder nur-Lese Teile der Anwendung verwenden. Sie needn't für die Instanz, die Einschränkungen eines Aggregats aufweisen, wenn Sie Daten aus, um einen Bericht anzuzeigen oder zum Anzeigen von Daten für ein Dashboard abrufen. Es ist vollkommen akzeptabel, eine separate, einfacher read-Modell für diese Anforderungen zu erhalten.

> ### <a name="references--domain-driven-design"></a>Verweise – Domain Driven Design
> - **DDD im Klartext (StackOverflow Answers)**  
> <https://stackoverflow.com/questions/1222392/can-someone-EXPLAIN-Domain-Driven-Design-ddd-in-Plain-English-Please/1222488#1222488>

## <a name="deployment"></a>Bereitstellung

Es gibt einige Schritte Beteiligten im Verlauf der Bereitstellung Ihrer Anwendung ASP.NET Core unabhängig davon, in dem sie gehostet wird. Der erste Schritt ist zum Veröffentlichen der Anwendung, die ausgeführt werden können mithilfe der Dotnet CLI-Befehl "Veröffentlichen". Die Anwendung kompilieren wird und platzieren alle Dateien, die erforderlich sind, um die Anwendung in einem designierten Ordner auszuführen. Wenn Sie in Visual Studio bereitstellen, ist dieser Schritt automatisch ausgeführt. Dem Veröffentlichungsordner enthält .exe und DLL-Dateien für die Anwendung und ihre Abhängigkeiten. Eine eigenständige Anwendung dazu gehören auch eine Version der .NET Runtime. ASP.NET Core Anwendungen gehören auch Konfigurationsdateien, statischen Client Bestand und MVC-Ansichten.

ASP.NET Core-Anwendungen sind konsolenanwendungen, die gestartet werden müssen, wenn der Server gestartet wird und neu gestartet, wenn die Anwendung (oder Server) stürzt ab. Prozess-Manager kann verwendet werden, um diesen Prozess zu automatisieren. Die am häufigsten verwendeten Prozess-Manager für ASP.NET Core sind Nginx und Apache unter Linux und unter IIS oder Windows-Dienst unter Windows.

Zusätzlich zu einem Prozess-Manager müssen ASP.NET Core-Anwendungen, die in den Kestrel Webserver gehostet einen reverse-Proxy-Server verwenden. Ein reverse-Proxy-Server empfängt HTTP-Anforderungen aus dem Internet und an Kestrel weiterleitet, nachdem einige vorläufige Behandlung. Reverse-Proxy-Server eine Sicherheitsebene für die Anwendung bereitzustellen und für Edge-Bereitstellungen (für den Datenverkehr aus dem Internet ausgesetzt) erforderlich sind. Kestrel ist relativ neu und entsprechende Schutzmaßnahmen gegen bestimmte Angriffe noch nicht verfügbar ist. Kestrel unterstützt auch mehrere Anwendungen auf demselben Port hosten, sodass Techniken, wie Sie Hostheader mit ihm verwendet werden können, zum Aktivieren des Hostings mehrere Anwendungen auf dem gleichen Port und IP-Adresse nicht.

![Kestrel zum Internet](./media/image7-5.png)

Abbildung 7 – 5 ASP.NET gehostete Kestrel hinter einem reverse-Proxy-server

Ein weiteres Szenario, in dem Reverseproxy hilfreich sein kann, ist Sichern von mehreren Anwendungen, die mithilfe von SSL/HTTPS. In diesem Fall würde nur die Reverseproxy müssen SSL konfiguriert haben. Kommunikation zwischen dem reverse-Proxy-Server und Kestrel konnte über HTTP, stattfinden wie in Abbildung 7 – 6 gezeigt.

![](./media/image7-6.png)

Abbildung 7 – 6 ASP.NET gehostet hinter eine sichere HTTPS-reverse-Proxy-server

Ein immer beliebter Ansatz ist zum Hosten der ASP.NET Core-Anwendung in einem Docker-Container, der dann lokal gehostet oder in Azure zum Hosten von Cloud-basierten bereitgestellt werden kann. Der Docker-Container konnte Anwendungscode Kestrel, unter enthalten und wird hinter einem reverse-Proxy-Server bereitgestellt werden, wie oben gezeigt.

Wenn Sie Ihre Anwendung in Azure hosten, können Microsoft Azure Application Gateway als dediziertes virtuelles Gerät Sie mehrere Dienste bereitstellen können. Zusätzlich zu den fungiert als Reverseproxy für einzelne Anwendungen, bieten Application Gateway auch die folgenden Funktionen:

-   HTTP-Lastenausgleich

-   SSL Offloading (SSL nur für Internet)

-   End-to-End-SSL

-   Routing mit mehreren Standorten (Konsolidieren von bis zu 20 Standorten auf ein einzelnes Gateway für die Anwendung)

-   Web Application-firewall

-   WebSocket-Unterstützung

-   Erweiterte Diagnose

*Erfahren Sie mehr über Azure Bereitstellungsoptionen in Kapitel 10.*

> ### <a name="references--deployment"></a>Verweise – Bereitstellung
> - **Hosting- und -Bereitstellungsübersicht**  
> <https://docs.Microsoft.com/ASPNET/Core/Publishing/>
> - **Verwendung von Kestrel mit einer reverse-proxy**  
> <https://docs.Microsoft.com/ASPNET/Core/Fundamentals/Servers/kestrel#When-to-Use-kestrel-with-a-Reverse-Proxy>
> - **Host ASP.NET Core-apps in Docker**  
> <https://docs.Microsoft.com/ASPNET/Core/Publishing/docker>
> - **Einführung in Azure-Anwendung-Gateway**  
> <https://docs.Microsoft.com/Azure/Application-Gateway/Application-Gateway-Introduction>

>[!div class="step-by-step"]
[Vorherigen] (Allgemeine-Client-Side-Web-technologies.md) [weiter] (Work-with-data-in-asp-net-core-apps.md)

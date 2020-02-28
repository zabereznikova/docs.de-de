---
title: Testen von ASP.NET Core MVC-Apps
description: Entwerfen moderner Webanwendungen mit ASP.NET Core und Azure | Testen von ASP.NET Core MVC-Apps
author: ardalis
ms.author: wiwagn
ms.date: 12/04/2019
ms.openlocfilehash: 164e820ffa6030b3dcb9180d56e57ce39bb03143
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503934"
---
# <a name="test-aspnet-core-mvc-apps"></a>Testen von ASP.NET Core MVC-Apps

> *„Wenn es Ihnen nicht gefällt, Komponententests für Ihr Produkt auszuführen, ist es sehr wahrscheinlich, dass es Ihren Kunden auch nicht gefallen wird.“*
 > \_–Anonym

Software von beliebiger Komplexität kann aufgrund von Änderungen auf unerwartete Weisen fehlschlagen. Daher ist es erforderlich, Anwendungen auf Änderungen zu testen, mit Ausnahme von unbedeutenden (bzw. weniger wichtigen) Anwendungen. Manuelle Tests sind die langsamste, unzuverlässigste und aufwendigste Möglichkeit zum Testen von Software. Leider können diese die einzige verfügbare Methode sein, wenn Anwendungen nicht zum Testen entworfen wurden. Anwendungen, die gemäß den in [Kapitel 4](architectural-principles.md) beschriebenen Architekturprinzipien geschrieben wurden, sollten komponententestfähig sein. ASP.NET Core-Anwendungen unterstützen automatisierte Integrations- und Funktionstests.

## <a name="kinds-of-automated-tests"></a>Arten von automatisierten Tests

Es gibt viele Arten von automatisierten Tests für Softwareanwendungen. Der einfachste, spezifischste Test ist der Komponententest. Integrationstests und Funktionstests sind etwas allgemeiner. Andere Arten von Tests werden in dieser Dokumentation nicht behandelt, z. B. UI-Tests, Auslastungstests, Belastungstests und Buildakzeptanztests.

### <a name="unit-tests"></a>Komponententests

Ein Komponententest überprüft einen einzelnen Teil der Logik Ihrer Anwendung. Man kann diesen Test genauer beschreiben, indem man aufführt, was er nicht umfasst. Ein Komponententest überprüft nicht, wie Ihr Code mit Abhängigkeiten oder Infrastruktur interagiert. Dafür gibt es Integrationstests. Ein Komponententest überprüft nicht das Framework, auf dem Ihr Code geschrieben wurde. Sie sollten davon ausgehen, dass dieses funktioniert. Wenn es nicht funktioniert, melden Sie den Fehler und schreiben eine Problemumgehung. Komponententests werden vollständig im Arbeitsspeicher und im Prozess ausgeführt. Sie kommunizieren nicht mit dem Dateisystem, dem Netzwerk oder einer Datenbank. Komponententests sollten Ihren Code nur überprüfen.

Aufgrund der Tatsache, dass Komponententests nur eine einzelne Komponente Ihres Codes überprüfen und über keine externen Abhängigkeiten verfügen, werden diese sehr schnell ausgeführt. Daher sollten Sie eine Testsammlung aus Hunderten von Komponententests in wenigen Sekunden ausführen können. Führen Sie diese regelmäßig aus, im Idealfall vor jedem Push an ein öffentliches Repository für die Quellcodeverwaltung und insbesondere vor jedem automatisierten Buildvorgang auf Ihrem Buildserver.

### <a name="integration-tests"></a>Integrationstests

Obwohl es eine gute Idee ist, Code zu kapseln, der mit Infrastruktur interagiert (z.B. Datenbanken und Dateisysteme), wird ein Teil des Codes übrig bleiben, den Sie wahrscheinlich testen möchten. Darüber hinaus sollten Sie sicherstellen, dass die Schichten Ihres Codes wie erwartet interagieren, wenn die Abhängigkeiten Ihrer Anwendung vollständig aufgelöst werden. Hierfür sind Integrationstests verantwortlich. Integrationstests sind langsamer und schwieriger einzurichten als Komponententests, da sie oft von externen Abhängigkeiten und Infrastrukturen abhängig sind. Daher sollten Sie es vermeiden, Szenarios zu testen, die Tests mit Komponententests in Integrationstests darstellen könnten. Wenn Sie ein bestimmtes Szenario mit einem Komponententest testen können, sollten Sie dieses Szenario mit einem Komponententest testen. Wenn dies nicht möglich ist, sollten Sie einen Integrationstest verwenden.

Integrationstests verfügen meistens über komplexere Setup- und Nachbereitungsprozeduren als Komponententests. Ein Integrationstest, der beispielsweise auf eine Datenbank angewendet wird, benötigt eine Möglichkeit, die Datenbank in einen bekannten Zustand zurückzusetzen, bevor jeder Test ausgeführt wird. Wenn neue Tests hinzugefügt werden und das Datenbankschema für die Produktion sich weiterentwickelt, werden die Testskripts größer und komplexer. In vielen großen Systemen ist es unpraktisch, vollständige Testsammlungen auf den Arbeitsstationen von Entwicklern auszuführen, bevor Änderungen in die Quellcodeverwaltung eingetragen werden. In diesen Fällen können Integrationstests auf einem Buildserver ausgeführt werden.

### <a name="functional-tests"></a>Funktionstests

Integrationstests werden aus der Perspektive des Entwicklers geschrieben, um sicherzustellen, dass einige der Systemkomponenten ordnungsgemäß interagieren. Funktionstests werden aus der Perspektive des Benutzers geschrieben, um die Richtigkeit des Systems basierend auf den Anforderungen sicherzustellen. Der folgende Auszug bietet eine nützliche Analogie zum Vergleich von Funktionstests und Komponententests:

> „Oft wird das Entwickeln eines Systems mit dem Erbauen eines Hauses verglichen. Auch wenn diese Analogie nicht ganz richtig ist, können wir sie verwenden, um den Unterschied zwischen Komponententests und Funktionstests besser zu verstehen. Komponententests entsprechen einem Bauinspektor, der die Baustelle eines Hauses begutachtet. Er konzentriert sich auf die verschiedenen internen Systeme des Hauses, also das Gebäudefundament, den Rohbau, die Stromversorgung, die sanitären Einrichtungen, usw. Er stellt sicher (überprüft), dass die einzelnen Teile des Hauses voll funktionsfähig und sicher sind, d.h., dass sie der Bauordnung entsprechen. Funktionstests entsprechen in diesem Szenario dem Hauseigentümer, der ebenfalls diese Baustelle besucht. Er geht davon aus, dass die internen Systeme funktionieren und der Bauinspektor seine Arbeit macht. Der Hauseigentümer konzentriert sich darauf, wie es sein wird, in diesem Haus zu leben. Er kümmert sich zum Beispiel darum, wie das Haus aussieht, ob die verschiedenen Räume die passende Größe haben, ob das Haus den Bedürfnissen einer Familie gerecht wird, und ob die Fenster eine gute Ausrichtung dafür haben, die Morgensonne herein zu lassen. Der Hauseigentümer führt Funktionstests am Haus durch. Seine Perspektive ist die des Benutzers. Der Bauinspektor führt Komponententests am Haus durch. Seine Perspektive ist die des Entwicklers.“

Quelle: [Unit Testing versus Functional Tests (Vergleich von Komponententests und Funktionstests)](https://www.softwaretestingtricks.com/2007/01/unit-testing-versus-functional-tests.html)

Unter Entwicklern sagt man gern: „Als Entwickler machen wir zwei Fehler: wir erstellen falsch, oder wir erstellen das Falsche.“ Mit Komponententests stellen Sie sicher, dass Sie richtig erstellen. Funktionstests stellen sicher, dass Sie das Richtige erstellen.

Da Funktionstest auf der Systemebene ausgeführt werden, erfordern sie ein gewisses Maß an Automatisierung der Benutzeroberfläche. Wie Integrationstests arbeiten auch die Funktionstests in der Regel mit einer Art Testinfrastruktur. Dadurch werden sie langsamer und anfälliger für Fehler als Komponententests und Integrationstests. Sie sollten nur so viele Funktionstests anwenden, wie Sie benötigen, um sich sicher zu sein, dass das System sich so verhält, wie Benutzer es erwarten würden.

### <a name="testing-pyramid"></a>Testpyramide

Martin Fowler schrieb über die Testpyramide. Ein Beispiel dafür wird in Abbildung 9–1 dargestellt.

![Testpyramide](./media/image9-1.png)

**Abbildung 9-1**. Testpyramide

Die verschiedenen Schichten der Pyramide und ihre Größen stellen verschiedene Arten von Tests dar, und wie viele davon Sie für Ihre Anwendung schreiben sollten. Wie Sie sehen können, wird empfohlen, eine große Basis aus Komponententests zu verwenden, die von einer kleineren Menge von Integrationstests und einer noch kleineren Menge von Funktionstests unterstützt wird. Im Idealfall sollte jede Schicht nur aus Tests bestehen, die auf niedrigeren Schichten nicht ordnungsgemäß ausgeführt werden können. Behalten Sie die Testpyramide im Hinterkopf, wenn Sie sich entscheiden, welche Art von Test Sie für ein bestimmtes Szenario benötigen.

### <a name="what-to-test"></a>Der Testgegenstand

Herauszufinden, was getestet werden sollte, ist ein häufiges Problem für Entwickler, die noch unerfahren im Schreiben von automatisierten Tests sind. Ein guter Startpunkt ist das Testen der bedingten Logik. An jeder Stelle, an der eine Methode mit einem Verhalten vorhanden ist, das auf einer Bedingungsanweisung basiert (if-else, switch usw.), sollten Sie zumindest einige Tests erstellen, die das richtige Verhalten unter bestimmten Bedingungen überprüfen. Wenn Ihr Code über Fehlerbedingungen verfügt, sollten Sie mindestens einen Test für den „besten Pfad“ durch den Code (ohne Fehler) und einen Test für den „schlechtesten Pfad“ (mit Fehlern und ungewohnten Ergebnissen) verwenden, um sicherzustellen, dass Ihre Anwendung auf Fehler wie erwartet reagiert. Letztendlich sollten Sie sich darauf konzentrieren, Dinge zu testen, die fehlschlagen können, anstatt sich auf Metriken wie Code Coverage zu konzentrieren. Allgemein ist mehr Code Coverage besser als zu wenig. Allerdings können Sie Ihre Zeit sinnvoller nutzen, wenn Sie ein paar weitere Tests für eine komplexe und unternehmenskritische Methode schreiben, anstatt Tests für automatische Eigenschaften zu schreiben, um die Code Coverage-Metrik zu verbessern.

## <a name="organizing-test-projects"></a>Organisieren von Testprojekten

Sie können Testprojekte so organisieren, wie es für Sie am besten funktioniert. Es kann hilfreich sein, Tests je nach Typ (Komponententest, Integrationstest) und Testsubjekt (Projekt, Namespace) voneinander zu trennen. Ob diese Trennung aus Ordnern in einem einzelnen Testprojekt oder mehreren Testprojekten besteht, ist eine Entwurfsentscheidung. Ein einzelnes Projekt ist am einfachsten. Für ein großes Projekt mit vielen Tests sollten Sie mehrere verschiedene Testprojekte besitzen, um verschiedene Testgruppen einfacher ausführen zu können. Viele Teams organisieren Ihre Testprojekte basierend auf dem Projekt, das sie überprüfen. Dies resultiert bei Anwendungen mit einer größeren Anzahl von Projekten in einer großen Anzahl von Testprojekten, insbesondere dann, wenn Sie diese immer noch nach der Art von Tests in jedem Projekt sortieren. Ein Kompromiss für diesen Ansatz ist, ein Projekt mit Ordnern in den Testprojekten pro Art von Test für jede Anwendung zu besitzen, die das Projekt und die Klasse angeben, die geprüft werden.

Eine gängige Methode ist, die Anwendungsprojekte in einem SRC-Ordner und die Testprojekte der Anwendung im parallelen Ordner „Tests“ zu organisieren. Sie können entsprechende Projektmappenordner in Visual Studio anlegen, wenn Sie diese Organisierung hilfreich finden.

![Organisieren von Tests in Ihrer Projektmappe](./media/image9-2.png)

**Abbildung 9-2:** Organisieren von Tests in Ihrer Projektmappe

Sie können das Testframework verwenden, das Sie bevorzugen. Das xUnit-Framework funktioniert gut und wird für alle Tests für ASP.NET Core und EF Core verwendet. Mit der in Abbildung 9.3 gezeigten Vorlage können Sie ein xUnit-Testprojekt in Visual Studio oder über die CLI mithilfe des Befehls `dotnet new xunit` hinzufügen.

![Hinzufügen eines xUnit-Testprojekts in Visual Studio](./media/image9-3.png)

**Abbildung 9-3.** Hinzufügen eines xUnit-Testprojekts in Visual Studio

### <a name="test-naming"></a>Benennen von Tests

Weisen Sie Ihren Tests konsistente Namen zu, die den Zweck des jeweiligen Test angeben. Ein effektiver Ansatz ist, Testklassen nach der Klasse und Methode zu benennen, die sie testen. Dies resultiert in vielen kleinen Testklassen, verdeutlicht jedoch, wofür jeder Test zuständig ist. Mit dem eingerichteten Testklassennamen zum Identifizieren der Klasse und Methode, die getestet werden, kann der Testmethodenname dafür verwendet werden, das zu testende Verhalten anzugeben. Dies sollte das erwartete Verhalten und alle Eingaben oder Annahmen einschließen, die dieses Verhalten verursachen. Beispiele für Testnamen:

- `CatalogControllerGetImage.CallsImageServiceWithId`

- `CatalogControllerGetImage.LogsWarningGivenImageMissingException`

- `CatalogControllerGetImage.ReturnsFileResultWithBytesGivenSuccess`

- `CatalogControllerGetImage.ReturnsNotFoundResultGivenImageMissingException`

Eine Variante dieses Ansatzes beendet jeden Testklassennamen mit „Should“ und ändert die Zeitform:

- `CatalogControllerGetImage`**Should**`.`**Call**`ImageServiceWithId`

- `CatalogControllerGetImage`**Should**`.`**Log**`WarningGivenImageMissingException`

Einige Teams finden den zweiten Ansatz für die Benennung klarer, obwohl er etwas ausführlicher ist. In jedem Fall sollten Sie versuchen, eine Namenskonvention zu verwenden, die einen Einblick zum Verhalten des Tests bietet, damit klar ist, welche Fälle fehlschlagen. Vermeiden Sie ungenaue Namen, z. B. „ControllerTests.Test1“, da diese keine Informationen bieten, wenn sie in den Testergebnissen angezeigt werden.

Wenn Sie eine Namenskonvention befolgen, die viele kleine Testklassen produziert, wie eine der oben genannten, empfiehlt es sich, Ihre Tests auch mit Ordnern und Namespaces zu sortieren. Abbildung 9–4 veranschaulicht einen Ansatz zum Organisieren von Tests mit Ordnern in mehreren Testprojekten.

![Organisieren von Testklassen in Ordnern, basierend auf der getesteten Klasse](./media/image9-4.png)

**Abbildung 9–4** Organisieren von Testklassen in Ordnern, basierend auf der Klasse, die getestet wird.

Wenn viele Methoden (d. h. auch viele Testklassen) in einer Anwendungsklasse getestet werden sollen, kann es sinnvoll sein, diese in einem Ordner abzulegen, der der Anwendungsklasse entspricht. Diese Organisierung gleicht der Organisierung von Dateien in Ordnern. Wenn mehr als drei oder vier zusammengehörende Dateien in einem Ordner mit vielen anderen Dateien vorhanden sind, empfiehlt es sich, für diese einen Unterordner anzulegen.

## <a name="unit-testing-aspnet-core-apps"></a>Komponententests für ASP.NET Core-Apps

In einer gut entworfenen ASP.NET Core-Anwendung ist der Großteil der Komplexitäts- und Geschäftslogik in Geschäftselementen und einer Vielzahl von Diensten gekapselt. Die ASP.NET Core MVC-App selbst sollte mitsamt ihrer Controller, Filter, ViewModels und Ansichten nur wenige Komponententests benötigen. Viele der Funktionen einer bestimmten Aktion befinden sich außerhalb der Aktionsmethode. Ob das Routing oder die globale Fehlerbehandlung ordnungsgemäß funktioniert, kann mit einem Komponententest nicht effektiv geprüft werden. Ebenso können alle Filter, einschließlich der Modellvalidierung und die Authentifizierung sowie die Autorisierungsfilter nicht mit Komponententests geprüft werden, die auf die Aktionsmethode eines Controllers ausgerichtet sind. Ohne diese Quellen für Verhalten sollten die meisten Aktionsmethoden unbedeutend klein sein und das meiste Ihrer Arbeit an Dienste delegieren, die unabhängig vom Controller geprüft werden, der sie verwendet.

In manchen Fällen müssen Sie Ihren Code umgestalten, um einen Komponententest durchführen zu können. Dies umfasst häufig das Identifizieren von Abstraktionen und die Verwendung von Abhängigkeitsinjektionen, um auf den Code zuzugreifen, den Sie testen möchten, anstatt direkt auf die Infrastruktur zu codieren. Ziehen Sie zum Beispiel die folgende einfache Aktionsmethode zum Anzeigen von Bildern in Betracht:

```csharp
[HttpGet("[controller]/pic/{id}")]
public IActionResult GetImage(int id)
{
    var contentRoot = _env.ContentRootPath + "//Pics";
    var path = Path.Combine(contentRoot, id + ".png");
    Byte[] b = System.IO.File.ReadAllBytes(path);
    return File(b, "image/png");
}
```

Wegen der direkten Abhängigkeit von `System.IO.File`, die diese Methode zum Lesen aus dem Dateisystem verwendet, ist es schwer, Komponententests für sie durchzuführen. Sie können dieses Verhalten testen, um sicherzustellen, dass es wie erwartet funktioniert. Wenn Sie dies jedoch mit echten Dateien durchführen, handelt es sich um einen Integrationstest. Beachten Sie, dass Sie die Route dieser Methode nicht mit Komponententests testen können. Wie Sie diese mit einem Funktionstest testen können, wird im Folgenden erläutert.

Wenn Sie keinen direkten Komponententest für das Verhalten des Dateisystems und die Route durchführen können, gibt es dennoch Tests, die Sie durchführen sollten. Nach dem Refactoring zum Ermöglichen von Komponententests werden Ihnen möglicherweise Testfälle und fehlendes Verhalten auffallen, wie z.B. die Problembehandlung. Wie reagiert die Methode, wenn eine Datei nicht gefunden werden kann? Wie sollte sie reagieren? In diesem Beispiel sieht die umgestaltete Methode wie folgt aus:

```csharp
[HttpGet("[controller]/pic/{id}")]
public IActionResult GetImage(int id)
{
    byte[] imageBytes;
    try
    {
        imageBytes = _imageService.GetImageBytesById(id);
    }
    catch (CatalogImageMissingException ex)
    {
        _logger.LogWarning($"No image found for id: {id}");
        return NotFound();
    }
    return File(imageBytes, "image/png");
}
```

`_logger` und `_imageService` werden als Abhängigkeiten eingefügt. Sie können nun prüfen, ob dieselbe ID, die an die Aktionsmethode übergeben wird, an `_imageService` übergeben wird und ob die resultierenden Bytes als Teil von FileResult zurückgegeben werden. Sie können auch überprüfen, ob die Fehlerprotokollierung ordnungsgemäß erfolgt, und ob das Ergebnis `NotFound` zurückgegeben wird, wenn das Bild fehlt, vorausgesetzt, dass dies wichtig für das Verhalten der Anwendung ist (d. h., dass dies nicht nur temporärer Code ist, der vom Entwickler hinzugefügt wurde, um ein Problem zu diagnostizieren). Die eigentliche Dateilogik wurde in einen separaten Implementierungsdienst verschoben und wurde erweitert, damit sie im Fall einer fehlenden Datei eine anwendungsspezifische Ausnahme zurückgibt. Mit einem Integrationstest können Sie diese Implementierung unabhängig testen.

Für die meisten Fälle wird empfohlen, globale Ausnahmehandler in Ihren Controllern zu verwenden. Darum sollten der enthaltene Logikumfang minimal und Komponententests wahrscheinlich nicht notwendig sein. Für die meisten Tests von Controlleraktionen sollten Sie Funktionstests und die unten beschriebene `TestServer`-Klasse verwenden.

## <a name="integration-testing-aspnet-core-apps"></a>Integrationstests für ASP.NET Core-Apps

Die meisten Integrationstests in Ihren ASP.NET Core-Apps sollten Testdienste und andere Implementierungstypen sein, die in Ihrem Infrastrukturprojekt definiert wurden. Sie könnten beispielsweise über Ihre Datenzugriffsklassen im Infrastrukturprojekt [prüfen, ob EF Core die erwarteten Daten erfolgreich aktualisiert und abruft](https://docs.microsoft.com/ef/core/miscellaneous/testing/). Das korrekte Verhalten Ihres MVC-Projekts in ASP.NET Core können Sie am besten mit Funktionstests testen, die Sie für Ihre App ausführen, welche in einem Testhost ausgeführt wird.

## <a name="functional-testing-aspnet-core-apps"></a>Funktionstests für ASP.NET Core-Apps

Die `TestServer`-Klasse macht das Schreiben von Funktionstests für ASP.NET Core-Anwendungen relativ einfach. Sie konfigurieren einen `TestServer` mit `WebHostBuilder` (oder `HostBuilder`) direkt (wie Sie es normalerweise für Ihre Anwendung tun) oder mit dem Typ `WebApplicationFactory` (verfügbar seit Version 2.1). Sie sollten versuchen, einen Testhost zu verwenden, der dem Produktionshost so ähnlich wie möglich ist, damit das Verhalten der Tests dem Verhalten der App in der Produktion ähnelt. Die `WebApplicationFactory`-Klasse ist hilfreich für die ContentRoot-Konfiguration der TestServer-Klasse, die von ASP.NET Core verwendet wird, um statische Ressourcen wie Ansichten zu finden.

Sie können einfache Funktionstests erstellen, indem Sie eine Testklasse erstellen, die IClassFixture\<WebApplicationFactory\<TEntry>> implementiert, wobei es sich bei „TEntry“ um die Startklasse Ihrer Webanwendung handelt. Mit diesen Vorkehrungen kann Ihre Testfixture einen Client mithilfe der CreateClient-Methode der Zuordnungsinstanz erstellen:

```cs
public class BasicWebTests : IClassFixture<WebApplicationFactory<Startup>>
{
    protected readonly HttpClient _client;

    public BaseWebTest(WebApplicationFactory<Startup> factory)
    {
        _client = factory.CreateClient();
    }

    // write tests that use _client
}
```

In vielen Fällen führen Sie zusätzliche Konfigurationen für Ihre Website durch, bevor jeder Test ausgeführt wird, z.B. das Konfigurieren der Anwendung für die Verwendung eines Datenspeichers im Arbeitsspeicher und das anschließende Seeding der Anwendung mit Testdaten. Hierzu sollten Sie eine eigene Unterklasse von „WebApplicationFactory\<TEntry>“ erstellen und die dazugehörige Methode „ConfigureWebHost“ überschreiben. Das folgende Beispiel stammt vom Funktionstestprojekt „eShopOnWeb“ und wird als Teil der Tests für die Hauptwebanwendung verwendet.

```cs
using Microsoft.AspNetCore.Hosting;
using Microsoft.AspNetCore.Identity;
using Microsoft.AspNetCore.Mvc.Testing;
using Microsoft.EntityFrameworkCore;
using Microsoft.eShopWeb.Infrastructure.Data;
using Microsoft.eShopWeb.Infrastructure.Identity;
using Microsoft.eShopWeb.Web;
using Microsoft.Extensions.DependencyInjection;
using Microsoft.Extensions.Logging;
using System;

namespace Microsoft.eShopWeb.FunctionalTests.Web
{
    public class WebTestFixture : WebApplicationFactory<Startup>
    {
        protected override void ConfigureWebHost(IWebHostBuilder builder)
        {
            builder.UseEnvironment("Testing");

            builder.ConfigureServices(services =>
            {
                 services.AddEntityFrameworkInMemoryDatabase();

                // Create a new service provider.
                var provider = services
                    .AddEntityFrameworkInMemoryDatabase()
                    .BuildServiceProvider();

                // Add a database context (ApplicationDbContext) using an in-memory 
                // database for testing.
                services.AddDbContext<CatalogContext>(options =>
                {
                    options.UseInMemoryDatabase("InMemoryDbForTesting");
                    options.UseInternalServiceProvider(provider);
                });

                services.AddDbContext<AppIdentityDbContext>(options =>
                {
                    options.UseInMemoryDatabase("Identity");
                    options.UseInternalServiceProvider(provider);
                });

                // Build the service provider.
                var sp = services.BuildServiceProvider();

                // Create a scope to obtain a reference to the database
                // context (ApplicationDbContext).
                using (var scope = sp.CreateScope())
                {
                    var scopedServices = scope.ServiceProvider;
                    var db = scopedServices.GetRequiredService<CatalogContext>();
                    var loggerFactory = scopedServices.GetRequiredService<ILoggerFactory>();

                    var logger = scopedServices
                        .GetRequiredService<ILogger<WebTestFixture>>();

                    // Ensure the database is created.
                    db.Database.EnsureCreated();

                    try
                    {
                        // Seed the database with test data.
                        CatalogContextSeed.SeedAsync(db, loggerFactory).Wait();

                        // seed sample user data
                        var userManager = scopedServices.GetRequiredService<UserManager<ApplicationUser>>();
                        var roleManager = scopedServices.GetRequiredService<RoleManager<IdentityRole>>();
                        AppIdentityDbContextSeed.SeedAsync(userManager, roleManager).Wait();
                    }
                    catch (Exception ex)
                    {
                        logger.LogError(ex, $"An error occurred seeding the " +
                            "database with test messages. Error: {ex.Message}");
                    }
                }
            });
        }
    }
}
```

Tests können die benutzerdefinierte WebApplicationFactory nutzen, um einen Client zu erstellen und dann mithilfe dieser Clientinstanz Anforderungen an die Anwendung zu stellen. Die Anwendung verfügt über Daten, die als Teil der Assertionen des Tests verwendet werden können. Der folgende Test überprüft, ob die Startseite der Anwendung „eShopOnWeb“ ordnungsgemäß geladen wird und eine Produktliste enthält, die der Anwendung als Teil des Seedings hinzugefügt wurden.

```cs
using Microsoft.eShopWeb.FunctionalTests.Web;
using System.Net.Http;
using System.Threading.Tasks;
using Xunit;

namespace Microsoft.eShopWeb.FunctionalTests.WebRazorPages
{
    [Collection("Sequential")]
    public class HomePageOnGet : IClassFixture<WebTestFixture>
    {
        public HomePageOnGet(WebTestFixture factory)
        {
            Client = factory.CreateClient();
        }

        public HttpClient Client { get; }

        [Fact]
        public async Task ReturnsHomePageWithProductListing()
        {
            // Arrange & Act
            var response = await Client.GetAsync("/");
            response.EnsureSuccessStatusCode();
            var stringResponse = await response.Content.ReadAsStringAsync();

            // Assert
            Assert.Contains(".NET Bot Black Sweatshirt", stringResponse);
        }
    }
}
```

Dieser Funktionstest führt den gesamten ASP.NET Core MVC/Razor Pages-Anwendungsstapel aus, einschließlich aller Middleware, Filter, Binder usw., die verfügbar sind. Er überprüft, ob eine bestimmte Route („/“) den erwarteten Erfolgsstatuscode und die HTML-Ausgabe zurückgibt. Das funktioniert, ohne dass ein echter Webserver eingerichtet werden muss, und vermeidet deshalb einen Großteil der Fehleranfälligkeit, die bei einem echten Webserver auftreten kann (z.B. Probleme mit den Einstellungen der Firewall). Funktionstests, die für den TestServer ausgeführt werden, sind in der Regel langsamer als Integrations- und Komponententests, aber deutlich schneller als Tests, die über das Netzwerk auf einem Testwebserver ausgeführt werden. Sie sollten Funktionstests verwenden, um sicherzustellen, dass der Front-End-Stapel Ihrer Anwendung wie erwartet funktioniert. Diese Tests sind besonders hilfreich, wenn Sie Duplizierung in Ihren Controllern oder Seiten finden und Sie diese durch Hinzufügen von Filtern behandeln. Im Idealfall ändert dieses Refactoring nicht das Verhalten der Anwendung, und eine Reihe von Funktionstests überprüft, ob dies der Fall ist.

> ### <a name="references--test-aspnet-core-mvc-apps"></a>Ressourcen: Testen von ASP.NET Core MVC-Apps
>
> - **Testen in ASP.NET Core** \
>   <https://docs.microsoft.com/aspnet/core/testing/>
> - **Namenskonvention für Komponententests** \
>   <https://ardalis.com/unit-test-naming-convention>
> - **Testen von EF Core** \
>   <https://docs.microsoft.com/ef/core/miscellaneous/testing/>
> - **Integrationstests in ASP.NET Core** \
>   <https://docs.microsoft.com/aspnet/core/test/integration-tests>

>[!div class="step-by-step"]
>[Zurück](work-with-data-in-asp-net-core-apps.md)
>[Weiter](development-process-for-azure.md)

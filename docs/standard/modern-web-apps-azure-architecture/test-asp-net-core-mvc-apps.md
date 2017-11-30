---
title: Testen von ASP.NET Core MVC-Apps
description: Innovative Webanwendungen mit ASP.NET Core und Azure Architekt | Testen von ASP.NET Core MVC-Apps
author: ardalis
ms.author: wiwagn
ms.date: 10/08/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: 4611ffa8334e124946e849306d3281b695830eb1
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2017
---
# <a name="test-aspnet-core-mvc-apps"></a>Testen von ASP.NET Core MVC-Apps

> _"Wenn Sie Komponententests für das Produkt nicht mögen, wird nicht sehr wahrscheinlich Ihre Kunden möchten, entweder testen."_
> _ - Anonyme -

## <a name="summary"></a>Zusammenfassung

Software von beliebiger Komplexität kann auf unerwartete Weise als Reaktion auf Änderungen fehlschlagen. Daher ist die Tests nach Änderungen für alle Spalten mit Ausnahme der unbedeutendsten (oder am wenigsten wichtigen) Anwendungen erforderlich. Manuelle Tests ist der langsamste, mindestens zuverlässige Weise über die teuersten zum Testen von Software. Wenn Anwendungen nicht getestet werden können konzipiert wurden, kann es leider die einzige Möglichkeit, die verfügbar sein. Architekturprinzipien angeordnet, Folgendes in Kapitel X geschriebene Anwendungen sollten Einheit getestet werden können, und ASP.NET Core Anwendungen automatisierte Integration und Funktionstests ebenfalls unterstützt.

## <a name="kinds-of-automated-tests"></a>Arten von automatisierten Tests

Es gibt viele Arten von automatisierten Tests für softwareanwendungen. Die einfachste niedrigste Ebene Test hat den Komponententest. Auf einer etwas höheren Ebene sind bei der Integration und funktionale Tests vorhanden. Andere Arten von Tests, z. B. UI-Tests, Auslastungstests, Belastungstests und Feuerprobe durch sind nicht Gegenstand dieses Dokuments.

### <a name="unit-tests"></a>Komponententests

Ein Komponententest testet ein einzelnes Teil der Logik Ihrer Anwendung. Eine kann weitere beschreiben sie durch einige der Aufgaben, die dies nicht der Fall auflisten. Ein Komponententest Testen nicht, wie der Code funktioniert mit Abhängigkeiten oder Infrastruktur – welche Integrationstests sind. Ein Komponententest nicht die Framework-Code geschrieben wird, auf Testen – Sie davon ausgehen er funktioniert oder, wenn Sie es finden nicht, einen Fehler, und code dieses Problem zu umgehen. Ein Komponententest wird vollständig im Arbeitsspeicher und im Prozess ausgeführt. Es ist nicht mit dem Dateisystem, das Netzwerk oder eine Datenbank kommunizieren. Komponententests sollte nur den Code zu testen.

Komponententests, die aufgrund der Tatsache, dass sie nur eine einzelne Einheit des Codes, ohne externe Abhängigkeiten testen sollte äußerst schnell ausgeführt werden. Daher sollten Sie von Testsammlungen aus Hunderten von Komponententests in wenigen Sekunden ausführen können. Führen Sie sie häufig, idealerweise vor jeder Push eine freigegebene Quellcodeverwaltungs-Repository und sicherlich mit jedem Build automatisierte auf dem Buildserver.

### <a name="integration-tests"></a>Integrationstests

Zwar eine gute Idee, Code zu kapseln, der Interaktion mit Infrastrukturkomponenten, wie Datenbanken und Dateisysteme, noch müssen Teil des Codes, und Sie sollten es zu testen. Darüber hinaus sollten Sie sicherstellen, dass die Ebenen des Codes interagieren, wie Sie erwarten, wenn Ihre Anwendung Abhängigkeiten vollständig aufgelöst werden. Dies ist der Verantwortung des Integrationstests. Integrationstests tendenziell langsamer und schwieriger als Komponententests, die eingerichtet sein, da sie häufig externe Abhängigkeiten sowie Infrastruktur abhängig sind. Daher sollten Sie vermeiden, testen die Aufgaben aus, die Tests bei Komponententests in Integrationstests werden konnte. Wenn Sie ein bestimmtes Szenario mit einem Komponententest testen können, sollten Sie es mit einem Komponententest testen. Wenn Sie nicht möglich ist, sollten Sie einen Integrationstest verwenden.

Integrationstests müssen häufig komplexere Setup- und teardownvorgänge Prozeduren als Komponententests. Beispielsweise benötigen ein Integrationstest, der für eine tatsächliche Datenbank geht eine Möglichkeit zum Zurückgeben der Datenbank in einen bekannten Zustand vor jedem Test ausführen. Wenn neue Tests hinzugefügt werden, und das Datenbankschema Produktion weiterentwickelt, diese Tests Skripts erfolgen tendenziell in Größe und Komplexität wachsen. In zahlreiche großen Systemen ist es unpraktisch, vollständige Auflistungen von Integrationstests auf Entwicklerarbeitsstationen ausgeführt wird, vor dem Einchecken von Änderungen an den freigegebenen Datenquellen-Steuerelements. In diesen Fällen können die Integrationstests erfolgreich auf einem Build-Server ausgeführt werden.

Die Implementierungsklasse LocalFileImageService implementiert die Logik zum Abrufen und Zurückgeben einer Bilddatei Bytes aus einem bestimmten Ordner eine Id zugewiesen:

```cs
public class LocalFileImageService : IImageService
{
    private readonly IHostingEnvironment _env;
    public LocalFileImageService(IHostingEnvironment env)
    {
        _env = env;
    }
    public byte[] GetImageBytesById(int id)
    {
        try
        {
            var contentRoot = _env.ContentRootPath + "//Pics";
            var path = Path.Combine(contentRoot, id + ".png");
            return File.ReadAllBytes(path);
```

### <a name="functional-tests"></a>Funktionstests

Integrationstests werden geschrieben, aus der Perspektive des Entwicklers, um sicherzustellen, dass einige Komponenten des Systems ordnungsgemäß zusammenwirken. Funktionstests werden geschrieben, aus der Perspektive des Benutzers, und überprüfen die Richtigkeit des Systems basierend auf den Anforderungen. Der folgende Auszug bietet Analogie zum sind im Wesentlichen Funktionstests, im Vergleich zu Komponententests:

> "Oft die Entwicklung eines Systems ist auf die Erstellung eines Hauses Statusmodul vergleichbar. Während diese Analogie nicht ganz richtig ist, können wir ihn im Rahmen der Unterschied zwischen Einheit und Funktionstests erweitern. UnitTests erfolgt analog zur ein Erstellen von Inspektor ein Haus Konstruktion Website besuchen. Er konzentriert sich auf die verschiedenen internen Systemen des Hauses, die Grundlage, Abfassung, für die elektrische Sanitär- und usw.. Er stellt sicher, dass die Teile des Hauses werden voll funktionsfähig und sicher, d. h. das Erstellen von Code zu erfüllen (Tests). Funktionstests in diesem Szenario sind vergleichbar mit dem Hauseigentümer derselben Konstruktion Website besuchen. Er wird davon ausgegangen, dass die internen Systemen entsprechend verhält, dass das Erstellen von Inspektor seine Aufgabe ausgeführt wird. Die Hauseigentümer konzentriert sich darauf, was er z. B. in diesem Haus Gültigkeitsdauer kann. Er hat Bedenken hinsichtlich des Hauses wie sieht, sind die verschiedenen Räumen eine angenehme Größe und passt die House der Familie muss, sind die Fenster an eine gute Stelle zum Abfangen von Sun morgen. Die Hauseigentümer wird auf die House Funktionstests ausführen. Er verfügt über die Sicht des Benutzers. Erstellen von Inspektor ausführt Komponententests auf die House. Er verfügt über die Perspektive des."

Quelle: [Komponententests im Vergleich zu Funktionstests](http://www.softwaretestingtricks.com/2007/01/unit-testing-versus-functional-tests.html)

Ich bin sagen löschen "als Entwickler ein Fehler auf zwei Arten: Sie erstellen das, was falsche oder das falsche, was Sie erstellen." Komponententests stellen Sie sicher, dass Sie der Sache rechts erstellen; Funktionstests stellen Sie sicher, dass Sie das richtige erstellt werden.

Da Funktionstests auf Systemebene ausgeführt werden, können sie ein gewisses Maß an UI-Automatisierung verlangen. Wie Integrationstests arbeiten sie in der Regel mit irgendeine Testinfrastruktur ebenfalls. Dadurch sind sie langsamer und anfälliger als Einheit und Integration Tests. Sie müssen nur so viele Funktionstests, da Sie überzeugt ist das System verhält, als Benutzer erwarten, dass sein müssen.

### <a name="testing-pyramid"></a>Testen der Pyramide

Smell geschrieben wurde, zu der Tests Pyramide, ein die Beispiel für die in Abbildung 9 – 1 angezeigt wird.

![](./media/image9-1.png)

Abbildung 9 – 1 Pyramide testen

Die verschiedenen Ebenen der Pyramide und ihre relativen Größen darstellen, verschiedene Arten von Tests und wie viele für Ihre Anwendung geschrieben werden soll. Wie Sie sehen können, ist die Empfehlung eine große Basis von Komponententests, die durch eine kleinere Ebene von Integrationstests, mit dem eine noch kleinere Ebene der Funktionstests unterstützt. Jede Ebene sollte idealerweise nur Tests enthalten, die auf einer niedrigeren Ebene nicht ordnungsgemäß ausgeführt werden kann. Wenn Sie entscheiden, welche Art von Tests benötigen Sie für ein bestimmtes Szenario möchten, sollten Sie Bedenken der Pyramide testen.

### <a name="what-to-test"></a>Den Testgegenstand

Ein häufig auftretendes Problem für Entwickler, die für das Schreiben automatisierter Tests unerfahrenen stammt mit, was Sie testen. Ein guter Ausgangspunkt ist bedingten Logik zu testen. Eine beliebige Stelle stehen Ihnen eine Methode mit dem Verhalten, die Änderungen auf einer bedingten Anweisung basieren (If-else wechseln, usw.), Sie muss sich mindestens eine Reihe von Tests geschaltet wird, die das richtige Verhalten für bestimmte Bedingungen zu bestätigen. Wenn der Code fehlerbedingungen aufweist, ist es hilfreich, zumindest ein Test für die "zufriedene Path" durch den Code (mit keine Fehler) und mindestens ein Test für die "sad-Path" (mit Fehlern oder untypische Ergebnisse) zu schreiben, um zu bestätigen, dass Ihre Anwendung verhält sich wie erwartet bei Fehlern. Schließlich versucht, darauf konzentrieren, testen die Aufgaben aus, die ausgeführt werden können, statt die schwerpunktmäßige Darstellung Metriken wie Code Coverage. Weitere Code Coverage ist in der Regel kleiner, besser. Schreiben einer Methode sehr komplex und Ihre geschäftskritischen einige weitere Tests ist jedoch in der Regel eine bessere Verwendung von Zeit als das Schreiben von Tests für den Auto-Eigenschaften, um Tests Code Coverage Metriken zu verbessern.

## <a name="organizing-test-projects"></a>Organisieren von Projekten für Tests

Testprojekte können organisiert werden, jedoch für Sie am besten. Es ist eine gute Idee, trennen die Tests nach Typ (Komponententest, Integrationstest), und was sie (durch Projekt durch den Namespace) testen. Ob diese Trennung von Ordnern in einem einzelnen Testprojekt anlegen und mehrere Testprojekte besteht aus ist eine Entscheidung auf. Ein Projekt ist am einfachsten, allerdings bei großen Projekten mit vielen Tests oder um leichter verschiedene Gruppen von Tests ausführen, sollten Sie mehrere verschiedene Testprojekte haben. Viele Teams organisieren Testprojekte, die basierend auf das Projekt, das sie testen, das was für Anwendungen mit mehr als ein paar Projekte zu einer großen Anzahl von Testprojekte, führen kann, insbesondere dann, wenn Sie weiterhin diese Aufgliedern nach, welche Art von Tests in jedem Projekt sind. Ein Kompromiss-Ansatz ist, haben ein Projekt pro Art von Tests pro Anwendung, die Ordner in der Testprojekte, um die zu testenden Projekt (und -Klasse) anzugeben.

Eine gängige Methode ist die Anwendungsprojekte in einem Ordner "Src", und die Anwendung Testprojekte in einem parallelen "tests" Ordner zu organisieren. Sie können übereinstimmende Projektmappenordner in Visual Studio erstellen, wenn Sie diese Organisation nützlich sein.

![](./media/image9-2.png)

Abbildung 9-2-Test-Organisation in der Projektmappe

Sie können unabhängig davon, welche Testframework gewünscht. Das Framework xUnit gut funktioniert und was ist alle Tests ASP.NET Core und EF Core geschrieben werden. Sie können ein xUnit Testprojekt in Visual Studio mithilfe der Vorlage angezeigt, in Abbildung 9 – 3 oder über die CLI mit neuen Xunit Dotnet hinzufügen.

![](./media/image9-3.png)

Abbildung 9 – 3 hinzufügen ein xUnit Testprojekt in Visual Studio.

### <a name="test-naming"></a>Testen Sie die Benennung

Sie sollten die Tests auf konsistente Weise, mit Namen benennen, die angeben, was bewirkt, dass jeder Test. Ein Ansatz besteht darin, die erfolgreich waren werden Namen von Testklassen gemäß der Klasse und Methode, die sie testen möchten. Führt dies zu viele kleine Testklassen, allerdings vereinfacht extrem verdeutlichen, was jeder Test für zuständig ist. Mit dem Test-Klassennamen, der zum Identifizieren der Klasse und die zu testende Methode einrichten kann der Methodennamen für den Test verwendet werden, zum Festlegen des Verhaltens, das getestet wird. Dazu gehören das erwartete Verhalten und Eingaben oder Annahmen, die dieses Verhalten ergeben sollten. Einige Beispielnamen Test:

-   CatalogControllerGetImage.CallsImageServiceWithId

-   CatalogControllerGetImage.LogsWarningGivenImageMissingException

-   CatalogControllerGetImage.ReturnsFileResultWithBytesGivenSuccess

-   CatalogControllerGetImage.ReturnsNotFoundResultGivenImageMissingException

Eine Variante dieses Ansatzes endet jeder Test-Klassennamen in "Sollte" und die Zeitformen geringfügig geändert:

-   CatalogControllerGetImage**sollten**. **Rufen Sie**ImageServiceWithId

-   CatalogControllerGetImage**sollten**. **Protokoll**WarningGivenImageMissingException

Einige Teams finden naming Ansatz klarer, jedoch etwas ausführlicher. In jedem Fall verwenden Sie eine Benennungskonvention, die einen Einblick in das Verhalten von Testserver bereitstellt, wenn eine oder mehrere Tests fehlschlagen, aus deren Namen ersichtlich ist welchen Fällen fehlschlugen. Vermeiden Sie benennen Sie Tests vaguely, z. B. ControllerTests.Test1, da diese kein Wert bieten, wenn Sie sie in Testergebnisse finden Sie unter.

Wenn Sie eine Benennungskonvention befolgen, wie die gezeigte, die viele kleine Testklassen erzeugt, ist es eine gute Idee, um die Tests unter Verwendung von Ordnern und Namespaces anzuordnen. Abbildung 9 – 4 zeigt eine Möglichkeit zum Organisieren von Tests nach dem Ordner, in mehrere Testprojekte.

![](./media/image9-4.png)

**Abbildung 9 – 4.** Organisieren von Testklassen Ordner basierend auf der Klasse getestet wird.

Natürlich, wenn eine bestimmte Anwendung-Klasse verfügt über zahlreiche Methoden, die zu testenden (und daher viele Testklassen), kann es sich, platzieren Sie diese in einen Ordner für die Anwendungsklasse einzubinden. Diese Organisation ist, unterscheidet sich nicht, wie Sie Dateien in Ordnern an anderer Stelle organisieren können. Wenn Sie über mehr als drei oder vier Dateien in einem Ordner mit vielen anderen Dateien beziehen, ist es oft hilfreich, die sie in ihren eigenen Unterordner verschieben.

## <a name="unit-testing-aspnet-core-apps"></a>Einheit Testen von ASP.NET Core-Apps

In einer gut entworfenen ASP.NET Core-Anwendung wird ein Großteil der Komplexität und Geschäftslogik in Geschäftseinheiten und eine Vielzahl von Diensten gekapselt werden. Die ASP.NET Core MVC-app selbst mit seiner Controller, Filter, Viewmodels und Ansichten, müssen normalerweise nur sehr wenige Komponententests. Viele der Funktionen einer bestimmten Aktion liegt außerhalb der Aktionsmethode selbst. Testen, ob routing ordnungsgemäß funktioniert oder globalen Fehlerbehandlung, kann nicht mit einem Komponententest effektiv erfolgen. Ebenso alle, einschließlich modellvalidierung und Authentifizierung und Autorisierungsfilter, nicht mit Komponententests getestet. Ohne diese Quellen des Verhaltens sollte die meisten Aktionsmethoden Trivial "klein", delegieren den Großteil der Arbeit bei Diensten, die unabhängig von der Controller getestet werden können, die sie verwendet.

In einigen Fällen müssen Sie für die Umgestaltung in Code bestellen Komponententest. Dies umfasst das häufig Abstraktionen identifizieren und mithilfe der Abhängigkeitsinjektion zu die Abstraktion im Code zugreifen, die Sie testen möchten, anstatt direkt auf die Infrastruktur Codierung. Betrachten Sie beispielsweise diese einfache Aktion-Methode für das Anzeigen von Bildern aus:

```cs
[HttpGet("[controller]/pic/{id}")]
public IActionResult GetImage(int id)
{
    var contentRoot = _env.ContentRootPath + "//Pics";
    var path = Path.Combine(contentRoot, id + ".png");
    Byte[] b = System.IO.File.ReadAllBytes(path);
    return File(b, "image/png");
}
```

Komponententests, die diese Methode nur schwer von seiner direkte Abhängigkeit System.IO.File, erfolgt die verwendet wird, aus dem Dateisystem gelesen. Sie können dieses Verhalten, um sicherzustellen, dass sie erwartungsgemäß funktioniert, aber mit echten Dateien, die auf diese Weise wird ein Integrationstest testen. Beachten Sie können nicht testen diese Methode Route – sehen Sie, wie Sie dies in Kürze mit getestet durchführen.

Wenn Sie nicht direkt Komponententest das Systemverhalten für die Datei, und Sie können nicht die Route testen, besteht was testen? Auch nach der Umgestaltung um Komponententests zu ermöglichen, werden Sie möglicherweise einige Testfälle und fehlende Verhalten, z. B. Fehlerbehandlung feststellen. Wie funktioniert die Methode? Wenn Sie eine Datei nicht gefunden wird Was muss dabei vorgehen? In diesem Beispiel sieht die umgestaltete Methode:

```cs
[HttpGet("[controller]/pic/{id}")\]
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

Die \_Protokollierung und \_ImageService werden sowohl als Abhängigkeiten eingefügt. Nun können Sie testen, dass dieselbe Id, die an die Aktionsmethode übergeben wird, übergeben, wird die \_ImageService, und die resultierenden Bytes werden als Teil der FileResult zurückgegeben. Sie können auch testen, dass die Protokollierung von Anzeigefehlern wie erwartet erfolgt und ein NotFound Ergebnis zurückgegeben wird, wenn das Bild ist nicht vorhanden ist, vorausgesetzt, dass dies wichtig Anwendungsverhalten (d. h. nicht nur temporäre Code vom Entwickler hinzugefügt, um ein Problem zu diagnostizieren) ist. Die eigentliche Datei Logik in einem separaten Implementierung Dienst verschoben wurde, und wurde erweitert wurde, um eine anwendungsspezifische-Ausnahme für den Fall einer fehlenden Datei zurück. Sie können diese Implementierung unabhängig voneinander und testen, verwenden einen Integrationstest.

## <a name="integration-testing-aspnet-core-apps"></a>Integration Testen von ASP.NET Core-Apps

```cs
    }
        catch (FileNotFoundException ex)
        {
            throw new CatalogImageMissingException(ex);
        }
    }
}
```

Dieser Dienst verwendet die IHostingEnvironment ebenso wie der Code hat, bevor es in einem separaten Dienst umgestaltet wurde CatalogController. Da dies der einzige Code im Controller, die IHostingEnvironment verwendet wurde, wurde diese Abhängigkeit vom Konstruktor des CatalogController entfernt.

Um zu testen, dass dieser Dienst ordnungsgemäß funktioniert, müssen Sie eine bekannte Test Image erstellt, und stellen Sie sicher, dass der Dienst eine bestimmte Eingaben zurückgegeben. Sie sollten darauf achten nicht zur Verwendung von Pseudoobjekten auf das Verhalten, die Sie tatsächlich (in diesem Fall aus dem Dateisystem lesen) testen möchten. Pseudoobjekte sind jedoch immer noch nützlich zum Einrichten von Integrationstests möglicherweise. In diesem Fall können Sie IHostingEnvironment modellieren, damit seine ContentRootPath auf den Ordner verweist, die für die Test-Image verwendet werden sollen. Die vollständige arbeiten Integration Testklasse wird hier gezeigt:

```cs
public class LocalFileImageServiceGetImageBytesById
{
    private byte[] _testBytes = new byte[] { 0x01, 0x02, 0x03 };
    private readonly Mock<IHostingEnvironment> _mockEnvironment = new Mock<IHostingEnvironment>();
    private int _testImageId = 123;
    private string _testFileName = "123.png";
    public LocalFileImageServiceGetImageBytesById()
    {
        // create folder if necessary
        Directory.CreateDirectory(Path.Combine(GetFileDirectory(), "Pics"));
        string filePath = GetFilePath(_testFileName);
        System.IO.File.WriteAllBytes(filePath, _testBytes);
        _mockEnvironment.SetupGet<string>(m => m.ContentRootPath).Returns(GetFileDirectory());
    }
    private string GetFilePath(string fileName)
    {
        return Path.Combine(GetFileDirectory(), "Pics", fileName);
        }
            private string GetFileDirectory()
        {
            var location = System.Reflection.Assembly.GetEntryAssembly().Location;
            return Path.GetDirectoryName(location);
        }

        [Fact]
        public void ReturnsFileContentResultGivenValidId()
        {
            var fileService = new LocalFileImageService(_mockEnvironment.Object);
            var result = fileService.GetImageBytesById(_testImageId);
            Assert.Equal(_testBytes, result);
        }
    }
```

> [!NOTE]
> dass der Test selbst sehr einfache – ist ist der Großteil des Codes erforderlich, das System konfigurieren und Erstellen von der Testinfrastruktur (in diesem Fall kann eine tatsächliche Datei vom Datenträger gelesen werden). Dies ist typisch für Integrationstests, die häufig komplexen Setup als Komponententests in Anspruch nehmen.

## <a name="functional-testing-aspnet-core-apps"></a>Funktionale Testen von ASP.NET Core-Apps

Für ASP.NET Core-Anwendungen erleichtert die TestServer-Klasse Funktionstests relativ zum Schreiben. Sie konfigurieren einen TestServer verwenden eine WebHostBuilder, ebenso wie Sie normalerweise für Ihre Anwendung. Diese WebHostBuilder muss konfiguriert werden, wie Ihre echten Anwendungshost, aber Sie können ändern, dass alle Aspekte des Zertifikats, die testen vereinfachen. In den meisten Fällen, müssen Sie wiederverwenden der gleichen TestServer für viele Testfälle, damit Sie es in eine wiederverwendbare-Methode (möglicherweise in einer Basisklasse) kapseln können:

```cs
public abstract class BaseWebTest
{
    protected readonly HttpClient _client;
    protected string _contentRoot;

    public BaseWebTest()
    {
        _client = GetClient();
    }
    
    protected HttpClient GetClient()
    {
        var startupAssembly = typeof(Startup).GetTypeInfo().Assembly;
        _contentRoot = GetProjectPath("src", startupAssembly);
        var builder = new WebHostBuilder()
        .UseContentRoot(_contentRoot)
        .UseStartup&lt;Startup&gt;();
        var server = new TestServer(builder);
        var client = server.CreateClient();
        return client;
    }
}
```

GetProjectPath-Methode gibt einfach den physischen Pfad zum Webprojekt (Download-Beispielprojektmappe) zurück. Die WebHostBuilder gibt in diesem Fall einfach, wobei die Inhalte-Stamm für die Webanwendung und verweist auf die gleiche Startup-Klasse, die die echte Webanwendung verwendet. Um mit dem TestServer arbeiten, verwenden Sie der System.Net.HttpClient als Standardtyp, um Anforderungen zu stellen. TestServer macht eine hilfreiche CreateClient-Methode, die einen vorkonfigurierten Client, der bereitstellt für die Anforderungen an die Anwendung auf dem TestServer senden bereit ist. Verwenden Sie diesen Client (Legen Sie auf den geschützten \_Client-Element auf der Basis Test oben) beim Funktionstests für die ASP.NET Core-Anwendung zu schreiben:

```cs
public class CatalogControllerGetImage : BaseWebTest
{
    [Fact]
    public async Task ReturnsFileContentResultGivenValidId()
    {
        var testFilePath = Path.Combine(_contentRoot, "pics//1.png");
        var expectedFileBytes = File.ReadAllBytes(testFilePath);
        var response = await _client.GetAsync("/catalog/pic/1");
        response.EnsureSuccessStatusCode();
        var streamResponse = await response.Content.ReadAsStreamAsync();
        byte[] byteResult;
        using (var ms = new MemoryStream())
        {
            streamResponse.CopyTo(ms);
            byteResult = ms.ToArray();
        }
        Assert.Equal(expectedFileBytes, byteResult);
    }
}
```

Diese funktionale Tests ausführt, die vollständige Aufrufliste zur ASP.NET Core MVC-Anwendung, einschließlich aller Middleware, Filter, Bindern usw., die vorhanden sein können. Überprüft, ob eine angegebene Route ("/ Katalog/Pic/1") gibt das erwartete Bytearray für eine Datei an einem bekannten Speicherort. Es tut ohne einen echten Webserver einrichten zu müssen, und vermeidet also ein Großteil der unzulänglichen, bei denen unter Verwendung einer echten Server zum Testen (z. B. bei Problemen mit Firewalleinstellungen) auftreten kann. Funktionstests, die für den TestServer ausgeführt sind normalerweise langsamer als Integration und Komponententests, aber wesentlich schneller durchführt als Tests, die über das Netzwerk an einen Test-Webserver ausführen würden.

>[!div class="step-by-step"]
[Vorherigen] (Work-with-data-in-asp-net-core-apps.md) [weiter] (Development-Prozess-für-azure.md)

---
title: Testen von ASP.NET Core-Diensten und -Webanwendungen
description: .NET-Microservicearchitektur für .NET-Containeranwendungen | Übersicht über Architektur zum Testen von ASP.NET Core-Diensten und -Webanwendungen in Containern
ms.date: 01/13/2021
ms.openlocfilehash: dfd0a320491f92154bc9e2804d56c00120224e62
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98188002"
---
# <a name="testing-aspnet-core-services-and-web-apps"></a>Testen von ASP.NET Core-Diensten und -Webanwendungen

Controller sind ein zentraler Bestandteil jedes ASP.NET Core API-Diensts und jeder ASP.NET MVC-Webanwendung. Daher sollten Sie auch darauf vertrauen, dass sie in Ihrer Anwendung wie beabsichtigt funktionieren. Automatisierte Tests können Ihnen dieses Vertrauen vermitteln. Sie können zudem dabei helfen, Fehler aufzudecken, bevor diese die Produktion erreichen.

Sie müssen testen, wie der Controller sich auf Grundlage von gültigen bzw. ungültigen Eingaben verhält, und wie die Testcontroller abhängig vom Ergebnis des durchgeführten Geschäftsvorgangs antworten. Allerdings sollten Sie über diese Arten von Tests für Ihre Microservices verfügen:

- Komponententests. Diese Tests stellen sicher, dass die einzelnen Komponenten der Anwendung erwartungsgemäß funktionieren. Assertionstests für die Komponenten-API.

- Integrationstests. Diese Tests stellen sicher, dass die Komponenteninteraktionen für externe Elemente wie Datenbanken erwartungsgemäß funktionieren. Assertionen können Komponenten-APIs, Benutzeroberflächen oder die Nebeneffekte von Aktionen wie Datenbank-E/A, Protokollierung usw. testen.

- Funktionstests für jeden Microservice. Diese Tests stellen sicher, dass die Anwendung für Benutzer erwartungsgemäß funktioniert.

- Diensttests. Diese Tests stellen sicher, dass Anwendungsfälle für End-to-End-Dienste, einschließlich der Tests mehrerer Dienste gleichzeitig, überprüft werden. Für diese Art von Tests müssen Sie zunächst die Umgebung vorbereiten. In diesem Fall müssen die Dienste gestartet werden (z.B. mit dem Befehl „docker-compose up“).

### <a name="implementing-unit-tests-for-aspnet-core-web-apis"></a>Implementieren von Komponententests für ASP.NET Core-Web-APIs

Ein Komponententest beinhaltet das Testen einer Anwendungskomponente isoliert von ihrer Infrastruktur und ihren Abhängigkeiten. Bei einem Komponententest der Controllerlogik werden nur die Inhalte einer einzelnen Aktion oder Methode getestet, nicht das Verhalten ihrer Abhängigkeiten oder des Frameworks selbst. Komponententests erkennen keine Probleme bei der Interaktion zwischen den Komponenten. Dazu dienen Integrationstests.

Konzentrieren Sie sich bei der Durchführung eines Komponententests für Ihre Controlleraktionen daher nur auf deren Verhalten. Ein Controllerkomponententest vermeidet beispielsweise Filter, Routing oder Modellbindung, das ist die Zuordnung von Anforderungsdaten an ein ViewModel- oder Datentransferobjekt (DTO). Durch die Fokussierung auf nur einen Aspekt sind Komponententests in der Regel einfach zu schreiben und schnell in der Ausführung. Gut geschriebene Komponententests können häufig ohne großen Mehraufwand ausgeführt werden.

Komponententests werden basierend auf Testframeworks wie xUnit.net, MSTest, Moq oder NUnit implementiert. Für die Beispielanwendung eShopOnContainers wird xUnit verwendet.

Wenn Sie einen Komponententest für einen Web-API-Controller schreiben, instanziieren Sie die Controllerklasse, und verwenden Sie direkt das New-Schlüsselwort in C\#, damit der Test so schnell wie möglich ausgeführt wird. Im folgenden Beispiel wird gezeigt, wie dies unter Verwendung von [xUnit](https://xunit.net/) als Testframework erfolgt.

```csharp
[Fact]
public async Task Get_order_detail_success()
{
    //Arrange
    var fakeOrderId = "12";
    var fakeOrder = GetFakeOrder();

    //...

    //Act
    var orderController = new OrderController(
        _orderServiceMock.Object,
        _basketServiceMock.Object,
        _identityParserMock.Object);

    orderController.ControllerContext.HttpContext = _contextMock.Object;
    var actionResult = await orderController.Detail(fakeOrderId);

    //Assert
    var viewResult = Assert.IsType<ViewResult>(actionResult);
    Assert.IsAssignableFrom<Order>(viewResult.ViewData.Model);
}
```

### <a name="implementing-integration-and-functional-tests-for-each-microservice"></a>Implementieren der Integrations- und Funktionstests für jeden Microservice

Wie bereits erwähnt, haben Integrationstests und Funktionstests verschiedene Zwecke und Ziele. Allerdings ist die Implementierung der beiden beim Testen von ASP.NET Core-Controllern ähnlich. Aus diesem Grund konzentrieren wir uns in diesem Abschnitt auf Integrationstests.

Integrationstests stellen sicher, dass die Komponenten einer Anwendung ordnungsgemäß funktionieren, wenn sie zusammengestellt werden. ASP.NET Core unterstützt Integrationstests durch Komponententestframeworks und einen integrierten Testwebhost, der zur Verarbeitung von Anforderungen ohne Netzwerkmehraufwand verwendet werden kann.

Im Gegensatz zu Komponententests umfassen Integrationstests häufig Infrastrukturprobleme, z.B. eine Datenbank, ein Dateisystem, Netzwerkressourcen oder Webanforderungen und -antworten. Komponententests verwenden gefälschte oder Mockobjekte anstelle dieser Probleme. Aber der Zweck von Integrationstests ist die Bestätigung, dass das System mit diesen Systemen erwartungsgemäß funktioniert, damit Integrationstests keine gefälschten oder Mockobjekte verwenden müssen. Stattdessen können Sie die Infrastruktur einschließen, z.B. Datenbankzugriff oder Dienstaufruf von anderen Diensten.

Da Integrationstests größere Codesegmente ausführen als Komponententests, und da Integrationstests von Infrastrukturelementen abhängig sind, sind sie tendenziell erheblich langsamer als Komponententests. Daher ist es ratsam, die Anzahl der Integrationstests, die Sie schreiben und ausführen, zu beschränken.

ASP.NET Core bietet einen integrierten Testwebhost, der zum Verarbeiten von HTTP-Anforderungen ohne Netzwerkmehrbelastung verwendet werden kann. Dies bedeutet, dass Sie diese Tests schneller ausführen können als bei Verwendung eines echten Webhosts. Der Testwebhost (TestServer) ist als Microsoft.AspNetCore.TestHost in einer NuGet-Komponente verfügbar. Er kann zu den Integrationstestprojekten hinzugefügt und zum Hosten von ASP.NET Core-Anwendungen verwendet werden.

Wie Sie im folgenden Code sehen können, instanziieren Sie die Controller durch den Testhost, wenn Sie Integrationstest für ASP.NET Core-Controller erstellen. Diese Funktionalität ist mit einer HTTP-Anforderung vergleichbar, wird jedoch schneller ausgeführt.

```csharp
public class PrimeWebDefaultRequestShould
{
    private readonly TestServer _server;
    private readonly HttpClient _client;

    public PrimeWebDefaultRequestShould()
    {
        // Arrange
        _server = new TestServer(new WebHostBuilder()
           .UseStartup<Startup>());
           _client = _server.CreateClient();
    }

    [Fact]
    public async Task ReturnHelloWorld()
    {
        // Act
        var response = await _client.GetAsync("/");
        response.EnsureSuccessStatusCode();
        var responseString = await response.Content.ReadAsStringAsync();
        // Assert
        Assert.Equal("Hello World!", responseString);
    }
}
```

#### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Steve Smith. Testen von Controllern** (ASP.NET Core) \
    [https://docs.microsoft.com/aspnet/core/mvc/controllers/testing](/aspnet/core/mvc/controllers/testing)

- **Steve Smith. Integrationstests** (ASP.NET Core) \
    [https://docs.microsoft.com/aspnet/core/test/integration-tests](/aspnet/core/test/integration-tests)

- **Komponententests in .NET mit dotnet test** \
    [https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test](../../../core/testing/unit-testing-with-dotnet-test.md)

- **xUnit.net**. Offizielle Website. \
    <https://xunit.net/>

- **Grundlagen zum Komponententest** \
    [https://docs.microsoft.com/visualstudio/test/unit-test-basics](/visualstudio/test/unit-test-basics)

- **Moq**. GitHub-Repository. \
    <https://github.com/moq/moq>

- **NUnit**. Offizielle Website. \
    <https://nunit.org/>

### <a name="implementing-service-tests-on-a-multi-container-application"></a>Implementieren von Diensttests in einer Anwendung mit mehreren Containern

Wie bereits erwähnt: Wenn Sie Multicontaineranwendungen testen, müssen alle Microservices innerhalb des Docker-Hosts oder Containerclusters ausgeführt werden. End-to-End-Diensttests, die mehrere Vorgänge im Zusammenhang mit mehreren Microservices enthalten, erfordern die Bereitstellung und den Start der gesamten Anwendung im Docker-Host durch Ausführen des Befehls „docker-compose up“ (oder eines vergleichbaren Mechanismus bei Verwendung eines Orchestrators). Nachdem die gesamte Anwendung und alle zugehörigen Dienste ausgeführt werden, können Sie die End-to-End-Integration und Funktionstests ausführen.

Es gibt einige Ansätze, die Sie verwenden können. In der Datei „docker-compose.yml“, mit der Sie die Anwendung bereitstellen, können Sie auf Projektmappenebene den Eingangspunkt erweitern, um [dotnet test](../../../core/tools/dotnet-test.md) zu verwenden. Sie können auch eine andere Compose-Datei verwenden, die Ihre Tests im Image Ihrer Zielgruppe ausführen würde. Durch Verwendung einer anderen Compose-Datei für Integrationstests, die Ihre Microservices und Datenbanken für Container enthält, können Sie sicherstellen, dass die verwandten Daten vor dem Ausführen der Tests immer auf den ursprünglichen Zustand zurückgesetzt werden.

Sobald die Compose-Anwendung ausgeführt wird, können Sie Haltepunkte und Ausnahmen nutzen, wenn Sie Visual Studio ausführen. Alternativ können Sie die Integrationstests automatisch in der CI-Pipeline in Azure DevOps Services oder in jedem anderen CI/CD-System ausführen, das Docker-Container unterstützt.

## <a name="testing-in-eshoponcontainers"></a>Testen in eShopOnContainers

Die Tests der Referenzanwendung (eShopOnContainers) wurden kürzlich neu strukturiert. Nun gibt es vier Kategorien:

1. **Komponententests** sind simple alte reguläre Komponententests, die in **{MicroserviceName}.UnitTests**-Projekten enthalten sind.

2. **Funktions-/Integrationstests von Microservices** umfassen Testsituationen, die die Infrastruktur für jeden Microservice betreffen, aber voneinander isoliert und in **{MicroserviceName}.FunctionalTests**-Projekten enthalten sind.

3. **Funktions-/Integrationstests von Anwendungen** konzentrieren sich auf die Integration von Microservices und umfassen Testsituationen, die sich auf mehrere Microservices beziehen. Diese Tests befinden sich im **Anwendung.FunctionalTests**-Projekt.

Während Komponenten- und Integrationstests in einem Testordner innerhalb des Microserviceprojekts gespeichert werden, werden Anwendungs-und Auslastungstests wie in Abbildung 6-25 dargestellt separat unter dem Stammordner verwaltet.

![Screenshot von VS, das auf einige der Testprojekte in der Projektmappe verweist.](./media/test-aspnet-core-services-web-apps/eshoponcontainers-test-folder-structure.png)

**Abbildung 6-25**. Struktur des Testordners in eShopOnContainers

Funktions- und Integrationstests von Microservices und Anwendungen werden über Visual Studio mit dem regulären Test Runner ausgeführt. Zuerst müssen Sie allerdings die erforderlichen Infrastrukturdienste mithilfe der docker-compose-Dateien starten, die im Testordner der Projektmappe enthalten sind:

**docker-compose-test.yml**

```yml
version: '3.4'

services:
  redis.data:
    image: redis:alpine
  rabbitmq:
    image: rabbitmq:3-management-alpine
  sqldata:
    image: mcr.microsoft.com/mssql/server:2017-latest
  nosqldata:
    image: mongo
```

**docker-compose-test.override.yml**

```yml
version: '3.4'

services:
  redis.data:
    ports:
      - "6379:6379"
  rabbitmq:
    ports:
      - "15672:15672"
      - "5672:5672"
  sqldata:
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
  nosqldata:
    ports:
      - "27017:27017"
```

Zum Testen von Funktionen und Integrationen müssen Sie also zunächst diesen Befehl aus dem Testordner der Projektmappe ausführen:

```console
docker-compose -f docker-compose-test.yml -f docker-compose-test.override.yml up
```

Wie Sie sehen können, starten diese docker-compose-Dateien nur die Microservices Redis, RabbitMQ, SQL Server und MongoDB.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Komponenten- und Integrationstests** für eShopOnContainers\
    <https://github.com/dotnet-architecture/eShopOnContainers/wiki/Unit-and-integration-testing>

- **Auslastungstests** für eShopOnContainers\
    <https://github.com/dotnet-architecture/eShopOnContainers/wiki/Load-testing>

> [!div class="step-by-step"]
> [Zurück](subscribe-events.md)
> [Weiter](background-tasks-with-ihostedservice.md)

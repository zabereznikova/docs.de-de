---
title: Testen von ASP.NET Core-Diensten und -Webanwendungen
description: .NET Microservicesarchitektur für .NET-Containeranwendungen | Testen von ASP.NET Core-Diensten und -Webanwendungen
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.openlocfilehash: f7bd75ecdd85e49524ccdf67f3e59aa4be46bdce
ms.sourcegitcommit: 702d5ffc6e733b6c4ded85bf1c92e2293638ee9a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/04/2018
ms.locfileid: "37792412"
---
# <a name="testing-aspnet-core-services-and-web-apps"></a>Testen von ASP.NET Core-Diensten und -Webanwendungen

Controller sind ein zentraler Bestandteil jedes ASP.NET Core API-Diensts und jeder ASP.NET MVC-Webanwendung. Daher sollten Sie auch darauf vertrauen, dass sie in Ihrer Anwendung wie beabsichtigt funktionieren. Automatisierte Tests können Ihnen dieses Vertrauen vermitteln. Sie können zudem dabei helfen, Fehler aufzudecken, bevor diese die Produktion erreichen.

Sie müssen testen, wie der Controller sich auf Grundlage von gültigen bzw. ungültigen Eingaben verhält, und wie die Testcontroller abhängig vom Ergebnis des durchgeführten Geschäftsvorgangs antworten. Allerdings sollten Sie über diese Art von Tests in Ihren Microservices verfügen:

-   Komponententests. Diese stellen sicher, dass die einzelnen Komponenten der Anwendung erwartungsgemäß funktionieren. Assertionstests für die Komponenten-API.

-   Integrationstests. Diese stellen sicher, dass die Komponenteninteraktionen für externe Elemente wie beispielsweise Datenbanken erwartungsgemäß funktionieren. Assertionen können Komponenten-APIs, Benutzeroberflächen oder die Nebeneffekte von Aktionen wie Datenbank-E/A, Protokollierung usw. testen.

-   Funktionstests für jeden Microservice. Diese stellen sicher, dass die Anwendung aus Sicht des Benutzers erwartungsgemäß funktioniert.

-   Diensttests. Diese stellen sicher, dass Anwendungsfälle für End-to-End-Dienste, einschließlich der Tests mehrerer Dienste gleichzeitig, getestet werden. Für diese Art von Tests müssen Sie zunächst die Umgebung vorbereiten. In diesem Fall müssen die Dienste gestartet werden (z.B. mit dem Befehl „docker-compose up“).

### <a name="implementing-unit-tests-for-aspnet-core-web-apis"></a>Implementieren von Komponententests für ASP.NET Core-Web-APIs

Ein Komponententest beinhaltet das Testen einer Anwendungskomponente isoliert von ihrer Infrastruktur und ihren Abhängigkeiten. Bei einem Komponententest der Controllerlogik werden nur die Inhalte einer einzelnen Aktion oder Methode getestet, nicht das Verhalten ihrer Abhängigkeiten oder des Frameworks selbst. Komponententests erkennen keine Probleme bei der Interaktion zwischen den Komponenten. Dazu dienen Integrationstests.

Konzentrieren Sie sich bei der Durchführung eines Komponententests für Ihre Controlleraktionen daher nur auf deren Verhalten. Bei einem Komponententest des Controllers werden z.B. Filter, Routing oder Modellbindung vermieden. Durch die Fokussierung auf nur einen Aspekt sind Komponententests in der Regel einfach zu schreiben und schnell in der Ausführung. Gut geschriebene Komponententests können häufig ohne großen Mehraufwand ausgeführt werden.

Komponententests werden basierend auf Testframeworks wie xUnit.net, MSTest, Moq oder NUnit implementiert. Für die Beispielanwendung eShopOnContainers verwenden wir XUnit.

Wenn Sie einen Komponententest für einen Web-API-Controller schreiben, instanziieren Sie die Controllerklasse, und verwenden Sie direkt das New-Schlüsselwort in C\#, damit der Test so schnell wie möglich ausgeführt wird. Das folgende Beispiel zeigt die Vorgehensweise bei Verwendung von [XUnit](https://xunit.github.io/) als Testframework.

```csharp
[Fact]
public void Add_new_Order_raises_new_event()
{
    // Arrange
    var street = " FakeStreet ";
    var city = "FakeCity";
    // Other variables omitted for brevity ...
    // Act
    var fakeOrder = new Order(new Address(street, city, state, country, zipcode),
        cardTypeId, cardNumber,
        cardSecurityNumber, cardHolderName,
        cardExpiration);
    // Assert
    Assert.Equal(fakeOrder.DomainEvents.Count, expectedResult);
}
```

### <a name="implementing-integration-and-functional-tests-for-each-microservice"></a>Implementieren der Integrations- und Funktionstests für jeden Microservice

Wie bereits erwähnt, haben Integrationstests und Funktionstests verschiedene Zwecke und Ziele. Allerdings ist die Implementierung der beiden beim Testen von ASP.NET Core-Controllern ähnlich. Aus diesem Grund konzentrieren wir uns in diesem Abschnitt auf Integrationstests.

Integrationstests stellen sicher, dass die Komponenten einer Anwendung ordnungsgemäß funktionieren, wenn sie zusammengestellt werden. ASP.NET Core unterstützt Integrationstests durch Komponententestframeworks und einen integrierten Testwebhost, der zur Verarbeitung von Anforderungen ohne Netzwerkmehraufwand verwendet werden kann.

Im Gegensatz zu Komponententests umfassen Integrationstests häufig Infrastrukturprobleme, z.B. eine Datenbank, ein Dateisystem, Netzwerkressourcen oder Webanforderungen und -antworten. Komponententests verwenden gefälschte oder Mockobjekte anstelle dieser Probleme. Aber der Zweck von Integrationstests ist die Bestätigung, dass das System mit diesen Systemen erwartungsgemäß funktioniert, damit Integrationstests keine gefälschten oder Mockobjekte verwenden müssen. Stattdessen können Sie die Infrastruktur einschließen, z.B. Datenbankzugriff oder Dienstaufruf von anderen Diensten.

Da Integrationstests größere Codesegmente ausführen als Komponententests, und da Integrationstests von Infrastrukturelementen abhängig sind, sind sie tendenziell erheblich langsamer als Komponententests. Daher ist es ratsam, die Anzahl der Integrationstests, die Sie schreiben und ausführen, zu beschränken.

ASP.NET Core enthält einen integrierte Testwebhost, der zum Verarbeiten von HTTP-Anforderungen ohne Netzwerkmehraufwand verwendet werden kann. Dies bedeutet, dass Sie diese Tests schneller ausführen können als bei der Verwendung eines echten Webhosts. Der Testwebhost ist als Microsoft.AspNetCore.TestHost in einer NuGet-Komponenten verfügbar. Er kann zu den Integrationstestprojekten hinzugefügt und zum Hosten von ASP.NET Core-Anwendungen verwendet werden.

Wie Sie im folgenden Code sehen können, instanziieren Sie die Controller durch den Testhost, wenn Sie Integrationstest für ASP.NET Core-Controller erstellen. Dies ist vergleichbar mit einer HTTP-Anforderung, aber es wird schneller ausgeführt.

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

-   **Steve Smith. Testing controllers (Testen von Controllern)** (ASP.NET Core) [*https://docs.microsoft.com/aspnet/core/mvc/controllers/testing*](/aspnet/core/mvc/controllers/testing)

-   **Steve Smith. Integration testing (Integrationstests)** (ASP.NET Core) [*https://docs.microsoft.com/aspnet/core/test/integration-tests*](/aspnet/core/test/integration-tests)

-   **Unit testing in .NET Core using dotnet test (Komponententests in .NET Core mit dotnet-test)**
    [*https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test*](../../../core/testing/unit-testing-with-dotnet-test.md)

-   **xUnit.net**. Offizielle Website.
    [*https://xunit.github.io/*](https://xunit.github.io/)

-   **Unit Test Basics (Grundlagen zu Komponententests)**
    [*https://msdn.microsoft.com/library/hh694602.aspx*](https://msdn.microsoft.com/library/hh694602.aspx)

-   **Moq**. GitHub repo (Scrutor. GitHub-Reporitory).
    [*https://github.com/moq/moq*](https://github.com/moq/moq)

-   **NUnit**. Offizielle Website.
    [*https://www.nunit.org/*](https://www.nunit.org/)

### <a name="implementing-service-tests-on-a-multi-container-application"></a>Implementieren von Diensttests in einer Anwendung mit mehreren Containern 

Wie bereits erwähnt: Wenn Sie Multicontaineranwendungen testen, müssen alle Microservices innerhalb des Docker-Hosts oder Containerclusters ausgeführt werden. End-to-End-Diensttests, die mehrere Vorgänge im Zusammenhang mit mehreren Microservices enthalten, erfordern die Bereitstellung und den Start der gesamten Anwendung im Docker-Host durch Ausführen des Befehls „docker-compose up“ (oder eines vergleichbaren Mechanismus bei Verwendung eines Orchestrators). Nachdem die gesamte Anwendung und alle zugehörigen Dienste ausgeführt werden, können Sie die End-to-End-Integration und Funktionstests ausführen.

Es gibt einige Ansätze, die Sie verwenden können. In der Datei „Docker-compose.yml“, die Sie verwenden, um die Anwendung (oder ähnliche wie Docker-compose.ci.build.yml) bereitzustellen, können Sie auf Projektmappenebene den Eingangspunkt erweitern, um [dotnet test](../../../core/tools/dotnet-test.md) zu verwenden. Sie können auch eine andere Compose-Datei verwenden, die Ihre Tests im Image Ihrer Zielgruppe ausführen würde. Durch Verwendung einer anderen Compose-Datei für Integrationstests, die Ihre Microservices und Datenbanken für Container enthält, können Sie sicherstellen, dass die verwandten Daten vor dem Ausführen der Tests immer auf den ursprünglichen Zustand zurückgesetzt werden.

Sobald die Compose-Anwendung ausgeführt wird, können Sie Haltepunkte und Ausnahmen nutzen, wenn Sie Visual Studio ausführen. Oder Sie können die Integrationstests automatisch in der CI-Pipeline in Visual Studio Team Services oder in jedem anderen CI/CD-System ausführen, das Docker-Container unterstützt.

>[!div class="step-by-step"]
[Zurück](subscribe-events.md)
[Weiter](../microservice-ddd-cqrs-patterns/index.md)

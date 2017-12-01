---
title: Testen von ASP.NET Core Services und Web-apps
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Testen von ASP.NET Core Services und Web-apps"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f756a679befee676db2bf6d402fd7e34b1621b9d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="testing-aspnet-core-services-and-web-apps"></a>Testen von ASP.NET Core Services und Web-apps

Controller sind ein zentraler Bestandteil von ASP.NET Core API-Dienste und ASP.NET MVC-Webanwendung. Daher sollten Sie vertrauen verfügen, die sie für die Anwendung erwartungsgemäß Verhalten. Automatisierte Tests vermittelt Ihnen dieses Vertrauen und Fehler können erkannt werden, bevor sie die Produktion erreichen.

Sie müssen zu testen, wie die Controller basierend auf gültige bzw. ungültige Eingaben verhält, und Testen abhängig vom Ergebnis des Vorgangs Business ausgeführten Domänencontroller-Antworten. Allerdings sollten Sie diese Art von Tests der Microservices verfügen:

-   Komponententests. Diese Stellen Sie sicher, dass die einzelne Komponenten der Anwendung erwartungsgemäß arbeiten. Assertionen testen Sie die Komponente-API.

-   Integrationstests. Diese Stellen Sie sicher, dass die Komponenteninteraktionen erwartungsgemäß für externe Elemente wie beispielsweise Datenbanken. Assertionen können Komponenten-API, angezeigte Benutzeroberfläche oder die Nebeneffekte des Aktionen wie Datenbank-e/a, Protokollierung usw. testen.

-   Funktionstests für jede Microservice. Diese Stellen Sie sicher, dass die Anwendung erwartungsgemäß aus Sicht des Benutzers.

-   Testet. Diese Stellen Sie sicher, dass Anwendungsfälle für End-to-End-Dienst, einschließlich der Tests mehrere Dienste zur gleichen Zeit getestet werden. Für diese Art von Tests müssen Sie zunächst die Umgebung vorzubereiten. In diesem Fall daher starten die Dienste (z. B. mit Docker-verfassen oben).

### <a name="implementing-unit-tests-for-aspnet-core-web-apis"></a>Implementieren von Komponententests für ASP.NET Core Web-APIs

UnitTests umfasst einen Teil einer Anwendung unabhängig von der Infrastruktur und die Abhängigkeiten testen. Wenn Sie Komponententests für Controllerlogik, nur den Inhalt einer einzigen Aktion oder-Methode getestet wird, nicht das Verhalten der zugehörigen Abhängigkeiten oder Framework selbst. Komponententests nicht erkennen Probleme bei der Interaktion zwischen Komponenten – d. h. den Zweck von Integrationstests.

Testen Sie als Einheit Sie Ihre Controlleraktionen, stellen Sie sicher, dass Sie sich nur auf ihr Verhalten konzentrieren. Ein Komponententest Controller wird z. B. Filter, routing oder wurden die modellbindung vermieden. Da sie zum Testen von nur einem Schritt zu konzentrieren, sind Komponententests im Allgemeinen einfach zu schreiben und schnell ausgeführt. Ein gut geschriebener Satz von Komponententests kann ohne Mehraufwand häufig ausgeführt werden.

Komponententests werden basierend auf Testframeworks wie xUnit.net MSTest, Moq oder NUnit implementiert. Für die beispielanwendung eShopOnContainers verwenden XUnit.

Wenn Sie einen Komponententest für eine Web-API-Controller schreiben, instanziieren Sie die Controllerklasse, die direkt mit dem new-Schlüsselwort in C\#, damit der Test so schnell wie möglich ausgeführt wird. Das folgende Beispiel zeigt die Vorgehensweise bei Verwendung [XUnit](https://xunit.github.io/) als das Testframework.

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

### <a name="implementing-integration-and-functional-tests-for-each-microservice"></a>Implementieren der Integration und funktionale Tests für jede microservice

Wie bereits erwähnt, haben Integrationstests und Funktionstests, verschiedene Zwecke und Ziele. Allerdings ist die Möglichkeit, die beide beim Testen von ASP.NET Core Controller implementieren ähnlich, damit in diesem Abschnitt es Integrationstests konzentrieren können.

Integrationstests wird sichergestellt, dass eine Anwendung Komponenten ordnungsgemäß, wenn assembliert. ASP.NET Core unterstützt Integrationstests zu legen, mit der Komponententest-Frameworks und einem integrierten Test Webhost, der verwendet werden kann, um Mehraufwand von Netzwerk-Anforderungen zu verarbeiten.

Im Gegensatz zu Komponententests ausgeführt werden umfassen Integrationstests häufig Infrastruktur anwendungsaspekten, z. B. eine Datenbank, Dateisystem, Netzwerkressourcen, oder webanforderungen und-Antworten an. Komponententests mithilfe von Fakes oder Modellieren Objekte anstelle von diese Probleme. Aber Integrationstests zu bestätigen, dass das System erwartungsgemäß mit diesen Systemen funktioniert deshalb für Integrationstests für die Sie nicht mithilfe von Fakes oder Modellieren der Objekte dient. Stattdessen können Sie die Infrastruktur, z. B. Datenbank Zugriff oder Dienst der Aufruf von anderen Diensten.

Da Integrationstests größere Codesegmente als Komponententests Übung, und Integrationstests erfolgreich Infrastrukturelemente abhängig, tendenziell sie erheblich langsamer als Komponententests. Daher ist es eine gute Idee, wie viele Integrationstests zu beschränken, schreiben und ausführen.

ASP.NET Core enthält einen integrierte Test Webhost, der zum Verarbeiten von HTTP-Anforderungen ohne netzwerkmehraufwand verwendet werden kann dies bedeutet, dass Sie diese Tests schneller ausführen können, wenn mit einem echten Webhost. Der Test-Webhost ist als Microsoft.AspNetCore.TestHost in einer Komponente NuGet verfügbar. Diese Integration Testprojekte hinzugefügt werden kann und zum Hosten von ASP.NET Core Anwendungen verwendeten.

Wie Sie den folgenden Code Erstellung Integrationstests für ASP.NET Core Controller sehen können, die Controller über Testhost instanziiert werden. Dies ist vergleichbar mit einer HTTP-Anforderung, aber schneller ausgeführt.

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

-   **Steve Smith. Testen von Controllern** (ASP.NET Core) [ *https://docs.microsoft.com/aspnet/core/mvc/controllers/testing*](https://docs.microsoft.com/aspnet/core/mvc/controllers/testing)

-   **Steve Smith. Integrationstests** (ASP.NET Core) [ *https://docs.microsoft.com/aspnet/core/testing/integration-testing*](https://docs.microsoft.com/aspnet/core/testing/integration-testing)

-   **Komponententests in .NET Core-Dotnet-Test mit**
    [*https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test*](https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test)

-   **xUnit.net**. Offizielle Website.
    [*https://xUnit.github.IO/*](https://xunit.github.io/)

-   **Grundlagen zum Komponententest. ** 
     [ *https://msdn.microsoft.com/en-us/library/hh694602.aspx*](https://msdn.microsoft.com/en-us/library/hh694602.aspx)

-   **Moq**. GitHub-Repository.
    [*https://github.com/moq/moq*](https://github.com/moq/moq)

-   **NUnit**. Offizielle Website.
    [*https://www.NUnit.org/*](https://www.nunit.org/)

### <a name="implementing-service-tests-on-a-multi-container-application"></a>Für eine Anwendung mit mehreren Container implementierende diensttests 

Wie bereits erwähnt, wenn Sie Multi-containeranwendungen testen, müssen alle Microservices innerhalb des Docker-Host oder Container-Clusters ausgeführt werden. End-to-End diensttests, die mehrere Vorgänge im Zusammenhang mit mehreren Microservices enthalten erfordern Sie zum Bereitstellen und starten Sie die gesamte Anwendung in der Docker-Host, durch Ausführen von Docker-verfassen nach-oben (oder einen vergleichbaren Mechanismus bei Verwendung von ein Orchestrator). Nachdem die gesamte Anwendung und alle zugehörigen Dienste ausgeführt werden, können Sie die End-to-End-Integration und funktionale Tests ausführen.

Es gibt einige Ansätze, die Sie verwenden können. In der Docker-compose.yml-Datei, die Sie verwenden, um die Anwendung (oder ähnliche wie Docker compose.ci.build.yml) bereitstellen, auf Projektmappenebene können erweitern Sie den zu verwendenden Einstiegspunkt [Dotnet Test](https://docs.microsoft.com/dotnet/core/tools/dotnet-test). Sie können auch eine andere Compose-Datei, die in der Abbildung Ihrer Zielgruppe, die Tests ausführen müssen. Durch Verwendung einer anderen Compose-Datei Integrationstests, die die Microservices und die Datenbanken für Container enthält, können Sie sicherstellen, dass die verwandten Daten immer auf den ursprünglichen Zustand zurückgesetzt werden, vor dem Ausführen der Tests.

Sobald die Compose-Anwendung ausgeführt wird, können Sie Haltepunkte und Ausnahmen nutzen, wenn Sie Visual Studio ausgeführt werden. Oder Sie können die Integrationstests erfolgreich automatisch ausführen, in der CI-Pipeline in Visual Studio Team Services oder eines anderen Systems von CI-CD, das Docker-Containern unterstützt.

>[!div class="step-by-step"]
[Vorherigen] (Abonnieren-events.md) [weiter] (.. /microservice-ddd-CQRS-Patterns/Index.MD)

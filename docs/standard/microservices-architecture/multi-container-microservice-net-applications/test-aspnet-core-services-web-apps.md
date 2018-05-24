---
title: Testen von ASP.NET Core-Diensten und -Webanwendungen
description: .NET Microservicesarchitektur für .NET-Containeranwendungen | Testen von ASP.NET Core-Diensten und -Webanwendungen
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.openlocfilehash: b3aa0d50ba3ab64440ef51201d611177fea78ce4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="testing-aspnet-core-services-and-web-apps"></a><span data-ttu-id="22d0d-103">Testen von ASP.NET Core-Diensten und -Webanwendungen</span><span class="sxs-lookup"><span data-stu-id="22d0d-103">Testing ASP.NET Core services and web apps</span></span>

<span data-ttu-id="22d0d-104">Controller sind ein zentraler Bestandteil jedes ASP.NET Core API-Diensts und jeder ASP.NET MVC-Webanwendung.</span><span class="sxs-lookup"><span data-stu-id="22d0d-104">Controllers are a central part of any ASP.NET Core API service and ASP.NET MVC Web application.</span></span> <span data-ttu-id="22d0d-105">Daher sollten Sie auch darauf vertrauen, dass sie in Ihrer Anwendung wie beabsichtigt funktionieren.</span><span class="sxs-lookup"><span data-stu-id="22d0d-105">As such, you should have confidence they behave as intended for your application.</span></span> <span data-ttu-id="22d0d-106">Automatisierte Tests können Ihnen dieses Vertrauen vermitteln. Sie können zudem dabei helfen, Fehler aufzudecken, bevor diese die Produktion erreichen.</span><span class="sxs-lookup"><span data-stu-id="22d0d-106">Automated tests can provide you with this confidence and can detect errors before they reach production.</span></span>

<span data-ttu-id="22d0d-107">Sie müssen testen, wie der Controller sich auf Grundlage von gültigen bzw. ungültigen Eingaben verhält, und wie die Testcontroller abhängig vom Ergebnis des durchgeführten Geschäftsvorgangs antworten.</span><span class="sxs-lookup"><span data-stu-id="22d0d-107">You need to test how the controller behaves based on valid or invalid inputs, and test controller responses based on the result of the business operation it performs.</span></span> <span data-ttu-id="22d0d-108">Allerdings sollten Sie über diese Art von Tests in Ihren Microservices verfügen:</span><span class="sxs-lookup"><span data-stu-id="22d0d-108">However, you should have these types of tests your microservices:</span></span>

-   <span data-ttu-id="22d0d-109">Komponententests.</span><span class="sxs-lookup"><span data-stu-id="22d0d-109">Unit tests.</span></span> <span data-ttu-id="22d0d-110">Diese stellen sicher, dass die einzelnen Komponenten der Anwendung erwartungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="22d0d-110">These ensure that individual components of the application work as expected.</span></span> <span data-ttu-id="22d0d-111">Assertionstests für die Komponenten-API.</span><span class="sxs-lookup"><span data-stu-id="22d0d-111">Assertions test the component API.</span></span>

-   <span data-ttu-id="22d0d-112">Integrationstests.</span><span class="sxs-lookup"><span data-stu-id="22d0d-112">Integration tests.</span></span> <span data-ttu-id="22d0d-113">Diese stellen sicher, dass die Komponenteninteraktionen für externe Elemente wie beispielsweise Datenbanken erwartungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="22d0d-113">These ensure that component interactions work as expected against external artifacts like databases.</span></span> <span data-ttu-id="22d0d-114">Assertionen können Komponenten-APIs, Benutzeroberflächen oder die Nebeneffekte von Aktionen wie Datenbank-E/A, Protokollierung usw. testen.</span><span class="sxs-lookup"><span data-stu-id="22d0d-114">Assertions can test component API, UI, or the side effects of actions like database I/O, logging, etc.</span></span>

-   <span data-ttu-id="22d0d-115">Funktionstests für jeden Microservice.</span><span class="sxs-lookup"><span data-stu-id="22d0d-115">Functional tests for each microservice.</span></span> <span data-ttu-id="22d0d-116">Diese stellen sicher, dass die Anwendung aus Sicht des Benutzers erwartungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="22d0d-116">These ensure that the application works as expected from the user’s perspective.</span></span>

-   <span data-ttu-id="22d0d-117">Diensttests.</span><span class="sxs-lookup"><span data-stu-id="22d0d-117">Service tests.</span></span> <span data-ttu-id="22d0d-118">Diese stellen sicher, dass Anwendungsfälle für End-to-End-Dienste, einschließlich der Tests mehrerer Dienste gleichzeitig, getestet werden.</span><span class="sxs-lookup"><span data-stu-id="22d0d-118">These ensure that end-to-end service use cases, including testing multiple services at the same time, are tested.</span></span> <span data-ttu-id="22d0d-119">Für diese Art von Tests müssen Sie zunächst die Umgebung vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="22d0d-119">For this type of testing, you need to prepare the environment first.</span></span> <span data-ttu-id="22d0d-120">In diesem Fall müssen die Dienste gestartet werden (z.B. mit dem Befehl „docker-compose up“).</span><span class="sxs-lookup"><span data-stu-id="22d0d-120">In this case, it means starting the services (for example, by using docker-compose up).</span></span>

### <a name="implementing-unit-tests-for-aspnet-core-web-apis"></a><span data-ttu-id="22d0d-121">Implementieren von Komponententests für ASP.NET Core-Web-APIs</span><span class="sxs-lookup"><span data-stu-id="22d0d-121">Implementing unit tests for ASP.NET Core Web APIs</span></span>

<span data-ttu-id="22d0d-122">Ein Komponententest beinhaltet das Testen einer Anwendungskomponente isoliert von ihrer Infrastruktur und ihren Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="22d0d-122">Unit testing involves testing a part of an application in isolation from its infrastructure and dependencies.</span></span> <span data-ttu-id="22d0d-123">Bei einem Komponententest der Controllerlogik werden nur die Inhalte einer einzelnen Aktion oder Methode getestet, nicht das Verhalten ihrer Abhängigkeiten oder des Frameworks selbst.</span><span class="sxs-lookup"><span data-stu-id="22d0d-123">When you unit test controller logic, only the content of a single action or method is tested, not the behavior of its dependencies or of the framework itself.</span></span> <span data-ttu-id="22d0d-124">Komponententests erkennen keine Probleme bei der Interaktion zwischen den Komponenten. Dazu dienen Integrationstests.</span><span class="sxs-lookup"><span data-stu-id="22d0d-124">Unit tests do not detect issues in the interaction between components—that is the purpose of integration testing.</span></span>

<span data-ttu-id="22d0d-125">Konzentrieren Sie sich bei der Durchführung eines Komponententests für Ihre Controlleraktionen daher nur auf deren Verhalten.</span><span class="sxs-lookup"><span data-stu-id="22d0d-125">As you unit test your controller actions, make sure you focus only on their behavior.</span></span> <span data-ttu-id="22d0d-126">Bei einem Komponententest des Controllers werden z.B. Filter, Routing oder Modellbindung vermieden.</span><span class="sxs-lookup"><span data-stu-id="22d0d-126">A controller unit test avoids things like filters, routing, or model binding.</span></span> <span data-ttu-id="22d0d-127">Durch die Fokussierung auf nur einen Aspekt sind Komponententests in der Regel einfach zu schreiben und schnell in der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="22d0d-127">Because they focus on testing just one thing, unit tests are generally simple to write and quick to run.</span></span> <span data-ttu-id="22d0d-128">Gut geschriebene Komponententests können häufig ohne großen Mehraufwand ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="22d0d-128">A well-written set of unit tests can be run frequently without much overhead.</span></span>

<span data-ttu-id="22d0d-129">Komponententests werden basierend auf Testframeworks wie xUnit.net, MSTest, Moq oder NUnit implementiert.</span><span class="sxs-lookup"><span data-stu-id="22d0d-129">Unit tests are implemented based on test frameworks like xUnit.net, MSTest, Moq, or NUnit.</span></span> <span data-ttu-id="22d0d-130">Für die Beispielanwendung eShopOnContainers verwenden wir XUnit.</span><span class="sxs-lookup"><span data-stu-id="22d0d-130">For the eShopOnContainers sample application, we are using XUnit.</span></span>

<span data-ttu-id="22d0d-131">Wenn Sie einen Komponententest für einen Web-API-Controller schreiben, instanziieren Sie die Controllerklasse, und verwenden Sie direkt das New-Schlüsselwort in C\#, damit der Test so schnell wie möglich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="22d0d-131">When you write a unit test for a Web API controller, you instantiate the controller class directly using the new keyword in C\#, so that the test will run as fast as possible.</span></span> <span data-ttu-id="22d0d-132">Das folgende Beispiel zeigt die Vorgehensweise bei Verwendung von [XUnit](https://xunit.github.io/) als Testframework.</span><span class="sxs-lookup"><span data-stu-id="22d0d-132">The following example shows how to do this when using [XUnit](https://xunit.github.io/) as the Test framework.</span></span>

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

### <a name="implementing-integration-and-functional-tests-for-each-microservice"></a><span data-ttu-id="22d0d-133">Implementieren der Integrations- und Funktionstests für jeden Microservice</span><span class="sxs-lookup"><span data-stu-id="22d0d-133">Implementing integration and functional tests for each microservice</span></span>

<span data-ttu-id="22d0d-134">Wie bereits erwähnt, haben Integrationstests und Funktionstests verschiedene Zwecke und Ziele.</span><span class="sxs-lookup"><span data-stu-id="22d0d-134">As noted, integration tests and functional tests have different purposes and goals.</span></span> <span data-ttu-id="22d0d-135">Allerdings ist die Implementierung der beiden beim Testen von ASP.NET Core-Controllern ähnlich. Aus diesem Grund konzentrieren wir uns in diesem Abschnitt auf Integrationstests.</span><span class="sxs-lookup"><span data-stu-id="22d0d-135">However, the way you implement both when testing ASP.NET Core controllers is similar, so in this section we concentrate on integration tests.</span></span>

<span data-ttu-id="22d0d-136">Integrationstests stellen sicher, dass die Komponenten einer Anwendung ordnungsgemäß funktionieren, wenn sie zusammengestellt werden.</span><span class="sxs-lookup"><span data-stu-id="22d0d-136">Integration testing ensures that an application's components function correctly when assembled.</span></span> <span data-ttu-id="22d0d-137">ASP.NET Core unterstützt Integrationstests durch Komponententestframeworks und einen integrierten Testwebhost, der zur Verarbeitung von Anforderungen ohne Netzwerkmehraufwand verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="22d0d-137">ASP.NET Core supports integration testing using unit test frameworks and a built-in test web host that can be used to handle requests without network overhead.</span></span>

<span data-ttu-id="22d0d-138">Im Gegensatz zu Komponententests umfassen Integrationstests häufig Infrastrukturprobleme, z.B. eine Datenbank, ein Dateisystem, Netzwerkressourcen oder Webanforderungen und -antworten.</span><span class="sxs-lookup"><span data-stu-id="22d0d-138">Unlike unit testing, integration tests frequently involve application infrastructure concerns, such as a database, file system, network resources, or web requests and responses.</span></span> <span data-ttu-id="22d0d-139">Komponententests verwenden gefälschte oder Mockobjekte anstelle dieser Probleme.</span><span class="sxs-lookup"><span data-stu-id="22d0d-139">Unit tests use fakes or mock objects in place of these concerns.</span></span> <span data-ttu-id="22d0d-140">Aber der Zweck von Integrationstests ist die Bestätigung, dass das System mit diesen Systemen erwartungsgemäß funktioniert, damit Integrationstests keine gefälschten oder Mockobjekte verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="22d0d-140">But the purpose of integration tests is to confirm that the system works as expected with these systems, so for integration testing you do not use fakes or mock objects.</span></span> <span data-ttu-id="22d0d-141">Stattdessen können Sie die Infrastruktur einschließen, z.B. Datenbankzugriff oder Dienstaufruf von anderen Diensten.</span><span class="sxs-lookup"><span data-stu-id="22d0d-141">Instead, you include the infrastructure, like database access or service invocation from other services.</span></span>

<span data-ttu-id="22d0d-142">Da Integrationstests größere Codesegmente ausführen als Komponententests, und da Integrationstests von Infrastrukturelementen abhängig sind, sind sie tendenziell erheblich langsamer als Komponententests.</span><span class="sxs-lookup"><span data-stu-id="22d0d-142">Because integration tests exercise larger segments of code than unit tests, and because integration tests rely on infrastructure elements, they tend to be orders of magnitude slower than unit tests.</span></span> <span data-ttu-id="22d0d-143">Daher ist es ratsam, die Anzahl der Integrationstests, die Sie schreiben und ausführen, zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="22d0d-143">Thus, it is a good idea to limit how many integration tests you write and run.</span></span>

<span data-ttu-id="22d0d-144">ASP.NET Core enthält einen integrierte Testwebhost, der zum Verarbeiten von HTTP-Anforderungen ohne Netzwerkmehraufwand verwendet werden kann. Dies bedeutet, dass Sie diese Tests schneller ausführen können als bei der Verwendung eines echten Webhosts.</span><span class="sxs-lookup"><span data-stu-id="22d0d-144">ASP.NET Core includes a built-in test web host that can be used to handle HTTP requests without network overhead, meaning that you can run those tests faster when using a real web host.</span></span> <span data-ttu-id="22d0d-145">Der Testwebhost ist als Microsoft.AspNetCore.TestHost in einer NuGet-Komponenten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="22d0d-145">The test web host is available in a NuGet component as Microsoft.AspNetCore.TestHost.</span></span> <span data-ttu-id="22d0d-146">Er kann zu den Integrationstestprojekten hinzugefügt und zum Hosten von ASP.NET Core-Anwendungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="22d0d-146">It can be added to integration test projects and used to host ASP.NET Core applications.</span></span>

<span data-ttu-id="22d0d-147">Wie Sie im folgenden Code sehen können, instanziieren Sie die Controller durch den Testhost, wenn Sie Integrationstest für ASP.NET Core-Controller erstellen.</span><span class="sxs-lookup"><span data-stu-id="22d0d-147">As you can see in the following code, when you create integration tests for ASP.NET Core controllers, you instantiate the controllers through the test host.</span></span> <span data-ttu-id="22d0d-148">Dies ist vergleichbar mit einer HTTP-Anforderung, aber es wird schneller ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="22d0d-148">This is comparable to an HTTP request, but it runs faster.</span></span>

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

#### <a name="additional-resources"></a><span data-ttu-id="22d0d-149">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="22d0d-149">Additional resources</span></span>

-   <span data-ttu-id="22d0d-150">**Steve Smith. Testing controllers (Testen von Controllern)** (ASP.NET Core) [*https://docs.microsoft.com/aspnet/core/mvc/controllers/testing*](/aspnet/core/mvc/controllers/testing)</span><span class="sxs-lookup"><span data-stu-id="22d0d-150">**Steve Smith. Testing controllers** (ASP.NET Core) [*https://docs.microsoft.com/aspnet/core/mvc/controllers/testing*](/aspnet/core/mvc/controllers/testing)</span></span>

-   <span data-ttu-id="22d0d-151">**Steve Smith. Integration testing (Integrationstests)** (ASP.NET Core) [*https://docs.microsoft.com/aspnet/core/testing/integration-testing*](/aspnet/core/testing/integration-testing)</span><span class="sxs-lookup"><span data-stu-id="22d0d-151">**Steve Smith. Integration testing** (ASP.NET Core) [*https://docs.microsoft.com/aspnet/core/testing/integration-testing*](/aspnet/core/testing/integration-testing)</span></span>

-   <span data-ttu-id="22d0d-152">**Unit testing in .NET Core using dotnet test (Komponententests in .NET Core mit dotnet-test)**
    [*https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test*](../../../core/testing/unit-testing-with-dotnet-test.md)</span><span class="sxs-lookup"><span data-stu-id="22d0d-152">**Unit testing in .NET Core using dotnet test**
[*https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test*](../../../core/testing/unit-testing-with-dotnet-test.md)</span></span>

-   <span data-ttu-id="22d0d-153">**xUnit.net**.</span><span class="sxs-lookup"><span data-stu-id="22d0d-153">**xUnit.net**.</span></span> <span data-ttu-id="22d0d-154">Offizielle Website.</span><span class="sxs-lookup"><span data-stu-id="22d0d-154">Official site.</span></span>
    [*https://xunit.github.io/*](https://xunit.github.io/)

-   <span data-ttu-id="22d0d-155">**Unit Test Basics (Grundlagen zu Komponententests)**
    [*https://msdn.microsoft.com/library/hh694602.aspx*](https://msdn.microsoft.com/library/hh694602.aspx)</span><span class="sxs-lookup"><span data-stu-id="22d0d-155">**Unit Test Basics.**
[*https://msdn.microsoft.com/library/hh694602.aspx*](https://msdn.microsoft.com/library/hh694602.aspx)</span></span>

-   <span data-ttu-id="22d0d-156">**Moq**.</span><span class="sxs-lookup"><span data-stu-id="22d0d-156">**Moq**.</span></span> <span data-ttu-id="22d0d-157">GitHub repo (Scrutor. GitHub-Reporitory).</span><span class="sxs-lookup"><span data-stu-id="22d0d-157">GitHub repo.</span></span>
    [*https://github.com/moq/moq*](https://github.com/moq/moq)

-   <span data-ttu-id="22d0d-158">**NUnit**.</span><span class="sxs-lookup"><span data-stu-id="22d0d-158">**NUnit**.</span></span> <span data-ttu-id="22d0d-159">Offizielle Website.</span><span class="sxs-lookup"><span data-stu-id="22d0d-159">Official site.</span></span>
    [*https://www.nunit.org/*](https://www.nunit.org/)

### <a name="implementing-service-tests-on-a-multi-container-application"></a><span data-ttu-id="22d0d-160">Implementieren von Diensttests in einer Anwendung mit mehreren Containern</span><span class="sxs-lookup"><span data-stu-id="22d0d-160">Implementing service tests on a multi-container application</span></span> 

<span data-ttu-id="22d0d-161">Wie bereits erwähnt: Wenn Sie Multicontaineranwendungen testen, müssen alle Microservices innerhalb des Docker-Hosts oder Containerclusters ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="22d0d-161">As noted earlier, when you test multi-container applications, all the microservices need to be running within the Docker host or container cluster.</span></span> <span data-ttu-id="22d0d-162">End-to-End-Diensttests, die mehrere Vorgänge im Zusammenhang mit mehreren Microservices enthalten, erfordern die Bereitstellung und den Start der gesamten Anwendung im Docker-Host durch Ausführen des Befehls „docker-compose up“ (oder eines vergleichbaren Mechanismus bei Verwendung eines Orchestrators).</span><span class="sxs-lookup"><span data-stu-id="22d0d-162">End-to-end service tests that include multiple operations involving several microservices require you to deploy and start the whole application in the Docker host by running docker-compose up (or a comparable mechanism if you are using an orchestrator).</span></span> <span data-ttu-id="22d0d-163">Nachdem die gesamte Anwendung und alle zugehörigen Dienste ausgeführt werden, können Sie die End-to-End-Integration und Funktionstests ausführen.</span><span class="sxs-lookup"><span data-stu-id="22d0d-163">Once the whole application and all its services is running, you can execute end-to-end integration and functional tests.</span></span>

<span data-ttu-id="22d0d-164">Es gibt einige Ansätze, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="22d0d-164">There are a few approaches you can use.</span></span> <span data-ttu-id="22d0d-165">In der Datei „Docker-compose.yml“, die Sie verwenden, um die Anwendung (oder ähnliche wie Docker-compose.ci.build.yml) bereitzustellen, können Sie auf Projektmappenebene den Eingangspunkt erweitern, um [dotnet test](../../../core/tools/dotnet-test.md) zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="22d0d-165">In the docker-compose.yml file that you use to deploy the application (or similar ones, like docker-compose.ci.build.yml), at the solution level you can expand the entry point to use [dotnet test](../../../core/tools/dotnet-test.md).</span></span> <span data-ttu-id="22d0d-166">Sie können auch eine andere Compose-Datei verwenden, die Ihre Tests im Image Ihrer Zielgruppe ausführen würde.</span><span class="sxs-lookup"><span data-stu-id="22d0d-166">You can also use another compose file that would run your tests in the image you are targeting.</span></span> <span data-ttu-id="22d0d-167">Durch Verwendung einer anderen Compose-Datei für Integrationstests, die Ihre Microservices und Datenbanken für Container enthält, können Sie sicherstellen, dass die verwandten Daten vor dem Ausführen der Tests immer auf den ursprünglichen Zustand zurückgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="22d0d-167">By using another compose file for integration tests that includes your microservices and databases on containers, you can make sure that the related data is always reset to its original state before running the tests.</span></span>

<span data-ttu-id="22d0d-168">Sobald die Compose-Anwendung ausgeführt wird, können Sie Haltepunkte und Ausnahmen nutzen, wenn Sie Visual Studio ausführen.</span><span class="sxs-lookup"><span data-stu-id="22d0d-168">Once the compose application is up and running, you can take advantage of breakpoints and exceptions if you are running Visual Studio.</span></span> <span data-ttu-id="22d0d-169">Oder Sie können die Integrationstests automatisch in der CI-Pipeline in Visual Studio Team Services oder in jedem anderen CI/CD-System ausführen, das Docker-Container unterstützt.</span><span class="sxs-lookup"><span data-stu-id="22d0d-169">Or you can run the integration tests automatically in your CI pipeline in Visual Studio Team Services or any other CI/CD system that supports Docker containers.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="22d0d-170">[Zurück] (subscribe-events.md) [Weiter] (../microservice-ddd-cqrs-patterns/index.md)</span><span class="sxs-lookup"><span data-stu-id="22d0d-170">[Previous] (subscribe-events.md) [Next] (../microservice-ddd-cqrs-patterns/index.md)</span></span>

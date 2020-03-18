---
title: Testen von ASP.NET Core-Diensten und -Webanwendungen
description: .NET-Microservicearchitektur für .NET-Containeranwendungen | Übersicht über Architektur zum Testen von ASP.NET Core-Diensten und -Webanwendungen in Containern
ms.date: 01/30/2020
ms.openlocfilehash: ab3ae6276ea4e4c741731f050913d956046271ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77501989"
---
# <a name="testing-aspnet-core-services-and-web-apps"></a><span data-ttu-id="96a64-103">Testen von ASP.NET Core-Diensten und -Webanwendungen</span><span class="sxs-lookup"><span data-stu-id="96a64-103">Testing ASP.NET Core services and web apps</span></span>

<span data-ttu-id="96a64-104">Controller sind ein zentraler Bestandteil jedes ASP.NET Core API-Diensts und jeder ASP.NET MVC-Webanwendung.</span><span class="sxs-lookup"><span data-stu-id="96a64-104">Controllers are a central part of any ASP.NET Core API service and ASP.NET MVC Web application.</span></span> <span data-ttu-id="96a64-105">Daher sollten Sie auch darauf vertrauen, dass sie in Ihrer Anwendung wie beabsichtigt funktionieren.</span><span class="sxs-lookup"><span data-stu-id="96a64-105">As such, you should have confidence they behave as intended for your application.</span></span> <span data-ttu-id="96a64-106">Automatisierte Tests können Ihnen dieses Vertrauen vermitteln. Sie können zudem dabei helfen, Fehler aufzudecken, bevor diese die Produktion erreichen.</span><span class="sxs-lookup"><span data-stu-id="96a64-106">Automated tests can provide you with this confidence and can detect errors before they reach production.</span></span>

<span data-ttu-id="96a64-107">Sie müssen testen, wie der Controller sich auf Grundlage von gültigen bzw. ungültigen Eingaben verhält, und wie die Testcontroller abhängig vom Ergebnis des durchgeführten Geschäftsvorgangs antworten.</span><span class="sxs-lookup"><span data-stu-id="96a64-107">You need to test how the controller behaves based on valid or invalid inputs, and test controller responses based on the result of the business operation it performs.</span></span> <span data-ttu-id="96a64-108">Allerdings sollten Sie über diese Arten von Tests für Ihre Microservices verfügen:</span><span class="sxs-lookup"><span data-stu-id="96a64-108">However, you should have these types of tests for your microservices:</span></span>

- <span data-ttu-id="96a64-109">Komponententests.</span><span class="sxs-lookup"><span data-stu-id="96a64-109">Unit tests.</span></span> <span data-ttu-id="96a64-110">Diese stellen sicher, dass die einzelnen Komponenten der Anwendung erwartungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="96a64-110">These ensure that individual components of the application work as expected.</span></span> <span data-ttu-id="96a64-111">Assertionstests für die Komponenten-API.</span><span class="sxs-lookup"><span data-stu-id="96a64-111">Assertions test the component API.</span></span>

- <span data-ttu-id="96a64-112">Integrationstests.</span><span class="sxs-lookup"><span data-stu-id="96a64-112">Integration tests.</span></span> <span data-ttu-id="96a64-113">Diese stellen sicher, dass die Komponenteninteraktionen für externe Elemente wie beispielsweise Datenbanken erwartungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="96a64-113">These ensure that component interactions work as expected against external artifacts like databases.</span></span> <span data-ttu-id="96a64-114">Assertionen können Komponenten-APIs, Benutzeroberflächen oder die Nebeneffekte von Aktionen wie Datenbank-E/A, Protokollierung usw. testen.</span><span class="sxs-lookup"><span data-stu-id="96a64-114">Assertions can test component API, UI, or the side effects of actions like database I/O, logging, etc.</span></span>

- <span data-ttu-id="96a64-115">Funktionstests für jeden Microservice.</span><span class="sxs-lookup"><span data-stu-id="96a64-115">Functional tests for each microservice.</span></span> <span data-ttu-id="96a64-116">Diese stellen sicher, dass die Anwendung aus Sicht des Benutzers erwartungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="96a64-116">These ensure that the application works as expected from the user’s perspective.</span></span>

- <span data-ttu-id="96a64-117">Diensttests.</span><span class="sxs-lookup"><span data-stu-id="96a64-117">Service tests.</span></span> <span data-ttu-id="96a64-118">Diese stellen sicher, dass Anwendungsfälle für End-to-End-Dienste, einschließlich der Tests mehrerer Dienste gleichzeitig, getestet werden.</span><span class="sxs-lookup"><span data-stu-id="96a64-118">These ensure that end-to-end service use cases, including testing multiple services at the same time, are tested.</span></span> <span data-ttu-id="96a64-119">Für diese Art von Tests müssen Sie zunächst die Umgebung vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="96a64-119">For this type of testing, you need to prepare the environment first.</span></span> <span data-ttu-id="96a64-120">In diesem Fall müssen die Dienste gestartet werden (z.B. mit dem Befehl „docker-compose up“).</span><span class="sxs-lookup"><span data-stu-id="96a64-120">In this case, it means starting the services (for example, by using docker-compose up).</span></span>

### <a name="implementing-unit-tests-for-aspnet-core-web-apis"></a><span data-ttu-id="96a64-121">Implementieren von Komponententests für ASP.NET Core-Web-APIs</span><span class="sxs-lookup"><span data-stu-id="96a64-121">Implementing unit tests for ASP.NET Core Web APIs</span></span>

<span data-ttu-id="96a64-122">Ein Komponententest beinhaltet das Testen einer Anwendungskomponente isoliert von ihrer Infrastruktur und ihren Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="96a64-122">Unit testing involves testing a part of an application in isolation from its infrastructure and dependencies.</span></span> <span data-ttu-id="96a64-123">Bei einem Komponententest der Controllerlogik werden nur die Inhalte einer einzelnen Aktion oder Methode getestet, nicht das Verhalten ihrer Abhängigkeiten oder des Frameworks selbst.</span><span class="sxs-lookup"><span data-stu-id="96a64-123">When you unit test controller logic, only the content of a single action or method is tested, not the behavior of its dependencies or of the framework itself.</span></span> <span data-ttu-id="96a64-124">Komponententests erkennen keine Probleme bei der Interaktion zwischen den Komponenten. Dazu dienen Integrationstests.</span><span class="sxs-lookup"><span data-stu-id="96a64-124">Unit tests do not detect issues in the interaction between components—that is the purpose of integration testing.</span></span>

<span data-ttu-id="96a64-125">Konzentrieren Sie sich bei der Durchführung eines Komponententests für Ihre Controlleraktionen daher nur auf deren Verhalten.</span><span class="sxs-lookup"><span data-stu-id="96a64-125">As you unit test your controller actions, make sure you focus only on their behavior.</span></span> <span data-ttu-id="96a64-126">Ein Controllerkomponententest vermeidet beispielsweise Filter, Routing oder Modellbindung, das ist die Zuordnung von Anforderungsdaten an ein ViewModel- oder Datentransferobjekt (DTO).</span><span class="sxs-lookup"><span data-stu-id="96a64-126">A controller unit test avoids things like filters, routing, or model binding (the mapping of request data to a ViewModel or DTO).</span></span> <span data-ttu-id="96a64-127">Durch die Fokussierung auf nur einen Aspekt sind Komponententests in der Regel einfach zu schreiben und schnell in der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="96a64-127">Because they focus on testing just one thing, unit tests are generally simple to write and quick to run.</span></span> <span data-ttu-id="96a64-128">Gut geschriebene Komponententests können häufig ohne großen Mehraufwand ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="96a64-128">A well-written set of unit tests can be run frequently without much overhead.</span></span>

<span data-ttu-id="96a64-129">Komponententests werden basierend auf Testframeworks wie xUnit.net, MSTest, Moq oder NUnit implementiert.</span><span class="sxs-lookup"><span data-stu-id="96a64-129">Unit tests are implemented based on test frameworks like xUnit.net, MSTest, Moq, or NUnit.</span></span> <span data-ttu-id="96a64-130">Für die Beispielanwendung eShopOnContainers wird xUnit verwendet.</span><span class="sxs-lookup"><span data-stu-id="96a64-130">For the eShopOnContainers sample application, we are using xUnit.</span></span>

<span data-ttu-id="96a64-131">Wenn Sie einen Komponententest für einen Web-API-Controller schreiben, instanziieren Sie die Controllerklasse, und verwenden Sie direkt das New-Schlüsselwort in C\#, damit der Test so schnell wie möglich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="96a64-131">When you write a unit test for a Web API controller, you instantiate the controller class directly using the new keyword in C\#, so that the test will run as fast as possible.</span></span> <span data-ttu-id="96a64-132">Im folgenden Beispiel wird gezeigt, wie dies unter Verwendung von [xUnit](https://xunit.github.io/) als Testframework erfolgt.</span><span class="sxs-lookup"><span data-stu-id="96a64-132">The following example shows how to do this when using [xUnit](https://xunit.github.io/) as the Test framework.</span></span>

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

### <a name="implementing-integration-and-functional-tests-for-each-microservice"></a><span data-ttu-id="96a64-133">Implementieren der Integrations- und Funktionstests für jeden Microservice</span><span class="sxs-lookup"><span data-stu-id="96a64-133">Implementing integration and functional tests for each microservice</span></span>

<span data-ttu-id="96a64-134">Wie bereits erwähnt, haben Integrationstests und Funktionstests verschiedene Zwecke und Ziele.</span><span class="sxs-lookup"><span data-stu-id="96a64-134">As noted, integration tests and functional tests have different purposes and goals.</span></span> <span data-ttu-id="96a64-135">Allerdings ist die Implementierung der beiden beim Testen von ASP.NET Core-Controllern ähnlich. Aus diesem Grund konzentrieren wir uns in diesem Abschnitt auf Integrationstests.</span><span class="sxs-lookup"><span data-stu-id="96a64-135">However, the way you implement both when testing ASP.NET Core controllers is similar, so in this section we concentrate on integration tests.</span></span>

<span data-ttu-id="96a64-136">Integrationstests stellen sicher, dass die Komponenten einer Anwendung ordnungsgemäß funktionieren, wenn sie zusammengestellt werden.</span><span class="sxs-lookup"><span data-stu-id="96a64-136">Integration testing ensures that an application's components function correctly when assembled.</span></span> <span data-ttu-id="96a64-137">ASP.NET Core unterstützt Integrationstests durch Komponententestframeworks und einen integrierten Testwebhost, der zur Verarbeitung von Anforderungen ohne Netzwerkmehraufwand verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="96a64-137">ASP.NET Core supports integration testing using unit test frameworks and a built-in test web host that can be used to handle requests without network overhead.</span></span>

<span data-ttu-id="96a64-138">Im Gegensatz zu Komponententests umfassen Integrationstests häufig Infrastrukturprobleme, z.B. eine Datenbank, ein Dateisystem, Netzwerkressourcen oder Webanforderungen und -antworten.</span><span class="sxs-lookup"><span data-stu-id="96a64-138">Unlike unit testing, integration tests frequently involve application infrastructure concerns, such as a database, file system, network resources, or web requests and responses.</span></span> <span data-ttu-id="96a64-139">Komponententests verwenden gefälschte oder Mockobjekte anstelle dieser Probleme.</span><span class="sxs-lookup"><span data-stu-id="96a64-139">Unit tests use fakes or mock objects in place of these concerns.</span></span> <span data-ttu-id="96a64-140">Aber der Zweck von Integrationstests ist die Bestätigung, dass das System mit diesen Systemen erwartungsgemäß funktioniert, damit Integrationstests keine gefälschten oder Mockobjekte verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="96a64-140">But the purpose of integration tests is to confirm that the system works as expected with these systems, so for integration testing you do not use fakes or mock objects.</span></span> <span data-ttu-id="96a64-141">Stattdessen können Sie die Infrastruktur einschließen, z.B. Datenbankzugriff oder Dienstaufruf von anderen Diensten.</span><span class="sxs-lookup"><span data-stu-id="96a64-141">Instead, you include the infrastructure, like database access or service invocation from other services.</span></span>

<span data-ttu-id="96a64-142">Da Integrationstests größere Codesegmente ausführen als Komponententests, und da Integrationstests von Infrastrukturelementen abhängig sind, sind sie tendenziell erheblich langsamer als Komponententests.</span><span class="sxs-lookup"><span data-stu-id="96a64-142">Because integration tests exercise larger segments of code than unit tests, and because integration tests rely on infrastructure elements, they tend to be orders of magnitude slower than unit tests.</span></span> <span data-ttu-id="96a64-143">Daher ist es ratsam, die Anzahl der Integrationstests, die Sie schreiben und ausführen, zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="96a64-143">Thus, it is a good idea to limit how many integration tests you write and run.</span></span>

<span data-ttu-id="96a64-144">ASP.NET Core bietet einen integrierten Testwebhost, der zum Verarbeiten von HTTP-Anforderungen ohne Netzwerkmehrbelastung verwendet werden kann. Dies bedeutet, dass Sie diese Tests schneller ausführen können als bei Verwendung eines echten Webhosts.</span><span class="sxs-lookup"><span data-stu-id="96a64-144">ASP.NET Core includes a built-in test web host that can be used to handle HTTP requests without network overhead, meaning that you can run those tests faster than when using a real web host.</span></span> <span data-ttu-id="96a64-145">Der Testwebhost (TestServer) ist als Microsoft.AspNetCore.TestHost in einer NuGet-Komponente verfügbar.</span><span class="sxs-lookup"><span data-stu-id="96a64-145">The test web host (TestServer) is available in a NuGet component as Microsoft.AspNetCore.TestHost.</span></span> <span data-ttu-id="96a64-146">Er kann zu den Integrationstestprojekten hinzugefügt und zum Hosten von ASP.NET Core-Anwendungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="96a64-146">It can be added to integration test projects and used to host ASP.NET Core applications.</span></span>

<span data-ttu-id="96a64-147">Wie Sie im folgenden Code sehen können, instanziieren Sie die Controller durch den Testhost, wenn Sie Integrationstest für ASP.NET Core-Controller erstellen.</span><span class="sxs-lookup"><span data-stu-id="96a64-147">As you can see in the following code, when you create integration tests for ASP.NET Core controllers, you instantiate the controllers through the test host.</span></span> <span data-ttu-id="96a64-148">Dies ist vergleichbar mit einer HTTP-Anforderung, aber es wird schneller ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="96a64-148">This is comparable to an HTTP request, but it runs faster.</span></span>

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

#### <a name="additional-resources"></a><span data-ttu-id="96a64-149">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="96a64-149">Additional resources</span></span>

- <span data-ttu-id="96a64-150">**Steve Smith. Testen von Controllern** (ASP.NET Core) </span><span class="sxs-lookup"><span data-stu-id="96a64-150">**Steve Smith. Testing controllers** (ASP.NET Core) </span></span>\
    [https://docs.microsoft.com/aspnet/core/mvc/controllers/testing](/aspnet/core/mvc/controllers/testing)

- <span data-ttu-id="96a64-151">**Steve Smith. Integrationstests** (ASP.NET Core) </span><span class="sxs-lookup"><span data-stu-id="96a64-151">**Steve Smith. Integration testing** (ASP.NET Core) </span></span>\
    [https://docs.microsoft.com/aspnet/core/test/integration-tests](/aspnet/core/test/integration-tests)

- <span data-ttu-id="96a64-152">**Komponententests in .NET Core mit dotnet test** </span><span class="sxs-lookup"><span data-stu-id="96a64-152">**Unit testing in .NET Core using dotnet test** </span></span>\
    [https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test](../../../core/testing/unit-testing-with-dotnet-test.md)

- <span data-ttu-id="96a64-153">**xUnit.net**.</span><span class="sxs-lookup"><span data-stu-id="96a64-153">**xUnit.net**.</span></span> <span data-ttu-id="96a64-154">Offizielle Website.</span><span class="sxs-lookup"><span data-stu-id="96a64-154">Official site.</span></span> \
    <https://xunit.github.io/>

- <span data-ttu-id="96a64-155">**Grundlagen zum Komponententest**</span><span class="sxs-lookup"><span data-stu-id="96a64-155">**Unit Test Basics.**</span></span> \
    [https://docs.microsoft.com/visualstudio/test/unit-test-basics](/visualstudio/test/unit-test-basics)

- <span data-ttu-id="96a64-156">**Moq**.</span><span class="sxs-lookup"><span data-stu-id="96a64-156">**Moq**.</span></span> <span data-ttu-id="96a64-157">GitHub-Repository.</span><span class="sxs-lookup"><span data-stu-id="96a64-157">GitHub repo.</span></span> \
    <https://github.com/moq/moq>

- <span data-ttu-id="96a64-158">**NUnit**.</span><span class="sxs-lookup"><span data-stu-id="96a64-158">**NUnit**.</span></span> <span data-ttu-id="96a64-159">Offizielle Website.</span><span class="sxs-lookup"><span data-stu-id="96a64-159">Official site.</span></span> \
    <https://www.nunit.org/>

### <a name="implementing-service-tests-on-a-multi-container-application"></a><span data-ttu-id="96a64-160">Implementieren von Diensttests in einer Anwendung mit mehreren Containern</span><span class="sxs-lookup"><span data-stu-id="96a64-160">Implementing service tests on a multi-container application</span></span>

<span data-ttu-id="96a64-161">Wie bereits erwähnt: Wenn Sie Multicontaineranwendungen testen, müssen alle Microservices innerhalb des Docker-Hosts oder Containerclusters ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="96a64-161">As noted earlier, when you test multi-container applications, all the microservices need to be running within the Docker host or container cluster.</span></span> <span data-ttu-id="96a64-162">End-to-End-Diensttests, die mehrere Vorgänge im Zusammenhang mit mehreren Microservices enthalten, erfordern die Bereitstellung und den Start der gesamten Anwendung im Docker-Host durch Ausführen des Befehls „docker-compose up“ (oder eines vergleichbaren Mechanismus bei Verwendung eines Orchestrators).</span><span class="sxs-lookup"><span data-stu-id="96a64-162">End-to-end service tests that include multiple operations involving several microservices require you to deploy and start the whole application in the Docker host by running docker-compose up (or a comparable mechanism if you are using an orchestrator).</span></span> <span data-ttu-id="96a64-163">Nachdem die gesamte Anwendung und alle zugehörigen Dienste ausgeführt werden, können Sie die End-to-End-Integration und Funktionstests ausführen.</span><span class="sxs-lookup"><span data-stu-id="96a64-163">Once the whole application and all its services is running, you can execute end-to-end integration and functional tests.</span></span>

<span data-ttu-id="96a64-164">Es gibt einige Ansätze, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="96a64-164">There are a few approaches you can use.</span></span> <span data-ttu-id="96a64-165">In der Datei „docker-compose.yml“, mit der Sie die Anwendung bereitstellen, können Sie auf Projektmappenebene den Eingangspunkt erweitern, um [dotnet test](../../../core/tools/dotnet-test.md) zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="96a64-165">In the docker-compose.yml file that you use to deploy the application at the solution level you can expand the entry point to use [dotnet test](../../../core/tools/dotnet-test.md).</span></span> <span data-ttu-id="96a64-166">Sie können auch eine andere Compose-Datei verwenden, die Ihre Tests im Image Ihrer Zielgruppe ausführen würde.</span><span class="sxs-lookup"><span data-stu-id="96a64-166">You can also use another compose file that would run your tests in the image you are targeting.</span></span> <span data-ttu-id="96a64-167">Durch Verwendung einer anderen Compose-Datei für Integrationstests, die Ihre Microservices und Datenbanken für Container enthält, können Sie sicherstellen, dass die verwandten Daten vor dem Ausführen der Tests immer auf den ursprünglichen Zustand zurückgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="96a64-167">By using another compose file for integration tests that includes your microservices and databases on containers, you can make sure that the related data is always reset to its original state before running the tests.</span></span>

<span data-ttu-id="96a64-168">Sobald die Compose-Anwendung ausgeführt wird, können Sie Haltepunkte und Ausnahmen nutzen, wenn Sie Visual Studio ausführen.</span><span class="sxs-lookup"><span data-stu-id="96a64-168">Once the compose application is up and running, you can take advantage of breakpoints and exceptions if you are running Visual Studio.</span></span> <span data-ttu-id="96a64-169">Alternativ können Sie die Integrationstests automatisch in der CI-Pipeline in Azure DevOps Services oder in jedem anderen CI/CD-System ausführen, das Docker-Container unterstützt.</span><span class="sxs-lookup"><span data-stu-id="96a64-169">Or you can run the integration tests automatically in your CI pipeline in Azure DevOps Services or any other CI/CD system that supports Docker containers.</span></span>

## <a name="testing-in-eshoponcontainers"></a><span data-ttu-id="96a64-170">Testen in eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="96a64-170">Testing in eShopOnContainers</span></span>

<span data-ttu-id="96a64-171">Die Tests der Referenzanwendung (eShopOnContainers) wurden kürzlich neu strukturiert. Nun gibt es vier Kategorien:</span><span class="sxs-lookup"><span data-stu-id="96a64-171">The reference application (eShopOnContainers) tests were recently restructured and now there are four categories:</span></span>

1. <span data-ttu-id="96a64-172">**Komponententests** sind simple alte reguläre Komponententests, die in **{MicroserviceName}.UnitTests**-Projekten enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="96a64-172">**Unit** tests, just plain old regular unit tests, contained in the **{MicroserviceName}.UnitTests** projects</span></span>

2. <span data-ttu-id="96a64-173">**Funktions-/Integrationstests von Microservices** umfassen Testsituationen, die die Infrastruktur für jeden Microservice betreffen, aber voneinander isoliert und in **{MicroserviceName}.FunctionalTests**-Projekten enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="96a64-173">**Microservice functional/integration tests**, with test cases involving the infrastructure for each microservice but isolated from the others and are contained in the **{MicroserviceName}.FunctionalTests** projects.</span></span>

3. <span data-ttu-id="96a64-174">**Funktions-/Integrationstests von Anwendungen** konzentrieren sich auf die Integration von Microservices und umfassen Testsituationen, die sich auf mehrere Microservices beziehen.</span><span class="sxs-lookup"><span data-stu-id="96a64-174">**Application functional/integration tests**, which focus on microservices integration, with test cases that exert several microservices.</span></span> <span data-ttu-id="96a64-175">Diese Tests befinden sich im **Anwendung.FunctionalTests**-Projekt.</span><span class="sxs-lookup"><span data-stu-id="96a64-175">These tests are located in project **Application.FunctionalTests**.</span></span>

<span data-ttu-id="96a64-176">Komponenten- und Integrationstest pro Microservice sind in jedem Microservice in einem Testordner enthalten. Anwendungs- und Auslastungstests befinden sich im Testordner des Projektmappenordners (s. Abbildung 6-25).</span><span class="sxs-lookup"><span data-stu-id="96a64-176">Unit and integration test per microservice are contained in a test folder in each microservice and Application a Load tests are contained under the test folder in the solution folder, as shown in Figure 6-25.</span></span>

![Screenshot von VS, das auf einige der Testprojekte in der Projektmappe verweist.](./media/test-aspnet-core-services-web-apps/eshoponcontainers-test-folder-structure.png)

<span data-ttu-id="96a64-178">**Abbildung 6-25**.</span><span class="sxs-lookup"><span data-stu-id="96a64-178">**Figure 6-25**.</span></span> <span data-ttu-id="96a64-179">Struktur des Testordners in eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="96a64-179">Test folder structure in eShopOnContainers</span></span>

<span data-ttu-id="96a64-180">Funktions- und Integrationstests von Microservices und Anwendungen werden über Visual Studio mit dem regulären Test Runner ausgeführt. Zuerst müssen Sie allerdings die erforderlichen Infrastrukturdienste mithilfe einer Gruppe von „docker-compose“-Dateien starten, die im Testordner der Projektmappe enthalten sind:</span><span class="sxs-lookup"><span data-stu-id="96a64-180">Microservice and Application functional/integration tests are run from Visual Studio, using the regular tests runner, but first you need to start the required infrastructure services, by means of a set of docker-compose files contained in the solution test folder:</span></span>

<span data-ttu-id="96a64-181">**docker-compose-test.yml**</span><span class="sxs-lookup"><span data-stu-id="96a64-181">**docker-compose-test.yml**</span></span>

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

<span data-ttu-id="96a64-182">**docker-compose-test.override.yml**</span><span class="sxs-lookup"><span data-stu-id="96a64-182">**docker-compose-test.override.yml**</span></span>

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

<span data-ttu-id="96a64-183">Zum Testen von Funktionen und Integrationen müssen Sie also zunächst diesen Befehl aus dem Testordner der Projektmappe ausführen:</span><span class="sxs-lookup"><span data-stu-id="96a64-183">So, to run the functional/integration tests you must first run this command, from the solution test folder:</span></span>

```console
docker-compose -f docker-compose-test.yml -f docker-compose-test.override.yml up
```

<span data-ttu-id="96a64-184">Wie Sie sehen können, starten diese „docker-compose“-Dateien nur die Microservices Redis, RabbitMQ, SQL Server und MongoDB.</span><span class="sxs-lookup"><span data-stu-id="96a64-184">As you can see, these docker-compose files only start the Redis, RabbitMQ, SQL Server and MongoDB microservices.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="96a64-185">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="96a64-185">Additional resources</span></span>

- <span data-ttu-id="96a64-186">**Infodatei für Tests** im GitHub-Repository „eShopOnContainers“ </span><span class="sxs-lookup"><span data-stu-id="96a64-186">**Tests README file** on the eShopOnContainers repo on GitHub </span></span>\
    <https://github.com/dotnet-architecture/eShopOnContainers/tree/dev/test>

- <span data-ttu-id="96a64-187">**Infodatei für Auslastungstests** im GitHub-Repository „eShopOnContainers“ </span><span class="sxs-lookup"><span data-stu-id="96a64-187">**Load tests README file** on the eShopOnContainers repo on GitHub </span></span>\
    <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/test/ServicesTests/LoadTest/>

> [!div class="step-by-step"]
> <span data-ttu-id="96a64-188">[Zurück](subscribe-events.md)
> [Weiter](background-tasks-with-ihostedservice.md)</span><span class="sxs-lookup"><span data-stu-id="96a64-188">[Previous](subscribe-events.md)
[Next](background-tasks-with-ihostedservice.md)</span></span>

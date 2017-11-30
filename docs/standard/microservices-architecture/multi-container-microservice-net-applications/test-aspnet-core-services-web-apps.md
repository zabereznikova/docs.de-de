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
# <a name="testing-aspnet-core-services-and-web-apps"></a><span data-ttu-id="f68f7-104">Testen von ASP.NET Core Services und Web-apps</span><span class="sxs-lookup"><span data-stu-id="f68f7-104">Testing ASP.NET Core services and web apps</span></span>

<span data-ttu-id="f68f7-105">Controller sind ein zentraler Bestandteil von ASP.NET Core API-Dienste und ASP.NET MVC-Webanwendung.</span><span class="sxs-lookup"><span data-stu-id="f68f7-105">Controllers are a central part of any ASP.NET Core API service and ASP.NET MVC Web application.</span></span> <span data-ttu-id="f68f7-106">Daher sollten Sie vertrauen verfügen, die sie für die Anwendung erwartungsgemäß Verhalten.</span><span class="sxs-lookup"><span data-stu-id="f68f7-106">As such, you should have confidence they behave as intended for your application.</span></span> <span data-ttu-id="f68f7-107">Automatisierte Tests vermittelt Ihnen dieses Vertrauen und Fehler können erkannt werden, bevor sie die Produktion erreichen.</span><span class="sxs-lookup"><span data-stu-id="f68f7-107">Automated tests can provide you with this confidence and can detect errors before they reach production.</span></span>

<span data-ttu-id="f68f7-108">Sie müssen zu testen, wie die Controller basierend auf gültige bzw. ungültige Eingaben verhält, und Testen abhängig vom Ergebnis des Vorgangs Business ausgeführten Domänencontroller-Antworten.</span><span class="sxs-lookup"><span data-stu-id="f68f7-108">You need to test how the controller behaves based on valid or invalid inputs, and test controller responses based on the result of the business operation it performs.</span></span> <span data-ttu-id="f68f7-109">Allerdings sollten Sie diese Art von Tests der Microservices verfügen:</span><span class="sxs-lookup"><span data-stu-id="f68f7-109">However, you should have these types of tests your microservices:</span></span>

-   <span data-ttu-id="f68f7-110">Komponententests.</span><span class="sxs-lookup"><span data-stu-id="f68f7-110">Unit tests.</span></span> <span data-ttu-id="f68f7-111">Diese Stellen Sie sicher, dass die einzelne Komponenten der Anwendung erwartungsgemäß arbeiten.</span><span class="sxs-lookup"><span data-stu-id="f68f7-111">These ensure that individual components of the application work as expected.</span></span> <span data-ttu-id="f68f7-112">Assertionen testen Sie die Komponente-API.</span><span class="sxs-lookup"><span data-stu-id="f68f7-112">Assertions test the component API.</span></span>

-   <span data-ttu-id="f68f7-113">Integrationstests.</span><span class="sxs-lookup"><span data-stu-id="f68f7-113">Integration tests.</span></span> <span data-ttu-id="f68f7-114">Diese Stellen Sie sicher, dass die Komponenteninteraktionen erwartungsgemäß für externe Elemente wie beispielsweise Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="f68f7-114">These ensure that component interactions work as expected against external artifacts like databases.</span></span> <span data-ttu-id="f68f7-115">Assertionen können Komponenten-API, angezeigte Benutzeroberfläche oder die Nebeneffekte des Aktionen wie Datenbank-e/a, Protokollierung usw. testen.</span><span class="sxs-lookup"><span data-stu-id="f68f7-115">Assertions can test component API, UI, or the side effects of actions like database I/O, logging, etc.</span></span>

-   <span data-ttu-id="f68f7-116">Funktionstests für jede Microservice.</span><span class="sxs-lookup"><span data-stu-id="f68f7-116">Functional tests for each microservice.</span></span> <span data-ttu-id="f68f7-117">Diese Stellen Sie sicher, dass die Anwendung erwartungsgemäß aus Sicht des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="f68f7-117">These ensure that the application works as expected from the user’s perspective.</span></span>

-   <span data-ttu-id="f68f7-118">Testet.</span><span class="sxs-lookup"><span data-stu-id="f68f7-118">Service tests.</span></span> <span data-ttu-id="f68f7-119">Diese Stellen Sie sicher, dass Anwendungsfälle für End-to-End-Dienst, einschließlich der Tests mehrere Dienste zur gleichen Zeit getestet werden.</span><span class="sxs-lookup"><span data-stu-id="f68f7-119">These ensure that end-to-end service use cases, including testing multiple services at the same time, are tested.</span></span> <span data-ttu-id="f68f7-120">Für diese Art von Tests müssen Sie zunächst die Umgebung vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="f68f7-120">For this type of testing, you need to prepare the environment first.</span></span> <span data-ttu-id="f68f7-121">In diesem Fall daher starten die Dienste (z. B. mit Docker-verfassen oben).</span><span class="sxs-lookup"><span data-stu-id="f68f7-121">In this case, it means starting the services (for example, by using docker-compose up).</span></span>

### <a name="implementing-unit-tests-for-aspnet-core-web-apis"></a><span data-ttu-id="f68f7-122">Implementieren von Komponententests für ASP.NET Core Web-APIs</span><span class="sxs-lookup"><span data-stu-id="f68f7-122">Implementing unit tests for ASP.NET Core Web APIs</span></span>

<span data-ttu-id="f68f7-123">UnitTests umfasst einen Teil einer Anwendung unabhängig von der Infrastruktur und die Abhängigkeiten testen.</span><span class="sxs-lookup"><span data-stu-id="f68f7-123">Unit testing involves testing a part of an application in isolation from its infrastructure and dependencies.</span></span> <span data-ttu-id="f68f7-124">Wenn Sie Komponententests für Controllerlogik, nur den Inhalt einer einzigen Aktion oder-Methode getestet wird, nicht das Verhalten der zugehörigen Abhängigkeiten oder Framework selbst.</span><span class="sxs-lookup"><span data-stu-id="f68f7-124">When you unit test controller logic, only the content of a single action or method is tested, not the behavior of its dependencies or of the framework itself.</span></span> <span data-ttu-id="f68f7-125">Komponententests nicht erkennen Probleme bei der Interaktion zwischen Komponenten – d. h. den Zweck von Integrationstests.</span><span class="sxs-lookup"><span data-stu-id="f68f7-125">Unit tests do not detect issues in the interaction between components—that is the purpose of integration testing.</span></span>

<span data-ttu-id="f68f7-126">Testen Sie als Einheit Sie Ihre Controlleraktionen, stellen Sie sicher, dass Sie sich nur auf ihr Verhalten konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="f68f7-126">As you unit test your controller actions, make sure you focus only on their behavior.</span></span> <span data-ttu-id="f68f7-127">Ein Komponententest Controller wird z. B. Filter, routing oder wurden die modellbindung vermieden.</span><span class="sxs-lookup"><span data-stu-id="f68f7-127">A controller unit test avoids things like filters, routing, or model binding.</span></span> <span data-ttu-id="f68f7-128">Da sie zum Testen von nur einem Schritt zu konzentrieren, sind Komponententests im Allgemeinen einfach zu schreiben und schnell ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f68f7-128">Because they focus on testing just one thing, unit tests are generally simple to write and quick to run.</span></span> <span data-ttu-id="f68f7-129">Ein gut geschriebener Satz von Komponententests kann ohne Mehraufwand häufig ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f68f7-129">A well-written set of unit tests can be run frequently without much overhead.</span></span>

<span data-ttu-id="f68f7-130">Komponententests werden basierend auf Testframeworks wie xUnit.net MSTest, Moq oder NUnit implementiert.</span><span class="sxs-lookup"><span data-stu-id="f68f7-130">Unit tests are implemented based on test frameworks like xUnit.net, MSTest, Moq, or NUnit.</span></span> <span data-ttu-id="f68f7-131">Für die beispielanwendung eShopOnContainers verwenden XUnit.</span><span class="sxs-lookup"><span data-stu-id="f68f7-131">For the eShopOnContainers sample application, we are using XUnit.</span></span>

<span data-ttu-id="f68f7-132">Wenn Sie einen Komponententest für eine Web-API-Controller schreiben, instanziieren Sie die Controllerklasse, die direkt mit dem new-Schlüsselwort in C\#, damit der Test so schnell wie möglich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f68f7-132">When you write a unit test for a Web API controller, you instantiate the controller class directly using the new keyword in C\#, so that the test will run as fast as possible.</span></span> <span data-ttu-id="f68f7-133">Das folgende Beispiel zeigt die Vorgehensweise bei Verwendung [XUnit](https://xunit.github.io/) als das Testframework.</span><span class="sxs-lookup"><span data-stu-id="f68f7-133">The following example shows how to do this when using [XUnit](https://xunit.github.io/) as the Test framework.</span></span>

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

### <a name="implementing-integration-and-functional-tests-for-each-microservice"></a><span data-ttu-id="f68f7-134">Implementieren der Integration und funktionale Tests für jede microservice</span><span class="sxs-lookup"><span data-stu-id="f68f7-134">Implementing integration and functional tests for each microservice</span></span>

<span data-ttu-id="f68f7-135">Wie bereits erwähnt, haben Integrationstests und Funktionstests, verschiedene Zwecke und Ziele.</span><span class="sxs-lookup"><span data-stu-id="f68f7-135">As noted, integration tests and functional tests have different purposes and goals.</span></span> <span data-ttu-id="f68f7-136">Allerdings ist die Möglichkeit, die beide beim Testen von ASP.NET Core Controller implementieren ähnlich, damit in diesem Abschnitt es Integrationstests konzentrieren können.</span><span class="sxs-lookup"><span data-stu-id="f68f7-136">However, the way you implement both when testing ASP.NET Core controllers is similar, so in this section we concentrate on integration tests.</span></span>

<span data-ttu-id="f68f7-137">Integrationstests wird sichergestellt, dass eine Anwendung Komponenten ordnungsgemäß, wenn assembliert.</span><span class="sxs-lookup"><span data-stu-id="f68f7-137">Integration testing ensures that an application's components function correctly when assembled.</span></span> <span data-ttu-id="f68f7-138">ASP.NET Core unterstützt Integrationstests zu legen, mit der Komponententest-Frameworks und einem integrierten Test Webhost, der verwendet werden kann, um Mehraufwand von Netzwerk-Anforderungen zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="f68f7-138">ASP.NET Core supports integration testing using unit test frameworks and a built-in test web host that can be used to handle requests without network overhead.</span></span>

<span data-ttu-id="f68f7-139">Im Gegensatz zu Komponententests ausgeführt werden umfassen Integrationstests häufig Infrastruktur anwendungsaspekten, z. B. eine Datenbank, Dateisystem, Netzwerkressourcen, oder webanforderungen und-Antworten an.</span><span class="sxs-lookup"><span data-stu-id="f68f7-139">Unlike unit testing, integration tests frequently involve application infrastructure concerns, such as a database, file system, network resources, or web requests and responses.</span></span> <span data-ttu-id="f68f7-140">Komponententests mithilfe von Fakes oder Modellieren Objekte anstelle von diese Probleme.</span><span class="sxs-lookup"><span data-stu-id="f68f7-140">Unit tests use fakes or mock objects in place of these concerns.</span></span> <span data-ttu-id="f68f7-141">Aber Integrationstests zu bestätigen, dass das System erwartungsgemäß mit diesen Systemen funktioniert deshalb für Integrationstests für die Sie nicht mithilfe von Fakes oder Modellieren der Objekte dient.</span><span class="sxs-lookup"><span data-stu-id="f68f7-141">But the purpose of integration tests is to confirm that the system works as expected with these systems, so for integration testing you do not use fakes or mock objects.</span></span> <span data-ttu-id="f68f7-142">Stattdessen können Sie die Infrastruktur, z. B. Datenbank Zugriff oder Dienst der Aufruf von anderen Diensten.</span><span class="sxs-lookup"><span data-stu-id="f68f7-142">Instead, you include the infrastructure, like database access or service invocation from other services.</span></span>

<span data-ttu-id="f68f7-143">Da Integrationstests größere Codesegmente als Komponententests Übung, und Integrationstests erfolgreich Infrastrukturelemente abhängig, tendenziell sie erheblich langsamer als Komponententests.</span><span class="sxs-lookup"><span data-stu-id="f68f7-143">Because integration tests exercise larger segments of code than unit tests, and because integration tests rely on infrastructure elements, they tend to be orders of magnitude slower than unit tests.</span></span> <span data-ttu-id="f68f7-144">Daher ist es eine gute Idee, wie viele Integrationstests zu beschränken, schreiben und ausführen.</span><span class="sxs-lookup"><span data-stu-id="f68f7-144">Thus, it is a good idea to limit how many integration tests you write and run.</span></span>

<span data-ttu-id="f68f7-145">ASP.NET Core enthält einen integrierte Test Webhost, der zum Verarbeiten von HTTP-Anforderungen ohne netzwerkmehraufwand verwendet werden kann dies bedeutet, dass Sie diese Tests schneller ausführen können, wenn mit einem echten Webhost.</span><span class="sxs-lookup"><span data-stu-id="f68f7-145">ASP.NET Core includes a built-in test web host that can be used to handle HTTP requests without network overhead, meaning that you can run those tests faster when using a real web host.</span></span> <span data-ttu-id="f68f7-146">Der Test-Webhost ist als Microsoft.AspNetCore.TestHost in einer Komponente NuGet verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f68f7-146">The test web host is available in a NuGet component as Microsoft.AspNetCore.TestHost.</span></span> <span data-ttu-id="f68f7-147">Diese Integration Testprojekte hinzugefügt werden kann und zum Hosten von ASP.NET Core Anwendungen verwendeten.</span><span class="sxs-lookup"><span data-stu-id="f68f7-147">It can be added to integration test projects and used to host ASP.NET Core applications.</span></span>

<span data-ttu-id="f68f7-148">Wie Sie den folgenden Code Erstellung Integrationstests für ASP.NET Core Controller sehen können, die Controller über Testhost instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="f68f7-148">As you can see in the following code, when you create integration tests for ASP.NET Core controllers, you instantiate the controllers through the test host.</span></span> <span data-ttu-id="f68f7-149">Dies ist vergleichbar mit einer HTTP-Anforderung, aber schneller ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f68f7-149">This is comparable to an HTTP request, but it runs faster.</span></span>

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

#### <a name="additional-resources"></a><span data-ttu-id="f68f7-150">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="f68f7-150">Additional resources</span></span>

-   <span data-ttu-id="f68f7-151">**Steve Smith. Testen von Controllern** (ASP.NET Core) [ *https://docs.microsoft.com/aspnet/core/mvc/controllers/testing*](https://docs.microsoft.com/aspnet/core/mvc/controllers/testing)</span><span class="sxs-lookup"><span data-stu-id="f68f7-151">**Steve Smith. Testing controllers** (ASP.NET Core) [*https://docs.microsoft.com/aspnet/core/mvc/controllers/testing*](https://docs.microsoft.com/aspnet/core/mvc/controllers/testing)</span></span>

-   <span data-ttu-id="f68f7-152">**Steve Smith. Integrationstests** (ASP.NET Core) [ *https://docs.microsoft.com/aspnet/core/testing/integration-testing*](https://docs.microsoft.com/aspnet/core/testing/integration-testing)</span><span class="sxs-lookup"><span data-stu-id="f68f7-152">**Steve Smith. Integration testing** (ASP.NET Core) [*https://docs.microsoft.com/aspnet/core/testing/integration-testing*](https://docs.microsoft.com/aspnet/core/testing/integration-testing)</span></span>

-   <span data-ttu-id="f68f7-153">**Komponententests in .NET Core-Dotnet-Test mit**
    [*https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test*](https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test)</span><span class="sxs-lookup"><span data-stu-id="f68f7-153">**Unit testing in .NET Core using dotnet test**
[*https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test*](https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test)</span></span>

-   <span data-ttu-id="f68f7-154">**xUnit.net**.</span><span class="sxs-lookup"><span data-stu-id="f68f7-154">**xUnit.net**.</span></span> <span data-ttu-id="f68f7-155">Offizielle Website.</span><span class="sxs-lookup"><span data-stu-id="f68f7-155">Official site.</span></span>
    [<span data-ttu-id="f68f7-156">*https://xUnit.github.IO/*</span><span class="sxs-lookup"><span data-stu-id="f68f7-156">*https://xunit.github.io/*</span></span>](https://xunit.github.io/)

-   <span data-ttu-id="f68f7-157">**Grundlagen zum Komponententest. ** 
     [ *https://msdn.microsoft.com/en-us/library/hh694602.aspx*](https://msdn.microsoft.com/en-us/library/hh694602.aspx)</span><span class="sxs-lookup"><span data-stu-id="f68f7-157">**Unit Test Basics.**
[*https://msdn.microsoft.com/en-us/library/hh694602.aspx*](https://msdn.microsoft.com/en-us/library/hh694602.aspx)</span></span>

-   <span data-ttu-id="f68f7-158">**Moq**.</span><span class="sxs-lookup"><span data-stu-id="f68f7-158">**Moq**.</span></span> <span data-ttu-id="f68f7-159">GitHub-Repository.</span><span class="sxs-lookup"><span data-stu-id="f68f7-159">GitHub repo.</span></span>
    [<span data-ttu-id="f68f7-160">*https://github.com/moq/moq*</span><span class="sxs-lookup"><span data-stu-id="f68f7-160">*https://github.com/moq/moq*</span></span>](https://github.com/moq/moq)

-   <span data-ttu-id="f68f7-161">**NUnit**.</span><span class="sxs-lookup"><span data-stu-id="f68f7-161">**NUnit**.</span></span> <span data-ttu-id="f68f7-162">Offizielle Website.</span><span class="sxs-lookup"><span data-stu-id="f68f7-162">Official site.</span></span>
    [<span data-ttu-id="f68f7-163">*https://www.NUnit.org/*</span><span class="sxs-lookup"><span data-stu-id="f68f7-163">*https://www.nunit.org/*</span></span>](https://www.nunit.org/)

### <a name="implementing-service-tests-on-a-multi-container-application"></a><span data-ttu-id="f68f7-164">Für eine Anwendung mit mehreren Container implementierende diensttests</span><span class="sxs-lookup"><span data-stu-id="f68f7-164">Implementing service tests on a multi-container application</span></span> 

<span data-ttu-id="f68f7-165">Wie bereits erwähnt, wenn Sie Multi-containeranwendungen testen, müssen alle Microservices innerhalb des Docker-Host oder Container-Clusters ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f68f7-165">As noted earlier, when you test multi-container applications, all the microservices need to be running within the Docker host or container cluster.</span></span> <span data-ttu-id="f68f7-166">End-to-End diensttests, die mehrere Vorgänge im Zusammenhang mit mehreren Microservices enthalten erfordern Sie zum Bereitstellen und starten Sie die gesamte Anwendung in der Docker-Host, durch Ausführen von Docker-verfassen nach-oben (oder einen vergleichbaren Mechanismus bei Verwendung von ein Orchestrator).</span><span class="sxs-lookup"><span data-stu-id="f68f7-166">End-to-end service tests that include multiple operations involving several microservices require you to deploy and start the whole application in the Docker host by running docker-compose up (or a comparable mechanism if you are using an orchestrator).</span></span> <span data-ttu-id="f68f7-167">Nachdem die gesamte Anwendung und alle zugehörigen Dienste ausgeführt werden, können Sie die End-to-End-Integration und funktionale Tests ausführen.</span><span class="sxs-lookup"><span data-stu-id="f68f7-167">Once the whole application and all its services is running, you can execute end-to-end integration and functional tests.</span></span>

<span data-ttu-id="f68f7-168">Es gibt einige Ansätze, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="f68f7-168">There are a few approaches you can use.</span></span> <span data-ttu-id="f68f7-169">In der Docker-compose.yml-Datei, die Sie verwenden, um die Anwendung (oder ähnliche wie Docker compose.ci.build.yml) bereitstellen, auf Projektmappenebene können erweitern Sie den zu verwendenden Einstiegspunkt [Dotnet Test](https://docs.microsoft.com/dotnet/core/tools/dotnet-test).</span><span class="sxs-lookup"><span data-stu-id="f68f7-169">In the docker-compose.yml file that you use to deploy the application (or similar ones, like docker-compose.ci.build.yml), at the solution level you can expand the entry point to use [dotnet test](https://docs.microsoft.com/dotnet/core/tools/dotnet-test).</span></span> <span data-ttu-id="f68f7-170">Sie können auch eine andere Compose-Datei, die in der Abbildung Ihrer Zielgruppe, die Tests ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="f68f7-170">You can also use another compose file that would run your tests in the image you are targeting.</span></span> <span data-ttu-id="f68f7-171">Durch Verwendung einer anderen Compose-Datei Integrationstests, die die Microservices und die Datenbanken für Container enthält, können Sie sicherstellen, dass die verwandten Daten immer auf den ursprünglichen Zustand zurückgesetzt werden, vor dem Ausführen der Tests.</span><span class="sxs-lookup"><span data-stu-id="f68f7-171">By using another compose file for integration tests that includes your microservices and databases on containers, you can make sure that the related data is always reset to its original state before running the tests.</span></span>

<span data-ttu-id="f68f7-172">Sobald die Compose-Anwendung ausgeführt wird, können Sie Haltepunkte und Ausnahmen nutzen, wenn Sie Visual Studio ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f68f7-172">Once the compose application is up and running, you can take advantage of breakpoints and exceptions if you are running Visual Studio.</span></span> <span data-ttu-id="f68f7-173">Oder Sie können die Integrationstests erfolgreich automatisch ausführen, in der CI-Pipeline in Visual Studio Team Services oder eines anderen Systems von CI-CD, das Docker-Containern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f68f7-173">Or you can run the integration tests automatically in your CI pipeline in Visual Studio Team Services or any other CI/CD system that supports Docker containers.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="f68f7-174">[Vorherigen] (Abonnieren-events.md) [weiter] (.. /microservice-ddd-CQRS-Patterns/Index.MD)</span><span class="sxs-lookup"><span data-stu-id="f68f7-174">[Previous] (subscribe-events.md) [Next] (../microservice-ddd-cqrs-patterns/index.md)</span></span>

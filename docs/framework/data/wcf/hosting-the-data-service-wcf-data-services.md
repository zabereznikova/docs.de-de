---
title: Hosting des Datendiensts (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, Windows Communication Foundation
ms.assetid: b48f42ce-22ce-4f8d-8f0d-f7ddac9125ee
ms.openlocfilehash: 3abcd901bcb8a175aa6f30e53b142cbbde56a579
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975243"
---
# <a name="hosting-the-data-service-wcf-data-services"></a><span data-ttu-id="aefd6-102">Hosting des Datendiensts (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="aefd6-102">Hosting the Data Service (WCF Data Services)</span></span>
<span data-ttu-id="aefd6-103">Mithilfe WCF Data Services können Sie einen Dienst erstellen, der Daten als Open Data Protocol (odata)-Feed verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="aefd6-103">By using WCF Data Services, you can create a service that exposes data as an Open Data Protocol (OData) feed.</span></span> <span data-ttu-id="aefd6-104">Dieser Datendienst wird als Klasse definiert, die von <xref:System.Data.Services.DataService%601> erbt.</span><span class="sxs-lookup"><span data-stu-id="aefd6-104">This data service is defined as a class that inherits from <xref:System.Data.Services.DataService%601>.</span></span> <span data-ttu-id="aefd6-105">Diese Klasse stellt die Funktionalität bereit, die erforderlich ist, um Anforderungs Nachrichten zu verarbeiten, Updates für die Datenquelle auszuführen und Antwort Nachrichten zu generieren, die von odata benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="aefd6-105">This class provides the functionality required to process request messages, perform updates against the data source, and generate responses messages, as required by OData.</span></span> <span data-ttu-id="aefd6-106">Ein Datendienst kann jedoch keine Bindung an einen Netzwerk Socket für eingehende HTTP-Anforderungen herstellen und diesen überwachen.</span><span class="sxs-lookup"><span data-stu-id="aefd6-106">However, a data service cannot bind to and listen on a network socket for incoming HTTP requests.</span></span> <span data-ttu-id="aefd6-107">Für diese erforderliche Funktion benötigt der Datendienst eine Hostingkomponente.</span><span class="sxs-lookup"><span data-stu-id="aefd6-107">For this required functionality, the data service relies on a hosting component.</span></span>

 <span data-ttu-id="aefd6-108">Der Datendiensthost führt die folgenden Aufgaben im Namen des Datendiensts aus:</span><span class="sxs-lookup"><span data-stu-id="aefd6-108">The data service host performs the following tasks on behalf of the data service:</span></span>

- <span data-ttu-id="aefd6-109">Lauscht auf Anforderungen und leitet diese an den Datendienst weiter.</span><span class="sxs-lookup"><span data-stu-id="aefd6-109">Listens for requests and routes these requests to the data service.</span></span>

- <span data-ttu-id="aefd6-110">Erstellt für jede Anforderung eine Instanz des Datendiensts.</span><span class="sxs-lookup"><span data-stu-id="aefd6-110">Creates an instance of the data service for each request.</span></span>

- <span data-ttu-id="aefd6-111">Fordert an, dass der Datendienst die eingehende Anforderung verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="aefd6-111">Requests that the data service process the incoming request.</span></span>

- <span data-ttu-id="aefd6-112">Sendet die Antwort im Namen des Datendiensts.</span><span class="sxs-lookup"><span data-stu-id="aefd6-112">Sends the response on behalf of the data service.</span></span>

 <span data-ttu-id="aefd6-113">Um das Hosting eines Daten Diensts zu vereinfachen, ist WCF Data Services für die Integration in Windows Communication Foundation (WCF) konzipiert.</span><span class="sxs-lookup"><span data-stu-id="aefd6-113">To simplify hosting a data service, WCF Data Services is designed to integrate with Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="aefd6-114">Der Datendienst bietet eine WCF-Standard Implementierung, die in einer ASP.NET-Anwendung als Datendienst Host fungiert.</span><span class="sxs-lookup"><span data-stu-id="aefd6-114">The data service provides a default WCF implementation that serves as the data service host in an ASP.NET application.</span></span> <span data-ttu-id="aefd6-115">Daher können Sie einen Datendienst in einer der folgenden Methoden hosten:</span><span class="sxs-lookup"><span data-stu-id="aefd6-115">Therefore, you can host a data service in one of the following ways:</span></span>

- <span data-ttu-id="aefd6-116">In einer ASP.NET-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="aefd6-116">In an ASP.NET application.</span></span>

- <span data-ttu-id="aefd6-117">In einer verwalteten Anwendung, die selbst gehostete WCF-Dienste unterstützt.</span><span class="sxs-lookup"><span data-stu-id="aefd6-117">In a managed application that supports self-hosted WCF services.</span></span>

- <span data-ttu-id="aefd6-118">In einem anderen benutzerdefinierten Datendiensthost.</span><span class="sxs-lookup"><span data-stu-id="aefd6-118">In some other custom data service host.</span></span>

## <a name="hosting-a-data-service-in-an-aspnet-application"></a><span data-ttu-id="aefd6-119">Hosten eines Datendiensts in einer ASP.NET-Anwendung</span><span class="sxs-lookup"><span data-stu-id="aefd6-119">Hosting a Data Service in an ASP.NET Application</span></span>

<span data-ttu-id="aefd6-120">Wenn Sie das Dialogfeld **Neues Element hinzufügen** in Visual Studio 2015 verwenden, um einen Datendienst in einer ASP.NET-Anwendung zu definieren, generiert das Tool zwei neue Dateien im Projekt.</span><span class="sxs-lookup"><span data-stu-id="aefd6-120">When you use the **Add New Item** dialog in Visual Studio 2015 to define a data service in an ASP.NET application, the tool generates two new files in the project.</span></span> <span data-ttu-id="aefd6-121">Die erste Datei verfügt über die `.svc`-Erweiterung und weist die WCF-Laufzeit an, wie der Datendienst instanziiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="aefd6-121">The first file has a `.svc` extension and instructs the WCF runtime how to instantiate the data service.</span></span> <span data-ttu-id="aefd6-122">Im folgenden finden Sie ein Beispiel für diese Datei für den Northwind-Beispiel Datendienst, der erstellt wird, wenn Sie den [Schnellstart](quickstart-wcf-data-services.md)ausführen:</span><span class="sxs-lookup"><span data-stu-id="aefd6-122">The following is an example of this file for the Northwind sample data service created when you complete the [quickstart](quickstart-wcf-data-services.md):</span></span>

```aspx-csharp
<%@ ServiceHost Language="C#"
    Factory="System.Data.Services.DataServiceHostFactory,
            System.Data.Services, Version=4.0.0.0,
            Culture=neutral, PublicKeyToken=b77a5c561934e089"
    Service="NorthwindService.Northwind" %>
```

 <span data-ttu-id="aefd6-123">Diese Direktive weist die Anwendung an, den Diensthost für die benannte Datendienstklasse mithilfe der <xref:System.Data.Services.DataServiceHostFactory>-Klasse zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="aefd6-123">This directive tells the application to create the service host for the named data service class by using the <xref:System.Data.Services.DataServiceHostFactory> class.</span></span>

 <span data-ttu-id="aefd6-124">Die CodeBehind-Seite für die `.svc`-Datei enthält die Klasse, bei der es sich um die Implementierung des Datendiensts selbst handelt und die für den Northwind-Beispieldatendienst folgendermaßen definiert wird:</span><span class="sxs-lookup"><span data-stu-id="aefd6-124">The code-behind page for the `.svc` file contains the class that is the implementation of the data service itself, which is defined as follows for the Northwind sample data service:</span></span>

 [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
 [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

 <span data-ttu-id="aefd6-125">Da sich ein Datendienst wie ein WCF-Dienst verhält, wird der Datendienst in ASP.NET integriert und folgt dem WCF-webprogrammier Modell.</span><span class="sxs-lookup"><span data-stu-id="aefd6-125">Because a data service behaves like a WCF service, the data service integrates with ASP.NET and follows the WCF Web programming model.</span></span> <span data-ttu-id="aefd6-126">Weitere Informationen finden Sie unter [WCF-Dienste und ASP.net](../../wcf/feature-details/wcf-services-and-aspnet.md) und [WCF-Web-HTTP-Programmiermodell](../../wcf/feature-details/wcf-web-http-programming-model.md).</span><span class="sxs-lookup"><span data-stu-id="aefd6-126">For more information, see [WCF Services and ASP.NET](../../wcf/feature-details/wcf-services-and-aspnet.md) and [WCF Web HTTP Programming Model](../../wcf/feature-details/wcf-web-http-programming-model.md).</span></span>

## <a name="self-hosted-wcf-services"></a><span data-ttu-id="aefd6-127">Selbst gehostete WCF-Dienste</span><span class="sxs-lookup"><span data-stu-id="aefd6-127">Self-Hosted WCF Services</span></span>
 <span data-ttu-id="aefd6-128">Da Sie eine WCF-Implementierung beinhaltet, wird WCF Data Services das Self-Hosting eines Daten Diensts als WCF-Dienst unterstützen.</span><span class="sxs-lookup"><span data-stu-id="aefd6-128">Because it incorporates a WCF implementation, WCF Data Services support self-hosting a data service as a WCF service.</span></span> <span data-ttu-id="aefd6-129">Ein Dienst kann in jeder .NET Framework Anwendung, z. b. einer Konsolenanwendung, selbstgeh ostet werden.</span><span class="sxs-lookup"><span data-stu-id="aefd6-129">A service can be self-hosted in any .NET Framework application, such as a console application.</span></span> <span data-ttu-id="aefd6-130">Die <xref:System.Data.Services.DataServiceHost>-Klasse, die von <xref:System.ServiceModel.Web.WebServiceHost> erbt, wird verwendet, um den Datendienst bei einer bestimmten Adresse zu instanziieren.</span><span class="sxs-lookup"><span data-stu-id="aefd6-130">The <xref:System.Data.Services.DataServiceHost> class, which inherits from <xref:System.ServiceModel.Web.WebServiceHost>, is used to instantiate the data service at a specific address.</span></span>

 <span data-ttu-id="aefd6-131">Selbsthosting kann für die Entwicklung und für Tests verwendet werden, da die Bereitstellung und Problembehandlung vereinfacht wird.</span><span class="sxs-lookup"><span data-stu-id="aefd6-131">Self-hosting can be used for development and testing because it can make it easier to deploy and troubleshoot the service.</span></span> <span data-ttu-id="aefd6-132">Diese Art von Hosting stellt jedoch nicht die erweiterten Hosting-und Verwaltungsfunktionen bereit, die von ASP.net oder Internetinformationsdienste (IIS) bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="aefd6-132">However, this kind of hosting does not provide the advanced hosting and management features provided by ASP.NET or by Internet Information Services (IIS).</span></span> <span data-ttu-id="aefd6-133">Weitere Informationen finden Sie unter [Hosting in einer verwalteten Anwendung](../../wcf/feature-details/hosting-in-a-managed-application.md).</span><span class="sxs-lookup"><span data-stu-id="aefd6-133">For more information, see [Hosting in a Managed Application](../../wcf/feature-details/hosting-in-a-managed-application.md).</span></span>

## <a name="defining-a-custom-data-service-host"></a><span data-ttu-id="aefd6-134">Definieren eines benutzerdefinierten Datendiensthosts</span><span class="sxs-lookup"><span data-stu-id="aefd6-134">Defining a Custom Data Service Host</span></span>
 <span data-ttu-id="aefd6-135">Wenn die WCF-Hostimplementierung zu restriktiv ist, können Sie für einen Datendienst auch einen benutzerdefinierten Host definieren.</span><span class="sxs-lookup"><span data-stu-id="aefd6-135">For cases where the WCF host implementation is too restrictive, you can also define a custom host for a data service.</span></span> <span data-ttu-id="aefd6-136">Alle Klassen, die eine <xref:System.Data.Services.IDataServiceHost>-Schnittstelle implementieren, können für einen Datendienst als Netzwerkhost verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aefd6-136">Any class that implements <xref:System.Data.Services.IDataServiceHost> interface can be used as the network host for a data service.</span></span> <span data-ttu-id="aefd6-137">Ein benutzerdefinierter Host muss die <xref:System.Data.Services.IDataServiceHost>-Schnittstelle implementieren und in der Lage sein, die folgenden grundlegenden Aufgaben des Datendiensthosts zu übernehmen:</span><span class="sxs-lookup"><span data-stu-id="aefd6-137">A custom host must implement the <xref:System.Data.Services.IDataServiceHost> interface and be able to handle the following basic responsibilities of the data service host:</span></span>

- <span data-ttu-id="aefd6-138">Bereitstellen des Dienststammpfads für den Datendienst</span><span class="sxs-lookup"><span data-stu-id="aefd6-138">Provide the data service with the service root path.</span></span>

- <span data-ttu-id="aefd6-139">Verarbeiten der Anforderungs- und Antwortheaderinformationen für die entsprechende <xref:System.Data.Services.IDataServiceHost>-Memberimplementierung</span><span class="sxs-lookup"><span data-stu-id="aefd6-139">Process request and response headers information to the appropriate <xref:System.Data.Services.IDataServiceHost> member implementation.</span></span>

- <span data-ttu-id="aefd6-140">Behandeln der vom Datendienst ausgelösten Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="aefd6-140">Handle exceptions raised by the data service.</span></span>

- <span data-ttu-id="aefd6-141">Überprüfen der Parameter in der Abfragezeichenfolge</span><span class="sxs-lookup"><span data-stu-id="aefd6-141">Validate parameters in the query string.</span></span>

## <a name="see-also"></a><span data-ttu-id="aefd6-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aefd6-142">See also</span></span>

- [<span data-ttu-id="aefd6-143">Defining WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="aefd6-143">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)
- [<span data-ttu-id="aefd6-144">Verfügbarmachen der Daten als Dienst</span><span class="sxs-lookup"><span data-stu-id="aefd6-144">Exposing Your Data as a Service</span></span>](exposing-your-data-as-a-service-wcf-data-services.md)
- [<span data-ttu-id="aefd6-145">Konfigurieren des Datendiensts</span><span class="sxs-lookup"><span data-stu-id="aefd6-145">Configuring the Data Service</span></span>](configuring-the-data-service-wcf-data-services.md)

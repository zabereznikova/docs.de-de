---
title: 'Vorgehensweise: Hosten eines WCF-Diensts in IIS'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b044b1c9-c1e5-4c9f-84d8-0f02f4537f8b
ms.openlocfilehash: 44c1b489897a25d293644c5a3ef7d446dd8d4a3b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54651122"
---
# <a name="how-to-host-a-wcf-service-in-iis"></a><span data-ttu-id="1c981-102">Vorgehensweise: Hosten eines WCF-Diensts in IIS</span><span class="sxs-lookup"><span data-stu-id="1c981-102">How to: Host a WCF Service in IIS</span></span>
<span data-ttu-id="1c981-103">Dieses Thema beschreibt die grundlegenden Schritte zum Erstellen eines Windows Communication Foundation (WCF)-Diensts, der gehostet wird in Internet Information Services (IIS) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1c981-103">This topic outlines the basic steps required to create a Windows Communication Foundation (WCF) service that is hosted in Internet Information Services (IIS).</span></span> <span data-ttu-id="1c981-104">Es wird vorausgesetzt, dass Sie mit IIS vertraut sind und wissen, wie mithilfe des IIS-Verwaltungstools IIS-Anwendungen erstellt und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="1c981-104">This topic assumes you are familiar with IIS and understand how to use the IIS management tool to create and manage IIS applications.</span></span> <span data-ttu-id="1c981-105">Weitere Informationen zu IIS finden Sie unter [Internet Information Services](https://go.microsoft.com/fwlink/?LinkId=132449).</span><span class="sxs-lookup"><span data-stu-id="1c981-105">For more information about IIS see [Internet Information Services](https://go.microsoft.com/fwlink/?LinkId=132449).</span></span> <span data-ttu-id="1c981-106">Ein WCF-Dienst, der ausgeführt wird, in der IIS-Umgebung nutzt die Vorteile der IIS-Funktionen, beispielsweise die prozesswiederverwendung, Herunterfahren bei Leerlauf, prozessüberwachung und Nachrichtenbasierte Aktivierung.</span><span class="sxs-lookup"><span data-stu-id="1c981-106">A WCF service that runs in the IIS environment takes full advantage of IIS features, such as process recycling, idle shutdown, process health monitoring, and message-based activation.</span></span> <span data-ttu-id="1c981-107">Diese Hostingoption erfordert, dass IIS korrekt konfiguriert wurde, jedoch muss keinerlei Hostcode für die Anwendung geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="1c981-107">This hosting option requires that IIS be properly configured, but it does not require that any hosting code be written as part of the application.</span></span> <span data-ttu-id="1c981-108">Sie können IIS-Hosting nur mit einem HTTP-Transport verwenden.</span><span class="sxs-lookup"><span data-stu-id="1c981-108">You can use IIS hosting only with an HTTP transport.</span></span>  
  
 <span data-ttu-id="1c981-109">Weitere Informationen dazu, wie WCF und [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] interagieren, finden Sie unter [WCF-Dienste und ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).</span><span class="sxs-lookup"><span data-stu-id="1c981-109">For more information about how WCF and [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] interact, see [WCF Services and ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).</span></span> <span data-ttu-id="1c981-110">Weitere Informationen zum Konfigurieren der Sicherheit finden Sie unter [Sicherheit](../../../../docs/framework/wcf/feature-details/security.md).</span><span class="sxs-lookup"><span data-stu-id="1c981-110">For more information about configuring security, see [Security](../../../../docs/framework/wcf/feature-details/security.md).</span></span>  
  
 <span data-ttu-id="1c981-111">Die Quellkopie dieses Beispiels, finden Sie unter [IIS-Hosting mithilfe von Inlinecode](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md).</span><span class="sxs-lookup"><span data-stu-id="1c981-111">For the source copy of this example, see [IIS Hosting Using Inline Code](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md).</span></span>  
  
### <a name="to-create-a-service-hosted-by-iis"></a><span data-ttu-id="1c981-112">So erstellen Sie einen von IIS gehosteten Dienst</span><span class="sxs-lookup"><span data-stu-id="1c981-112">To create a service hosted by IIS</span></span>  
  
1.  <span data-ttu-id="1c981-113">Vergewissern Sie sich, dass IIS installiert ist und auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1c981-113">Confirm that IIS is installed and running on your computer.</span></span> <span data-ttu-id="1c981-114">Weitere Informationen zum Installieren und Konfigurieren von IIS finden Sie unter [installieren und Konfigurieren von IIS 7.0](https://go.microsoft.com/fwlink/?LinkID=132128)</span><span class="sxs-lookup"><span data-stu-id="1c981-114">For more information about installing and configuring IIS see [Installing and Configuring IIS 7.0](https://go.microsoft.com/fwlink/?LinkID=132128)</span></span>  
  
2.  <span data-ttu-id="1c981-115">Erstellen Sie einen neuen Ordner namens "IISHostedCalcService" für die Anwendungsdateien, stellen Sie sicher, dass [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] auf den Inhalt des Ordners zugreifen kann, und verwenden Sie das IIS-Verwaltungstool, um eine neue IIS-Anwendung zu erstellen, die physisch in diesem Anwendungsverzeichnis gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="1c981-115">Create a new folder for your application files called "IISHostedCalcService", ensure that [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] has access to the contents of the folder, and use the IIS management tool to create a new IIS application that is physically located in this application directory.</span></span> <span data-ttu-id="1c981-116">Verwenden Sie "IISHostedCalc", wenn Sie einen Alias für das Anwendungsverzeichnis erstellen.</span><span class="sxs-lookup"><span data-stu-id="1c981-116">When creating an alias for the application directory use "IISHostedCalc".</span></span>  
  
3.  <span data-ttu-id="1c981-117">Erstellen Sie eine neue Datei namens "service.svc" im Anwendungsverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="1c981-117">Create a new file named "service.svc" in the application directory.</span></span> <span data-ttu-id="1c981-118">Bearbeiten Sie diese Datei durch Hinzufügen des folgenden @ServiceHost Element.</span><span class="sxs-lookup"><span data-stu-id="1c981-118">Edit this file by adding the following @ServiceHost element.</span></span>  
  
    ```  
    <%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService"%>  
    ```  
  
4.  <span data-ttu-id="1c981-119">Erstellen Sie im Stammverzeichnis der Anwendung das Unterverzeichnis App_Code.</span><span class="sxs-lookup"><span data-stu-id="1c981-119">Create an App_Code subdirectory within the application directory.</span></span>  
  
5.  <span data-ttu-id="1c981-120">Erstellen Sie eine Codedatei namens "Service.svc" im Unterverzeichnis "App_Code".</span><span class="sxs-lookup"><span data-stu-id="1c981-120">Create a code file named Service.cs in the App_Code subdirectory.</span></span>  
  
6.  <span data-ttu-id="1c981-121">Fügen Sie am Anfang der Datei "Service.cs" die folgenden using-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="1c981-121">Add the following using statements to the top of the Service.cs file.</span></span>  
  
    ```csharp  
    using System;  
    using System.ServiceModel;  
    ```  
  
7.  <span data-ttu-id="1c981-122">Fügen Sie nach den using-Anweisungen die folgende Namespacedeklaration hinzu.</span><span class="sxs-lookup"><span data-stu-id="1c981-122">Add the following namespace declaration after the using statements.</span></span>  
  
    ```csharp  
    namespace Microsoft.ServiceModel.Samples  
    {  
    }  
    ```  
  
8.  <span data-ttu-id="1c981-123">Definieren Sie den Dienstvertrag in der Namespacedeklaration, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1c981-123">Define the service contract inside the namespace declaration as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInIIS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#11)]
     [!code-vb[c_HowTo_HostInIIS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#11)]  
  
9. <span data-ttu-id="1c981-124">Implementieren Sie den Dienstvertrag nach der Dienstvertragsdefinition, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1c981-124">Implement the service contract after the service contract definition as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInIIS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#12)]
     [!code-vb[c_HowTo_HostInIIS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#12)]  
  
10. <span data-ttu-id="1c981-125">Erstellen Sie eine Datei namens "Web.config" im Anwendungsverzeichnis, und fügen Sie der Datei den folgenden Konfigurationscode hinzu.</span><span class="sxs-lookup"><span data-stu-id="1c981-125">Create a file named "Web.config" in the application directory and add the following configuration code into the file.</span></span> <span data-ttu-id="1c981-126">Zur Laufzeit verwendet die WCF-Infrastruktur die Informationen zur Erstellung eines Endpunkts, mit dem Clientanwendungen kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="1c981-126">At runtime, the WCF infrastructure uses the information to construct an endpoint that client applications can communicate with.</span></span>  
  
     [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]      
  
     <span data-ttu-id="1c981-127">In diesem Beispiel werden die Endpunkte in der Konfigurationsdatei explizit angegeben.</span><span class="sxs-lookup"><span data-stu-id="1c981-127">This example explicitly specifies endpoints in the configuration file.</span></span> <span data-ttu-id="1c981-128">Wenn Sie dem Dienst keine Endpunkte hinzufügen, werden von der Runtime automatisch Standardendpunkte hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1c981-128">If you do not add any endpoints to the service, the runtime adds default endpoints for you.</span></span> <span data-ttu-id="1c981-129">Weitere Informationen zu Standardendpunkten, Bindungen und Verhaltensweisen finden Sie unter [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) und [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="1c981-129">For more information about default endpoints, bindings, and behaviors see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
11. <span data-ttu-id="1c981-130">Um sicherzustellen, dass der Dienst korrekt gehostet wird, öffnen Sie eine Instanz von Internet Explorer, und navigieren Sie zur URL des Diensts: `http://localhost/IISHostedCalc/Service.svc`</span><span class="sxs-lookup"><span data-stu-id="1c981-130">To make sure the service is hosted correctly, open an instance of Internet Explorer and browse to the service's URL: `http://localhost/IISHostedCalc/Service.svc`</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c981-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1c981-131">Example</span></span>  
 <span data-ttu-id="1c981-132">Im Folgenden finden Sie eine vollständige Auflistung des Codes für den von IIS gehosteten Dienst.</span><span class="sxs-lookup"><span data-stu-id="1c981-132">The following is a complete listing of the code for the IIS hosted calculator service.</span></span>  
  
 [!code-csharp[C_HowTo_HostInIIS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#1)] 
 [!code-vb[C_HowTo_HostInIIS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#1)] 
 [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]  
  
## <a name="see-also"></a><span data-ttu-id="1c981-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c981-133">See also</span></span>
- [<span data-ttu-id="1c981-134">Hosten in IIS (Internetinformationsdienste)</span><span class="sxs-lookup"><span data-stu-id="1c981-134">Hosting in Internet Information Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)
- [<span data-ttu-id="1c981-135">Hosting-Dienste</span><span class="sxs-lookup"><span data-stu-id="1c981-135">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)
- [<span data-ttu-id="1c981-136">WCF-Dienste und ASP.NET</span><span class="sxs-lookup"><span data-stu-id="1c981-136">WCF Services and ASP.NET</span></span>](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)
- [<span data-ttu-id="1c981-137">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="1c981-137">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)
- [<span data-ttu-id="1c981-138">Windows Server AppFabric-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="1c981-138">Windows Server App Fabric Hosting Features</span></span>](https://go.microsoft.com/fwlink/?LinkId=201276)

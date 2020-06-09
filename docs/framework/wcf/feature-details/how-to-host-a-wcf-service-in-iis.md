---
title: 'Vorgehensweise: Hosten eines WCF-Diensts in IIS'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b044b1c9-c1e5-4c9f-84d8-0f02f4537f8b
ms.openlocfilehash: 326a270c4af38738c910828acd483070ab02ecd1
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593086"
---
# <a name="how-to-host-a-wcf-service-in-iis"></a><span data-ttu-id="02d34-102">Vorgehensweise: Hosten eines WCF-Diensts in IIS</span><span class="sxs-lookup"><span data-stu-id="02d34-102">How to: Host a WCF Service in IIS</span></span>
<span data-ttu-id="02d34-103">In diesem Thema werden die grundlegenden Schritte beschrieben, die zum Erstellen eines in Internetinformationsdienste (IIS) gehosteten Windows Communication Foundation (WCF)-Dienstanbieter erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="02d34-103">This topic outlines the basic steps required to create a Windows Communication Foundation (WCF) service that is hosted in Internet Information Services (IIS).</span></span> <span data-ttu-id="02d34-104">Es wird vorausgesetzt, dass Sie mit IIS vertraut sind und wissen, wie mithilfe des IIS-Verwaltungstools IIS-Anwendungen erstellt und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="02d34-104">This topic assumes you are familiar with IIS and understand how to use the IIS management tool to create and manage IIS applications.</span></span> <span data-ttu-id="02d34-105">Weitere Informationen zu IIS finden Sie unter [Internetinformationsdienste](https://www.iis.net/).</span><span class="sxs-lookup"><span data-stu-id="02d34-105">For more information about IIS see [Internet Information Services](https://www.iis.net/).</span></span> <span data-ttu-id="02d34-106">Ein WCF-Dienst, der in der IIS-Umgebung ausgeführt wird, nutzt die IIS-Features, wie z. b. die Prozess Wiederverwendung, das Herunterfahren im Leerlauf, die Prozessüberwachung und die Nachrichten basierte Aktivierung.</span><span class="sxs-lookup"><span data-stu-id="02d34-106">A WCF service that runs in the IIS environment takes full advantage of IIS features, such as process recycling, idle shutdown, process health monitoring, and message-based activation.</span></span> <span data-ttu-id="02d34-107">Diese Hostingoption erfordert, dass IIS korrekt konfiguriert wurde, jedoch muss keinerlei Hostcode für die Anwendung geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="02d34-107">This hosting option requires that IIS be properly configured, but it does not require that any hosting code be written as part of the application.</span></span> <span data-ttu-id="02d34-108">Sie können IIS-Hosting nur mit einem HTTP-Transport verwenden.</span><span class="sxs-lookup"><span data-stu-id="02d34-108">You can use IIS hosting only with an HTTP transport.</span></span>  
  
 <span data-ttu-id="02d34-109">Weitere Informationen zur Interaktion von WCF und ASP.net finden Sie unter [WCF-Dienste und ASP.net](wcf-services-and-aspnet.md).</span><span class="sxs-lookup"><span data-stu-id="02d34-109">For more information about how WCF and ASP.NET interact, see [WCF Services and ASP.NET](wcf-services-and-aspnet.md).</span></span> <span data-ttu-id="02d34-110">Weitere Informationen zum Konfigurieren der Sicherheit finden Sie unter [Sicherheit](security.md).</span><span class="sxs-lookup"><span data-stu-id="02d34-110">For more information about configuring security, see [Security](security.md).</span></span>  
  
 <span data-ttu-id="02d34-111">Die Quell Kopie dieses Beispiels finden [Sie unter IIS-Hosting mithilfe von Inline Code](../samples/iis-hosting-using-inline-code.md).</span><span class="sxs-lookup"><span data-stu-id="02d34-111">For the source copy of this example, see [IIS Hosting Using Inline Code](../samples/iis-hosting-using-inline-code.md).</span></span>  
  
### <a name="to-create-a-service-hosted-by-iis"></a><span data-ttu-id="02d34-112">So erstellen Sie einen von IIS gehosteten Dienst</span><span class="sxs-lookup"><span data-stu-id="02d34-112">To create a service hosted by IIS</span></span>  
  
1. <span data-ttu-id="02d34-113">Vergewissern Sie sich, dass IIS installiert ist und auf dem Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="02d34-113">Confirm that IIS is installed and running on your computer.</span></span> <span data-ttu-id="02d34-114">Weitere Informationen zum Installieren und Konfigurieren von IIS finden Sie unter [Installieren und Konfigurieren von IIS 7,0](https://docs.microsoft.com/iis/install/installing-iis-7/installing-necessary-iis-components-on-windows-vista) .</span><span class="sxs-lookup"><span data-stu-id="02d34-114">For more information about installing and configuring IIS see [Installing and Configuring IIS 7.0](https://docs.microsoft.com/iis/install/installing-iis-7/installing-necessary-iis-components-on-windows-vista)</span></span>  
  
2. <span data-ttu-id="02d34-115">Erstellen Sie einen neuen Ordner für die Anwendungs Dateien namens "IISHostedCalcService", stellen Sie sicher, dass ASP.net auf den Inhalt des Ordners zugreifen kann, und erstellen Sie mit dem IIS-Verwaltungs Tool eine neue IIS-Anwendung, die sich physisch in diesem Anwendungsverzeichnis befindet.</span><span class="sxs-lookup"><span data-stu-id="02d34-115">Create a new folder for your application files called "IISHostedCalcService", ensure that ASP.NET has access to the contents of the folder, and use the IIS management tool to create a new IIS application that is physically located in this application directory.</span></span> <span data-ttu-id="02d34-116">Verwenden Sie "IISHostedCalc", wenn Sie einen Alias für das Anwendungsverzeichnis erstellen.</span><span class="sxs-lookup"><span data-stu-id="02d34-116">When creating an alias for the application directory use "IISHostedCalc".</span></span>  
  
3. <span data-ttu-id="02d34-117">Erstellen Sie eine neue Datei namens "service.svc" im Anwendungsverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="02d34-117">Create a new file named "service.svc" in the application directory.</span></span> <span data-ttu-id="02d34-118">Bearbeiten Sie diese Datei, indem Sie das folgende-Element hinzufügen @ServiceHost .</span><span class="sxs-lookup"><span data-stu-id="02d34-118">Edit this file by adding the following @ServiceHost element.</span></span>  
  
   ```
   <%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService"%>
   ```  
  
4. <span data-ttu-id="02d34-119">Erstellen Sie im Stammverzeichnis der Anwendung das Unterverzeichnis App_Code.</span><span class="sxs-lookup"><span data-stu-id="02d34-119">Create an App_Code subdirectory within the application directory.</span></span>  
  
5. <span data-ttu-id="02d34-120">Erstellen Sie eine Codedatei namens "Service.svc" im Unterverzeichnis "App_Code".</span><span class="sxs-lookup"><span data-stu-id="02d34-120">Create a code file named Service.cs in the App_Code subdirectory.</span></span>  
  
6. <span data-ttu-id="02d34-121">Fügen Sie am Anfang der Datei "Service.cs" die folgenden using-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="02d34-121">Add the following using statements to the top of the Service.cs file.</span></span>  
  
    ```csharp  
    using System;  
    using System.ServiceModel;  
    ```  
  
7. <span data-ttu-id="02d34-122">Fügen Sie nach den using-Anweisungen die folgende Namespacedeklaration hinzu.</span><span class="sxs-lookup"><span data-stu-id="02d34-122">Add the following namespace declaration after the using statements.</span></span>  
  
    ```csharp  
    namespace Microsoft.ServiceModel.Samples  
    {  
    }  
    ```  
  
8. <span data-ttu-id="02d34-123">Definieren Sie den Dienstvertrag in der Namespacedeklaration, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="02d34-123">Define the service contract inside the namespace declaration as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInIIS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#11)]
     [!code-vb[c_HowTo_HostInIIS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#11)]  
  
9. <span data-ttu-id="02d34-124">Implementieren Sie den Dienstvertrag nach der Dienstvertragsdefinition, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="02d34-124">Implement the service contract after the service contract definition as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInIIS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#12)]
     [!code-vb[c_HowTo_HostInIIS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#12)]  
  
10. <span data-ttu-id="02d34-125">Erstellen Sie eine Datei namens "Web.config" im Anwendungsverzeichnis, und fügen Sie der Datei den folgenden Konfigurationscode hinzu.</span><span class="sxs-lookup"><span data-stu-id="02d34-125">Create a file named "Web.config" in the application directory and add the following configuration code into the file.</span></span> <span data-ttu-id="02d34-126">Zur Laufzeit verwendet die WCF-Infrastruktur die Informationen, um einen Endpunkt zu erstellen, mit dem Client Anwendungen kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="02d34-126">At runtime, the WCF infrastructure uses the information to construct an endpoint that client applications can communicate with.</span></span>  
  
     [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]
  
     <span data-ttu-id="02d34-127">In diesem Beispiel werden die Endpunkte in der Konfigurationsdatei explizit angegeben.</span><span class="sxs-lookup"><span data-stu-id="02d34-127">This example explicitly specifies endpoints in the configuration file.</span></span> <span data-ttu-id="02d34-128">Wenn Sie dem Dienst keine Endpunkte hinzufügen, werden von der Runtime automatisch Standardendpunkte hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="02d34-128">If you do not add any endpoints to the service, the runtime adds default endpoints for you.</span></span> <span data-ttu-id="02d34-129">Weitere Informationen zu Standard Endpunkten, Bindungen und Verhaltensweisen finden Sie in der [vereinfachten Konfiguration](../simplified-configuration.md) und [vereinfachten Konfiguration für WCF-Dienste](../samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="02d34-129">For more information about default endpoints, bindings, and behaviors see [Simplified Configuration](../simplified-configuration.md) and [Simplified Configuration for WCF Services](../samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
11. <span data-ttu-id="02d34-130">Um sicherzustellen, dass der Dienst korrekt gehostet wird, öffnen Sie eine Instanz von Internet Explorer, und navigieren Sie zur URL des Diensts: `http://localhost/IISHostedCalc/Service.svc`</span><span class="sxs-lookup"><span data-stu-id="02d34-130">To make sure the service is hosted correctly, open an instance of Internet Explorer and browse to the service's URL: `http://localhost/IISHostedCalc/Service.svc`</span></span>  
  
## <a name="example"></a><span data-ttu-id="02d34-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="02d34-131">Example</span></span>  
 <span data-ttu-id="02d34-132">Im Folgenden finden Sie eine vollständige Auflistung des Codes für den von IIS gehosteten Dienst.</span><span class="sxs-lookup"><span data-stu-id="02d34-132">The following is a complete listing of the code for the IIS hosted calculator service.</span></span>  
  
 [!code-csharp[C_HowTo_HostInIIS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#1)]
 [!code-vb[C_HowTo_HostInIIS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#1)]
 [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]  
  
## <a name="see-also"></a><span data-ttu-id="02d34-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="02d34-133">See also</span></span>

- [<span data-ttu-id="02d34-134">Hosten in Internetinformationsdiensten</span><span class="sxs-lookup"><span data-stu-id="02d34-134">Hosting in Internet Information Services</span></span>](hosting-in-internet-information-services.md)
- [<span data-ttu-id="02d34-135">Hosting-Dienste</span><span class="sxs-lookup"><span data-stu-id="02d34-135">Hosting Services</span></span>](../hosting-services.md)
- [<span data-ttu-id="02d34-136">WCF-Dienste und ASP.NET</span><span class="sxs-lookup"><span data-stu-id="02d34-136">WCF Services and ASP.NET</span></span>](wcf-services-and-aspnet.md)
- [<span data-ttu-id="02d34-137">Security</span><span class="sxs-lookup"><span data-stu-id="02d34-137">Security</span></span>](security.md)
- <span data-ttu-id="02d34-138">[Windows Server AppFabric-Hostingfunktionen](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="02d34-138">[Windows Server App Fabric Hosting Features](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span></span>

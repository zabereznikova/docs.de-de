---
title: Kryptografische Flexibilität in WCF-Sicherheit
ms.date: 03/30/2017
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 40f4f8523d5286911216180846e94ec18e40da1c
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33810212"
---
# <a name="cryptographic-agility-in-wcf-security"></a><span data-ttu-id="6608d-102">Kryptografische Flexibilität in WCF-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="6608d-102">Cryptographic Agility in WCF Security</span></span>
<span data-ttu-id="6608d-103">Dieses Beispiel zeigt, wie ein Standard-/benutzerdefinierter Algorithmus ermöglichen eine agile kryptografieimplementierung in Windows Communication Foundation (WCF)-Client und Dienst angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6608d-103">This sample shows how to specify in a standard/custom algorithm to provide a cryptographic agile implementation in a Windows Communication Foundation (WCF) client and service.</span></span> <span data-ttu-id="6608d-104">Das Beispiel besteht aus den folgenden Projekten:</span><span class="sxs-lookup"><span data-stu-id="6608d-104">The sample is composed of the following projects:</span></span>  
  
 <span data-ttu-id="6608d-105">Dienst</span><span class="sxs-lookup"><span data-stu-id="6608d-105">Service</span></span>  
 <span data-ttu-id="6608d-106">Dies ist eine selbst gehostete WCF-Dienst, der implementiert die `ICalculator` -Schnittstelle und sichert den Endpunkt mithilfe der <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> mit sicheren Sitzung und zuverlässige Sitzung deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="6608d-106">This is a self-hosted WCF service that implements the `ICalculator` interface and secures the endpoint using the <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> with secure session and reliable session disabled.</span></span> <span data-ttu-id="6608d-107">Der Dienst definiert eine benutzerdefinierte `SecurityAlgorithmSuite`-Klasse, um die Kryptografiealgorithmen zur Nachrichtensicherheit anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6608d-107">The service defines a custom `SecurityAlgorithmSuite` class to specify the cryptographic algorithms to be used for message security.</span></span>  
  
 <span data-ttu-id="6608d-108">Client</span><span class="sxs-lookup"><span data-stu-id="6608d-108">Client</span></span>  
 <span data-ttu-id="6608d-109">Hierbei handelt es sich um eine WCFclient, die auf den Dienst nach der erfolgreichen Authentifizierung zugreift.</span><span class="sxs-lookup"><span data-stu-id="6608d-109">This is a WCFclient that accesses the service after successful authentication.</span></span> <span data-ttu-id="6608d-110">Er ruft die Vorgänge auf, die von der `ICalculator`-Schnittstelle verfügbar gemacht und vom Dienst implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="6608d-110">It invokes the operations exposed by the `ICalculator` interface and implemented by the service.</span></span> <span data-ttu-id="6608d-111">Vom Client wird zusätzlich die gleiche benutzerdefinierte `SecurityAlgorithmSuite`-Klasse definiert, um die Kryptografiealgorithmen für die Nachrichtensicherheit anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6608d-111">The client also defines the same custom `SecurityAlgorithmSuite` class to specify the cryptographic algorithms to be used for message security.</span></span>  
  
### <a name="to-use-this-sample"></a><span data-ttu-id="6608d-112">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="6608d-112">To use this sample</span></span>  
  
1.  <span data-ttu-id="6608d-113">Öffnen Sie die CryptoAgility-Projektmappe in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6608d-113">Open the CryptoAgility.sln solution in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="6608d-114">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6608d-114">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="6608d-115">Open [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] und navigieren Sie zum Verzeichnis \WCF\Basic\Security\CryptoAgility\Service\bin, und führen Sie die service.exe-Datei mit Administratorberechtigungen aus, indem Sie mit der rechten Maustaste service.exe und auswählen **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="6608d-115">Open [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] and navigate to the \WCF\Basic\Security\CryptoAgility\Service\bin directory and run the service.exe file with administrator privileges by right-clicking service.exe and selecting **Run as administrator**.</span></span>  
  
4.  <span data-ttu-id="6608d-116">Navigieren Sie zum Verzeichnis \WCF\Basic\Security\CryptoAgility\Client\bin, und führen Sie die CLIENT.EXE-Datei wie gewohnt aus.</span><span class="sxs-lookup"><span data-stu-id="6608d-116">Navigate to \WCF\Basic\Security\CryptoAgility\Client\bin directory and run the client.exe file normally.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6608d-117">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="6608d-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6608d-118">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="6608d-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6608d-119">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="6608d-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6608d-120">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="6608d-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`  
  
## <a name="see-also"></a><span data-ttu-id="6608d-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6608d-121">See Also</span></span>  
 [<span data-ttu-id="6608d-122">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="6608d-122">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)

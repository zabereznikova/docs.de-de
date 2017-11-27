---
title: "Kryptografische Flexibilität in WCF-Sicherheit"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
caps.latest.revision: "9"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 8b07b23f4428053964fa33150c4300645242f918
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="cryptographic-agility-in-wcf-security"></a><span data-ttu-id="552fa-102">Kryptografische Flexibilität in WCF-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="552fa-102">Cryptographic Agility in WCF Security</span></span>
<span data-ttu-id="552fa-103">In diesem Beispiel wird gezeigt, wie ein Standard-/benutzerdefinierter Algorithmus angegeben wird, um eine agile Kryptografieimplementierung in einem [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Client und -Dienst bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="552fa-103">This sample shows how to specify in a standard/custom algorithm to provide a cryptographic agile implementation in a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client and service.</span></span> <span data-ttu-id="552fa-104">Das Beispiel besteht aus den folgenden Projekten:</span><span class="sxs-lookup"><span data-stu-id="552fa-104">The sample is composed of the following projects:</span></span>  
  
 <span data-ttu-id="552fa-105">Dienst</span><span class="sxs-lookup"><span data-stu-id="552fa-105">Service</span></span>  
 <span data-ttu-id="552fa-106">Dies ist eine selbst gehostete [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Dienst, implementiert die `ICalculator` -Schnittstelle und sichert den Endpunkt mithilfe der <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> mit sicheren Sitzung und zuverlässige Sitzung deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="552fa-106">This is a self-hosted [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service that implements the `ICalculator` interface and secures the endpoint using the <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> with secure session and reliable session disabled.</span></span> <span data-ttu-id="552fa-107">Der Dienst definiert eine benutzerdefinierte `SecurityAlgorithmSuite`-Klasse, um die Kryptografiealgorithmen zur Nachrichtensicherheit anzugeben.</span><span class="sxs-lookup"><span data-stu-id="552fa-107">The service defines a custom `SecurityAlgorithmSuite` class to specify the cryptographic algorithms to be used for message security.</span></span>  
  
 <span data-ttu-id="552fa-108">Client</span><span class="sxs-lookup"><span data-stu-id="552fa-108">Client</span></span>  
 <span data-ttu-id="552fa-109">Hierbei handelt es sich um einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client, der nach erfolgreicher Authentifizierung auf den Dienst zugreift.</span><span class="sxs-lookup"><span data-stu-id="552fa-109">This is a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]client that accesses the service after successful authentication.</span></span> <span data-ttu-id="552fa-110">Er ruft die Vorgänge auf, die von der `ICalculator`-Schnittstelle verfügbar gemacht und vom Dienst implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="552fa-110">It invokes the operations exposed by the `ICalculator` interface and implemented by the service.</span></span> <span data-ttu-id="552fa-111">Vom Client wird zusätzlich die gleiche benutzerdefinierte `SecurityAlgorithmSuite`-Klasse definiert, um die Kryptografiealgorithmen für die Nachrichtensicherheit anzugeben.</span><span class="sxs-lookup"><span data-stu-id="552fa-111">The client also defines the same custom `SecurityAlgorithmSuite` class to specify the cryptographic algorithms to be used for message security.</span></span>  
  
### <a name="to-use-this-sample"></a><span data-ttu-id="552fa-112">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="552fa-112">To use this sample</span></span>  
  
1.  <span data-ttu-id="552fa-113">Öffnen Sie die CryptoAgility-Projektmappe in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="552fa-113">Open the CryptoAgility.sln solution in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="552fa-114">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="552fa-114">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="552fa-115">Open [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] und navigieren Sie zum Verzeichnis \WCF\Basic\Security\CryptoAgility\Service\bin, und führen Sie die service.exe-Datei mit Administratorberechtigungen aus, indem Sie mit der rechten Maustaste service.exe und auswählen **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="552fa-115">Open [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] and navigate to the \WCF\Basic\Security\CryptoAgility\Service\bin directory and run the service.exe file with administrator privileges by right-clicking service.exe and selecting **Run as administrator**.</span></span>  
  
4.  <span data-ttu-id="552fa-116">Navigieren Sie zum Verzeichnis \WCF\Basic\Security\CryptoAgility\Client\bin, und führen Sie die CLIENT.EXE-Datei wie gewohnt aus.</span><span class="sxs-lookup"><span data-stu-id="552fa-116">Navigate to \WCF\Basic\Security\CryptoAgility\Client\bin directory and run the client.exe file normally.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="552fa-117">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="552fa-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="552fa-118">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="552fa-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="552fa-119">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="552fa-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="552fa-120">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="552fa-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`  
  
## <a name="see-also"></a><span data-ttu-id="552fa-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="552fa-121">See Also</span></span>  
 [<span data-ttu-id="552fa-122">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="552fa-122">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)

---
title: Kryptografische Flexibilität in WCF-Sicherheit
ms.date: 03/30/2017
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
author: BrucePerlerMS
ms.openlocfilehash: ebc1b51e2e16f1414f2ed1f4a49a69e26583a17b
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48579457"
---
# <a name="cryptographic-agility-in-wcf-security"></a><span data-ttu-id="d7d16-102">Kryptografische Flexibilität in WCF-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d7d16-102">Cryptographic Agility in WCF Security</span></span>
<span data-ttu-id="d7d16-103">Dieses Beispiel zeigt, wie ein Standard-/benutzerdefinierter Algorithmus eine agile kryptografieimplementierung in einem Windows Communication Foundation (WCF)-Client und Dienst bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d7d16-103">This sample shows how to specify in a standard/custom algorithm to provide a cryptographic agile implementation in a Windows Communication Foundation (WCF) client and service.</span></span> <span data-ttu-id="d7d16-104">Das Beispiel besteht aus den folgenden Projekten:</span><span class="sxs-lookup"><span data-stu-id="d7d16-104">The sample is composed of the following projects:</span></span>

 <span data-ttu-id="d7d16-105">Dienst Hierbei handelt es sich um einen selbst gehosteten WCF-Dienst, implementiert die `ICalculator` Schnittstelle und sichert den Endpunkt mithilfe der <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> mit der sicheren Sitzung und zuverlässige Sitzung deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="d7d16-105">Service This is a self-hosted WCF service that implements the `ICalculator` interface and secures the endpoint using the <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> with secure session and reliable session disabled.</span></span> <span data-ttu-id="d7d16-106">Der Dienst definiert eine benutzerdefinierte `SecurityAlgorithmSuite`-Klasse, um die Kryptografiealgorithmen zur Nachrichtensicherheit anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d7d16-106">The service defines a custom `SecurityAlgorithmSuite` class to specify the cryptographic algorithms to be used for message security.</span></span>

 <span data-ttu-id="d7d16-107">Client dies ist eine WCFclient, die nach der erfolgreichen Authentifizierung auf den Dienst zugreift.</span><span class="sxs-lookup"><span data-stu-id="d7d16-107">Client This is a WCFclient that accesses the service after successful authentication.</span></span> <span data-ttu-id="d7d16-108">Er ruft die Vorgänge auf, die von der `ICalculator`-Schnittstelle verfügbar gemacht und vom Dienst implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="d7d16-108">It invokes the operations exposed by the `ICalculator` interface and implemented by the service.</span></span> <span data-ttu-id="d7d16-109">Vom Client wird zusätzlich die gleiche benutzerdefinierte `SecurityAlgorithmSuite`-Klasse definiert, um die Kryptografiealgorithmen für die Nachrichtensicherheit anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d7d16-109">The client also defines the same custom `SecurityAlgorithmSuite` class to specify the cryptographic algorithms to be used for message security.</span></span>

### <a name="to-use-this-sample"></a><span data-ttu-id="d7d16-110">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="d7d16-110">To use this sample</span></span>

1.  <span data-ttu-id="d7d16-111">Öffnen Sie die Cryptoagility-Projektmappe in Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="d7d16-111">Open the CryptoAgility.sln solution in Visual Studio 2012.</span></span>

2.  <span data-ttu-id="d7d16-112">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d7d16-112">Press CTRL+SHIFT+B to build the solution.</span></span>

3.  <span data-ttu-id="d7d16-113">Open [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] navigieren Sie zum Verzeichnis \WCF\Basic\Security\CryptoAgility\Service\bin, und führen Sie die service.exe-Datei mit Administratorberechtigungen aus, indem Sie mit der rechten Maustaste service.exe und auswählen **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d7d16-113">Open [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] and navigate to the \WCF\Basic\Security\CryptoAgility\Service\bin directory and run the service.exe file with administrator privileges by right-clicking service.exe and selecting **Run as administrator**.</span></span>

4.  <span data-ttu-id="d7d16-114">Navigieren Sie zum Verzeichnis \WCF\Basic\Security\CryptoAgility\Client\bin, und führen Sie die CLIENT.EXE-Datei wie gewohnt aus.</span><span class="sxs-lookup"><span data-stu-id="d7d16-114">Navigate to \WCF\Basic\Security\CryptoAgility\Client\bin directory and run the client.exe file normally.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="d7d16-115">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="d7d16-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d7d16-116">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="d7d16-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d7d16-117">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="d7d16-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d7d16-118">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d7d16-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`  
  
## <a name="see-also"></a><span data-ttu-id="d7d16-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7d16-119">See Also</span></span>  
 [<span data-ttu-id="d7d16-120">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d7d16-120">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)

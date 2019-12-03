---
title: Kryptografische Agilität in der WCF-Sicherheit
ms.date: 03/30/2017
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
ms.openlocfilehash: 2dbacd53876ded76ea212dd5656cd2dded4a6e48
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714925"
---
# <a name="cryptographic-agility-in-wcf-security"></a><span data-ttu-id="2036b-102">Kryptografische Agilität in der WCF-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="2036b-102">Cryptographic agility in WCF security</span></span>

<span data-ttu-id="2036b-103">In diesem Beispiel wird gezeigt, wie in einem standardmäßigen/benutzerdefinierten Algorithmus angegeben wird, um eine kryptografische Agile-Implementierung in einem Windows Communication Foundation (WCF)-Client und-Dienst bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="2036b-103">This sample shows how to specify in a standard/custom algorithm to provide a cryptographic agile implementation in a Windows Communication Foundation (WCF) client and service.</span></span> <span data-ttu-id="2036b-104">Das Beispiel besteht aus den folgenden Projekten:</span><span class="sxs-lookup"><span data-stu-id="2036b-104">The sample is composed of the following projects:</span></span>

<span data-ttu-id="2036b-105">**Dienst**</span><span class="sxs-lookup"><span data-stu-id="2036b-105">**Service**</span></span>

<span data-ttu-id="2036b-106">Dabei handelt es sich um einen selbst gehosteten WCF-Dienst, der die `ICalculator`-Schnittstelle implementiert und den Endpunkt mithilfe der <xref:System.ServiceModel.WSHttpBinding> mit deaktivierter sicherer Sitzung und zuverlässiger Sitzung sichert.</span><span class="sxs-lookup"><span data-stu-id="2036b-106">This is a self-hosted WCF service that implements the `ICalculator` interface and secures the endpoint using the <xref:System.ServiceModel.WSHttpBinding> with secure session and reliable session disabled.</span></span> <span data-ttu-id="2036b-107">Der Dienst definiert eine benutzerdefinierte `SecurityAlgorithmSuite`-Klasse, um die Kryptografiealgorithmen zur Nachrichtensicherheit anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2036b-107">The service defines a custom `SecurityAlgorithmSuite` class to specify the cryptographic algorithms to be used for message security.</span></span>

<span data-ttu-id="2036b-108">**Client**</span><span class="sxs-lookup"><span data-stu-id="2036b-108">**Client**</span></span>

<span data-ttu-id="2036b-109">Dies ist ein WCF-Client, der nach erfolgreicher Authentifizierung auf den Dienst zugreift.</span><span class="sxs-lookup"><span data-stu-id="2036b-109">This is a WCF client that accesses the service after successful authentication.</span></span> <span data-ttu-id="2036b-110">Er ruft die Vorgänge auf, die von der `ICalculator`-Schnittstelle verfügbar gemacht und vom Dienst implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="2036b-110">It invokes the operations exposed by the `ICalculator` interface and implemented by the service.</span></span> <span data-ttu-id="2036b-111">Vom Client wird zusätzlich die gleiche benutzerdefinierte `SecurityAlgorithmSuite`-Klasse definiert, um die Kryptografiealgorithmen für die Nachrichtensicherheit anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2036b-111">The client also defines the same custom `SecurityAlgorithmSuite` class to specify the cryptographic algorithms to be used for message security.</span></span>

## <a name="to-use-this-sample"></a><span data-ttu-id="2036b-112">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="2036b-112">To use this sample</span></span>

1. <span data-ttu-id="2036b-113">Öffnen Sie die Projekt Mappe cryptoagilität. sln in Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="2036b-113">Open the CryptoAgility.sln solution in Visual Studio 2012.</span></span>

2. <span data-ttu-id="2036b-114">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2036b-114">Press CTRL+SHIFT+B to build the solution.</span></span>

3. <span data-ttu-id="2036b-115">Öffnen Sie den Datei-Explorer, navigieren Sie zum Verzeichnis \wcf\basic\security\cryptoagility\service\bin, und führen Sie die Datei Service. exe mit Administratorrechten aus, indem Sie mit der rechten Maustaste auf Service. exe klicken und **als Administrator ausführen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="2036b-115">Open File Explorer and navigate to the \WCF\Basic\Security\CryptoAgility\Service\bin directory and run the service.exe file with administrator privileges by right-clicking service.exe and selecting **Run as administrator**.</span></span>

4. <span data-ttu-id="2036b-116">Navigieren Sie zum Verzeichnis \WCF\Basic\Security\CryptoAgility\Client\bin, und führen Sie die CLIENT.EXE-Datei wie gewohnt aus.</span><span class="sxs-lookup"><span data-stu-id="2036b-116">Navigate to \WCF\Basic\Security\CryptoAgility\Client\bin directory and run the client.exe file normally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2036b-117">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="2036b-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2036b-118">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="2036b-118">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="2036b-119">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="2036b-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2036b-120">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="2036b-120">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`

## <a name="see-also"></a><span data-ttu-id="2036b-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2036b-121">See also</span></span>

- [<span data-ttu-id="2036b-122">Windows Communication Foundation Sicherheit</span><span class="sxs-lookup"><span data-stu-id="2036b-122">Windows Communication Foundation Security</span></span>](../feature-details/security.md)

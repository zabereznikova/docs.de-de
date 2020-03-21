---
title: Beispiel für Workflowsuche
ms.date: 03/30/2017
ms.assetid: 82cc43f1-3c8f-4771-ac19-a75ac936e2c3
ms.openlocfilehash: b3a2d88028f3854746d4e1d2fad80aae4f6be7be
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143485"
---
# <a name="workflow-discovery-sample"></a><span data-ttu-id="ee264-102">Beispiel für Workflowsuche</span><span class="sxs-lookup"><span data-stu-id="ee264-102">Workflow Discovery Sample</span></span>
<span data-ttu-id="ee264-103">Dieses Beispiel veranschaulicht, wie ein Workflowdienst erkennbar gemacht wird, und wie eine benutzerdefinierte Codeaktivität erstellt wird, die nach einem bestimmten Dienst sucht.</span><span class="sxs-lookup"><span data-stu-id="ee264-103">This sample demonstrates how to make a workflow service discoverable and how to author a custom code activity that searches for a particular service.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="ee264-104">Zeigt</span><span class="sxs-lookup"><span data-stu-id="ee264-104">Demonstrates</span></span>  
 <span data-ttu-id="ee264-105">Suchaktivität und Workflowverwendung</span><span class="sxs-lookup"><span data-stu-id="ee264-105">Discovery Find Activity and Workflow Usage</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="ee264-106">Diskussion</span><span class="sxs-lookup"><span data-stu-id="ee264-106">Discussion</span></span>  
 <span data-ttu-id="ee264-107">Im ersten Teil des Beispiels wird ein Workflowdienst mithilfe der Konfiguration erkennbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="ee264-107">In the first part of the sample, a workflow service is made discoverable using configuration.</span></span> <span data-ttu-id="ee264-108">Die Konfiguration kann auch verwendet werden, um den Dienst mit benutzerdefinierten Metadaten (z. B. Bereiche) ordnungsgemäß anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="ee264-108">Configuration can also be used to apply the service appropriately with custom metadata (such as scopes).</span></span> <span data-ttu-id="ee264-109">Im Beispiel wird eine benutzerdefinierte Codeaktivität für den Client verwendet, die mit dem Suchdienst nach einem Dienst sucht, der mit einem bestimmten Vertrag übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="ee264-109">On the client, the sample uses a custom code activity, which uses Discovery to search for a service matching a particular contract.</span></span> <span data-ttu-id="ee264-110">Die Codeaktivität gibt einen URI aus, der später von einer Sendeaktivität verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ee264-110">The code activity outputs a URI, which is later used by a send activity.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ee264-111">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="ee264-111">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="ee264-112">In diesem Beispiel werden HTTP-Endpunkte verwendet, für die die Ausführung über die richtigen URL-ACLs verfügen muss (Details finden Sie unter [Konfigurieren von HTTP und HTTPS).](../feature-details/configuring-http-and-https.md)</span><span class="sxs-lookup"><span data-stu-id="ee264-112">This sample uses HTTP endpoints, which must have proper URL ACLs to run (see [Configuring HTTP and HTTPS](../feature-details/configuring-http-and-https.md) for details).</span></span> <span data-ttu-id="ee264-113">Wenn der folgende Befehl an einer Eingabeaufforderung auf höherer Ebene ausgeführt wird, sollten die entsprechenden ACLs hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="ee264-113">Executing the following command at an elevated command prompt should add the appropriate ACLs.</span></span> <span data-ttu-id="ee264-114">Wenn Ihre Shell das Variablenformat nicht versteht, ersetzen Sie Ihre Domäne und Ihren Benutzernamen durch die folgenden Argumente.</span><span class="sxs-lookup"><span data-stu-id="ee264-114">If your shell does not understand the variable format, substitute your Domain and Username for the following arguments.</span></span>  
  
     <span data-ttu-id="ee264-115">**netsh http urlaclhttp://+:8000/ url= user=%DOMAIN%\\%UserName%**</span><span class="sxs-lookup"><span data-stu-id="ee264-115">**netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\\%UserName%**</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ee264-116">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="ee264-116">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ee264-117">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="ee264-117">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="ee264-118">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="ee264-118">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ee264-119">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="ee264-119">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\WorkflowDiscovery`

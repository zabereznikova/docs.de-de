---
title: XAML-Aktivierung
ms.date: 03/30/2017
ms.assetid: 486760e2-bb10-4ed5-8c02-fe7472498d2d
ms.openlocfilehash: 8621b0ea7b390c81e76ac7eeedb0b547b44320d7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517711"
---
# <a name="xaml-activation"></a><span data-ttu-id="9389b-102">XAML-Aktivierung</span><span class="sxs-lookup"><span data-stu-id="9389b-102">XAML Activation</span></span>
<span data-ttu-id="9389b-103">In diesem Beispiel wird veranschaulicht, wie ein deklarativer Workflow in IIS gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="9389b-103">This sample demonstrates how to host a declarative workflow in IIS.</span></span> <span data-ttu-id="9389b-104">Das Beispiel umfasst den grundlegenden Workflow `EchoService` mit einem Vorgang.</span><span class="sxs-lookup"><span data-stu-id="9389b-104">The sample is a basic workflow called `EchoService` that has one operation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9389b-105">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="9389b-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9389b-106">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="9389b-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9389b-107">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie (Downloadseite) auf allen Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="9389b-107">If this directory does not exist, go to (download page) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9389b-108">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="9389b-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\XAMLActivation`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="9389b-109">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="9389b-109">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="9389b-110">Öffnen Sie die Projektmappe "XAMLActivation.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9389b-110">Open the XAMLActivation.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="9389b-111">Erstellen Sie die Projektmappe durch Drücken von **F5**.</span><span class="sxs-lookup"><span data-stu-id="9389b-111">Build the solution by pressing **F5**.</span></span>  
  
3.  <span data-ttu-id="9389b-112">Führen Sie WcfTestClient.exe aus.</span><span class="sxs-lookup"><span data-stu-id="9389b-112">Run WcfTestClient.exe.</span></span> <span data-ttu-id="9389b-113">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9389b-113">From a command prompt, type in the following:</span></span>  
  
    1.  <span data-ttu-id="9389b-114">cd %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE</span><span class="sxs-lookup"><span data-stu-id="9389b-114">cd %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE</span></span>  
  
    2.  <span data-ttu-id="9389b-115">Führen Sie WcfTestClient.exe aus.</span><span class="sxs-lookup"><span data-stu-id="9389b-115">Run WcfTestClient.exe.</span></span>  
  
4.  <span data-ttu-id="9389b-116">Legen Sie die Adresse des Diensts auf WcfTestClient.exe, indem Sie STRG + UMSCHALT + A drücken und die Dienstadresse auf http://localhost:56133/Service.xamlx.</span><span class="sxs-lookup"><span data-stu-id="9389b-116">Set the address of the service on WcfTestClient.exe by pressing CTRL+SHIFT+A and setting the service address to http://localhost:56133/Service.xamlx.</span></span>  
  
5.  <span data-ttu-id="9389b-117">Führen Sie den Echo-Vorgang aus, um den Dienst zu testen.</span><span class="sxs-lookup"><span data-stu-id="9389b-117">Perform the echo operation to test the service.</span></span>  
  
6.  <span data-ttu-id="9389b-118">Stellen Sie den Dienst in IIS mithilfe von DeployToIIS.Bat an einer Eingabeaufforderung mit Administratorrechten bereit.</span><span class="sxs-lookup"><span data-stu-id="9389b-118">Deploy the Service in IIS using DeployToIIS.Bat in a command prompt with administrator privileges.</span></span>  
  
7.  <span data-ttu-id="9389b-119">Aktualisieren Sie die Dienstadresse auf dem Client http://localhost/XAMLActivation/Service.xamlx und Testen Sie den Dienst erneut mit WcfTestClient.exe.</span><span class="sxs-lookup"><span data-stu-id="9389b-119">Update the service address in the client to http://localhost/XAMLActivation/Service.xamlx and test the service again using WcfTestClient.exe.</span></span>

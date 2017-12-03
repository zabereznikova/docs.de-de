---
title: "Einfacher nur XAML-fähiger Dienst"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c106feb0-0245-43b5-aefe-93ce0e4d38eb
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 06a302b13db3b82dabb43989ac272df0d9aac008
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="basic-xaml-only-service"></a><span data-ttu-id="151fc-102">Einfacher nur XAML-fähiger Dienst</span><span class="sxs-lookup"><span data-stu-id="151fc-102">Basic XAML only Service</span></span>
<span data-ttu-id="151fc-103">In diesem Beispiel wird veranschaulicht, wie ein nur XAML-fähiger Dienst erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="151fc-103">This sample demonstrates how to create a XAML only service.</span></span> <span data-ttu-id="151fc-104">Das Szenario ist ein Diagnosedienst für Probleme bei Fahrzeugen.</span><span class="sxs-lookup"><span data-stu-id="151fc-104">The scenario is a diagnostics service for car-related problems.</span></span> <span data-ttu-id="151fc-105">Der Dienst wird als Workflow implementiert, der dem Client eine Reihe von Fragen stellt, um das Problem zu diagnostizieren.</span><span class="sxs-lookup"><span data-stu-id="151fc-105">The service is implemented as a workflow that asks the client a series of questions to diagnose the problem.</span></span> <span data-ttu-id="151fc-106">Es gibt zwei Arten von Problemen, die der Dienst diagnostizieren kann (Auto startet nicht oder Klimaanlage funktioniert nicht).</span><span class="sxs-lookup"><span data-stu-id="151fc-106">There are two types of issues the service can diagnose (car does not start or air conditioning not working).</span></span> <span data-ttu-id="151fc-107">Der Workflow macht mithilfe der Anforderungs-/Antwortvorlage aus dem Designer drei einfache Dienstvorgänge verfügbar.</span><span class="sxs-lookup"><span data-stu-id="151fc-107">The workflow uses Request/Reply template from the designer to expose three simple service operations.</span></span> <span data-ttu-id="151fc-108">Der Dienst wird in IIS gehostet, indem ein virtuelles Verzeichnis in IIS erstellt und die Dateien service1.xamlx und Web.config in das virtuelle Verzeichnis kopiert werden. Es ist kein kompilierter Code erforderlich.</span><span class="sxs-lookup"><span data-stu-id="151fc-108">The service is hosted in IIS by creating a virtual directory in IIS and copying the service1.xamlx and Web.config files into the virtual directory, no compiled code is required.</span></span> <span data-ttu-id="151fc-109">Standardmäßig in diesem Beispiel wird automatisch kopieren die benötigten Dateien in das virtuelle Verzeichnis erstellt, wenn Sie den Setup-für die WCF- und WF-Beispiele Anweisungen: [zum einmaligen Setupprozedur für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) Wenn in der Visual Studio 2010 erstellt.</span><span class="sxs-lookup"><span data-stu-id="151fc-109">By default this sample will automatically copy the needed files into the virtual directory created when you follow the setup instructions for the WCF and WF samples: [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) when built in Visual Studio 2010.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="151fc-110">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="151fc-110">To use this sample</span></span>  
  
1.  <span data-ttu-id="151fc-111">Laden Sie die Projektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], und erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="151fc-111">Load the project solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="151fc-112">Führen Sie die unter "[Projektmappenbasisverzeichnis] \Client\bin\debug" generierte Clientanwendung aus.</span><span class="sxs-lookup"><span data-stu-id="151fc-112">Run the Client application generated in [solution base directory]\Client\bin\debug.</span></span>  
  
3.  <span data-ttu-id="151fc-113">Die Anwendung druckt Optionen aus und aktiviert eine Option.</span><span class="sxs-lookup"><span data-stu-id="151fc-113">The application prints out options, selects an option.</span></span> <span data-ttu-id="151fc-114">Die Anwendung stellt dann einige Fragen; beantworten Sie diese (mithilfe der J/N-Tasten) mit Ja oder Nein.</span><span class="sxs-lookup"><span data-stu-id="151fc-114">The application then asks some questions, answer them yes or no (using Y/N keys).</span></span> <span data-ttu-id="151fc-115">Wenn der Dienst mit der Diagnose der Probleme fertig ist, druckt die Anwendung eine Diagnose aus.</span><span class="sxs-lookup"><span data-stu-id="151fc-115">When the service is done diagnosing the issues, the application prints out a diagnosis.</span></span>  
  
4.  <span data-ttu-id="151fc-116">Die Anwendung wechselt zu den Optionen zurück.</span><span class="sxs-lookup"><span data-stu-id="151fc-116">The application goes back to the options.</span></span> <span data-ttu-id="151fc-117">Sie können ein anderes Problem diagnostizieren oder die Anwendung beenden.</span><span class="sxs-lookup"><span data-stu-id="151fc-117">You can diagnose another problem or exit the application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="151fc-118">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="151fc-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="151fc-119">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="151fc-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="151fc-120">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="151fc-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="151fc-121">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="151fc-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\XAMLService`
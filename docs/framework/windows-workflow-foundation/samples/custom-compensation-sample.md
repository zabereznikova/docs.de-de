---
title: "Beispiel für benutzerdefinierte Kompensationslogik"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 385920da-9284-44bf-9fe9-0d87c7478ec5
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4ace7d38a456bb9d7f5dd59776b9ae5843b7b651
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="custom-compensation-sample"></a><span data-ttu-id="c5b47-102">Beispiel für benutzerdefinierte Kompensationslogik</span><span class="sxs-lookup"><span data-stu-id="c5b47-102">Custom Compensation Sample</span></span>
<span data-ttu-id="c5b47-103">In diesem Beispiel wird gezeigt, wie <xref:System.Activities.Statements.CompensableActivity> und der zugehörige Kompensierungshandler zur Definition benutzerdefinierter Kompensierungslogik verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c5b47-103">This sample shows how to use <xref:System.Activities.Statements.CompensableActivity> and its compensation handler to define custom compensation logic.</span></span> <span data-ttu-id="c5b47-104">Das Szenario in diesem Beispiel ist eine LKW-Vermietung.</span><span class="sxs-lookup"><span data-stu-id="c5b47-104">The scenario modeled in this sample is a Truck Rental Agency.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="c5b47-105">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="c5b47-105">Sample Details</span></span>  
 <span data-ttu-id="c5b47-106">Die folgenden Schritte werden simuliert:</span><span class="sxs-lookup"><span data-stu-id="c5b47-106">The steps simulated are:</span></span>  
  
1.  <span data-ttu-id="c5b47-107">Der Benutzer fordert Mietangebote für ein bestimmtes Datum an.</span><span class="sxs-lookup"><span data-stu-id="c5b47-107">The user requests truck rental quotes for a given date.</span></span>  
  
2.  <span data-ttu-id="c5b47-108">Drei LKW-Unternehmen werden kontaktiert und drei Angebote bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c5b47-108">Three truck companies are contacted and the three quotes are provided.</span></span>  
  
3.  <span data-ttu-id="c5b47-109">Der Benutzer wählt ein Angebot aus und führt die Bestellung per Kreditkarte durch.</span><span class="sxs-lookup"><span data-stu-id="c5b47-109">The user selects one truck quote and proceeds to order by credit card.</span></span>  
  
4.  <span data-ttu-id="c5b47-110">Die Anwendung bricht die anderen beiden Angebote ab.</span><span class="sxs-lookup"><span data-stu-id="c5b47-110">The application cancels the other two truck quotes.</span></span>  
  
5.  <span data-ttu-id="c5b47-111">Die Anwendung erhebt eine Dienstgebühr, die für Benutzer ohne Premium-Konto nicht erstattet werden kann, wenn eine Stornierung zehn Tage oder weniger vor dem reservierten Termin erfolgt.</span><span class="sxs-lookup"><span data-stu-id="c5b47-111">The application charges a service fee that is non-refundable for non-premium accounts if cancelation happens 10 days or less prior to the reservation date.</span></span>  
  
6.  <span data-ttu-id="c5b47-112">Die Anwendung stellt die LKW-Mietgebühr in Rechnung.</span><span class="sxs-lookup"><span data-stu-id="c5b47-112">The application charges the truck rental fee.</span></span>  
  
7.  <span data-ttu-id="c5b47-113">Die Anwendung wartet bis zum reservierten Datum bzw. bis sich der Kunde entscheidet, den Reservierungsvorgang abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="c5b47-113">The application waits until the reservation date or until the customer decided to cancel the reservation, whichever comes first.</span></span>  
  
8.  <span data-ttu-id="c5b47-114">Wenn der Kunde den Reservierungsvorgang abbricht, wird der benutzerdefinierte <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>-Code nach der folgenden Logik ausführt:</span><span class="sxs-lookup"><span data-stu-id="c5b47-114">If the customer cancels the reservation, the <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> custom compensation logic runs according to the following logic:</span></span>  
  
    1.  <span data-ttu-id="c5b47-115">Wenn der Kunde nicht über ein Premium-Konto verfügt und die Reservierung weniger als zehn Tage vor dem reservierten Datum storniert, wird die Dienstgebühr in Rechnung gestellt. Andernfalls erstattet die Anwendung die Dienstgebühr.</span><span class="sxs-lookup"><span data-stu-id="c5b47-115">If the customer has a non-premium account and it is less than 10 days prior to the reservation date, then the service fee is still charged; otherwise, the application refunds the service fee.</span></span>  
  
    2.  <span data-ttu-id="c5b47-116">Die weiteren kompensierbaren Aktivitäten (LKW-Bestellung + LKW-Gebühr) werden nach der Standardkompensierungslogik ausgeführt, d. h. in umgekehrter Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="c5b47-116">The rest of the compensable activities (truck order + truck order fee) are run according to the default compensation logic, which is to compensate in reverse order of execution.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c5b47-117">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="c5b47-117">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="c5b47-118">Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "CustomCompensation.sln".</span><span class="sxs-lookup"><span data-stu-id="c5b47-118">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the CustomCompensation.sln solution.</span></span> <span data-ttu-id="c5b47-119">Sie befindet sich im Verzeichnis \WF\Basic\Compensation\CustomCompensation.</span><span class="sxs-lookup"><span data-stu-id="c5b47-119">It is located in the \WF\Basic\Compensation\CustomCompensation directory.</span></span>  
  
2.  <span data-ttu-id="c5b47-120">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c5b47-120">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="c5b47-121">Drücken Sie STRG+F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c5b47-121">Press CTRL + F5 to run the application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c5b47-122">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="c5b47-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c5b47-123">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="c5b47-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c5b47-124">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="c5b47-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c5b47-125">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c5b47-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\CustomCompensation`
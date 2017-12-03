---
title: "Ablaufverfolgungstyp – Zusammenfassung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c1570832e5f179b6d2685ad33fad743c9530bb16
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="trace-type-summary"></a><span data-ttu-id="1914a-102">Ablaufverfolgungstyp – Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="1914a-102">Trace Type Summary</span></span>
<span data-ttu-id="1914a-103">[Quellebenen](http://go.microsoft.com/fwlink/?LinkID=94943) Definieren verschiedener nachverfolgungsebenen: Kritisch, Fehler, Warnung, Informationen und ausführlich, auch als Beschreibung bietet die `ActivityTracing` -Flag, das die Ausgabe der nachverfolgungsgrenzen und der aktivitätsübertragungsereignisse zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="1914a-103">[Source Levels](http://go.microsoft.com/fwlink/?LinkID=94943) defines various trace levels: Critical, Error, Warning, Information, and Verbose, as well as provides description of the `ActivityTracing` flag, which toggles the output of trace boundary and activity transfer events.</span></span>  
  
 <span data-ttu-id="1914a-104">Sie können auch überprüfen, [TraceEventType](http://go.microsoft.com/fwlink/?LinkId=95169) für die Typen von ablaufverfolgungstypen, die von ausgegeben werden können <xref:System.Diagnostics>.</span><span class="sxs-lookup"><span data-stu-id="1914a-104">You can also review [TraceEventType](http://go.microsoft.com/fwlink/?LinkId=95169) for the types of traces which can be emitted from <xref:System.Diagnostics>.</span></span>  
  
 <span data-ttu-id="1914a-105">In der folgenden Tabelle werden die Wichtigsten aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="1914a-105">The following table lists the most important ones.</span></span>  
  
|<span data-ttu-id="1914a-106">Ablaufverfolgungstyp</span><span class="sxs-lookup"><span data-stu-id="1914a-106">Trace Type</span></span>|<span data-ttu-id="1914a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1914a-107">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="1914a-108">Kritisch</span><span class="sxs-lookup"><span data-stu-id="1914a-108">Critical</span></span>|<span data-ttu-id="1914a-109">Schwer wiegender Fehler oder Anwendungsabsturz.</span><span class="sxs-lookup"><span data-stu-id="1914a-109">Fatal error or application crash.</span></span>|  
|<span data-ttu-id="1914a-110">Fehler</span><span class="sxs-lookup"><span data-stu-id="1914a-110">Error</span></span>|<span data-ttu-id="1914a-111">Behebbarer Fehler.</span><span class="sxs-lookup"><span data-stu-id="1914a-111">Recoverable error.</span></span>|  
|<span data-ttu-id="1914a-112">Warnung</span><span class="sxs-lookup"><span data-stu-id="1914a-112">Warning</span></span>|<span data-ttu-id="1914a-113">Informationsnachricht.</span><span class="sxs-lookup"><span data-stu-id="1914a-113">Informational message.</span></span>|  
|<span data-ttu-id="1914a-114">Information</span><span class="sxs-lookup"><span data-stu-id="1914a-114">Information</span></span>|<span data-ttu-id="1914a-115">Kein kritisches Problem.</span><span class="sxs-lookup"><span data-stu-id="1914a-115">Non-critical problem.</span></span>|  
|<span data-ttu-id="1914a-116">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="1914a-116">Verbose</span></span>|<span data-ttu-id="1914a-117">Debuggen der Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="1914a-117">Debugging trace.</span></span>|  
|<span data-ttu-id="1914a-118">Starten</span><span class="sxs-lookup"><span data-stu-id="1914a-118">Start</span></span>|<span data-ttu-id="1914a-119">Starten einer logischen Verarbeitungseinheit.</span><span class="sxs-lookup"><span data-stu-id="1914a-119">Starting of a logical unit of processing.</span></span>|  
|<span data-ttu-id="1914a-120">Suspend (Anhalten)</span><span class="sxs-lookup"><span data-stu-id="1914a-120">Suspend</span></span>|<span data-ttu-id="1914a-121">Anhalten einer logischen Verarbeitungseinheit.</span><span class="sxs-lookup"><span data-stu-id="1914a-121">Suspension of a logical unit of processing.</span></span>|  
|<span data-ttu-id="1914a-122">Fortsetzen</span><span class="sxs-lookup"><span data-stu-id="1914a-122">Resume</span></span>|<span data-ttu-id="1914a-123">Fortsetzen einer logischen Verarbeitungseinheit.</span><span class="sxs-lookup"><span data-stu-id="1914a-123">Resumption of a logical unit of processing.</span></span>|  
|<span data-ttu-id="1914a-124">Anhalten</span><span class="sxs-lookup"><span data-stu-id="1914a-124">Stop</span></span>|<span data-ttu-id="1914a-125">Beenden einer logischen Verarbeitungseinheit.</span><span class="sxs-lookup"><span data-stu-id="1914a-125">Stopping of a logical unit of processing.</span></span>|  
|<span data-ttu-id="1914a-126">Übertragung</span><span class="sxs-lookup"><span data-stu-id="1914a-126">Transfer</span></span>|<span data-ttu-id="1914a-127">Ändern der Korrelationsidentität.</span><span class="sxs-lookup"><span data-stu-id="1914a-127">Changing of correlation identity.</span></span>|  
  
 <span data-ttu-id="1914a-128">Eine Aktivität ist als Kombination der oben genannten Ablaufverfolgungstypen definiert.</span><span class="sxs-lookup"><span data-stu-id="1914a-128">An activity is defined as a combination of the trace types above.</span></span>  
  
 <span data-ttu-id="1914a-129">Beim folgenden Beispiel handelt es sich um einen regulären Ausdruck zum Definieren einer idealen Aktivität in einem lokalen Bereich (Ablaufverfolgungsquelle):</span><span class="sxs-lookup"><span data-stu-id="1914a-129">The following is a regular expression that defines an ideal activity in a local (trace source) scope,</span></span>  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 <span data-ttu-id="1914a-130">Das bedeutet, dass eine Aktivität die folgenden Bedingungen erfüllen muss:</span><span class="sxs-lookup"><span data-stu-id="1914a-130">This means that an activity must satisfy the following conditions.</span></span>  
  
-   <span data-ttu-id="1914a-131">Sie muss mithilfe der Starten-Ablaufverfolgung gestartet bzw. mithilfe der Beenden-Ablaufverfolgung beendet werden können.</span><span class="sxs-lookup"><span data-stu-id="1914a-131">It must start and stop respectively by a Start and Stop traces</span></span>  
  
-   <span data-ttu-id="1914a-132">Sie muss eine Übertragen-Ablaufverfolgung besitzen, die direkt vor einer Anhalten- oder einer Fortsetzen-Ablaufverfolgung platziert ist.</span><span class="sxs-lookup"><span data-stu-id="1914a-132">It must have a Transfer trace immediately preceding a Suspend or Resume trace</span></span>  
  
-   <span data-ttu-id="1914a-133">Sie darf keine Ablaufverfolgungen zwischen der Anhalten- und der Fortsetzen-Ablaufverfolgung besitzen, sofern diese beiden Ablaufverfolgungen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="1914a-133">It must not have any traces between the Suspend and Resume traces if such traces exist</span></span>  
  
-   <span data-ttu-id="1914a-134">Sie kann eine beliebige Kombination aus sowie eine beliebige Anzahl von Ablaufverfolgungen des Typs Wichtig/Fehler/Warnung/Information/Verbose/Übertragen besitzen, sofern die oben genannten Bedingungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="1914a-134">It can have any and as many of critical/Error/Warning/Information/Verbose/Transfer traces as long as the previous conditions are observed</span></span>  
  
 <span data-ttu-id="1914a-135">Beim folgenden Beispiel handelt es sich um einen regulären Ausdruck zum Definieren einer idealen Aktivität in einem globalen Bereich:</span><span class="sxs-lookup"><span data-stu-id="1914a-135">The following is a regular expression that defines an ideal activity in the global scope,</span></span>  
  
```  
R+   
```  
  
 <span data-ttu-id="1914a-136">R steht hierbei für den regulären Ausdruck einer Aktivität im lokalen Bereich.</span><span class="sxs-lookup"><span data-stu-id="1914a-136">with R being the regular expression for an activity in the local scope.</span></span> <span data-ttu-id="1914a-137">Dies wird folgendermaßen übersetzt:</span><span class="sxs-lookup"><span data-stu-id="1914a-137">This translates to,</span></span>  
  
```  
[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+  
```

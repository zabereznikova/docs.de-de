---
title: Ablaufverfolgungstyp – Zusammenfassung
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: e8d222d6f093f5db3bd620194bfde7edd4b998a8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96259244"
---
# <a name="trace-type-summary"></a><span data-ttu-id="60bc5-102">Ablaufverfolgungstyp – Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="60bc5-102">Trace Type Summary</span></span>

<span data-ttu-id="60bc5-103">[Quell Ebenen](xref:System.Diagnostics.SourceLevels) definieren verschiedene Ablauf Verfolgungs Ebenen: "kritisch", "Fehler", "Warnung", "Information" und "ausführlich". Außerdem wird eine Beschreibung des Flags bereitstellt `ActivityTracing` , das die Ausgabe von Ablauf Verfolgungs Grenzen und Aktivitäts Übertragungs Ereignissen umschaltet.</span><span class="sxs-lookup"><span data-stu-id="60bc5-103">[Source Levels](xref:System.Diagnostics.SourceLevels) defines various trace levels: Critical, Error, Warning, Information, and Verbose, as well as provides a description of the `ActivityTracing` flag, which toggles the output of trace boundary and activity transfer events.</span></span>  
  
 <span data-ttu-id="60bc5-104">Sie können auch die Ablauf Verfolgungs Typen überprüfen <xref:System.Diagnostics.TraceEventType> , die von ausgegeben werden können <xref:System.Diagnostics> .</span><span class="sxs-lookup"><span data-stu-id="60bc5-104">You can also review <xref:System.Diagnostics.TraceEventType> for the types of traces which can be emitted from <xref:System.Diagnostics>.</span></span>  
  
 <span data-ttu-id="60bc5-105">In der folgenden Tabelle werden die Wichtigsten aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="60bc5-105">The following table lists the most important ones.</span></span>  
  
|<span data-ttu-id="60bc5-106">Ablaufverfolgungstyp</span><span class="sxs-lookup"><span data-stu-id="60bc5-106">Trace Type</span></span>|<span data-ttu-id="60bc5-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="60bc5-107">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="60bc5-108">Kritisch</span><span class="sxs-lookup"><span data-stu-id="60bc5-108">Critical</span></span>|<span data-ttu-id="60bc5-109">Schwer wiegender Fehler oder Anwendungsabsturz.</span><span class="sxs-lookup"><span data-stu-id="60bc5-109">Fatal error or application crash.</span></span>|  
|<span data-ttu-id="60bc5-110">Fehler</span><span class="sxs-lookup"><span data-stu-id="60bc5-110">Error</span></span>|<span data-ttu-id="60bc5-111">Behebbarer Fehler.</span><span class="sxs-lookup"><span data-stu-id="60bc5-111">Recoverable error.</span></span>|  
|<span data-ttu-id="60bc5-112">Warnung</span><span class="sxs-lookup"><span data-stu-id="60bc5-112">Warning</span></span>|<span data-ttu-id="60bc5-113">Informationsmeldung.</span><span class="sxs-lookup"><span data-stu-id="60bc5-113">Informational message.</span></span>|  
|<span data-ttu-id="60bc5-114">Information</span><span class="sxs-lookup"><span data-stu-id="60bc5-114">Information</span></span>|<span data-ttu-id="60bc5-115">Kein kritisches Problem.</span><span class="sxs-lookup"><span data-stu-id="60bc5-115">Non-critical problem.</span></span>|  
|<span data-ttu-id="60bc5-116">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="60bc5-116">Verbose</span></span>|<span data-ttu-id="60bc5-117">Debuggen der Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="60bc5-117">Debugging trace.</span></span>|  
|<span data-ttu-id="60bc5-118">Start</span><span class="sxs-lookup"><span data-stu-id="60bc5-118">Start</span></span>|<span data-ttu-id="60bc5-119">Starten einer logischen Verarbeitungseinheit.</span><span class="sxs-lookup"><span data-stu-id="60bc5-119">Starting of a logical unit of processing.</span></span>|  
|<span data-ttu-id="60bc5-120">Angehalten</span><span class="sxs-lookup"><span data-stu-id="60bc5-120">Suspend</span></span>|<span data-ttu-id="60bc5-121">Anhalten einer logischen Verarbeitungseinheit.</span><span class="sxs-lookup"><span data-stu-id="60bc5-121">Suspension of a logical unit of processing.</span></span>|  
|<span data-ttu-id="60bc5-122">Fortsetzen</span><span class="sxs-lookup"><span data-stu-id="60bc5-122">Resume</span></span>|<span data-ttu-id="60bc5-123">Fortsetzen einer logischen Verarbeitungseinheit.</span><span class="sxs-lookup"><span data-stu-id="60bc5-123">Resumption of a logical unit of processing.</span></span>|  
|<span data-ttu-id="60bc5-124">Beenden</span><span class="sxs-lookup"><span data-stu-id="60bc5-124">Stop</span></span>|<span data-ttu-id="60bc5-125">Beenden einer logischen Verarbeitungseinheit.</span><span class="sxs-lookup"><span data-stu-id="60bc5-125">Stopping of a logical unit of processing.</span></span>|  
|<span data-ttu-id="60bc5-126">Übertragen</span><span class="sxs-lookup"><span data-stu-id="60bc5-126">Transfer</span></span>|<span data-ttu-id="60bc5-127">Ändern der Korrelationsidentität.</span><span class="sxs-lookup"><span data-stu-id="60bc5-127">Changing of correlation identity.</span></span>|  
  
 <span data-ttu-id="60bc5-128">Eine Aktivität ist als Kombination der oben genannten Ablaufverfolgungstypen definiert.</span><span class="sxs-lookup"><span data-stu-id="60bc5-128">An activity is defined as a combination of the trace types above.</span></span>  
  
 <span data-ttu-id="60bc5-129">Beim folgenden Beispiel handelt es sich um einen regulären Ausdruck zum Definieren einer idealen Aktivität in einem lokalen Bereich (Ablaufverfolgungsquelle):</span><span class="sxs-lookup"><span data-stu-id="60bc5-129">The following is a regular expression that defines an ideal activity in a local (trace source) scope,</span></span>  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 <span data-ttu-id="60bc5-130">Das bedeutet, dass eine Aktivität die folgenden Bedingungen erfüllen muss:</span><span class="sxs-lookup"><span data-stu-id="60bc5-130">This means that an activity must satisfy the following conditions.</span></span>  
  
- <span data-ttu-id="60bc5-131">Sie muss mithilfe der Starten-Ablaufverfolgung gestartet bzw. mithilfe der Beenden-Ablaufverfolgung beendet werden können.</span><span class="sxs-lookup"><span data-stu-id="60bc5-131">It must start and stop respectively by a Start and Stop traces</span></span>  
  
- <span data-ttu-id="60bc5-132">Sie muss eine Übertragen-Ablaufverfolgung besitzen, die direkt vor einer Anhalten- oder einer Fortsetzen-Ablaufverfolgung platziert ist.</span><span class="sxs-lookup"><span data-stu-id="60bc5-132">It must have a Transfer trace immediately preceding a Suspend or Resume trace</span></span>  
  
- <span data-ttu-id="60bc5-133">Sie darf keine Ablaufverfolgungen zwischen der Anhalten- und der Fortsetzen-Ablaufverfolgung besitzen, sofern diese beiden Ablaufverfolgungen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="60bc5-133">It must not have any traces between the Suspend and Resume traces if such traces exist</span></span>  
  
- <span data-ttu-id="60bc5-134">Sie kann eine beliebige Kombination aus sowie eine beliebige Anzahl von Ablaufverfolgungen des Typs Wichtig/Fehler/Warnung/Information/Verbose/Übertragen besitzen, sofern die oben genannten Bedingungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="60bc5-134">It can have any and as many of critical/Error/Warning/Information/Verbose/Transfer traces as long as the previous conditions are observed</span></span>  
  
 <span data-ttu-id="60bc5-135">Beim folgenden Beispiel handelt es sich um einen regulären Ausdruck zum Definieren einer idealen Aktivität in einem globalen Bereich:</span><span class="sxs-lookup"><span data-stu-id="60bc5-135">The following is a regular expression that defines an ideal activity in the global scope,</span></span>  
  
`R+`  
  
 <span data-ttu-id="60bc5-136">R steht hierbei für den regulären Ausdruck einer Aktivität im lokalen Bereich.</span><span class="sxs-lookup"><span data-stu-id="60bc5-136">with R being the regular expression for an activity in the local scope.</span></span> <span data-ttu-id="60bc5-137">Dies wird folgendermaßen übersetzt:</span><span class="sxs-lookup"><span data-stu-id="60bc5-137">This translates to,</span></span>  
  
`[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+`

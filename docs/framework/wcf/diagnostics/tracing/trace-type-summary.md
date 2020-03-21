---
title: Ablaufverfolgungstyp – Zusammenfassung
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: 8ed6dceb19caa52f928f285064c60337e3f15a87
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674837"
---
# <a name="trace-type-summary"></a><span data-ttu-id="9691a-102">Ablaufverfolgungstyp – Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="9691a-102">Trace Type Summary</span></span>
<span data-ttu-id="9691a-103">[Quellebenen](xref:System.Diagnostics.SourceLevels) definieren verschiedene Ablaufverfolgungsebenen: Critical, Error, Warning, Information und Verbose, sowie eine Beschreibung des `ActivityTracing` Flags, das die Ausgabe von Ablaufverfolgungsbegrenzungs- und Aktivitätsübertragungsereignissen umschaltet.</span><span class="sxs-lookup"><span data-stu-id="9691a-103">[Source Levels](xref:System.Diagnostics.SourceLevels) defines various trace levels: Critical, Error, Warning, Information, and Verbose, as well as provides a description of the `ActivityTracing` flag, which toggles the output of trace boundary and activity transfer events.</span></span>  
  
 <span data-ttu-id="9691a-104">Sie können <xref:System.Diagnostics.TraceEventType> auch die Arten von Ablaufverfolgungen <xref:System.Diagnostics>überprüfen, die von emittiert werden können.</span><span class="sxs-lookup"><span data-stu-id="9691a-104">You can also review <xref:System.Diagnostics.TraceEventType> for the types of traces which can be emitted from <xref:System.Diagnostics>.</span></span>  
  
 <span data-ttu-id="9691a-105">In der folgenden Tabelle werden die Wichtigsten aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="9691a-105">The following table lists the most important ones.</span></span>  
  
|<span data-ttu-id="9691a-106">Ablaufverfolgungstyp</span><span class="sxs-lookup"><span data-stu-id="9691a-106">Trace Type</span></span>|<span data-ttu-id="9691a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9691a-107">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="9691a-108">Kritisch</span><span class="sxs-lookup"><span data-stu-id="9691a-108">Critical</span></span>|<span data-ttu-id="9691a-109">Schwer wiegender Fehler oder Anwendungsabsturz.</span><span class="sxs-lookup"><span data-stu-id="9691a-109">Fatal error or application crash.</span></span>|  
|<span data-ttu-id="9691a-110">Fehler</span><span class="sxs-lookup"><span data-stu-id="9691a-110">Error</span></span>|<span data-ttu-id="9691a-111">Behebbarer Fehler.</span><span class="sxs-lookup"><span data-stu-id="9691a-111">Recoverable error.</span></span>|  
|<span data-ttu-id="9691a-112">Warnung</span><span class="sxs-lookup"><span data-stu-id="9691a-112">Warning</span></span>|<span data-ttu-id="9691a-113">Informationsmeldung.</span><span class="sxs-lookup"><span data-stu-id="9691a-113">Informational message.</span></span>|  
|<span data-ttu-id="9691a-114">Information</span><span class="sxs-lookup"><span data-stu-id="9691a-114">Information</span></span>|<span data-ttu-id="9691a-115">Kein kritisches Problem.</span><span class="sxs-lookup"><span data-stu-id="9691a-115">Non-critical problem.</span></span>|  
|<span data-ttu-id="9691a-116">Ausführlich</span><span class="sxs-lookup"><span data-stu-id="9691a-116">Verbose</span></span>|<span data-ttu-id="9691a-117">Debuggen der Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="9691a-117">Debugging trace.</span></span>|  
|<span data-ttu-id="9691a-118">Start</span><span class="sxs-lookup"><span data-stu-id="9691a-118">Start</span></span>|<span data-ttu-id="9691a-119">Starten einer logischen Verarbeitungseinheit.</span><span class="sxs-lookup"><span data-stu-id="9691a-119">Starting of a logical unit of processing.</span></span>|  
|<span data-ttu-id="9691a-120">Angehalten</span><span class="sxs-lookup"><span data-stu-id="9691a-120">Suspend</span></span>|<span data-ttu-id="9691a-121">Anhalten einer logischen Verarbeitungseinheit.</span><span class="sxs-lookup"><span data-stu-id="9691a-121">Suspension of a logical unit of processing.</span></span>|  
|<span data-ttu-id="9691a-122">Fortfahren</span><span class="sxs-lookup"><span data-stu-id="9691a-122">Resume</span></span>|<span data-ttu-id="9691a-123">Fortsetzen einer logischen Verarbeitungseinheit.</span><span class="sxs-lookup"><span data-stu-id="9691a-123">Resumption of a logical unit of processing.</span></span>|  
|<span data-ttu-id="9691a-124">Beenden</span><span class="sxs-lookup"><span data-stu-id="9691a-124">Stop</span></span>|<span data-ttu-id="9691a-125">Beenden einer logischen Verarbeitungseinheit.</span><span class="sxs-lookup"><span data-stu-id="9691a-125">Stopping of a logical unit of processing.</span></span>|  
|<span data-ttu-id="9691a-126">Übertragung</span><span class="sxs-lookup"><span data-stu-id="9691a-126">Transfer</span></span>|<span data-ttu-id="9691a-127">Ändern der Korrelationsidentität.</span><span class="sxs-lookup"><span data-stu-id="9691a-127">Changing of correlation identity.</span></span>|  
  
 <span data-ttu-id="9691a-128">Eine Aktivität ist als Kombination der oben genannten Ablaufverfolgungstypen definiert.</span><span class="sxs-lookup"><span data-stu-id="9691a-128">An activity is defined as a combination of the trace types above.</span></span>  
  
 <span data-ttu-id="9691a-129">Beim folgenden Beispiel handelt es sich um einen regulären Ausdruck zum Definieren einer idealen Aktivität in einem lokalen Bereich (Ablaufverfolgungsquelle):</span><span class="sxs-lookup"><span data-stu-id="9691a-129">The following is a regular expression that defines an ideal activity in a local (trace source) scope,</span></span>  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 <span data-ttu-id="9691a-130">Das bedeutet, dass eine Aktivität die folgenden Bedingungen erfüllen muss:</span><span class="sxs-lookup"><span data-stu-id="9691a-130">This means that an activity must satisfy the following conditions.</span></span>  
  
- <span data-ttu-id="9691a-131">Sie muss mithilfe der Starten-Ablaufverfolgung gestartet bzw. mithilfe der Beenden-Ablaufverfolgung beendet werden können.</span><span class="sxs-lookup"><span data-stu-id="9691a-131">It must start and stop respectively by a Start and Stop traces</span></span>  
  
- <span data-ttu-id="9691a-132">Sie muss eine Übertragen-Ablaufverfolgung besitzen, die direkt vor einer Anhalten- oder einer Fortsetzen-Ablaufverfolgung platziert ist.</span><span class="sxs-lookup"><span data-stu-id="9691a-132">It must have a Transfer trace immediately preceding a Suspend or Resume trace</span></span>  
  
- <span data-ttu-id="9691a-133">Sie darf keine Ablaufverfolgungen zwischen der Anhalten- und der Fortsetzen-Ablaufverfolgung besitzen, sofern diese beiden Ablaufverfolgungen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="9691a-133">It must not have any traces between the Suspend and Resume traces if such traces exist</span></span>  
  
- <span data-ttu-id="9691a-134">Sie kann eine beliebige Kombination aus sowie eine beliebige Anzahl von Ablaufverfolgungen des Typs Wichtig/Fehler/Warnung/Information/Verbose/Übertragen besitzen, sofern die oben genannten Bedingungen erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="9691a-134">It can have any and as many of critical/Error/Warning/Information/Verbose/Transfer traces as long as the previous conditions are observed</span></span>  
  
 <span data-ttu-id="9691a-135">Beim folgenden Beispiel handelt es sich um einen regulären Ausdruck zum Definieren einer idealen Aktivität in einem globalen Bereich:</span><span class="sxs-lookup"><span data-stu-id="9691a-135">The following is a regular expression that defines an ideal activity in the global scope,</span></span>  
  
`R+`  
  
 <span data-ttu-id="9691a-136">R steht hierbei für den regulären Ausdruck einer Aktivität im lokalen Bereich.</span><span class="sxs-lookup"><span data-stu-id="9691a-136">with R being the regular expression for an activity in the local scope.</span></span> <span data-ttu-id="9691a-137">Dies wird folgendermaßen übersetzt:</span><span class="sxs-lookup"><span data-stu-id="9691a-137">This translates to,</span></span>  
  
`[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+`

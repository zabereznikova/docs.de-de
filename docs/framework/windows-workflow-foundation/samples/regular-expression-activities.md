---
title: "Aktivitäten mit regulären Ausdrücken"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b8f24694-49db-4339-92ec-014e3d4ae63b
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: edeb55f25abf9e6f22ebfe1d0ea63eb07ba0f203
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="regular-expression-activities"></a><span data-ttu-id="69b0e-102">Aktivitäten mit regulären Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="69b0e-102">Regular Expression Activities</span></span>
<span data-ttu-id="69b0e-103">In diesem Beispiel wird veranschaulicht, wie ein Satz von Aktivitäten erstellt wird, der die reguläre Ausdrucksfunktionalität des <xref:System.Text.RegularExpressions>-Namespaces verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="69b0e-103">This sample demonstrates how to create a set of activities that expose the regular expression functionality of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="69b0e-104">Diese benutzerdefinierten Aktivitäten können innerhalb einer Workflowanwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="69b0e-104">These custom activities can be used within a workflow application.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="69b0e-105">reguläre Ausdrücke finden Sie unter [System.Text.RegularExpressions](http://go.microsoft.com/fwlink/?LinkId=150434) Namespace.</span><span class="sxs-lookup"><span data-stu-id="69b0e-105"> regular expressions, see [N:System.Text.RegularExpressions](http://go.microsoft.com/fwlink/?LinkId=150434) Namespace.</span></span>  
  
 <span data-ttu-id="69b0e-106">In der folgenden Tabelle sind die benutzerdefinierten Aktivitäten in diesem Beispiel aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="69b0e-106">The following table details the custom activities in this sample.</span></span>  
  
|<span data-ttu-id="69b0e-107">Aktivität</span><span class="sxs-lookup"><span data-stu-id="69b0e-107">Activity</span></span>|<span data-ttu-id="69b0e-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="69b0e-108">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="69b0e-109">IsMatch</span><span class="sxs-lookup"><span data-stu-id="69b0e-109">IsMatch</span></span>|<span data-ttu-id="69b0e-110">Gibt an, ob der reguläre Ausdruck eine Übereinstimmung in der Eingabezeichenfolge gefunden hat.</span><span class="sxs-lookup"><span data-stu-id="69b0e-110">Specifies whether the regular expression found a match in the input string.</span></span>|  
|<span data-ttu-id="69b0e-111">Entsprechungen</span><span class="sxs-lookup"><span data-stu-id="69b0e-111">Matches</span></span>|<span data-ttu-id="69b0e-112">Sucht in einer Eingabezeichenfolge nach allen Vorkommnissen eines regulären Ausdrucks und gibt alle erfolgreichen Übereinstimmungen zurück.</span><span class="sxs-lookup"><span data-stu-id="69b0e-112">Searches an input string for all occurrences of a regular expression and returns all the successful matches.</span></span>|  
|<span data-ttu-id="69b0e-113">Ersetzen</span><span class="sxs-lookup"><span data-stu-id="69b0e-113">Replace</span></span>|<span data-ttu-id="69b0e-114">Ersetzt innerhalb einer angegebenen Eingabezeichenfolge Zeichenfolgen, die ein Muster eines regulären Ausdrucks mit einer angegebenen Ersatzzeichenfolge vergleichen.</span><span class="sxs-lookup"><span data-stu-id="69b0e-114">Within a specified input string, replaces strings that match a regular expression pattern with a specified replacement string.</span></span>|  
  
## <a name="ismatch"></a><span data-ttu-id="69b0e-115">IsMatch</span><span class="sxs-lookup"><span data-stu-id="69b0e-115">IsMatch</span></span>  
 <span data-ttu-id="69b0e-116">Die benutzerdefinierte `IsMatch`-Aktivität gibt `true` zurück, wenn die `Input`-Zeichenfolge eine Übereinstimmung im regulären Ausdruck findet, der in der `Pattern`-Eigenschaft angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="69b0e-116">The `IsMatch` custom activity returns `true` if the `Input` string property finds a match in the regular expression specified in the `Pattern` property.</span></span> <span data-ttu-id="69b0e-117">Wenn die Aktivität von <xref:System.Activities.CodeActivity%601> abgeleitet wird, ruft die <xref:System.Activities.CodeActivity%601.Execute%2A>-Methode die <xref:System.Text.RegularExpressions.Regex.IsMatch%2A>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="69b0e-117">The activity derives from <xref:System.Activities.CodeActivity%601> and within the <xref:System.Activities.CodeActivity%601.Execute%2A> method calls the <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> method.</span></span>  
  
 <span data-ttu-id="69b0e-118">In der folgenden Tabelle sind die Eigenschaften und der Rückgabewert für die benutzeraktivierte `IsMatch` Aktivität beschrieben.</span><span class="sxs-lookup"><span data-stu-id="69b0e-118">The following table describes the properties and return value for the `IsMatch` custom activity.</span></span>  
  
|<span data-ttu-id="69b0e-119">Eigenschaft oder Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="69b0e-119">Property or Return Value</span></span>|<span data-ttu-id="69b0e-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="69b0e-120">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="69b0e-121">Muster (erforderlich)</span><span class="sxs-lookup"><span data-stu-id="69b0e-121">Pattern (required)</span></span>|<span data-ttu-id="69b0e-122">Der für die Suche zu verwendende reguläre Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="69b0e-122">The regular expression to search with.</span></span>|  
|<span data-ttu-id="69b0e-123">Eingabe (erforderlich)</span><span class="sxs-lookup"><span data-stu-id="69b0e-123">Input (required)</span></span>|<span data-ttu-id="69b0e-124">Die zu suchende Eingabezeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="69b0e-124">The input string to search.</span></span>|  
|<span data-ttu-id="69b0e-125">RegexOptions</span><span class="sxs-lookup"><span data-stu-id="69b0e-125">RegexOptions</span></span>|<span data-ttu-id="69b0e-126">Bitweise OR-Kombination von [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) Enumerationswerte.</span><span class="sxs-lookup"><span data-stu-id="69b0e-126">Bitwise OR combination of [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) enumeration values.</span></span>|  
|<span data-ttu-id="69b0e-127">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="69b0e-127">Return value</span></span>|<span data-ttu-id="69b0e-128">`true`, wenn die Eingabe eine Übereinstimmung im bereitgestellten Muster findet; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="69b0e-128">`true` if the input finds a match in the provided pattern; otherwise `false`.</span></span>|  
  
 <span data-ttu-id="69b0e-129">Das folgende Codebeispiel zeigt, wie Sie die benutzerdefinierte `IsMatch`-Aktivität verwenden.</span><span class="sxs-lookup"><span data-stu-id="69b0e-129">The following code example demonstrates how to use the `IsMatch` custom activity.</span></span>  
  
```  
new IsMatch  
{  
    Pattern = new InArgument<string>( @"^-?\d+(\.\d{2})?$"),  
    Input = "20.00",  
};  
```  
  
## <a name="matches"></a><span data-ttu-id="69b0e-130">Entsprechungen</span><span class="sxs-lookup"><span data-stu-id="69b0e-130">Matches</span></span>  
 <span data-ttu-id="69b0e-131">Die benutzerdefinierte `Matches`-Aktivität sucht in einer Eingabezeichenfolge nach allen Vorkommnissen eines regulären Ausdrucks und gibt alle erfolgreichen Übereinstimmungen zurück.</span><span class="sxs-lookup"><span data-stu-id="69b0e-131">The `Matches` custom activity searches an input string for all occurrences of a regular expression and returns all the successful matches.</span></span> <span data-ttu-id="69b0e-132">Wenn die Aktivität von <xref:System.Activities.CodeActivity%601> abgeleitet wird, ruft die <xref:System.Activities.CodeActivity%601.Execute%2A>-Methode die <xref:System.Text.RegularExpressions.Regex.Matches%2A>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="69b0e-132">The activity derives from <xref:System.Activities.CodeActivity%601> and within the <xref:System.Activities.CodeActivity%601.Execute%2A> method calls the <xref:System.Text.RegularExpressions.Regex.Matches%2A> method.</span></span>  
  
 <span data-ttu-id="69b0e-133">In der folgenden Tabelle sind die Eigenschaften und der Rückgabewert für die benutzeraktivierte `IsMatch` Aktivität beschrieben.</span><span class="sxs-lookup"><span data-stu-id="69b0e-133">The following table describes the properties and return value for the `IsMatch` custom activity.</span></span>  
  
|<span data-ttu-id="69b0e-134">Eigenschaft oder Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="69b0e-134">Property or Return Value</span></span>|<span data-ttu-id="69b0e-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="69b0e-135">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="69b0e-136">Muster (erforderlich)</span><span class="sxs-lookup"><span data-stu-id="69b0e-136">Pattern (required)</span></span>|<span data-ttu-id="69b0e-137">Der für die Suche zu verwendende reguläre Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="69b0e-137">The regular expression to search with.</span></span>|  
|<span data-ttu-id="69b0e-138">Eingabe (erforderlich)</span><span class="sxs-lookup"><span data-stu-id="69b0e-138">Input (required)</span></span>|<span data-ttu-id="69b0e-139">Die zu suchende Eingabezeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="69b0e-139">The input string to search.</span></span>|  
|<span data-ttu-id="69b0e-140">RegexOptions</span><span class="sxs-lookup"><span data-stu-id="69b0e-140">RegexOptions</span></span>|<span data-ttu-id="69b0e-141">Bitweise OR-Kombination von [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) Enumerationswerte.</span><span class="sxs-lookup"><span data-stu-id="69b0e-141">Bitwise OR combination of [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) enumeration values.</span></span>|  
|<span data-ttu-id="69b0e-142">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="69b0e-142">Return Value</span></span>|<span data-ttu-id="69b0e-143">Eine <xref:System.Text.RegularExpressions.MatchCollection>, die die Auflistung erfolgreicher Übereinstimmungen enthält.</span><span class="sxs-lookup"><span data-stu-id="69b0e-143">A <xref:System.Text.RegularExpressions.MatchCollection> that contains the collection of successful matches.</span></span>|  
  
 <span data-ttu-id="69b0e-144">Das folgende Codebeispiel zeigt, wie Sie die benutzerdefinierte `Matches`-Aktivität verwenden.</span><span class="sxs-lookup"><span data-stu-id="69b0e-144">The following code example demonstrates how to use the `Matches` custom activity.</span></span>  
  
```  
new Matches  
{  
    Pattern = @"\b(?<word>\w+)\s+(\k<word>)\b",  
    Input = "The quick brown fox  fox jumped over over the lazy dog dog.",  
};  
```  
  
## <a name="replace"></a><span data-ttu-id="69b0e-145">Ersetzen</span><span class="sxs-lookup"><span data-stu-id="69b0e-145">Replace</span></span>  
 <span data-ttu-id="69b0e-146">Die benutzerdefinierte `Replace`-Aktivität sucht eine Eingabezeichenfolge und ersetzt alle Zeichenfolgen, die einen angegebenen regulären Ausdruck mit einer Zeichenfolge vergleichen.</span><span class="sxs-lookup"><span data-stu-id="69b0e-146">The `Replace` custom activity searches an input string and replaces all strings that match a specified regular expression with a string.</span></span> <span data-ttu-id="69b0e-147">Wenn die Aktivität von <xref:System.Activities.CodeActivity%601> abgeleitet wird, ruft die <xref:System.Activities.CodeActivity%601.Execute%2A>-Methode die <xref:System.Text.RegularExpressions.Regex.Replace%2A>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="69b0e-147">The activity derives from <xref:System.Activities.CodeActivity%601> and within the <xref:System.Activities.CodeActivity%601.Execute%2A> method calls the <xref:System.Text.RegularExpressions.Regex.Replace%2A> method.</span></span>  
  
 <span data-ttu-id="69b0e-148">In der folgenden Tabelle sind die Eigenschaften und der Rückgabewert für die benutzeraktivierte `Replace` Aktivität beschrieben.</span><span class="sxs-lookup"><span data-stu-id="69b0e-148">The following table describes the properties and return value for the `Replace` custom activity.</span></span>  
  
|<span data-ttu-id="69b0e-149">Eigenschaft oder Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="69b0e-149">Property or Return Value</span></span>|<span data-ttu-id="69b0e-150">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="69b0e-150">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="69b0e-151">Muster (erforderlich)</span><span class="sxs-lookup"><span data-stu-id="69b0e-151">Pattern (required)</span></span>|<span data-ttu-id="69b0e-152">Der für die Suche zu verwendende reguläre Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="69b0e-152">The regular expression to search with.</span></span>|  
|<span data-ttu-id="69b0e-153">Eingabe (erforderlich)</span><span class="sxs-lookup"><span data-stu-id="69b0e-153">Input (required)</span></span>|<span data-ttu-id="69b0e-154">Die zu suchende Eingabezeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="69b0e-154">The input string to search.</span></span>|  
|<span data-ttu-id="69b0e-155">Ersetzung</span><span class="sxs-lookup"><span data-stu-id="69b0e-155">Replacement</span></span>|<span data-ttu-id="69b0e-156">Die Ersatzzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="69b0e-156">The replacement string.</span></span><br /><br /> <span data-ttu-id="69b0e-157">Wenn eine `Replacement` angegeben wurde, wird die `MatchEvaluator`-Eigenschaft ignoriert.</span><span class="sxs-lookup"><span data-stu-id="69b0e-157">If a `Replacement` is specified, then the `MatchEvaluator` property is ignored.</span></span> <span data-ttu-id="69b0e-158">Es muss entweder die `Replacement`-Eigenschaft oder die `MatchEvaluator`-Eigenschaft angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="69b0e-158">Either the `Replacement` or `MatchEvaluator` property must be set.</span></span>|  
|<span data-ttu-id="69b0e-159">MatchEvaluator</span><span class="sxs-lookup"><span data-stu-id="69b0e-159">MatchEvaluator</span></span>|<span data-ttu-id="69b0e-160">Eine benutzerdefinierte Methode, die jede Übereinstimmung überprüft und entweder die ursprüngliche entsprechende Zeichenfolge oder eine Ersatzzeichenfolge zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="69b0e-160">A custom method that examines each match and returns either the original matched string or a replacement string.</span></span><br /><br /> <span data-ttu-id="69b0e-161">Wenn eine `Replacement` angegeben wurde, wird die `MatchEvaluator`-Eigenschaft ignoriert.</span><span class="sxs-lookup"><span data-stu-id="69b0e-161">If a `Replacement` is specified, then the `MatchEvaluator` property is ignored.</span></span> <span data-ttu-id="69b0e-162">Es muss entweder die `Replacement`-Eigenschaft oder die `MatchEvaluator`-Eigenschaft angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="69b0e-162">Either the `Replacement` or `MatchEvaluator` property must be set.</span></span>|  
|<span data-ttu-id="69b0e-163">RegexOptions</span><span class="sxs-lookup"><span data-stu-id="69b0e-163">RegexOptions</span></span>|<span data-ttu-id="69b0e-164">Bitweise OR-Kombination von [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) Enumerationswerte.</span><span class="sxs-lookup"><span data-stu-id="69b0e-164">Bitwise OR combination of [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446) enumeration values.</span></span>|  
|<span data-ttu-id="69b0e-165">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="69b0e-165">Return Value</span></span>|<span data-ttu-id="69b0e-166">Eine <xref:System.Text.RegularExpressions.MatchCollection>, die die Auflistung erfolgreicher Übereinstimmungen enthält.</span><span class="sxs-lookup"><span data-stu-id="69b0e-166">A <xref:System.Text.RegularExpressions.MatchCollection> that contains the collection of successful matches.</span></span>|  
  
 <span data-ttu-id="69b0e-167">Das folgende Codebeispiel zeigt, wie Sie die benutzerdefinierte `Replace`-Aktivität verwenden.</span><span class="sxs-lookup"><span data-stu-id="69b0e-167">The following code example demonstrates how to use the `Replace` custom activity.</span></span>  
  
```  
// Using the replacement string.  
new Replace  
{  
    Pattern = @"\bWorld\b",  
    Input = "Hello World! This is a wonderful World",  
    Replacement = "Universe"  
};  
  
// Using a match evaluator.  
new Replace  
{  
    Pattern = new InArgument<string>(pattern),  
    Input = new InArgument<string>(input),  
    MatchEvaluator = new MatchEvaluator(CapText)                  
};  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="69b0e-168">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="69b0e-168">To use this sample</span></span>  
  
1.  <span data-ttu-id="69b0e-169">Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei RegexActivities.sln.</span><span class="sxs-lookup"><span data-stu-id="69b0e-169">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the RegexActivities.sln solution file.</span></span>  
  
2.  <span data-ttu-id="69b0e-170">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="69b0e-170">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="69b0e-171">Drücken Sie STRG+F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="69b0e-171">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="69b0e-172">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="69b0e-172">The samples may already be installed on your machine.</span></span> <span data-ttu-id="69b0e-173">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="69b0e-173">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="69b0e-174">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="69b0e-174">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="69b0e-175">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="69b0e-175">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Regex`  
  
## <a name="see-also"></a><span data-ttu-id="69b0e-176">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69b0e-176">See Also</span></span>

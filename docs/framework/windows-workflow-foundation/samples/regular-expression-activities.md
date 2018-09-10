---
title: Aktivitäten mit regulären Ausdrücken
ms.date: 03/30/2017
ms.assetid: b8f24694-49db-4339-92ec-014e3d4ae63b
ms.openlocfilehash: 50daa5b6d7baab37f372de4c30c2e0d12b4fa943
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44079681"
---
# <a name="regular-expression-activities"></a><span data-ttu-id="de987-102">Aktivitäten mit regulären Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="de987-102">Regular Expression Activities</span></span>
<span data-ttu-id="de987-103">In diesem Beispiel wird veranschaulicht, wie ein Satz von Aktivitäten erstellt wird, der die reguläre Ausdrucksfunktionalität des <xref:System.Text.RegularExpressions>-Namespaces verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="de987-103">This sample demonstrates how to create a set of activities that expose the regular expression functionality of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="de987-104">Diese benutzerdefinierten Aktivitäten können innerhalb einer Workflowanwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="de987-104">These custom activities can be used within a workflow application.</span></span> <span data-ttu-id="de987-105">Weitere Informationen zu regulären Ausdrücken finden Sie unter [n: System.Text.RegularExpressions](https://go.microsoft.com/fwlink/?LinkId=150434) Namespace.</span><span class="sxs-lookup"><span data-stu-id="de987-105">For more information about regular expressions, see [N:System.Text.RegularExpressions](https://go.microsoft.com/fwlink/?LinkId=150434) Namespace.</span></span>  
  
 <span data-ttu-id="de987-106">In der folgenden Tabelle sind die benutzerdefinierten Aktivitäten in diesem Beispiel aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="de987-106">The following table details the custom activities in this sample.</span></span>  
  
|<span data-ttu-id="de987-107">Aktivität</span><span class="sxs-lookup"><span data-stu-id="de987-107">Activity</span></span>|<span data-ttu-id="de987-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="de987-108">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="de987-109">IsMatch</span><span class="sxs-lookup"><span data-stu-id="de987-109">IsMatch</span></span>|<span data-ttu-id="de987-110">Gibt an, ob der reguläre Ausdruck eine Übereinstimmung in der Eingabezeichenfolge gefunden hat.</span><span class="sxs-lookup"><span data-stu-id="de987-110">Specifies whether the regular expression found a match in the input string.</span></span>|  
|<span data-ttu-id="de987-111">Entsprechungen</span><span class="sxs-lookup"><span data-stu-id="de987-111">Matches</span></span>|<span data-ttu-id="de987-112">Sucht in einer Eingabezeichenfolge nach allen Vorkommnissen eines regulären Ausdrucks und gibt alle erfolgreichen Übereinstimmungen zurück.</span><span class="sxs-lookup"><span data-stu-id="de987-112">Searches an input string for all occurrences of a regular expression and returns all the successful matches.</span></span>|  
|<span data-ttu-id="de987-113">Ersetzen</span><span class="sxs-lookup"><span data-stu-id="de987-113">Replace</span></span>|<span data-ttu-id="de987-114">Ersetzt innerhalb einer angegebenen Eingabezeichenfolge Zeichenfolgen, die ein Muster eines regulären Ausdrucks mit einer angegebenen Ersatzzeichenfolge vergleichen.</span><span class="sxs-lookup"><span data-stu-id="de987-114">Within a specified input string, replaces strings that match a regular expression pattern with a specified replacement string.</span></span>|  
  
## <a name="ismatch"></a><span data-ttu-id="de987-115">IsMatch</span><span class="sxs-lookup"><span data-stu-id="de987-115">IsMatch</span></span>  
 <span data-ttu-id="de987-116">Die benutzerdefinierte `IsMatch`-Aktivität gibt `true` zurück, wenn die `Input`-Zeichenfolge eine Übereinstimmung im regulären Ausdruck findet, der in der `Pattern`-Eigenschaft angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="de987-116">The `IsMatch` custom activity returns `true` if the `Input` string property finds a match in the regular expression specified in the `Pattern` property.</span></span> <span data-ttu-id="de987-117">Wenn die Aktivität von <xref:System.Activities.CodeActivity%601> abgeleitet wird, ruft die <xref:System.Activities.CodeActivity%601.Execute%2A>-Methode die <xref:System.Text.RegularExpressions.Regex.IsMatch%2A>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="de987-117">The activity derives from <xref:System.Activities.CodeActivity%601> and within the <xref:System.Activities.CodeActivity%601.Execute%2A> method calls the <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> method.</span></span>  
  
 <span data-ttu-id="de987-118">In der folgenden Tabelle sind die Eigenschaften und der Rückgabewert für die benutzeraktivierte `IsMatch` Aktivität beschrieben.</span><span class="sxs-lookup"><span data-stu-id="de987-118">The following table describes the properties and return value for the `IsMatch` custom activity.</span></span>  
  
|<span data-ttu-id="de987-119">Eigenschaft oder Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="de987-119">Property or Return Value</span></span>|<span data-ttu-id="de987-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="de987-120">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="de987-121">Muster (erforderlich)</span><span class="sxs-lookup"><span data-stu-id="de987-121">Pattern (required)</span></span>|<span data-ttu-id="de987-122">Der für die Suche zu verwendende reguläre Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="de987-122">The regular expression to search with.</span></span>|  
|<span data-ttu-id="de987-123">Eingabe (erforderlich)</span><span class="sxs-lookup"><span data-stu-id="de987-123">Input (required)</span></span>|<span data-ttu-id="de987-124">Die zu suchende Eingabezeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="de987-124">The input string to search.</span></span>|  
|<span data-ttu-id="de987-125">RegexOptions</span><span class="sxs-lookup"><span data-stu-id="de987-125">RegexOptions</span></span>|<span data-ttu-id="de987-126">Bitweise OR-Kombination von [RegexOptions](https://go.microsoft.com/fwlink/?LinkId=150446) -Enumerationswerte fest.</span><span class="sxs-lookup"><span data-stu-id="de987-126">Bitwise OR combination of [RegexOptions](https://go.microsoft.com/fwlink/?LinkId=150446) enumeration values.</span></span>|  
|<span data-ttu-id="de987-127">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="de987-127">Return value</span></span>|<span data-ttu-id="de987-128">`true`, wenn die Eingabe eine Übereinstimmung im bereitgestellten Muster findet; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="de987-128">`true` if the input finds a match in the provided pattern; otherwise `false`.</span></span>|  
  
 <span data-ttu-id="de987-129">Das folgende Codebeispiel zeigt, wie Sie die benutzerdefinierte `IsMatch`-Aktivität verwenden.</span><span class="sxs-lookup"><span data-stu-id="de987-129">The following code example demonstrates how to use the `IsMatch` custom activity.</span></span>  
  
```  
new IsMatch  
{  
    Pattern = new InArgument<string>( @"^-?\d+(\.\d{2})?$"),  
    Input = "20.00",  
};  
```  
  
## <a name="matches"></a><span data-ttu-id="de987-130">Entsprechungen</span><span class="sxs-lookup"><span data-stu-id="de987-130">Matches</span></span>  
 <span data-ttu-id="de987-131">Die benutzerdefinierte `Matches`-Aktivität sucht in einer Eingabezeichenfolge nach allen Vorkommnissen eines regulären Ausdrucks und gibt alle erfolgreichen Übereinstimmungen zurück.</span><span class="sxs-lookup"><span data-stu-id="de987-131">The `Matches` custom activity searches an input string for all occurrences of a regular expression and returns all the successful matches.</span></span> <span data-ttu-id="de987-132">Wenn die Aktivität von <xref:System.Activities.CodeActivity%601> abgeleitet wird, ruft die <xref:System.Activities.CodeActivity%601.Execute%2A>-Methode die <xref:System.Text.RegularExpressions.Regex.Matches%2A>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="de987-132">The activity derives from <xref:System.Activities.CodeActivity%601> and within the <xref:System.Activities.CodeActivity%601.Execute%2A> method calls the <xref:System.Text.RegularExpressions.Regex.Matches%2A> method.</span></span>  
  
 <span data-ttu-id="de987-133">In der folgenden Tabelle sind die Eigenschaften und der Rückgabewert für die benutzeraktivierte `IsMatch` Aktivität beschrieben.</span><span class="sxs-lookup"><span data-stu-id="de987-133">The following table describes the properties and return value for the `IsMatch` custom activity.</span></span>  
  
|<span data-ttu-id="de987-134">Eigenschaft oder Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="de987-134">Property or Return Value</span></span>|<span data-ttu-id="de987-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="de987-135">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="de987-136">Muster (erforderlich)</span><span class="sxs-lookup"><span data-stu-id="de987-136">Pattern (required)</span></span>|<span data-ttu-id="de987-137">Der für die Suche zu verwendende reguläre Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="de987-137">The regular expression to search with.</span></span>|  
|<span data-ttu-id="de987-138">Eingabe (erforderlich)</span><span class="sxs-lookup"><span data-stu-id="de987-138">Input (required)</span></span>|<span data-ttu-id="de987-139">Die zu suchende Eingabezeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="de987-139">The input string to search.</span></span>|  
|<span data-ttu-id="de987-140">RegexOptions</span><span class="sxs-lookup"><span data-stu-id="de987-140">RegexOptions</span></span>|<span data-ttu-id="de987-141">Bitweise OR-Kombination von [RegexOptions](https://go.microsoft.com/fwlink/?LinkId=150446) -Enumerationswerte fest.</span><span class="sxs-lookup"><span data-stu-id="de987-141">Bitwise OR combination of [RegexOptions](https://go.microsoft.com/fwlink/?LinkId=150446) enumeration values.</span></span>|  
|<span data-ttu-id="de987-142">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="de987-142">Return Value</span></span>|<span data-ttu-id="de987-143">Eine <xref:System.Text.RegularExpressions.MatchCollection>, die die Auflistung erfolgreicher Übereinstimmungen enthält.</span><span class="sxs-lookup"><span data-stu-id="de987-143">A <xref:System.Text.RegularExpressions.MatchCollection> that contains the collection of successful matches.</span></span>|  
  
 <span data-ttu-id="de987-144">Das folgende Codebeispiel zeigt, wie Sie die benutzerdefinierte `Matches`-Aktivität verwenden.</span><span class="sxs-lookup"><span data-stu-id="de987-144">The following code example demonstrates how to use the `Matches` custom activity.</span></span>  
  
```  
new Matches  
{  
    Pattern = @"\b(?<word>\w+)\s+(\k<word>)\b",  
    Input = "The quick brown fox  fox jumped over over the lazy dog dog.",  
};  
```  
  
## <a name="replace"></a><span data-ttu-id="de987-145">Ersetzen</span><span class="sxs-lookup"><span data-stu-id="de987-145">Replace</span></span>  
 <span data-ttu-id="de987-146">Die benutzerdefinierte `Replace`-Aktivität sucht eine Eingabezeichenfolge und ersetzt alle Zeichenfolgen, die einen angegebenen regulären Ausdruck mit einer Zeichenfolge vergleichen.</span><span class="sxs-lookup"><span data-stu-id="de987-146">The `Replace` custom activity searches an input string and replaces all strings that match a specified regular expression with a string.</span></span> <span data-ttu-id="de987-147">Wenn die Aktivität von <xref:System.Activities.CodeActivity%601> abgeleitet wird, ruft die <xref:System.Activities.CodeActivity%601.Execute%2A>-Methode die <xref:System.Text.RegularExpressions.Regex.Replace%2A>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="de987-147">The activity derives from <xref:System.Activities.CodeActivity%601> and within the <xref:System.Activities.CodeActivity%601.Execute%2A> method calls the <xref:System.Text.RegularExpressions.Regex.Replace%2A> method.</span></span>  
  
 <span data-ttu-id="de987-148">In der folgenden Tabelle sind die Eigenschaften und der Rückgabewert für die benutzeraktivierte `Replace` Aktivität beschrieben.</span><span class="sxs-lookup"><span data-stu-id="de987-148">The following table describes the properties and return value for the `Replace` custom activity.</span></span>  
  
|<span data-ttu-id="de987-149">Eigenschaft oder Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="de987-149">Property or Return Value</span></span>|<span data-ttu-id="de987-150">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="de987-150">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="de987-151">Muster (erforderlich)</span><span class="sxs-lookup"><span data-stu-id="de987-151">Pattern (required)</span></span>|<span data-ttu-id="de987-152">Der für die Suche zu verwendende reguläre Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="de987-152">The regular expression to search with.</span></span>|  
|<span data-ttu-id="de987-153">Eingabe (erforderlich)</span><span class="sxs-lookup"><span data-stu-id="de987-153">Input (required)</span></span>|<span data-ttu-id="de987-154">Die zu suchende Eingabezeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="de987-154">The input string to search.</span></span>|  
|<span data-ttu-id="de987-155">Ersetzung</span><span class="sxs-lookup"><span data-stu-id="de987-155">Replacement</span></span>|<span data-ttu-id="de987-156">Die Ersatzzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="de987-156">The replacement string.</span></span><br /><br /> <span data-ttu-id="de987-157">Wenn eine `Replacement` angegeben wurde, wird die `MatchEvaluator`-Eigenschaft ignoriert.</span><span class="sxs-lookup"><span data-stu-id="de987-157">If a `Replacement` is specified, then the `MatchEvaluator` property is ignored.</span></span> <span data-ttu-id="de987-158">Es muss entweder die `Replacement`-Eigenschaft oder die `MatchEvaluator`-Eigenschaft angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="de987-158">Either the `Replacement` or `MatchEvaluator` property must be set.</span></span>|  
|<span data-ttu-id="de987-159">MatchEvaluator</span><span class="sxs-lookup"><span data-stu-id="de987-159">MatchEvaluator</span></span>|<span data-ttu-id="de987-160">Eine benutzerdefinierte Methode, die jede Übereinstimmung überprüft und entweder die ursprüngliche entsprechende Zeichenfolge oder eine Ersatzzeichenfolge zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="de987-160">A custom method that examines each match and returns either the original matched string or a replacement string.</span></span><br /><br /> <span data-ttu-id="de987-161">Wenn eine `Replacement` angegeben wurde, wird die `MatchEvaluator`-Eigenschaft ignoriert.</span><span class="sxs-lookup"><span data-stu-id="de987-161">If a `Replacement` is specified, then the `MatchEvaluator` property is ignored.</span></span> <span data-ttu-id="de987-162">Es muss entweder die `Replacement`-Eigenschaft oder die `MatchEvaluator`-Eigenschaft angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="de987-162">Either the `Replacement` or `MatchEvaluator` property must be set.</span></span>|  
|<span data-ttu-id="de987-163">RegexOptions</span><span class="sxs-lookup"><span data-stu-id="de987-163">RegexOptions</span></span>|<span data-ttu-id="de987-164">Bitweise OR-Kombination von [RegexOptions](https://go.microsoft.com/fwlink/?LinkId=150446) -Enumerationswerte fest.</span><span class="sxs-lookup"><span data-stu-id="de987-164">Bitwise OR combination of [RegexOptions](https://go.microsoft.com/fwlink/?LinkId=150446) enumeration values.</span></span>|  
|<span data-ttu-id="de987-165">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="de987-165">Return Value</span></span>|<span data-ttu-id="de987-166">Eine <xref:System.Text.RegularExpressions.MatchCollection>, die die Auflistung erfolgreicher Übereinstimmungen enthält.</span><span class="sxs-lookup"><span data-stu-id="de987-166">A <xref:System.Text.RegularExpressions.MatchCollection> that contains the collection of successful matches.</span></span>|  
  
 <span data-ttu-id="de987-167">Das folgende Codebeispiel zeigt, wie Sie die benutzerdefinierte `Replace`-Aktivität verwenden.</span><span class="sxs-lookup"><span data-stu-id="de987-167">The following code example demonstrates how to use the `Replace` custom activity.</span></span>  
  
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
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="de987-168">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="de987-168">To use this sample</span></span>  
  
1.  <span data-ttu-id="de987-169">Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei RegexActivities.sln.</span><span class="sxs-lookup"><span data-stu-id="de987-169">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the RegexActivities.sln solution file.</span></span>  
  
2.  <span data-ttu-id="de987-170">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="de987-170">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="de987-171">Drücken Sie STRG+F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="de987-171">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="de987-172">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="de987-172">The samples may already be installed on your machine.</span></span> <span data-ttu-id="de987-173">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="de987-173">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="de987-174">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="de987-174">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="de987-175">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="de987-175">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Regex`
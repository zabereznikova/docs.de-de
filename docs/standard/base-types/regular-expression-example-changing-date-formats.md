---
title: 'Beispiel für reguläre Ausdrücke: Ändern von Datumsformaten'
ms.date: 06/30/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- searching with regular expressions, examples
- parsing text with regular expressions, examples
- regular expressions, examples
- .NET Framework regular expressions, examples
- regular expressions [.NET Framework], examples
- pattern-matching with regular expressions, examples
ms.assetid: 5fcc75a5-09d7-45ae-a4c0-9ad6085ac83d
ms.openlocfilehash: 3b657ac6c88a1ee846f7f1d2156a18fd34621808
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803949"
---
# <a name="regular-expression-example-changing-date-formats"></a><span data-ttu-id="ef88e-102">Beispiel für reguläre Ausdrücke: Ändern von Datumsformaten</span><span class="sxs-lookup"><span data-stu-id="ef88e-102">Regular Expression Example: Changing Date Formats</span></span>
<span data-ttu-id="ef88e-103">Im folgenden Codebeispiel wird die <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType>-Methode verwendet, um Datumsangaben im Format *mm*/*tt*/*jj* durch Datumsangaben im Format *tt*-*mm*-*jj* zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="ef88e-103">The following code example uses the <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> method to replace dates that have the form *mm*/*dd*/*yy* with dates that have the form *dd*-*mm*-*yy*.</span></span>  

[!INCLUDE [regex](../../../includes/regex.md)]

## <a name="example"></a><span data-ttu-id="ef88e-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ef88e-104">Example</span></span>  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#1)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#1)]  
  
 <span data-ttu-id="ef88e-105">Der folgende Code zeigt, wie die `MDYToDMY`-Methode in einer Anwendung aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="ef88e-105">The following code shows how the `MDYToDMY` method can be called in an application.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#2)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#2)]  
  
## <a name="comments"></a><span data-ttu-id="ef88e-106">Kommentare</span><span class="sxs-lookup"><span data-stu-id="ef88e-106">Comments</span></span>  
 <span data-ttu-id="ef88e-107">Das Muster für reguläre Ausdrücke `\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b` wird entsprechend der folgenden Tabelle interpretiert.</span><span class="sxs-lookup"><span data-stu-id="ef88e-107">The regular expression pattern  `\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b` is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="ef88e-108">Muster</span><span class="sxs-lookup"><span data-stu-id="ef88e-108">Pattern</span></span>|<span data-ttu-id="ef88e-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ef88e-109">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="ef88e-110">Der Vergleich beginnt an einer Wortgrenze.</span><span class="sxs-lookup"><span data-stu-id="ef88e-110">Begin the match at a word boundary.</span></span>|  
|`(?<month>\d{1,2})`|<span data-ttu-id="ef88e-111">Entsprechung für eine oder zwei Dezimalstellen finden.</span><span class="sxs-lookup"><span data-stu-id="ef88e-111">Match one or two decimal digits.</span></span> <span data-ttu-id="ef88e-112">Dies ist die erfasste Gruppe `month`.</span><span class="sxs-lookup"><span data-stu-id="ef88e-112">This is the `month` captured group.</span></span>|  
|`/`|<span data-ttu-id="ef88e-113">Entsprechung für den Schrägstrich finden.</span><span class="sxs-lookup"><span data-stu-id="ef88e-113">Match the slash mark.</span></span>|  
|`(?<day>\d{1,2})`|<span data-ttu-id="ef88e-114">Entsprechung für eine oder zwei Dezimalstellen finden.</span><span class="sxs-lookup"><span data-stu-id="ef88e-114">Match one or two decimal digits.</span></span> <span data-ttu-id="ef88e-115">Dies ist die erfasste Gruppe `day`.</span><span class="sxs-lookup"><span data-stu-id="ef88e-115">This is the `day` captured group.</span></span>|  
|`/`|<span data-ttu-id="ef88e-116">Entsprechung für den Schrägstrich finden.</span><span class="sxs-lookup"><span data-stu-id="ef88e-116">Match the slash mark.</span></span>|  
|`(?<year>\d{2,4})`|<span data-ttu-id="ef88e-117">Entsprechung für zwei bis vier Dezimalstellen finden.</span><span class="sxs-lookup"><span data-stu-id="ef88e-117">Match from two to four decimal digits.</span></span> <span data-ttu-id="ef88e-118">Dies ist die erfasste Gruppe `year`.</span><span class="sxs-lookup"><span data-stu-id="ef88e-118">This is the `year` captured group.</span></span>|  
|`\b`|<span data-ttu-id="ef88e-119">Der Vergleich endet an einer Wortgrenze.</span><span class="sxs-lookup"><span data-stu-id="ef88e-119">End the match at a word boundary.</span></span>|  
  
 <span data-ttu-id="ef88e-120">Das Muster `${day}-${month}-${year}` definiert die Ersetzungszeichenfolge wie in der folgenden Tabelle gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ef88e-120">The pattern `${day}-${month}-${year}` defines the replacement string as shown in the following table.</span></span>  
  
|<span data-ttu-id="ef88e-121">Muster</span><span class="sxs-lookup"><span data-stu-id="ef88e-121">Pattern</span></span>|<span data-ttu-id="ef88e-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ef88e-122">Description</span></span>|  
|-------------|-----------------|  
|`$(day)`|<span data-ttu-id="ef88e-123">Zeichenfolge hinzufügen, die von der Erfassungsgruppe `day` erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="ef88e-123">Add the string captured by the `day` capturing group.</span></span>|  
|`-`|<span data-ttu-id="ef88e-124">Bindestrich hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ef88e-124">Add a hyphen.</span></span>|  
|`$(month)`|<span data-ttu-id="ef88e-125">Zeichenfolge hinzufügen, die von der Erfassungsgruppe `month` erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="ef88e-125">Add the string captured by the `month` capturing group.</span></span>|  
|`-`|<span data-ttu-id="ef88e-126">Bindestrich hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ef88e-126">Add a hyphen.</span></span>|  
|`$(year)`|<span data-ttu-id="ef88e-127">Zeichenfolge hinzufügen, die von der Erfassungsgruppe `year` erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="ef88e-127">Add the string captured by the `year` capturing group.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ef88e-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ef88e-128">See also</span></span>

- [<span data-ttu-id="ef88e-129">Reguläre Ausdrücke von .NET</span><span class="sxs-lookup"><span data-stu-id="ef88e-129">.NET Regular Expressions</span></span>](regular-expressions.md)

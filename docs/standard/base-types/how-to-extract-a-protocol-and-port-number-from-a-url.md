---
title: 'Gewusst wie: Extrahieren eines Protokolls und einer Portnummer aus einer URL'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
ms.assetid: ab7f62b3-6d2c-4efb-8ac6-28600df5fd5c
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 10ab05ac8b24c0658be2f27809137c6b0bd4834f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-extract-a-protocol-and-port-number-from-a-url"></a><span data-ttu-id="d0117-102">Gewusst wie: Extrahieren eines Protokolls und einer Portnummer aus einer URL</span><span class="sxs-lookup"><span data-stu-id="d0117-102">How to: Extract a Protocol and Port Number from a URL</span></span>
<span data-ttu-id="d0117-103">Das folgende Beispiel extrahiert ein Protokoll und eine Portnummer aus einer URL.</span><span class="sxs-lookup"><span data-stu-id="d0117-103">The following example extracts a protocol and port number from a URL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0117-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d0117-104">Example</span></span>  
 <span data-ttu-id="d0117-105">Im Beispiel wird die <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> Methode, um das Protokoll zurückgegeben, gefolgt von einem Doppelpunkt und die Portnummer an.</span><span class="sxs-lookup"><span data-stu-id="d0117-105">The example uses the <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> method to return the protocol followed by a colon followed by the port number.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/Example.vb#1)]  
  
 <span data-ttu-id="d0117-106">Das Muster für reguläre Ausdrücke `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/` kann wie in der folgenden Tabelle dargestellt interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="d0117-106">The regular expression pattern `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/` can be interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="d0117-107">Muster</span><span class="sxs-lookup"><span data-stu-id="d0117-107">Pattern</span></span>|<span data-ttu-id="d0117-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d0117-108">Description</span></span>|  
|-------------|-----------------|  
|`^`|<span data-ttu-id="d0117-109">Starten Sie den Vergleich am Beginn der Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="d0117-109">Begin the match at the start of the string.</span></span>|  
|`(?<proto>\w+)`|<span data-ttu-id="d0117-110">Übereinstimmung mit mindestens einem Wortzeichen.</span><span class="sxs-lookup"><span data-stu-id="d0117-110">Match one or more word characters.</span></span> <span data-ttu-id="d0117-111">Nennen Sie diese Gruppe `proto`.</span><span class="sxs-lookup"><span data-stu-id="d0117-111">Name this group `proto`.</span></span>|  
|`://`|<span data-ttu-id="d0117-112">Übereinstimmung mit einem Doppelpunkt, gefolgt von zwei Schrägstrichen.</span><span class="sxs-lookup"><span data-stu-id="d0117-112">Match a colon followed by two slash marks.</span></span>|  
|`[^/]+?`|<span data-ttu-id="d0117-113">Übereinstimmung mit mindestens einem Vorkommen (jedoch so wenigen wie möglich) eines beliebigen Zeichens außer einem Schrägstrich.</span><span class="sxs-lookup"><span data-stu-id="d0117-113">Match one or more occurrences (but as few as possible) of any character other than a slash mark.</span></span>|  
|`(?<port>:\d+)?`|<span data-ttu-id="d0117-114">Übereinstimmung mit keinem oder einem Vorkommen eines Doppelpunkts, gefolgt von mindestens einem Ziffernzeichen.</span><span class="sxs-lookup"><span data-stu-id="d0117-114">Match zero or one occurrence of a colon followed by one or more digit characters.</span></span> <span data-ttu-id="d0117-115">Nennen Sie diese Gruppe `port`.</span><span class="sxs-lookup"><span data-stu-id="d0117-115">Name this group `port`.</span></span>|  
|`/`|<span data-ttu-id="d0117-116">Übereinstimmung mit einem Schrägstrich.</span><span class="sxs-lookup"><span data-stu-id="d0117-116">Match a slash mark.</span></span>|  
  
 <span data-ttu-id="d0117-117">Die <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> Methode erweitert die `${proto}${port}` Ersatzsequenz, verkettet den Wert, der die zwei benannten Gruppen, die im Muster regulären Ausdrucks erfasst.</span><span class="sxs-lookup"><span data-stu-id="d0117-117">The <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> method expands the `${proto}${port}` replacement sequence, which concatenates the value of the two named groups captured in the regular expression pattern.</span></span> <span data-ttu-id="d0117-118">Es ist eine praktische Alternative zum Verketten von Zeichenfolgen abgerufen werden, von dem Auflistungsobjekt zurückgegebenes explizit die <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="d0117-118">It is a convenient alternative to explicitly concatenating the strings retrieved from the collection object returned by the <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="d0117-119">Im Beispiel wird die <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> Methode mit zwei substitutionen `${proto}` und `${port}`, um die ausgegebene Zeichenfolge die erfassten Gruppen einschließt.</span><span class="sxs-lookup"><span data-stu-id="d0117-119">The example uses the <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> method with two substitutions, `${proto}` and `${port}`, to include the captured groups in the output string.</span></span> <span data-ttu-id="d0117-120">Sie können die erfassten Gruppen abrufen, aus der Übereinstimmungssuche <xref:System.Text.RegularExpressions.GroupCollection> -Objekt stattdessen, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d0117-120">You can retrieve the captured groups from the match's <xref:System.Text.RegularExpressions.GroupCollection> object instead, as the following code shows.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/example2.cs#2)]
 [!code-vb[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/example2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="d0117-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0117-121">See Also</span></span>  
 [<span data-ttu-id="d0117-122">Reguläre Ausdrücke von .NET</span><span class="sxs-lookup"><span data-stu-id="d0117-122">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)

---
title: 'Gewusst wie: Extrahieren eines Protokolls und einer Portnummer aus einer URL'
ms.date: 06/30/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- searching with regular expressions, examples
- parsing text with regular expressions, examples
- regular expressions, examples
- .NET regular expressions, examples
- regular expressions [.NET], examples
- pattern-matching with regular expressions, examples
ms.assetid: ab7f62b3-6d2c-4efb-8ac6-28600df5fd5c
ms.openlocfilehash: ba512fbe4ebc7ec35ca590541fe5bf94d07c465d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734516"
---
# <a name="how-to-extract-a-protocol-and-port-number-from-a-url"></a><span data-ttu-id="90e8d-102">Gewusst wie: Extrahieren eines Protokolls und einer Portnummer aus einer URL</span><span class="sxs-lookup"><span data-stu-id="90e8d-102">How to: Extract a Protocol and Port Number from a URL</span></span>

<span data-ttu-id="90e8d-103">Das folgende Beispiel extrahiert ein Protokoll und eine Portnummer aus einer URL.</span><span class="sxs-lookup"><span data-stu-id="90e8d-103">The following example extracts a protocol and port number from a URL.</span></span>  

[!INCLUDE [regex](../../../includes/regex.md)]

## <a name="example"></a><span data-ttu-id="90e8d-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="90e8d-104">Example</span></span>  

 <span data-ttu-id="90e8d-105">Das Beispiel verwendet die <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType>-Methode, um das Protokoll, gefolgt von einem Doppelpunkt und der Portnummer, zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="90e8d-105">The example uses the <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> method to return the protocol followed by a colon followed by the port number.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.Protocol#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/Example.vb#1)]  
  
 <span data-ttu-id="90e8d-106">Das Muster für reguläre Ausdrücke `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/` kann wie in der folgenden Tabelle dargestellt interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="90e8d-106">The regular expression pattern `^(?<proto>\w+)://[^/]+?(?<port>:\d+)?/` can be interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="90e8d-107">Muster</span><span class="sxs-lookup"><span data-stu-id="90e8d-107">Pattern</span></span>|<span data-ttu-id="90e8d-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90e8d-108">Description</span></span>|  
|-------------|-----------------|  
|`^`|<span data-ttu-id="90e8d-109">Starten Sie den Vergleich am Beginn der Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="90e8d-109">Begin the match at the start of the string.</span></span>|  
|`(?<proto>\w+)`|<span data-ttu-id="90e8d-110">Übereinstimmung mit mindestens einem Wortzeichen.</span><span class="sxs-lookup"><span data-stu-id="90e8d-110">Match one or more word characters.</span></span> <span data-ttu-id="90e8d-111">Als Name der Gruppe wird `proto` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="90e8d-111">Name this group `proto`.</span></span>|  
|`://`|<span data-ttu-id="90e8d-112">Übereinstimmung mit einem Doppelpunkt, gefolgt von zwei Schrägstrichen.</span><span class="sxs-lookup"><span data-stu-id="90e8d-112">Match a colon followed by two slash marks.</span></span>|  
|`[^/]+?`|<span data-ttu-id="90e8d-113">Übereinstimmung mit mindestens einem Vorkommen (jedoch so wenigen wie möglich) eines beliebigen Zeichens außer einem Schrägstrich.</span><span class="sxs-lookup"><span data-stu-id="90e8d-113">Match one or more occurrences (but as few as possible) of any character other than a slash mark.</span></span>|  
|`(?<port>:\d+)?`|<span data-ttu-id="90e8d-114">Übereinstimmung mit keinem oder einem Vorkommen eines Doppelpunkts, gefolgt von mindestens einem Ziffernzeichen.</span><span class="sxs-lookup"><span data-stu-id="90e8d-114">Match zero or one occurrence of a colon followed by one or more digit characters.</span></span> <span data-ttu-id="90e8d-115">Als Name der Gruppe wird `port` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="90e8d-115">Name this group `port`.</span></span>|  
|`/`|<span data-ttu-id="90e8d-116">Übereinstimmung mit einem Schrägstrich.</span><span class="sxs-lookup"><span data-stu-id="90e8d-116">Match a slash mark.</span></span>|  
  
 <span data-ttu-id="90e8d-117">Die <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType>-Methode erweitert die `${proto}${port}`-Ersatzsequenz, die den Wert der beiden benannten Gruppen verkettet, die im Muster für reguläre Ausdrücke erfasst wurden.</span><span class="sxs-lookup"><span data-stu-id="90e8d-117">The <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> method expands the `${proto}${port}` replacement sequence, which concatenates the value of the two named groups captured in the regular expression pattern.</span></span> <span data-ttu-id="90e8d-118">Das ist eine praktische Alternative zum expliziten Verketten der Zeichenfolgen, die aus dem von der <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType>-Eigenschaft zurückgegebenen Auflistungsobjekt abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="90e8d-118">It is a convenient alternative to explicitly concatenating the strings retrieved from the collection object returned by the <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="90e8d-119">Das Beispiel verwendet die <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType>-Methode mit zwei Ersetzungen, `${proto}` und `${port}`, um die erfassten Gruppen in die Ausgabezeichenfolge einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="90e8d-119">The example uses the <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> method with two substitutions, `${proto}` and `${port}`, to include the captured groups in the output string.</span></span> <span data-ttu-id="90e8d-120">Sie können die erfassten Gruppen stattdessen aus dem <xref:System.Text.RegularExpressions.GroupCollection>-Objekt der Übereinstimmung abrufen, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="90e8d-120">You can retrieve the captured groups from the match's <xref:System.Text.RegularExpressions.GroupCollection> object instead, as the following code shows.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/cs/example2.cs#2)]
 [!code-vb[RegularExpressions.Examples.Protocol#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.Protocol/vb/example2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="90e8d-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="90e8d-121">See also</span></span>

- [<span data-ttu-id="90e8d-122">Reguläre Ausdrücke von .NET</span><span class="sxs-lookup"><span data-stu-id="90e8d-122">.NET Regular Expressions</span></span>](regular-expressions.md)

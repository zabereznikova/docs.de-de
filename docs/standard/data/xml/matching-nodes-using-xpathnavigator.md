---
title: Vergleich von Knoten mit XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: e6848c47-ee5d-401a-89a5-50b5eed40f30
ms.openlocfilehash: f0988c3a112fefc351175de02c790dc25fe6e94a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710686"
---
# <a name="matching-nodes-using-xpathnavigator"></a><span data-ttu-id="8d3c4-102">Vergleich von Knoten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="8d3c4-102">Matching Nodes using XPathNavigator</span></span>
<span data-ttu-id="8d3c4-103">Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt die <xref:System.Xml.XPath.XPathNavigator.Matches%2A>-Methode bereit, um zu bestimmen, ob ein Knoten einem XPath-Ausdruck entspricht.</span><span class="sxs-lookup"><span data-stu-id="8d3c4-103">The <xref:System.Xml.XPath.XPathNavigator> class provides the <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method to determine if a node matches an XPath expression.</span></span> <span data-ttu-id="8d3c4-104">Die <xref:System.Xml.XPath.XPathNavigator.Matches%2A>-Methode verwendet einen XPath-Ausdruck als Eingabe und gibt einen <xref:System.Boolean>-Wert zurück, der angibt, ob der aktuelle Knoten dem angegebenen XPath-Ausdruck oder dem angegebenen kompilierten <xref:System.Xml.XPath.XPathExpression>-Objekt entspricht.</span><span class="sxs-lookup"><span data-stu-id="8d3c4-104">The <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method takes an XPath expression as input and returns a <xref:System.Boolean> that indicates if the current node matches the given XPath expression or the given compiled <xref:System.Xml.XPath.XPathExpression> object.</span></span>  
  
## <a name="matching-nodes"></a><span data-ttu-id="8d3c4-105">Vergleich von Knoten</span><span class="sxs-lookup"><span data-stu-id="8d3c4-105">Matching Nodes</span></span>  
 <span data-ttu-id="8d3c4-106">Die <xref:System.Xml.XPath.XPathNavigator.Matches%2A>-Methode gibt `true` zurück, wenn der aktuelle Knoten dem angegebenen XPath-Ausdruck entspricht.</span><span class="sxs-lookup"><span data-stu-id="8d3c4-106">The <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method returns `true` if the current node matches the XPath expression specified.</span></span> <span data-ttu-id="8d3c4-107">Im folgenden Codebeispiel gibt z. B. die <xref:System.Xml.XPath.XPathNavigator.Matches%2A>-Methode `true` zurück, wenn es sich beim aktuellen Knoten um das `b`-Element handelt und das `b`-Element ein `c`-Attribut aufweist.</span><span class="sxs-lookup"><span data-stu-id="8d3c4-107">For example, in the code example that follows, the <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method will return `true` if the current node is the element `b`, and element `b` has an attribute `c`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8d3c4-108">Die <xref:System.Xml.XPath.XPathNavigator.Matches%2A>-Methode ändert den Status des <xref:System.Xml.XPath.XPathNavigator> nicht.</span><span class="sxs-lookup"><span data-stu-id="8d3c4-108">The <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method does not change the state of the <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
```vb  
Dim document as XPathDocument = New XPathDocument("input.xml")  
Dim navigator as XPathNavigator = document.CreateNavigator()  
  
navigator.Matches("b[@c]")  
```  
  
```csharp  
XPathDocument document = new XPathDocument("input.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.Matches("b[@c]");  
```  
  
## <a name="see-also"></a><span data-ttu-id="8d3c4-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8d3c4-109">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="8d3c4-110">Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells</span><span class="sxs-lookup"><span data-stu-id="8d3c4-110">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="8d3c4-111">Auswählen von XML-Daten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="8d3c4-111">Select XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="8d3c4-112">Auswerten von XPath-Ausdrücken mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="8d3c4-112">Evaluate XPath Expressions using XPathNavigator</span></span>](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)
- [<span data-ttu-id="8d3c4-113">In XPath-Abfragen erkannte Knotentypen</span><span class="sxs-lookup"><span data-stu-id="8d3c4-113">Node Types Recognized with XPath Queries</span></span>](../../../../docs/standard/data/xml/node-types-recognized-with-xpath-queries.md)
- [<span data-ttu-id="8d3c4-114">XPath-Abfragen und Namespaces</span><span class="sxs-lookup"><span data-stu-id="8d3c4-114">XPath Queries and Namespaces</span></span>](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)
- [<span data-ttu-id="8d3c4-115">Kompilierte XPath-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="8d3c4-115">Compiled XPath Expressions</span></span>](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)

---
title: Vergleich zwischen XPath und LINQ to XML
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 87d361b1-daa9-4fd4-a53a-cbfa40111ad3
ms.openlocfilehash: afd8701c6a37fd981d9fc23b57904da80eabf86e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54583163"
---
# <a name="comparison-of-xpath-and-linq-to-xml"></a><span data-ttu-id="44741-102">Vergleich zwischen XPath und LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="44741-102">Comparison of XPath and LINQ to XML</span></span>
<span data-ttu-id="44741-103">XPath und LINQ to XML haben einige Gemeinsamkeiten hinsichtlich ihrer Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="44741-103">XPath and LINQ to XML offer some similar functionality.</span></span> <span data-ttu-id="44741-104">Beide können verwendet werden, um Elementauflistungen, Attributauflistungen, Knotenauflistungen oder die Werte von Elementen oder Attributen aus XML-Strukturen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="44741-104">Both can be used to query an XML tree, returning such results as a collection of elements, a collection of attributes, a collection of nodes, or the value of an element or attribute.</span></span> <span data-ttu-id="44741-105">Aber es gibt auch einige Unterschiede.</span><span class="sxs-lookup"><span data-stu-id="44741-105">However, there are also some differences.</span></span>  
  
## <a name="differences-between-xpath-and-linq-to-xml"></a><span data-ttu-id="44741-106">Unterschiede zwischen XPath und LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="44741-106">Differences Between XPath and LINQ to XML</span></span>  
 <span data-ttu-id="44741-107">XPath lässt keine Projektion neuer Typen zu</span><span class="sxs-lookup"><span data-stu-id="44741-107">XPath does not allow projection of new types.</span></span> <span data-ttu-id="44741-108">Es können nur Sammlungen der Knoten aus der Struktur zurückgegeben werden. LINQ to XML kann dagegen eine Abfrage ausführen und ein Objektdiagramm oder eine XML-Struktur in einer neuen Form projizieren.</span><span class="sxs-lookup"><span data-stu-id="44741-108">It can only return collections of nodes from the tree, whereas LINQ to XML can execute a query and project an object graph or an XML tree in a new shape.</span></span> <span data-ttu-id="44741-109">LINQ to XML-Abfragen umfassen deutlich mehr Funktionen und sind viel leistungsstärker als XPath-Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="44741-109">LINQ to XML queries encompass much more functionality and are much more powerful than XPath expressions.</span></span>  
  
 <span data-ttu-id="44741-110">XPath-Ausdrücke existieren innerhalb einer Zeichenfolge isoliert.</span><span class="sxs-lookup"><span data-stu-id="44741-110">XPath expressions exist in isolation within a string.</span></span> <span data-ttu-id="44741-111">Der C#-Compiler kann nicht helfen, den XPath-Ausdruck beim Kompilieren zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="44741-111">The C# compiler cannot help parse the XPath expression at compile time.</span></span> <span data-ttu-id="44741-112">LINQ to XML-Abfragen werden dagegen vom C#-Compiler analysiert und kompiliert.</span><span class="sxs-lookup"><span data-stu-id="44741-112">By contrast, LINQ to XML queries are parsed and compiled by the C# compiler.</span></span> <span data-ttu-id="44741-113">Der Compiler kann eine Vielzahl von Abfragefehlern abfangen.</span><span class="sxs-lookup"><span data-stu-id="44741-113">The compiler is able to catch many query errors.</span></span>  
  
 <span data-ttu-id="44741-114">XPath-Ergebnisse sind nicht stark typisiert.</span><span class="sxs-lookup"><span data-stu-id="44741-114">XPath results are not strongly typed.</span></span> <span data-ttu-id="44741-115">In vielen Situationen ist das Ergebnis der Auswertung eines XPath-Ausdrucks ein Objekt, und es obliegt dem Entwickler, den richtigen Typ zu bestimmen und das Ergebnis nach Bedarf zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="44741-115">In a number of circumstances, the result of evaluating an XPath expression is an object, and it is up to the developer to determine the proper type and cast the result as necessary.</span></span> <span data-ttu-id="44741-116">Im Gegensatz dazu sind die Projektionen aus einer LINQ to XML-Abfrage stark typisiert.</span><span class="sxs-lookup"><span data-stu-id="44741-116">By contrast, the projections from a LINQ to XML query are strongly typed.</span></span>  
  
## <a name="result-ordering"></a><span data-ttu-id="44741-117">Reihenfolge der Ergebnisanzeige</span><span class="sxs-lookup"><span data-stu-id="44741-117">Result Ordering</span></span>  
 <span data-ttu-id="44741-118">Laut XPath 1.0-Empfehlung ist eine Auflistung, die das Ergebnis der Auswertung eines XPath-Ausdrucks ist, nicht geordnet.</span><span class="sxs-lookup"><span data-stu-id="44741-118">The XPath 1.0 Recommendation states that a collection that is the result of evaluating an XPath expression is unordered.</span></span>  
  
 <span data-ttu-id="44741-119">Beim Durchlaufen einer Sammlung, die von einer LINQ to XML-XPath-Achsenmethode zurückgegeben wurde, werden die Knoten in der Sammlung jedoch in der Dokumentreihenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="44741-119">However, when iterating through a collection returned by a LINQ to XML XPath axis method, the nodes in the collection are returned in document order.</span></span> <span data-ttu-id="44741-120">Dies ist auch beim Zugriff auf die XPath-Achsen der Fall, wo beim Ausdrücken von Prädikaten auf die umgekehrte Dokumentreihenfolge zurückgegriffen wird, wie z. B. `preceding` und `preceding-sibling`.</span><span class="sxs-lookup"><span data-stu-id="44741-120">This is the case even when accessing the XPath axes where predicates are expressed in terms of reverse document order, such as `preceding` and `preceding-sibling`.</span></span>  
  
 <span data-ttu-id="44741-121">Die meisten LINQ to XML-Achsen geben Sammlungen in der Dokumentreihenfolge zurück, aber bei zweien, <xref:System.Xml.Linq.XNode.Ancestors%2A> und <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A>, werden die Sammlungen in umgekehrter Dokumentreihenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="44741-121">By contrast, most of the LINQ to XML axes return collections in document order, but two of them, <xref:System.Xml.Linq.XNode.Ancestors%2A> and <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A>, return collections in reverse document order.</span></span> <span data-ttu-id="44741-122">In der folgenden Tabelle werden die Achsen aufgeführt, und es wird jeweils die Auflistungsreihenfolge angegeben:</span><span class="sxs-lookup"><span data-stu-id="44741-122">The following table enumerates the axes, and indicates collection order for each:</span></span>  
  
|<span data-ttu-id="44741-123">LINQ to XML-Achse</span><span class="sxs-lookup"><span data-stu-id="44741-123">LINQ to XML axis</span></span>|<span data-ttu-id="44741-124">Sortieren</span><span class="sxs-lookup"><span data-stu-id="44741-124">Ordering</span></span>|  
|----------------------|--------------|  
|<span data-ttu-id="44741-125">XContainer.DescendantNodes</span><span class="sxs-lookup"><span data-stu-id="44741-125">XContainer.DescendantNodes</span></span>|<span data-ttu-id="44741-126">Dokumentreihenfolge</span><span class="sxs-lookup"><span data-stu-id="44741-126">Document order</span></span>|  
|<span data-ttu-id="44741-127">XContainer.Descendants</span><span class="sxs-lookup"><span data-stu-id="44741-127">XContainer.Descendants</span></span>|<span data-ttu-id="44741-128">Dokumentreihenfolge</span><span class="sxs-lookup"><span data-stu-id="44741-128">Document order</span></span>|  
|<span data-ttu-id="44741-129">XContainer.Elements</span><span class="sxs-lookup"><span data-stu-id="44741-129">XContainer.Elements</span></span>|<span data-ttu-id="44741-130">Dokumentreihenfolge</span><span class="sxs-lookup"><span data-stu-id="44741-130">Document order</span></span>|  
|<span data-ttu-id="44741-131">XContainer.Nodes</span><span class="sxs-lookup"><span data-stu-id="44741-131">XContainer.Nodes</span></span>|<span data-ttu-id="44741-132">Dokumentreihenfolge</span><span class="sxs-lookup"><span data-stu-id="44741-132">Document order</span></span>|  
|<span data-ttu-id="44741-133">XContainer.NodesAfterSelf</span><span class="sxs-lookup"><span data-stu-id="44741-133">XContainer.NodesAfterSelf</span></span>|<span data-ttu-id="44741-134">Dokumentreihenfolge</span><span class="sxs-lookup"><span data-stu-id="44741-134">Document order</span></span>|  
|<span data-ttu-id="44741-135">XContainer.NodesBeforeSelf</span><span class="sxs-lookup"><span data-stu-id="44741-135">XContainer.NodesBeforeSelf</span></span>|<span data-ttu-id="44741-136">Dokumentreihenfolge</span><span class="sxs-lookup"><span data-stu-id="44741-136">Document order</span></span>|  
|<span data-ttu-id="44741-137">XElement.AncestorsAndSelf</span><span class="sxs-lookup"><span data-stu-id="44741-137">XElement.AncestorsAndSelf</span></span>|<span data-ttu-id="44741-138">Umgekehrte Dokumentreihenfolge</span><span class="sxs-lookup"><span data-stu-id="44741-138">Reverse document order</span></span>|  
|<span data-ttu-id="44741-139">XElement.Attributes</span><span class="sxs-lookup"><span data-stu-id="44741-139">XElement.Attributes</span></span>|<span data-ttu-id="44741-140">Dokumentreihenfolge</span><span class="sxs-lookup"><span data-stu-id="44741-140">Document order</span></span>|  
|<span data-ttu-id="44741-141">XElement.DescendantNodesAndSelf</span><span class="sxs-lookup"><span data-stu-id="44741-141">XElement.DescendantNodesAndSelf</span></span>|<span data-ttu-id="44741-142">Dokumentreihenfolge</span><span class="sxs-lookup"><span data-stu-id="44741-142">Document order</span></span>|  
|<span data-ttu-id="44741-143">XElement.DescendantsAndSelf</span><span class="sxs-lookup"><span data-stu-id="44741-143">XElement.DescendantsAndSelf</span></span>|<span data-ttu-id="44741-144">Dokumentreihenfolge</span><span class="sxs-lookup"><span data-stu-id="44741-144">Document order</span></span>|  
|<span data-ttu-id="44741-145">XNode.Ancestors</span><span class="sxs-lookup"><span data-stu-id="44741-145">XNode.Ancestors</span></span>|<span data-ttu-id="44741-146">Umgekehrte Dokumentreihenfolge</span><span class="sxs-lookup"><span data-stu-id="44741-146">Reverse document order</span></span>|  
|<span data-ttu-id="44741-147">XNode.ElementsAfterSelf</span><span class="sxs-lookup"><span data-stu-id="44741-147">XNode.ElementsAfterSelf</span></span>|<span data-ttu-id="44741-148">Dokumentreihenfolge</span><span class="sxs-lookup"><span data-stu-id="44741-148">Document order</span></span>|  
|<span data-ttu-id="44741-149">XNode.ElementsBeforeSelf</span><span class="sxs-lookup"><span data-stu-id="44741-149">XNode.ElementsBeforeSelf</span></span>|<span data-ttu-id="44741-150">Dokumentreihenfolge</span><span class="sxs-lookup"><span data-stu-id="44741-150">Document order</span></span>|  
|<span data-ttu-id="44741-151">XNode.NodesAfterSelf</span><span class="sxs-lookup"><span data-stu-id="44741-151">XNode.NodesAfterSelf</span></span>|<span data-ttu-id="44741-152">Dokumentreihenfolge</span><span class="sxs-lookup"><span data-stu-id="44741-152">Document order</span></span>|  
|<span data-ttu-id="44741-153">XNode.NodesBeforeSelf</span><span class="sxs-lookup"><span data-stu-id="44741-153">XNode.NodesBeforeSelf</span></span>|<span data-ttu-id="44741-154">Dokumentreihenfolge</span><span class="sxs-lookup"><span data-stu-id="44741-154">Document order</span></span>|  
  
## <a name="positional-predicates"></a><span data-ttu-id="44741-155">Positionsprädikate</span><span class="sxs-lookup"><span data-stu-id="44741-155">Positional Predicates</span></span>  
 <span data-ttu-id="44741-156">Innerhalb von XPath-Ausdrücken werden Positionsprädikate bei vielen Achsen in der Dokumentreihenfolge angegeben, aber bei den rückwärts gerichteten Achsen `preceding`, `preceding-sibling`, `ancestor` und `ancestor-or-self` wird die umgekehrte Dokumentreihenfolge verwendet.</span><span class="sxs-lookup"><span data-stu-id="44741-156">Within an XPath expression, positional predicates are expressed in terms of document order for many axes, but are expressed in reverse document order for reverse axes, which are `preceding`, `preceding-sibling`, `ancestor`, and `ancestor-or-self`.</span></span> <span data-ttu-id="44741-157">So gibt z. B. der XPath-Ausdruck `preceding-sibling::*[1]` das unmittelbar vorausgehende nebengeordnete Element zurück,</span><span class="sxs-lookup"><span data-stu-id="44741-157">For example, the XPath expression `preceding-sibling::*[1]` returns the immediately preceding sibling.</span></span> <span data-ttu-id="44741-158">auch wenn das endgültige Resultset in der Dokumentreihenfolge angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="44741-158">This is the case even though the final result set is presented in document order.</span></span>  
  
 <span data-ttu-id="44741-159">Dagegen werden alle Positionsprädikate in LINQ to XML stets in der Reihenfolge der Achse angegeben.</span><span class="sxs-lookup"><span data-stu-id="44741-159">By contrast, all positional predicates in LINQ to XML are always expressed in terms of the order of the axis.</span></span> <span data-ttu-id="44741-160">So wird z. B. bei `anElement.ElementsBeforeSelf().ElementAt(0)` statt des unmittelbar vorausgehenden nebengeordneten Elements das erste untergeordnete Element der Ebene oberhalb des abgefragten Elements zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="44741-160">For example, `anElement.ElementsBeforeSelf().ElementAt(0)` returns the first child element of the parent of the queried element, not the immediate preceding sibling.</span></span> <span data-ttu-id="44741-161">Ein anderes Beispiel: `anElement.Ancestors().ElementAt(0)` gibt das übergeordnete Element zurück.</span><span class="sxs-lookup"><span data-stu-id="44741-161">Another example: `anElement.Ancestors().ElementAt(0)` returns the parent element.</span></span>  
  
 <span data-ttu-id="44741-162">Wenn Sie für die Suche nach dem unmittelbar vorausgehenden Element LINQ to XML verwenden möchten, müssten Sie den folgenden Ausdruck schreiben:</span><span class="sxs-lookup"><span data-stu-id="44741-162">If you wanted to find the immediately preceding element in LINQ to XML, you would write the following expression:</span></span>  
  
```csharp
ElementsBeforeSelf().Last()
```
  
```vb
ElementsBeforeSelf().Last()
```
  
## <a name="performance-differences"></a><span data-ttu-id="44741-163">Leistungsunterschiede</span><span class="sxs-lookup"><span data-stu-id="44741-163">Performance Differences</span></span>  
 <span data-ttu-id="44741-164">XPath-Abfragen, die die XPath-Funktionalität in LINQ to XML verwenden, sind nicht so schnell, wie LINQ to XML-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="44741-164">XPath queries that use the XPath functionality in LINQ to XML will not perform as well as LINQ to XML queries.</span></span>  
  
## <a name="comparison-of-composition"></a><span data-ttu-id="44741-165">Verfassen von Abfragen im Vergleich</span><span class="sxs-lookup"><span data-stu-id="44741-165">Comparison of Composition</span></span>  
 <span data-ttu-id="44741-166">Das Verfassen einer LINQ to XML-Abfrage weist Parallelen mit dem Verfassen eines XPath-Ausdrucks auf, beide haben aber eine sehr unterschiedliche Syntax.</span><span class="sxs-lookup"><span data-stu-id="44741-166">Composition of a LINQ to XML query is somewhat parallel to composition of an XPath expression, although very different in syntax.</span></span>  
  
 <span data-ttu-id="44741-167">Wenn Sie z. B. ein Element in einer Variable namens `customers` haben und in allen untergeordneten Elementen mit dem Namen `CompanyName` nach einem Element der zweiten Unterebene namens `Customer` suchen, würden Sie den folgenden XPath-Ausdruck schreiben:</span><span class="sxs-lookup"><span data-stu-id="44741-167">For example, if you have an element in a variable named `customers`, and you want to find a grandchild element named `CompanyName` under all child elements named `Customer`, you would write an XPath expression as follows:</span></span>  
  
```csharp  
customers.XPathSelectElements("./Customer/CompanyName")
```  
  
```vb
customers.XPathSelectElements("./Customer/CompanyName")
```

 <span data-ttu-id="44741-168">Die entsprechende LINQ to XML-Abfrage lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="44741-168">The equivalent LINQ to XML query is:</span></span>  
  
```csharp  
customers.Elements("Customer").Elements("CompanyName")
```  
  
```vb
customers.Elements("Customer").Elements("CompanyName")
```  

 <span data-ttu-id="44741-169">Ähnliche Parallelen gibt es auch bei allen anderen XPath-Achsen.</span><span class="sxs-lookup"><span data-stu-id="44741-169">There are similar parallels for each of the XPath axes.</span></span>  
  
|<span data-ttu-id="44741-170">XPath-Achse</span><span class="sxs-lookup"><span data-stu-id="44741-170">XPath axis</span></span>|<span data-ttu-id="44741-171">LINQ to XML-Achse</span><span class="sxs-lookup"><span data-stu-id="44741-171">LINQ to XML axis</span></span>|  
|----------------|----------------------|  
|<span data-ttu-id="44741-172">child (Standardachse)</span><span class="sxs-lookup"><span data-stu-id="44741-172">child (the default axis)</span></span>|<xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="44741-173">parent (..)</span><span class="sxs-lookup"><span data-stu-id="44741-173">Parent (..)</span></span>|<xref:System.Xml.Linq.XObject.Parent%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="44741-174">@ (Attributachse)</span><span class="sxs-lookup"><span data-stu-id="44741-174">attribute axis (@)</span></span>|<xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=nameWithType><br /><br /> <span data-ttu-id="44741-175">oder</span><span class="sxs-lookup"><span data-stu-id="44741-175">or</span></span><br /><br /> <xref:System.Xml.Linq.XElement.Attributes%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="44741-176">ancestor-Achse</span><span class="sxs-lookup"><span data-stu-id="44741-176">ancestor axis</span></span>|<xref:System.Xml.Linq.XNode.Ancestors%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="44741-177">ancestor-or-self-Achse</span><span class="sxs-lookup"><span data-stu-id="44741-177">ancestor-or-self axis</span></span>|<xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="44741-178">descendant (//)</span><span class="sxs-lookup"><span data-stu-id="44741-178">descendant axis (//)</span></span>|<xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType><br /><br /> <span data-ttu-id="44741-179">oder</span><span class="sxs-lookup"><span data-stu-id="44741-179">or</span></span><br /><br /> <xref:System.Xml.Linq.XContainer.DescendantNodes%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="44741-180">descendant-or-self</span><span class="sxs-lookup"><span data-stu-id="44741-180">descendant-or-self</span></span>|<xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A?displayProperty=nameWithType><br /><br /> <span data-ttu-id="44741-181">oder</span><span class="sxs-lookup"><span data-stu-id="44741-181">or</span></span><br /><br /> <xref:System.Xml.Linq.XElement.DescendantNodesAndSelf%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="44741-182">following-sibling</span><span class="sxs-lookup"><span data-stu-id="44741-182">following-sibling</span></span>|<xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A?displayProperty=nameWithType><br /><br /> <span data-ttu-id="44741-183">oder</span><span class="sxs-lookup"><span data-stu-id="44741-183">or</span></span><br /><br /> <xref:System.Xml.Linq.XNode.NodesAfterSelf%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="44741-184">preceding-sibling</span><span class="sxs-lookup"><span data-stu-id="44741-184">preceding-sibling</span></span>|<xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType><br /><br /> <span data-ttu-id="44741-185">oder</span><span class="sxs-lookup"><span data-stu-id="44741-185">or</span></span><br /><br /> <xref:System.Xml.Linq.XNode.NodesBeforeSelf%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="44741-186">following</span><span class="sxs-lookup"><span data-stu-id="44741-186">following</span></span>|<span data-ttu-id="44741-187">Keine direkte Entsprechung.</span><span class="sxs-lookup"><span data-stu-id="44741-187">No direct equivalent.</span></span>|  
|<span data-ttu-id="44741-188">preceding</span><span class="sxs-lookup"><span data-stu-id="44741-188">preceding</span></span>|<span data-ttu-id="44741-189">Keine direkte Entsprechung.</span><span class="sxs-lookup"><span data-stu-id="44741-189">No direct equivalent.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44741-190">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44741-190">See also</span></span>

- [<span data-ttu-id="44741-191">LINQ to XML für XPath-Benutzer (C#)</span><span class="sxs-lookup"><span data-stu-id="44741-191">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)

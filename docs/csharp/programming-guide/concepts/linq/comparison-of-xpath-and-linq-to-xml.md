---
title: Vergleich zwischen XPath und LINQ to XML2
ms.date: 07/20/2015
ms.assetid: 87d361b1-daa9-4fd4-a53a-cbfa40111ad3
ms.openlocfilehash: 64860ab538105e7e3826b29f83b8e713ca525e21
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33326432"
---
# <a name="comparison-of-xpath-and-linq-to-xml"></a>Vergleich zwischen XPath und LINQ to XML
XPath und [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] haben hinsichtlich ihrer Funktionalität einige Gemeinsamkeiten. Beide können verwendet werden, um Elementauflistungen, Attributauflistungen, Knotenauflistungen oder die Werte von Elementen oder Attributen aus XML-Strukturen abzurufen. Aber es gibt auch einige Unterschiede.  
  
## <a name="differences-between-xpath-and-linq-to-xml"></a>Unterschiede zwischen XPath und LINQ to XML  
 XPath lässt keine Projektion neuer Typen zu Es können nur Auflistungen der Knoten aus der Struktur zurückgegeben werden. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] kann dagegen eine Abfrage ausführen und ein Objektdiagramm oder eine XML-Struktur in einer neuen Form projizieren. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfragen umfassen deutlich mehr Funktionen und sind viel leistungsstärker als XPath-Ausdrücke.  
  
 XPath-Ausdrücke existieren innerhalb einer Zeichenfolge isoliert. Der C#-Compiler kann nicht helfen, den XPath-Ausdruck beim Kompilieren zu analysieren. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfragen werden dagegen vom C#-Compiler analysiert und kompiliert. Der Compiler kann eine Vielzahl von Abfragefehlern abfangen.  
  
 XPath-Ergebnisse sind nicht stark typisiert. In vielen Situationen ist das Ergebnis der Auswertung eines XPath-Ausdrucks ein Objekt, und es obliegt dem Entwickler, den richtigen Typ zu bestimmen und das Ergebnis nach Bedarf zu konvertieren. Im Gegensatz dazu sind die Projektionen aus einer [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfrage stark typisiert.  
  
## <a name="result-ordering"></a>Reihenfolge der Ergebnisanzeige  
 Laut XPath 1.0-Empfehlung ist eine Auflistung, die das Ergebnis der Auswertung eines XPath-Ausdrucks ist, nicht geordnet.  
  
 Beim Durchlaufen einer Auflistung, die von einer [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-XPath-Achsenmethode zurückgegeben wurde, werden die Knoten in der Auflistung jedoch in der Dokumentreihenfolge zurückgegeben. Dies ist auch beim Zugriff auf die XPath-Achsen der Fall, wo beim Ausdrücken von Prädikaten auf die umgekehrte Dokumentreihenfolge zurückgegriffen wird, wie z. B. `preceding` und `preceding-sibling`.  
  
 Die meisten [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Achsen geben Auflistungen in der Dokumentreihenfolge zurück, aber bei zweien, <xref:System.Xml.Linq.XNode.Ancestors%2A> und <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A>, werden die Auflistungen in umgekehrter Dokumentreihenfolge zurückgegeben. In der folgenden Tabelle werden die Achsen aufgeführt, und es wird jeweils die Auflistungsreihenfolge angegeben:  
  
|LINQ to XML-Achse|Sortieren|  
|----------------------|--------------|  
|XContainer.DescendantNodes|Dokumentreihenfolge|  
|XContainer.Descendants|Dokumentreihenfolge|  
|XContainer.Elements|Dokumentreihenfolge|  
|XContainer.Nodes|Dokumentreihenfolge|  
|XContainer.NodesAfterSelf|Dokumentreihenfolge|  
|XContainer.NodesBeforeSelf|Dokumentreihenfolge|  
|XElement.AncestorsAndSelf|Umgekehrte Dokumentreihenfolge|  
|XElement.Attributes|Dokumentreihenfolge|  
|XElement.DescendantNodesAndSelf|Dokumentreihenfolge|  
|XElement.DescendantsAndSelf|Dokumentreihenfolge|  
|XNode.Ancestors|Umgekehrte Dokumentreihenfolge|  
|XNode.ElementsAfterSelf|Dokumentreihenfolge|  
|XNode.ElementsBeforeSelf|Dokumentreihenfolge|  
|XNode.NodesAfterSelf|Dokumentreihenfolge|  
|XNode.NodesBeforeSelf|Dokumentreihenfolge|  
  
## <a name="positional-predicates"></a>Positionsprädikate  
 Innerhalb von XPath-Ausdrücken werden Positionsprädikate bei vielen Achsen in der Dokumentreihenfolge angegeben, aber bei den rückwärts gerichteten Achsen `preceding`, `preceding-sibling`, `ancestor` und `ancestor-or-self` wird die umgekehrte Dokumentreihenfolge verwendet. So gibt z. B. der XPath-Ausdruck `preceding-sibling::*[1]` das unmittelbar vorausgehende nebengeordnete Element zurück, auch wenn das endgültige Resultset in der Dokumentreihenfolge angegeben wird.  
  
 Dagegen werden alle Positionsprädikate in LINQ to XML stets in der Reihenfolge der Achse angegeben. So wird z. B. bei `anElement.ElementsBeforeSelf().ToList()[0]` statt des unmittelbar vorausgehenden nebengeordneten Elements das erste untergeordnete Element der Ebene oberhalb des abgefragten Elements zurückgegeben. Ein anderes Beispiel: `anElement.Ancestors().ToList()[0]` gibt das übergeordnete Element zurück.  
  
 Beachten Sie, dass bei der oben beschriebenen Herangehensweise die gesamte Auflistung materialisiert wird. Dies ist nicht die effizienteste Art, diese Abfrage zu schreiben. Die Abfrage in der dargestellten Form soll lediglich das Verhalten der Positionsprädikate zeigen. Dieselbe Abfrage könnte vernünftiger mit der <xref:System.Linq.Enumerable.First%2A>-Methode geschrieben werden: `anElement.ElementsBeforeSelf().First()`.  
  
 Wenn Sie für die Suche nach dem unmittelbar vorausgehenden Element [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] verwenden möchten, müssten Sie den folgenden Ausdruck schreiben:  
  
 `ElementsBeforeSelf().Last()`  
  
## <a name="performance-differences"></a>Leistungsunterschiede  
 XPath-Abfragen, die die XPath-Funktionalität in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] verwenden, sind nicht so schnell, wie [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfragen.  
  
## <a name="comparison-of-composition"></a>Verfassen von Abfragen im Vergleich  
 Das Verfassen einer [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfrage weist Parallelen mit dem Verfassen eines XPath-Ausdrucks auf, beide haben aber eine sehr unterschiedliche Syntax.  
  
 Wenn Sie z. B. ein Element in einer Variable namens `customers` haben und in allen untergeordneten Elementen mit dem Namen `CompanyName` nach einem Element der zweiten Unterebene namens `Customer` suchen, würden Sie den folgenden XPath-Ausdruck schreiben:  
  
```csharp  
customers.XPathSelectElements("./Customer/CompanyName");  
```  
  
 Die entsprechende [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfrage würde wie folgt lauten:  
  
```csharp  
customers.Element("Customer").Elements("CompanyName");  
```  
  
 Ähnliche Parallelen gibt es auch bei allen anderen XPath-Achsen.  
  
|XPath-Achse|LINQ to XML-Achse|  
|----------------|----------------------|  
|child (Standardachse)|<xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>|  
|parent (..)|<xref:System.Xml.Linq.XObject.Parent%2A?displayProperty=nameWithType>|  
|@ (Attributachse)|<xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=nameWithType><br /><br /> oder<br /><br /> <xref:System.Xml.Linq.XElement.Attributes%2A?displayProperty=nameWithType>|  
|ancestor-Achse|<xref:System.Xml.Linq.XNode.Ancestors%2A?displayProperty=nameWithType>|  
|ancestor-or-self-Achse|<xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A?displayProperty=nameWithType>|  
|descendant (//)|<xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType><br /><br /> oder<br /><br /> <xref:System.Xml.Linq.XContainer.DescendantNodes%2A?displayProperty=nameWithType>|  
|descendant-or-self|<xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A?displayProperty=nameWithType><br /><br /> oder<br /><br /> <xref:System.Xml.Linq.XElement.DescendantNodesAndSelf%2A?displayProperty=nameWithType>|  
|following-sibling|<xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A?displayProperty=nameWithType><br /><br /> oder<br /><br /> <xref:System.Xml.Linq.XNode.NodesAfterSelf%2A?displayProperty=nameWithType>|  
|preceding-sibling|<xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType><br /><br /> oder<br /><br /> <xref:System.Xml.Linq.XNode.NodesBeforeSelf%2A?displayProperty=nameWithType>|  
|following|Keine direkte Entsprechung.|  
|preceding|Keine direkte Entsprechung.|  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ to XML für XPath-Benutzer (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)

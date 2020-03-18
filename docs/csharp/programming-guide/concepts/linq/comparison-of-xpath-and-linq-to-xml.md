---
title: Vergleich zwischen XPath und LINQ to XML
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 87d361b1-daa9-4fd4-a53a-cbfa40111ad3
ms.openlocfilehash: e9bf192a2075653802f0c5a8b4e44ff0ceacb975
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "66487532"
---
# <a name="comparison-of-xpath-and-linq-to-xml"></a>Vergleich zwischen XPath und LINQ to XML
XPath und LINQ to XML haben einige Gemeinsamkeiten hinsichtlich ihrer Funktionalität. Beide können verwendet werden, um Elementauflistungen, Attributauflistungen, Knotenauflistungen oder die Werte von Elementen oder Attributen aus XML-Strukturen abzurufen. Aber es gibt auch einige Unterschiede.  
  
## <a name="differences-between-xpath-and-linq-to-xml"></a>Unterschiede zwischen XPath und LINQ to XML  
 XPath lässt keine Projektion neuer Typen zu Es können nur Sammlungen der Knoten aus der Struktur zurückgegeben werden. LINQ to XML kann dagegen eine Abfrage ausführen und ein Objektdiagramm oder eine XML-Struktur in einer neuen Form projizieren. LINQ to XML-Abfragen umfassen deutlich mehr Funktionen und sind viel leistungsstärker als XPath-Ausdrücke.  
  
 XPath-Ausdrücke existieren innerhalb einer Zeichenfolge isoliert. Der C#-Compiler kann nicht helfen, den XPath-Ausdruck beim Kompilieren zu analysieren. LINQ to XML-Abfragen werden dagegen vom C#-Compiler analysiert und kompiliert. Der Compiler kann eine Vielzahl von Abfragefehlern abfangen.  
  
 XPath-Ergebnisse sind nicht stark typisiert. In vielen Situationen ist das Ergebnis der Auswertung eines XPath-Ausdrucks ein Objekt, und es obliegt dem Entwickler, den richtigen Typ zu bestimmen und das Ergebnis nach Bedarf zu konvertieren. Im Gegensatz dazu sind die Projektionen aus einer LINQ to XML-Abfrage stark typisiert.  
  
## <a name="result-ordering"></a>Reihenfolge der Ergebnisanzeige  
 Laut XPath 1.0-Empfehlung ist eine Auflistung, die das Ergebnis der Auswertung eines XPath-Ausdrucks ist, nicht geordnet.  
  
 Beim Durchlaufen einer Sammlung, die von einer LINQ to XML-XPath-Achsenmethode zurückgegeben wurde, werden die Knoten in der Sammlung jedoch in der Dokumentreihenfolge zurückgegeben. Dies ist auch beim Zugriff auf die XPath-Achsen der Fall, wo beim Ausdrücken von Prädikaten auf die umgekehrte Dokumentreihenfolge zurückgegriffen wird, wie z. B. `preceding` und `preceding-sibling`.  
  
 Die meisten LINQ to XML-Achsen geben Sammlungen in der Dokumentreihenfolge zurück, aber bei zweien, <xref:System.Xml.Linq.XNode.Ancestors%2A> und <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A>, werden die Sammlungen in umgekehrter Dokumentreihenfolge zurückgegeben. In der folgenden Tabelle werden die Achsen aufgeführt, und es wird jeweils die Auflistungsreihenfolge angegeben:  
  
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
  
 Dagegen werden alle Positionsprädikate in LINQ to XML stets in der Reihenfolge der Achse angegeben. So wird z. B. bei `anElement.ElementsBeforeSelf().ElementAt(0)` statt des unmittelbar vorausgehenden nebengeordneten Elements das erste untergeordnete Element der Ebene oberhalb des abgefragten Elements zurückgegeben. Ein anderes Beispiel: `anElement.Ancestors().ElementAt(0)` gibt das übergeordnete Element zurück.  
  
 Wenn Sie für die Suche nach dem unmittelbar vorausgehenden Element LINQ to XML verwenden möchten, müssten Sie den folgenden Ausdruck schreiben:  
  
```csharp
ElementsBeforeSelf().Last()
```
  
```vb
ElementsBeforeSelf().Last()
```
  
## <a name="performance-differences"></a>Leistungsunterschiede  
 XPath-Abfragen, die die XPath-Funktionalität in LINQ to XML verwenden, sind nicht so schnell, wie LINQ to XML-Abfragen.  
  
## <a name="comparison-of-composition"></a>Verfassen von Abfragen im Vergleich  
 Das Verfassen einer LINQ to XML-Abfrage weist Parallelen mit dem Verfassen eines XPath-Ausdrucks auf, beide haben aber eine sehr unterschiedliche Syntax.  
  
 Wenn Sie z. B. ein Element in einer Variable namens `customers` haben und in allen untergeordneten Elementen mit dem Namen `CompanyName` nach einem Element der zweiten Unterebene namens `Customer` suchen, würden Sie den folgenden XPath-Ausdruck schreiben:  
  
```csharp  
customers.XPathSelectElements("./Customer/CompanyName")
```  
  
```vb
customers.XPathSelectElements("./Customer/CompanyName")
```

 Die entsprechende LINQ to XML-Abfrage lautet wie folgt:  
  
```csharp  
customers.Elements("Customer").Elements("CompanyName")
```  
  
```vb
customers.Elements("Customer").Elements("CompanyName")
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
  
---
title: "LINQ to XML Axes (Übersicht) (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 9161f151-cfa8-4408-94ba-08a9ba3a486d
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b127aa6b443e865c76831d886f110550ec785e9b
ms.lasthandoff: 03/13/2017


---
# <a name="linq-to-xml-axes-overview-visual-basic"></a>LINQ to XML-Achsen (Übersicht) (Visual Basic)
Nachdem Sie eine XML-Struktur erstellt oder ein XML-Dokument in eine XML-Struktur geladen haben, können Sie durch Abfragen der XML-Struktur nach Elementen und Attributen suchen und deren Werte abrufen. Abrufen von Auflistungen erfolgt über die *Achsenmethoden*auch namens *Achsen*. Einige der Achsen sind Methoden in der <xref:System.Xml.Linq.XElement>und <xref:System.Xml.Linq.XDocument>Klassen zurückgegebene <xref:System.Collections.Generic.IEnumerable%601>Sammlungen.</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> Einige der Achsen sind Erweiterungsmethoden in der <xref:System.Xml.Linq.Extensions>Klasse.</xref:System.Xml.Linq.Extensions> Die Achsen, die als Erweiterungsmethode implementiert werden, arbeiten mit Auflistungen und geben Auflistungen zurück.  
  
 Wie unter [Übersicht über die XElement-Klasse](http://msdn.microsoft.com/library/d35180fe-7016-4895-9bfc-ba1e3f7875ec), ein <xref:System.Xml.Linq.XElement>-Objekt stellt einen einzelnen Elementknoten dar.</xref:System.Xml.Linq.XElement> Der Inhalt eines Elements kann komplex sein (dies wird mitunter als strukturierter Inhalt bezeichnet), es kann sich bei dem Element aber auch um ein einfaches Element handeln. Ein einfaches Element kann leer sein oder einen Wert enthalten. Wenn der Knoten strukturierten Inhalt enthält, können Sie mit den verschiedenen Achsenmethoden Enumerationen der Nachfolgerelemente abrufen. Die am häufigsten verwendeten Achsenmethoden sind, <xref:System.Xml.Linq.XContainer.Elements%2A>und <xref:System.Xml.Linq.XContainer.Descendants%2A>.</xref:System.Xml.Linq.XContainer.Descendants%2A> </xref:System.Xml.Linq.XContainer.Elements%2A>  
  
 Neben den Achsenmethoden, die Auflistungen zurückgeben, es gibt zwei weitere Methoden, die Sie häufig in verwenden [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] Abfragen. Die <xref:System.Xml.Linq.XContainer.Element%2A>Methode gibt ein einzelnes <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XContainer.Element%2A> Die <xref:System.Xml.Linq.XElement.Attribute%2A>Methode gibt ein einzelnes <xref:System.Xml.Linq.XAttribute>.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement.Attribute%2A>  
  
 Für viele Zwecke sind [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Abfragen die bessere Variante, eine Struktur zu prüfen, Daten aus einer Struktur zu extrahieren und die Daten zu transformieren. [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Abfragen arbeiten mit Objekten, die implementieren <xref:System.Collections.Generic.IEnumerable%601>, und die [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] -Achsen Return <xref:System.Collections.Generic.IEnumerable%601>von <xref:System.Xml.Linq.XElement>Sammlungen und <xref:System.Collections.Generic.IEnumerable%601>von <xref:System.Xml.Linq.XAttribute>Sammlungen.</xref:System.Xml.Linq.XAttribute> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.Generic.IEnumerable%601> Diese Auflistungen benötigen Sie zum Ausführen Ihrer Abfragen.  
  
 Neben den Achsenmethoden, die Auflistungen von Elementen und Attributen abrufen, gibt es auch Achsenmethoden, die es Ihnen erlauben, die Struktur sehr genau zu durchlaufen. So können Sie z. B. anstelle von Elementen und Attributen auch mit den Knoten der Struktur arbeiten. Knoten bieten im Vergleich zu Elementen und Attributen eine höhere Detailgenauigkeit (Granularität). Beim Arbeiten mit Knoten können Sie XML-Kommentare, -Textknoten, -Verarbeitungsanweisungen und anderes untersuchen. Diese Funktionalität ist z. B. für Entwickler wichtig, die ein Textverarbeitungsprogramm schreiben und Dokumente als XML speichern möchten. Die Mehrheit der XML-Programmierer hat aber vor allem mit Elementen und Attributen sowie deren Werten zu tun.  
  
## <a name="methods-for-retrieving-a-collection-of-elements"></a>Methoden zum Abrufen einer Auflistung von Elementen  
 Im folgenden werden eine Zusammenfassung der Methoden von der <xref:System.Xml.Linq.XElement>-Klasse (oder deren Basisklassen), die Sie aufrufen, ein <xref:System.Xml.Linq.XElement>zum Zurückgeben einer Auflistung von Elementen.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement>  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.Ancestors%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.Ancestors%2A?displayProperty=fullName>|Gibt eine <xref:System.Collections.Generic.IEnumerable%601>von <xref:System.Xml.Linq.XElement>von den übergeordneten Elementen dieses Elements.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> Eine Überladung gibt eine <xref:System.Collections.Generic.IEnumerable%601>der <xref:System.Xml.Linq.XElement>von den übergeordneten Elementen, die über den angegebenen <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601>|  
|<xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=fullName></xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=fullName>|Gibt eine <xref:System.Collections.Generic.IEnumerable%601>der <xref:System.Xml.Linq.XElement>der Nachfolger dieses Elements.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> Eine Überladung gibt eine <xref:System.Collections.Generic.IEnumerable%601>von <xref:System.Xml.Linq.XElement>der abhängigen Elemente, die über den angegebenen <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601>|  
|<xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName></xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName>|Gibt eine <xref:System.Collections.Generic.IEnumerable%601>der <xref:System.Xml.Linq.XElement>der untergeordneten Elemente dieses Elements.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> Eine Überladung gibt eine <xref:System.Collections.Generic.IEnumerable%601>der <xref:System.Xml.Linq.XElement>untergeordneten Elemente, die über den angegebenen <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601>|  
|<xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A?displayProperty=fullName>|Gibt eine <xref:System.Collections.Generic.IEnumerable%601>der <xref:System.Xml.Linq.XElement>der Elemente, die diesem Element folgen.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> Eine Überladung gibt eine <xref:System.Collections.Generic.IEnumerable%601>von <xref:System.Xml.Linq.XElement>der Elemente nach diesem Element, die über den angegebenen <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601>|  
|<xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=fullName>|Gibt eine <xref:System.Collections.Generic.IEnumerable%601>der <xref:System.Xml.Linq.XElement>der Elemente, die vor diesem Element befinden.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> Eine Überladung gibt eine <xref:System.Collections.Generic.IEnumerable%601>von <xref:System.Xml.Linq.XElement>der Elemente vor diesem Element, die über den angegebenen <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601>|  
|<xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A?displayProperty=fullName>|Gibt eine <xref:System.Collections.Generic.IEnumerable%601>der <xref:System.Xml.Linq.XElement>dieses Elements und dessen Vorgänger.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> Eine Überladung gibt eine <xref:System.Collections.Generic.IEnumerable%601>von <xref:System.Xml.Linq.XElement>der Elemente, die über den angegebenen <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601>|  
|<xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A?displayProperty=fullName>|Gibt eine <xref:System.Collections.Generic.IEnumerable%601>der <xref:System.Xml.Linq.XElement>dieses Elements und dessen Nachfolger.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> Eine Überladung gibt eine <xref:System.Collections.Generic.IEnumerable%601>von <xref:System.Xml.Linq.XElement>der Elemente, die über den angegebenen <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601>|  
  
## <a name="method-for-retrieving-a-single-element"></a>Methode zum Abrufen eines einzelnen Elements  
 Die folgende Methode ruft ein einzelnes untergeordnetes Element aus einem <xref:System.Xml.Linq.XElement>Objekt.</xref:System.Xml.Linq.XElement>  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=fullName></xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=fullName>|Gibt das erste untergeordnete <xref:System.Xml.Linq.XElement>Objekt, das den angegebenen <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> verfügt</xref:System.Xml.Linq.XElement>|  
  
## <a name="method-for-retrieving-a-collection-of-attributes"></a>Methoden zum Abrufen einer Auflistung von Attributen  
 Die folgende Methode ruft Attribute aus einem <xref:System.Xml.Linq.XElement>Objekt.</xref:System.Xml.Linq.XElement>  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Attributes%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Attributes%2A?displayProperty=fullName>|Gibt eine <xref:System.Collections.Generic.IEnumerable%601>der <xref:System.Xml.Linq.XAttribute>aller Attribute.</xref:System.Xml.Linq.XAttribute> </xref:System.Collections.Generic.IEnumerable%601>|  
  
## <a name="method-for-retrieving-a-single-attribute"></a>Methode zum Abrufen eines einzelnen Attributs  
 Die folgende Methode ruft ein einzelnes Attribut aus einer <xref:System.Xml.Linq.XElement>Objekt.</xref:System.Xml.Linq.XElement>  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName>|Gibt die <xref:System.Xml.Linq.XAttribute>, bei dem der angegebene <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XAttribute>|  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ to XML-Achsen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)

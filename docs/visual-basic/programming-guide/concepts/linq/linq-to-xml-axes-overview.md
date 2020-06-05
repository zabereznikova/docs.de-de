---
title: Übersicht über LINQ to XML-Achsen
ms.date: 07/20/2015
ms.assetid: 9161f151-cfa8-4408-94ba-08a9ba3a486d
ms.openlocfilehash: 447490e784aa531b6603ddcd32d01eabea8f7299
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84368997"
---
# <a name="linq-to-xml-axes-overview-visual-basic"></a>Übersicht über LINQ to XML-Achsen (Visual Basic)
Nachdem Sie eine XML-Struktur erstellt oder ein XML-Dokument in eine XML-Struktur geladen haben, können Sie durch Abfragen der XML-Struktur nach Elementen und Attributen suchen und deren Werte abrufen. Das Abrufen von Auflistungen erfolgt über die *Achsenmethoden*, auch kurz *Achsen* genannt. Einige der Achsen sind Methoden in der <xref:System.Xml.Linq.XElement>-Klasse und in der <xref:System.Xml.Linq.XDocument>-Klasse, die <xref:System.Collections.Generic.IEnumerable%601>-Auflistungen zurückgeben. Bei einigen Achsen handelt es sich um Erweiterungsmethoden in der <xref:System.Xml.Linq.Extensions>-Klasse. Die Achsen, die als Erweiterungsmethode implementiert werden, arbeiten mit Auflistungen und geben Auflistungen zurück.  
  
 Wie unter [Übersicht über die XElement-Klasse](xelement-class-overview.md) beschrieben wird, stellt ein <xref:System.Xml.Linq.XElement>-Objekt einen einzelnen Elementknoten dar. Der Inhalt eines Elements kann komplex sein (dies wird mitunter als strukturierter Inhalt bezeichnet), es kann sich bei dem Element aber auch um ein einfaches Element handeln. Ein einfaches Element kann leer sein oder einen Wert enthalten. Wenn der Knoten strukturierten Inhalt enthält, können Sie mit den verschiedenen Achsenmethoden Enumerationen der Nachfolgerelemente abrufen. Die am häufigsten verwendeten Achsenmethoden sind <xref:System.Xml.Linq.XContainer.Elements%2A> und <xref:System.Xml.Linq.XContainer.Descendants%2A>.  
  
 Neben den Achsenmethoden, die Auflistungen zurückgeben, gibt es zwei weitere Methoden, die häufig in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfragen eingesetzt werden. Die <xref:System.Xml.Linq.XContainer.Element%2A>-Methode gibt ein einzelnes <xref:System.Xml.Linq.XElement> zurück. Die <xref:System.Xml.Linq.XElement.Attribute%2A>-Methode gibt ein einzelnes <xref:System.Xml.Linq.XAttribute> zurück.  
  
 Für viele Zwecke sind LINQ-Abfragen die bessere Variante, eine Struktur zu prüfen, Daten aus einer Struktur zu extrahieren und die Daten zu transformieren. LINQ-Abfragen arbeiten mit Objekten, die <xref:System.Collections.Generic.IEnumerable%601> implementieren, und die [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Achsen geben <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement>-Sammlungen und <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XAttribute>-Sammlungen zurück. Diese Auflistungen benötigen Sie zum Ausführen Ihrer Abfragen.  
  
 Neben den Achsenmethoden, die Auflistungen von Elementen und Attributen abrufen, gibt es auch Achsenmethoden, die es Ihnen erlauben, die Struktur sehr genau zu durchlaufen. So können Sie z. B. anstelle von Elementen und Attributen auch mit den Knoten der Struktur arbeiten. Knoten bieten im Vergleich zu Elementen und Attributen eine höhere Detailgenauigkeit (Granularität). Beim Arbeiten mit Knoten können Sie XML-Kommentare, -Textknoten, -Verarbeitungsanweisungen und anderes untersuchen. Diese Funktionalität ist z. B. für Entwickler wichtig, die ein Textverarbeitungsprogramm schreiben und Dokumente als XML speichern möchten. Die Mehrheit der XML-Programmierer hat aber vor allem mit Elementen und Attributen sowie deren Werten zu tun.  
  
## <a name="methods-for-retrieving-a-collection-of-elements"></a>Methoden zum Abrufen einer Auflistung von Elementen  
 Im Folgenden finden Sie eine Zusammenfassung der Methoden der <xref:System.Xml.Linq.XElement>-Klasse (bzw. ihrer Basisklassen), die Sie für <xref:System.Xml.Linq.XElement> mit dem Ziel aufrufen, eine Auflistung von Elementen zurückzugeben.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.Ancestors%2A?displayProperty=nameWithType>|Gibt eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> der Vorgänger dieses Elements zurück. Eine Überladung gibt eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> der Vorgänger mit dem angegebenen <xref:System.Xml.Linq.XName> zurück.|  
|<xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>|Gibt eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> der Nachfolger dieses Elements zurück. Eine Überladung gibt eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> der Nachfolger mit dem angegebenen <xref:System.Xml.Linq.XName> zurück.|  
|<xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>|Gibt eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> der untergeordneten Elemente dieses Elements zurück. Eine Überladung gibt eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> der untergeordneten Elemente mit dem angegebenen <xref:System.Xml.Linq.XName> zurück.|  
|<xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A?displayProperty=nameWithType>|Gibt eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> der Elemente zurück, die diesem Element folgen. Eine Überladung gibt eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> der Elemente mit dem angegebenen <xref:System.Xml.Linq.XName> zurück, die diesem Element folgen.|  
|<xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType>|Gibt eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> der Elemente zurück, die sich vor diesem Element befinden. Eine Überladung gibt eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> der Elemente mit dem angegebenen <xref:System.Xml.Linq.XName> zurück, die sich vor diesem Element befinden.|  
|<xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A?displayProperty=nameWithType>|Gibt eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> dieses Elements und dessen Vorgänger zurück. Eine Überladung gibt eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> der Elemente mit dem angegebenen <xref:System.Xml.Linq.XName> zurück.|  
|<xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A?displayProperty=nameWithType>|Gibt eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> dieses Elements und dessen Nachfolger zurück. Eine Überladung gibt eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> der Elemente mit dem angegebenen <xref:System.Xml.Linq.XName> zurück.|  
  
## <a name="method-for-retrieving-a-single-element"></a>Methode zum Abrufen eines einzelnen Elements  
 Die folgende Methode ruft ein einzelnes untergeordnetes Element aus einem <xref:System.Xml.Linq.XElement>-Objekt ab.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=nameWithType>|Gibt das erste untergeordnete <xref:System.Xml.Linq.XElement>-Objekt zurück, das den angegebenen <xref:System.Xml.Linq.XName> hat.|  
  
## <a name="method-for-retrieving-a-collection-of-attributes"></a>Methoden zum Abrufen einer Auflistung von Attributen  
 Die folgende Methode ruft Attribute aus einem <xref:System.Xml.Linq.XElement>-Objekt ab.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Attributes%2A?displayProperty=nameWithType>|Gibt eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XAttribute> aller Attribute zurück.|  
  
## <a name="method-for-retrieving-a-single-attribute"></a>Methode zum Abrufen eines einzelnen Attributs  
 Die folgende Methode ruft ein einzelnes Attribut aus einem <xref:System.Xml.Linq.XElement>-Objekt ab.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=nameWithType>|Gibt das <xref:System.Xml.Linq.XAttribute> zurück, das den angegebenen <xref:System.Xml.Linq.XName> hat.|  
  
## <a name="see-also"></a>Weitere Informationen

- [LINQ to XML-Achsen (Visual Basic)](linq-to-xml-axes.md)

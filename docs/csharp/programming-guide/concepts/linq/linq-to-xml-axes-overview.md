---
title: "Übersicht über LINQ to XML-Achsen (C#) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 516792fb-461d-40a8-8a50-9993a51258fc
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b43d3cb5cc7154c1133c5fa17e5bdacca97a38c9
ms.lasthandoff: 03/13/2017


---
# <a name="linq-to-xml-axes-overview-c"></a>Übersicht über LINQ to XML-Achsen (C#)
Nachdem Sie eine XML-Struktur erstellt oder ein XML-Dokument in eine XML-Struktur geladen haben, können Sie durch Abfragen der XML-Struktur nach Elementen und Attributen suchen und deren Werte abrufen. Das Abrufen von Auflistungen erfolgt über die *Achsenmethoden*, auch kurz *Achsen* genannt. Einige der Achsen sind Methoden in der Klasse <xref:System.Xml.Linq.XElement> und <xref:System.Xml.Linq.XDocument>, die die Auflistungen <xref:System.Collections.Generic.IEnumerable%601> zurückgeben. Einige der Achsen sind Erweiterungsmethoden in der Klasse <xref:System.Xml.Linq.Extensions>. Die Achsen, die als Erweiterungsmethode implementiert werden, arbeiten mit Auflistungen und geben Auflistungen zurück.  
  
 Wie unter [Übersicht der XElement-Klasse](http://msdn.microsoft.com/library/d35180fe-7016-4895-9bfc-ba1e3f7875ec) beschrieben wird, stellt ein Objekt <xref:System.Xml.Linq.XElement> einen einzelnen Elementknoten dar. Der Inhalt eines Elements kann komplex sein (dies wird mitunter als strukturierter Inhalt bezeichnet), es kann sich bei dem Element aber auch um ein einfaches Element handeln. Ein einfaches Element kann leer sein oder einen Wert enthalten. Wenn der Knoten strukturierten Inhalt enthält, können Sie mit den verschiedenen Achsenmethoden Enumerationen der Nachfolgerelemente abrufen. Die am häufigsten verwendeten Achsenmethoden sind <xref:System.Xml.Linq.XContainer.Elements%2A> und <xref:System.Xml.Linq.XContainer.Descendants%2A>.  
  
 Neben den Achsenmethoden, die Auflistungen zurückgeben, gibt es zwei weitere Methoden, die häufig in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]-Abfragen eingesetzt werden. Die Methode <xref:System.Xml.Linq.XContainer.Element%2A> gibt ein einzelnes <xref:System.Xml.Linq.XElement> zurück. Die Methode <xref:System.Xml.Linq.XElement.Attribute%2A> gibt ein einzelnes <xref:System.Xml.Linq.XAttribute> zurück.  
  
 Für viele Zwecke sind [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Abfragen die bessere Variante, eine Struktur zu prüfen, Daten aus einer Struktur zu extrahieren und die Daten zu transformieren. [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Abfragen verarbeiten Objekte, die <xref:System.Collections.Generic.IEnumerable%601> implementieren; die [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]-Achse gibt <xref:System.Collections.Generic.IEnumerable%601> der Auflistungen <xref:System.Xml.Linq.XElement> sowie <xref:System.Collections.Generic.IEnumerable%601> der Auflistungen <xref:System.Xml.Linq.XAttribute> zurück. Diese Auflistungen benötigen Sie zum Ausführen Ihrer Abfragen.  
  
 Neben den Achsenmethoden, die Auflistungen von Elementen und Attributen abrufen, gibt es auch Achsenmethoden, die es Ihnen erlauben, die Struktur sehr genau zu durchlaufen. So können Sie z. B. anstelle von Elementen und Attributen auch mit den Knoten der Struktur arbeiten. Knoten bieten im Vergleich zu Elementen und Attributen eine höhere Detailgenauigkeit (Granularität). Beim Arbeiten mit Knoten können Sie XML-Kommentare, -Textknoten, -Verarbeitungsanweisungen und anderes untersuchen. Diese Funktionalität ist z. B. für Entwickler wichtig, die ein Textverarbeitungsprogramm schreiben und Dokumente als XML speichern möchten. Die Mehrheit der XML-Programmierer hat aber vor allem mit Elementen und Attributen sowie deren Werten zu tun.  
  
## <a name="methods-for-retrieving-a-collection-of-elements"></a>Methoden zum Abrufen einer Auflistung von Elementen  
 Im Folgenden finden Sie eine Zusammenfassung der Methoden der Klasse <xref:System.Xml.Linq.XElement> (bzw. ihrer Basisklassen), die Sie für <xref:System.Xml.Linq.XElement> aufrufen, um eine Auflistung von Elementen zurückzugeben.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.Ancestors%2A?displayProperty=fullName>|Gibt eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> der Vorgängerelemente von diesem Element zurück. Eine Überladung gibt <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> der Vorgängerelemente zurück, die den angegebenen <xref:System.Xml.Linq.XName> haben.|  
|<xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=fullName>|Gibt eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> der Nachfolgerelemente von diesem Element zurück. Eine Überladung gibt eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> der Nachfolgerelemente zurück, die den angegebenen <xref:System.Xml.Linq.XName> haben.|  
|<xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName>|Gibt eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> der untergeordneten Elemente dieses Elements zurück. Eine Überladung gibt eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> der untergeordneten Elemente zurück, die den angegebenen <xref:System.Xml.Linq.XName> haben.|  
|<xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A?displayProperty=fullName>|Gibt eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> der Elemente zurück, die auf dieses Element folgen. Eine Überladung gibt eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> der Elemente nach dem Element zurück, die den angegebenen <xref:System.Xml.Linq.XName> haben.|  
|<xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=fullName>|Gibt eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> der Elemente zurück, die vor diesem Element kommen. Eine Überladung gibt eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> der Elemente vor dem Element zurück, die den angegebenen <xref:System.Xml.Linq.XName> haben.|  
|<xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A?displayProperty=fullName>|Gibt eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> des Elements und seinen Vorgängerelementen zurück. Eine Überladung gibt eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> der Elemente zurück, die den angegebenen <xref:System.Xml.Linq.XName> haben.|  
|<xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A?displayProperty=fullName>|Gibt eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> des Elements und seinen Nachfolgerelementen zurück. Eine Überladung gibt eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> der Elemente zurück, die den angegebenen <xref:System.Xml.Linq.XName> haben.|  
  
## <a name="method-for-retrieving-a-single-element"></a>Methode zum Abrufen eines einzelnen Elements  
 Die folgende Methode ruft ein einzelnes untergeordnetes Element aus einem xref:System.Xml.Linq.XElement>-Objekt ab.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=fullName>|Gibt das erste untergeordnete Objekt <xref:System.Xml.Linq.XElement> zurück, das den angegebenen <xref:System.Xml.Linq.XName> hat|  
  
## <a name="method-for-retrieving-a-collection-of-attributes"></a>Methoden zum Abrufen einer Auflistung von Attributen  
 Die folgende Methode ruft Attribute von einem Objekt <xref:System.Xml.Linq.XElement> ab.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Attributes%2A?displayProperty=fullName>|Gibt ein <xref:System.Collections.Generic.IEnumerable%601> des <xref:System.Xml.Linq.XAttribute> von allen Attributen zurück|  
  
## <a name="method-for-retrieving-a-single-attribute"></a>Methode zum Abrufen eines einzelnen Attributs  
 Die folgende Methode ruft ein einzelnes Attribut aus einem xref:System.Xml.Linq.XElement>-Objekt ab.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName>|Gibt das erste <xref:System.Xml.Linq.XElement> zurück, das den angegebenen <xref:System.Xml.Linq.XName> hat|  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ to XML-Achsen (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)

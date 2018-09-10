---
title: Ändern von Elementen, Attributen und Knoten in einem XML-Struktur
ms.date: 07/20/2015
ms.assetid: 0ed22e4e-4c6b-4eb1-b0eb-06685efd8c33
ms.openlocfilehash: 9567d0c6c5cd4853eeb2a86066cd1a805f20a031
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43777349"
---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a>Ändern von Elementen, Attributen und Knoten in einer XML-Struktur
Die folgende Tabelle enthält eine Zusammenstellung der Methoden und Eigenschaften, die Sie zum Ändern eines Elements, der untergeordneten Elemente dieses Elements oder seiner Attribute verwenden können.  
  
 Mit den folgenden Methoden wird ein <xref:System.Xml.Linq.XElement>-Objekt geändert.  
  
|Methode|Beschreibung |  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>|Ersetzt ein Element durch analysiertes XML.|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|Entfernt den gesamten Inhalt (untergeordnete Knoten und Attribute) eines Elements.|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|Entfernt die Attribute eines Elements.|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=nameWithType>|Ersetzt den gesamten Inhalt (untergeordnete Knoten und Attribute) eines Elements.|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=nameWithType>|Ersetzt die Attribute eines Elements.|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|Legt den Wert eines Attributs fest. Erstellt das Attribut, wenn es nicht existiert. Entfernt das Attribut, wenn der Wert auf `null` gesetzt ist.|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|Legt den Wert eines untergeordneten Elements fest. Erstellt das Element, wenn es nicht existiert. Entfernt das Element, wenn der Wert auf `null` gesetzt ist.|  
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>|Ersetzt den Inhalt (untergeordnete Knoten) eines Elements durch den angegebenen Text.|  
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=nameWithType>|Legt den Wert eines Elements fest.|  
  
 Mit den folgenden Methoden wird ein <xref:System.Xml.Linq.XAttribute>-Objekt geändert.  
  
|Methode|Beschreibung |  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>|Legt den Wert eines Attributs fest.|  
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=nameWithType>|Legt den Wert eines Attributs fest.|  
  
 Mit den folgenden Methoden wird ein <xref:System.Xml.Linq.XNode> (einschließlich <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument>) geändert.  
  
|Methode|Beschreibung |  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=nameWithType>|Ersetzt einen Knoten durch neuen Inhalt.|  
  
 Mit den folgenden Methoden wird ein <xref:System.Xml.Linq.XContainer> (<xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument>) geändert.  
  
|Methode|Beschreibung |  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=nameWithType>|Ersetzt die untergeordneten Knoten durch neuen Inhalt.|  
  
## <a name="see-also"></a>Siehe auch

- [Modifying XML Trees (LINQ to XML) (C#) (Ändern von XML-Strukturen (LINQ to XML) (C#))](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)

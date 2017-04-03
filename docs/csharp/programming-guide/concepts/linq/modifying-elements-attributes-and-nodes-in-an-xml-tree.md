---
title: "Ändern von Elementen, Attributen und Knoten in einer XML-Struktur3 | Microsoft-Dokumentation"
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
ms.assetid: 0ed22e4e-4c6b-4eb1-b0eb-06685efd8c33
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6fa51b22af73d716b01444540edb7c8d814cd293
ms.lasthandoff: 03/13/2017


---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a>Ändern von Elementen, Attributen und Knoten in einer XML-Struktur
Die folgende Tabelle enthält eine Zusammenstellung der Methoden und Eigenschaften, die Sie zum Ändern eines Elements, der untergeordneten Elemente dieses Elements oder seiner Attribute verwenden können.  
  
 Die folgenden Methoden ändern ein <xref:System.Xml.Linq.XElement>.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>|Ersetzt ein Element durch analysiertes XML.|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName>|Entfernt den gesamten Inhalt (untergeordnete Knoten und Attribute) eines Elements.|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName>|Entfernt die Attribute eines Elements.|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=fullName>|Ersetzt den gesamten Inhalt (untergeordnete Knoten und Attribute) eines Elements.|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=fullName>|Ersetzt die Attribute eines Elements.|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName>|Legt den Wert eines Attributs fest. Erstellt das Attribut, wenn es nicht existiert. Entfernt das Attribut, wenn der Wert auf `null` gesetzt ist.|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName>|Legt den Wert eines untergeordneten Elements fest. Erstellt das Element, wenn es nicht existiert. Entfernt das Element, wenn der Wert auf `null` gesetzt ist.|  
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName>|Ersetzt den Inhalt (untergeordnete Knoten) eines Elements durch den angegebenen Text.|  
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=fullName>|Legt den Wert eines Elements fest.|  
  
 Die folgenden Methoden ändern ein <xref:System.Xml.Linq.XAttribute>.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>|Legt den Wert eines Attributs fest.|  
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=fullName>|Legt den Wert eines Attributs fest.|  
  
 Die folgenden Methoden ändern einen <xref:System.Xml.Linq.XNode> (einschließlich eines <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument>).  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=fullName>|Ersetzt einen Knoten durch neuen Inhalt.|  
  
 Die folgenden Methoden ändern ein <xref:System.Xml.Linq.XContainer> (ein <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument>).  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=fullName>|Ersetzt die untergeordneten Knoten durch neuen Inhalt.|  
  
## <a name="see-also"></a>Siehe auch  
 [Modifying XML Trees (LINQ to XML) (C#) (Ändern von XML-Strukturen (LINQ to XML) (C#))](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)

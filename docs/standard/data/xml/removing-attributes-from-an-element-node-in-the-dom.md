---
title: Entfernen von Attributen aus einem Elementknoten im DOM
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7ede6f9e-a3ac-49a4-8488-ab8360a44aa4
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b4ca08d8080c2116ce05634a544c91780869b165
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="removing-attributes-from-an-element-node-in-the-dom"></a>Entfernen von Attributen aus einem Elementknoten im DOM
Es gibt viele Möglichkeiten, Attribute zu entfernen. Eine Möglichkeit besteht darin, Attribute aus der Attributauflistung zu entfernen. Dabei werden die folgenden Schritte ausgeführt:  
  
1.  Rufen Sie mithilfe von `XmlAttributeCollection attrs = elem.Attributes;` die Attributauflistung aus dem Element ab.  
  
2.  Entfernen Sie das Attribut aus der Attributauflistung mithilfe einer dieser drei Methoden:  
  
    -   Entfernen Sie mit <xref:System.Xml.XmlAttributeCollection.Remove%2A> ein bestimmtes Attribut.  
  
    -   Entfernen Sie mit <xref:System.Xml.XmlAttributeCollection.RemoveAll%2A> alle Attribute aus der Auflistung, sodass das Element keine Attribute mehr aufweist.  
  
    -   Entfernen Sie mit <xref:System.Xml.XmlAttributeCollection.RemoveAt%2A> ein Attribut mithilfe der entsprechenden Indexnummer dieses Attributs aus der Attributauflistung.  
  
 Die folgenden Methoden entfernen Attribute aus dem Elementknoten.  
  
-   Verwenden Sie <xref:System.Xml.XmlElement.RemoveAllAttributes%2A>, um die Attributauflistung zu entfernen.  
  
-   Entfernen Sie mit <xref:System.Xml.XmlElement.RemoveAttribute%2A> ein einzelnes Attribut anhand seines Namens aus der Auflistung.  
  
-   Entfernen Sie mit <xref:System.Xml.XmlElement.RemoveAttributeAt%2A> ein einzelnes Attribut anhand seiner Indexnummer aus der Auflistung.  
  
 Eine weitere Möglichkeit ist das Abrufen des Elements, das Abrufen des Attributs aus der Attributauflistung und das direkte Entfernen des Attributknotens. Zum Abrufen des Attributs aus der Attributauflistung können Sie einen Namen verwenden, `XmlAttribute attr = attrs["attr_name"];`, einen Index `XmlAttribute attr = attrs[0];`, oder Sie können den Namen mit dem Namespace `XmlAttribute attr = attrs["attr_localName", "attr_namespace"]` voll qualifizieren.  
  
 Unabhängig davon, mithilfe welcher Methode Attribute entfernt wurden, bestehen spezielle Einschränkungen für das Entfernen von Standardattributen in der DTD (Document Type Definition). Standardattribute können nicht entfernt werden, wenn nicht das zugehörige Element ebenfalls entfernt wird. Es sind immer Standardattribute für Elemente vorhanden, für die Standardattribute deklariert wurden. Durch das Entfernen eines Standardattributs aus einer <xref:System.Xml.XmlAttributeCollection> oder aus dem <xref:System.Xml.XmlElement> wird ein Ersatzattribut in die <xref:System.Xml.XmlAttributeCollection> des Elements eingefügt, das mit dem deklarierten Standardwert initialisiert wurde. Wenn ein als `<book att1="1" att2="2" att3="3"></book>` definiertes Element vorhanden ist, ist dies ein `book`-Element mit drei deklarierten Standardattributen. Die Implementierung (XML-DOKUMENTOBJEKTMODELL) wird sichergestellt, dass solange dieses `book` Element vorhanden ist, sind diese drei Standardattribute `att1`, `att2`, und `att3`.  
  
 Bei einem Aufruf mit einem <xref:System.Xml.XmlAttribute> legt die <xref:System.Xml.XmlAttributeCollection.RemoveAll%2A>-Methode den Wert des Attributs auf <legacyBold>String.Empty</legacyBold> fest, da ein Attribut nicht ohne Wert existieren kann.  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)

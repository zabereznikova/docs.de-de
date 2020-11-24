---
title: Typenunterstützung in den System.Xml-Klassen
ms.date: 03/30/2017
ms.assetid: 63570538-06e3-4401-ad4d-ac50be90c7bf
ms.openlocfilehash: 8e4ef15980f488c473129f4f7c02be1778bcafea
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824622"
---
# <a name="type-support-in-the-systemxml-classes"></a>Typenunterstützung in den System.Xml-Klassen
In .NET Framework, Version 2.0, wurden die Kern-XML-Klassen erweitert und enthalten nun Funktionen zur Typunterstützung. Die Klassen <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> und <xref:System.Xml.XPath.XPathNavigator> enthalten Funktionen zur Typunterstützung. Dazu gehört auch die Funktion zum Konvertieren zwischen XML-Schematypen und CLR-Typen (Common Language Runtime).  
  
 In .NET Framework, Version 2.0, wurden die Klassen <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> und <xref:System.Xml.XPath.XPathNavigator> erweitert und enthalten nun Funktionen zur Typunterstützung.  
  
- Die <xref:System.Xml.XmlReader>-Klasse und die <xref:System.Xml.XPath.XPathNavigator>-Klasse enthalten jeweils eine **SchemaInfo**-Eigenschaft, die die Schemainformationen eines Knotens zurückgibt.  
  
- Die **ReadContentAs**-Eigenschaft und die **ReadElementContentAs**-Eigenschaft sowie die Methoden der <xref:System.Xml.XmlReader>-Klasse lesen einen Textwert und konvertieren diesen durch einen einzigen Methodenaufruf in einen CLR-Wert.  
  
- Die <xref:System.Xml.XmlWriter.WriteValue%2A>-Methode der <xref:System.Xml.XmlWriter>-Klasse konvertiert einen CLR-Typ beim Schreiben von XML-Daten in einen XML-Schematyp.  
  
- Die **ValueAs**-Eigenschaft und die <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A>-Eigenschaft der <xref:System.Xml.XPath.XPathNavigator>-Klasse geben einen Knotenwert zurück und konvertieren diesen durch einen einzigen Methodenaufruf in einen CLR-Wert.  
  
> [!NOTE]
> In .NET Framework, Version 1.0, war zum Konvertieren zwischen XML-Schematypen und CLR-Typen die <xref:System.Xml.XmlConvert>-Klasse erforderlich.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Zuordnen von XML-Datentypen zu CLR-Typen](mapping-xml-data-types-to-clr-types.md)  
 Beschreibt die Standardzuordnungen von XML-Datentypen zu CLR-Typen.  
  
 [Implementierungshinweise zur XML-Typunterstützung](xml-type-support-implementation-notes.md)  
 Erläutert einige Implementierungsdetails der Typunterstützung.  
  
 [Konvertierung von XML-Datentypen](conversion-of-xml-data-types.md)  
 Beschreibt die Verwendung der <xref:System.Xml.XmlConvert>-Klasse zum Konvertieren zwischen XML-Schematypen und CLR-Typen.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Zugreifen auf streng typisierte XML-Daten mit XPathNavigator](accessing-strongly-typed-xml-data-using-xpathnavigator.md)

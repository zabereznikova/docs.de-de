---
title: "Verwendung von System.Xml | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
caps.latest.revision: 4
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 4
---
# Verwendung von System.Xml
Dieser Abschnitt befasst sich mit Nutzung von mehreren Typen, die im <xref:System.Xml?displayProperty=fullName> \-Namespaces, die zum Darstellen von XML\-Daten verwendet werden kann.  
  
 **X nicht** verwenden <xref:System.Xml.XmlNode> oder <xref:System.Xml.XmlDocument> zur Darstellung von XML\-Daten. Mithilfe von Instanzen der bevorzugen <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, oder Untertypen von <xref:System.Xml.Linq.XNode> stattdessen.`XmlNode` und `XmlDocument` sind nicht für das Verfügbarmachen von öffentlichen APIs konzipiert.  
  
 **✓ führen** verwenden `XmlReader`, `IXPathNavigable`, oder Untertypen von `XNode` als Eingabe oder Ausgabe von Membern, die XML annehmen oder zurückgeben.  
  
 Verwenden Sie diese Abstraktionen anstelle von `XmlDocument`, `XmlNode`, oder <xref:System.Xml.XPath.XPathDocument>, da dadurch die Methoden von bestimmten Implementierungen eine speicherinterne XML\-Dokuments entkoppelt und zum Arbeiten mit virtuellen XML\-Datenquellen, die verfügbar machen `XNode`, `XmlReader`, oder <xref:System.Xml.XPath.XPathNavigator>.  
  
 **X nicht** Unterklasse `XmlDocument` wenn einen Typ zur Darstellung einer XML\-Ansicht der zugrunde liegenden Objektmodells oder einer Datenquelle erstellen möchten.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)   
 [Verwendungsrichtlinien](../../../docs/standard/design-guidelines/usage-guidelines.md)
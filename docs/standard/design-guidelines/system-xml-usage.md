---
title: Verwendung von System.Xml
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a9bfa0f984f97e774d00a64fc3fd8489b3d5b40e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="systemxml-usage"></a>Verwendung von System.Xml
In diesem Abschnitt finden Sie zur Verwendung von mehreren Typen, die in den <xref:System.Xml?displayProperty=nameWithType> Namespaces, die zum Darstellen von XML-Daten verwendet werden kann.  
  
 **X nicht** verwenden <xref:System.Xml.XmlNode> oder <xref:System.Xml.XmlDocument> zur Darstellung von XML-Daten. Mithilfe von Instanzen der begünstigen <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, oder Untertypen von <xref:System.Xml.Linq.XNode> stattdessen. `XmlNode`und `XmlDocument` dienen zum Verfügbarmachen von in öffentlichen APIs nicht.  
  
 **Führen Sie ✓** verwenden `XmlReader`, `IXPathNavigable`, oder Untertypen von `XNode` als Eingabe oder Ausgabe von Membern, die XML annehmen oder zurückgeben.  
  
 Verwenden Sie diese Abstraktionen anstelle von `XmlDocument`, `XmlNode`, oder <xref:System.Xml.XPath.XPathDocument>, da dies die Methoden aus bestimmter Implementierungen von XML-Dokuments im Arbeitsspeicher entkoppelt und ermöglicht es ihnen, die mit virtuellen XML-Datenquellen arbeiten, die verfügbar machen `XNode` , `XmlReader`, oder <xref:System.Xml.XPath.XPathNavigator>.  
  
 **X nicht** Unterklasse `XmlDocument` , wenn Sie einen Typ, eine XML-Sicht des zugrunde liegenden Modell oder die Datenquelle erstellen möchten.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
 [Verwendungsrichtlinien](../../../docs/standard/design-guidelines/usage-guidelines.md)

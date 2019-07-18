---
title: Verwendung von System.Xml
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
author: KrzysztofCwalina
ms.openlocfilehash: fc94ac62d1f2413c5f51446a8f6d0a52d9151557
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61650127"
---
# <a name="systemxml-usage"></a>Verwendung von System.Xml
Dieser Abschnitt behandelt wird, über die Verwendung von mehreren Typen, die sich im befinden <xref:System.Xml?displayProperty=nameWithType> Namespaces, die zum Darstellen von XML-Daten verwendet werden kann.  
  
 **X DO NOT** verwenden <xref:System.Xml.XmlNode> oder <xref:System.Xml.XmlDocument> zur Darstellung von XML-Daten. Bevorzugen Sie mithilfe von Instanzen der <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, oder Untertypen von <xref:System.Xml.Linq.XNode> stattdessen. `XmlNode` und `XmlDocument` sind nicht verfügbar zu machen, die in öffentlichen APIs konzipiert.  
  
 **✓ DO** verwenden `XmlReader`, `IXPathNavigable`, oder Untertypen von `XNode` als Eingabe oder Ausgabe von Membern, die XML annehmen oder zurückgeben.  
  
 Verwenden Sie diese Abstraktionen statt `XmlDocument`, `XmlNode`, oder <xref:System.Xml.XPath.XPathDocument>, da dies die Methoden von bestimmten Implementierungen eines in-Memory-XML-Dokuments entkoppelt und können sie mit virtuellen XML-Datenquellen, die verfügbar machen `XNode` , `XmlReader`, oder <xref:System.Xml.XPath.XPathNavigator>.  
  
 **X DO NOT** Unterklasse `XmlDocument` , wenn Sie einen Typ, eine XML-Sicht des zugrunde liegenden Modell oder die Datenquelle erstellen möchten.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Verwendungsrichtlinien](../../../docs/standard/design-guidelines/usage-guidelines.md)

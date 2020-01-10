---
title: Verwendung von System.Xml
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
ms.openlocfilehash: c57f5451526094d58066d7d391f41795f17732de
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709035"
---
# <a name="systemxml-usage"></a>Verwendung von System.Xml
In diesem Abschnitt wird die Verwendung mehrerer Typen in <xref:System.Xml?displayProperty=nameWithType> Namespaces erläutert, die zur Darstellung von XML-Daten verwendet werden können.  
  
 **X DO NOT** verwenden <xref:System.Xml.XmlNode> oder <xref:System.Xml.XmlDocument> zur Darstellung von XML-Daten. Bevorzugen Sie stattdessen die Verwendung von Instanzen von <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>oder Untertypen von <xref:System.Xml.Linq.XNode>. `XmlNode` und `XmlDocument` sind nicht für die Bereitstellung in öffentlichen APIs konzipiert.  
  
 **✓ DO** verwenden `XmlReader`, `IXPathNavigable`, oder Untertypen von `XNode` als Eingabe oder Ausgabe von Membern, die XML annehmen oder zurückgeben.  
  
 Verwenden Sie diese Abstraktionen anstelle von `XmlDocument`, `XmlNode`oder <xref:System.Xml.XPath.XPathDocument>, da dadurch die Methoden von bestimmten Implementierungen eines XML-Dokuments im Arbeitsspeicher entkoppelt werden und Sie mit virtuellen XML-Datenquellen arbeiten können, die `XNode`, `XmlReader`oder <xref:System.Xml.XPath.XPathNavigator>verfügbar machen.  
  
 **X DO NOT** Unterklasse `XmlDocument` , wenn Sie einen Typ, eine XML-Sicht des zugrunde liegenden Modell oder die Datenquelle erstellen möchten.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Verwendungsrichtlinien](../../../docs/standard/design-guidelines/usage-guidelines.md)

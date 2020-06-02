---
title: Verwendung von System.Xml
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
ms.openlocfilehash: 07828219f2e17be925d060fa3bb33a9209ecb62b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291668"
---
# <a name="systemxml-usage"></a>Verwendung von System.Xml
In diesem Abschnitt wird die Verwendung mehrerer Typen in <xref:System.Xml?displayProperty=nameWithType> Namespaces erläutert, die zum Darstellen von XML-Daten verwendet werden können.

 ❌Verwenden Sie <xref:System.Xml.XmlNode> oder nicht <xref:System.Xml.XmlDocument> , um XML-Daten darzustellen. Bevorzugen Sie stattdessen die Verwendung von Instanzen der-,-,- <xref:System.Xml.XPath.IXPathNavigable> <xref:System.Xml.XmlReader> oder- <xref:System.Xml.XmlWriter> Untertypen von <xref:System.Xml.Linq.XNode> . `XmlNode`und `XmlDocument` sind nicht für die Bereitstellung in öffentlichen APIs konzipiert.

 ✔️ verwenden `XmlReader` die-,-oder- `IXPathNavigable` Untertypen von `XNode` als Eingabe oder Ausgabe von Membern, die XML akzeptieren oder zurückgeben.

 Verwenden Sie diese Abstraktionen anstelle von `XmlDocument` , `XmlNode` oder <xref:System.Xml.XPath.XPathDocument> , da dadurch die Methoden von bestimmten Implementierungen eines XML-Dokuments im Arbeitsspeicher entkoppelt und mit virtuellen XML-Datenquellen verwendet werden können, die `XNode` , `XmlReader` oder <xref:System.Xml.XPath.XPathNavigator> verfügbar machen.

 ❌Verwenden Sie keine Unterklasse `XmlDocument` , wenn Sie einen Typ erstellen möchten, der eine XML-Sicht eines zugrunde liegenden Objektmodells oder einer zugrunde liegenden Datenquelle darstellt.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Framework-Entwurfs Richtlinien](index.md)
- [Verwendungs Richtlinien](usage-guidelines.md)

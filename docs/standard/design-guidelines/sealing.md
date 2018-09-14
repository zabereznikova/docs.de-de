---
title: Versiegeln
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- limiting extensibility
- classes [.NET Framework], sealing
- preventing customization
- sealed classes
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d8c445de44a69f6c0cb1eaefa0e59d682288318
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "45614007"
---
# <a name="sealing"></a>Versiegeln
Eines der Features von objektorientierten Frameworks ist, dass Entwickler erweitern können, und passen Sie sie in Methoden, die durch die Entwickler das Frameworks unvorhergesehenen. Dies ist die Leistung und die Gefahr von erweiterbaren Entwurf. Wenn Sie Ihr Framework entwerfen, es ist daher sehr wichtig für die Erweiterbarkeit von sorgfältig entworfen wird, wenn es gewünscht wird, um Erweiterbarkeit zu beschränken, wenn es gefährlich ist.  
  
 Ist ein leistungsstarker Mechanismus, der Erweiterbarkeit wird verhindert, dass beim versiegeln. Sie können entweder die Klasse oder eine einzelne Member versiegeln. Versiegelns einer Klasse wird verhindert, dass Benutzer erben von der Klasse. Versiegeln ein Element wird verhindert, dass Benutzer einen bestimmten Member überschreiben.  
  
 **X DO NOT** Klassen ohne einen guten Grund dazu versiegeln.  
  
 Versiegelns einer Klasse, da Sie eine Erweiterbarkeit Szenario vorstellen können nicht ist nicht aus einem triftigen Grund. Framework-Benutzer haben Lust sich aus verschiedenen Gründen nonobvious wie das Hinzufügen der Einfachheit halber Member von Klassen erben. Finden Sie unter [nicht versiegelte Klassen](../../../docs/standard/design-guidelines/unsealed-classes.md) Beispiele nonobvious Gründe für Benutzer von einem Typ erben möchten.  
  
 Gute Gründe für Versiegelns einer Klasse umfassen Folgendes:  
  
-   Die Klasse ist eine statische Klasse. Finden Sie unter [Entwurf statischer Klassen](../../../docs/standard/design-guidelines/static-class.md).  
  
-   Die Klasse speichert vertraulichen geheimen Schlüssel im geerbte geschützte Member an.  
  
-   Die Klasse erbt viele virtuelle Member aus, und die Kosten für das Versiegeln sie einzeln würde die Vorteile der Beibehaltung von nicht versiegelten Klasse überwiegen.  
  
-   Die Klasse ist ein Attribut, das Laufzeit sehr schnelle Suche erfordert. Sealed-Attribute haben geringfügig höherer Leistungsniveaus als nicht versiegeltes. finden Sie unter [Attribute](../../../docs/standard/design-guidelines/attributes.md).  
  
 **X DO NOT** geschützten oder virtuellen Member für versiegelte Typen deklarieren.  
  
 Per Definition können nicht versiegelte Typen von geerbt werden. Dies bedeutet, dass geschützte Member in versiegelten Typen nicht aufgerufen werden, und virtuelle Methoden für versiegelte Typen können nicht überschrieben werden.  
  
 **✓ CONSIDER** versiegeln Elemente, die Sie außer Kraft setzen.  
  
 Probleme, die sich ergeben können, aus der Einführung in virtuelle Member (ausführlicher [virtuelle Member](../../../docs/standard/design-guidelines/virtual-members.md)) auf Außerkraftsetzungen, die auch in etwas geringerem Maß anwenden. Versiegeln eine Außerkraftsetzung, schützt Sie vor solchen Problemen, die von diesem Punkt in der Vererbungshierarchie ab.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
- [Entwerfen für Erweiterbarkeit](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
- [Nicht versiegelte Klassen](../../../docs/standard/design-guidelines/unsealed-classes.md)

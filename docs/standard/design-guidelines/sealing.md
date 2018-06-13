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
ms.openlocfilehash: 3f7202e10e41b9f114f42a4502ee2e6694bf3821
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573737"
---
# <a name="sealing"></a>Versiegeln
Eine der Funktionen des Frameworks objektorientierte ist, dass Entwickler erweitern und Möglichkeiten, die bis zur servicebereitstellung durch die Framework-Designer anpassen können. Dies ist die Leistungsfähigkeit und die Gefahr eines extensible Entwurf. Wenn Sie Ihr Framework entwerfen, es ist daher sehr wichtig für die Erweiterbarkeit sorgfältig entworfen wird, wenn es gewünscht wird, und Erweiterbarkeit eingeschränkt werden, wenn es gefährlich ist.  
  
 Ein leistungsstarken Mechanismus, der die Erweiterbarkeit verhindert wird versiegeln. Sie können die Klasse oder die einzelnen Mitglieder versiegeln. Versiegelns einer Klasse wird verhindert, dass Benutzer von der Klasse erben. Versiegeln ein Element wird verhindert, dass Benutzer einen bestimmten Member überschreiben.  
  
 **X nicht** Klassen ohne einen guten Grund dazu versiegeln.  
  
 Versiegelns einer Klasse, da Sie eine Erweiterbarkeitsszenarios vorstellen können keine ist keinen guten Grund. Framework-Benutzer mögen aus verschiedenen Gründen nonobvious wie das Hinzufügen von halber Member von Klassen erben. Finden Sie unter [nicht versiegelte Klassen](../../../docs/standard/design-guidelines/unsealed-classes.md) Beispiele nonobvious Gründe für Benutzer von einem Typ erben möchten.  
  
 Gute Gründe für Versiegelns einer Klasse umfassen Folgendes:  
  
-   Die Klasse ist eine statische Klasse. Finden Sie unter [statische-Klassenentwurf](../../../docs/standard/design-guidelines/static-class.md).  
  
-   Die Klasse speichert sicherheitsrelevante geheime Schlüssel in geerbte geschützte Member an.  
  
-   Die Klasse erbt zahlreiche virtuelle Member und die Kosten für diese einzeln versiegeln würde überwiegen die Vorteile der Klasse nicht versiegelt.  
  
-   Die Klasse ist ein Attribut, das sehr schnelle Runtime Suche erfordert. Versiegelte Attribute haben leicht höhere Leistung als nicht versiegelten diejenigen. finden Sie unter [Attribute](../../../docs/standard/design-guidelines/attributes.md).  
  
 **X nicht** geschützten oder virtuellen Member für versiegelte Typen deklarieren.  
  
 Per Definition können nicht versiegelte Typen von vererbt werden. Dies bedeutet, dass geschützte Member in versiegelten Typen nicht aufgerufen werden, und virtuelle Methoden für versiegelte Typen können nicht überschrieben werden.  
  
 **✓ GGF.** versiegeln Elemente, die Sie außer Kraft setzen.  
  
 Probleme, die auftreten können, aus der Einführung in virtuelle Member (in behandelten [virtuelle Member](../../../docs/standard/design-guidelines/virtual-members.md)) gelten für Außerkraftsetzungen, auch in einem etwas geringeren Grad an. Versiegeln einer Außerkraftsetzung schützt Sie vor solchen Problemen, die von diesem Punkt in der Vererbungshierarchie ab.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
 [Entwerfen für Erweiterbarkeit](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [Nicht versiegelte Klassen](../../../docs/standard/design-guidelines/unsealed-classes.md)

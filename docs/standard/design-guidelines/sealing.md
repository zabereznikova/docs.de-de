---
title: Versiegeln
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- limiting extensibility
- classes [.NET Framework], sealing
- preventing customization
- sealed classes
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
ms.openlocfilehash: ddf463e98fb6a9c5ccaae90e9cfc74b5691b13a9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743625"
---
# <a name="sealing"></a>Versiegeln
Eines der Features von objektorientierten Frameworks besteht darin, dass Entwickler diese auf eine Weise erweitern und anpassen können, die von den Framework-Designern nicht erwartet wird. Dies ist sowohl die Leistungsfähigkeit als auch die Gefahr des erweiterbaren Entwurfs. Wenn Sie Ihr Framework entwerfen, ist es daher sehr wichtig, die Erweiterbarkeit bei Bedarf sorgfältig zu entwerfen und die Erweiterbarkeit zu begrenzen, wenn dies gefährlich ist.

 Ein leistungsfähiger Mechanismus, der die Erweiterbarkeit verhindert, ist das versiegeln. Sie können entweder die Klasse oder einzelne Member versiegeln. Durch das Versiegeln einer Klasse wird verhindert, dass Benutzer von der-Klasse erben. Das Versiegeln eines Members verhindert, dass Benutzer ein bestimmtes Element überschreiben.

 ❌ keine Klassen versiegeln, ohne einen guten Grund dafür zu haben.

 Das Versiegeln einer Klasse, da Sie sich kein Erweiterbarkeits Szenario vorstellen können, ist kein guter Grund. Frameworkbenutzer, die aus verschiedenen nicht offensichtlichen Gründen von Klassen erben, wie das Hinzufügen von hilfsmembern. Unter [nicht versiegelte Klassen](../../../docs/standard/design-guidelines/unsealed-classes.md) finden Sie Beispiele für nicht offensichtliche Gründe, warum Benutzer von einem Typ erben möchten.

 Gute Gründe für das Versiegeln einer Klasse sind folgende:

- Die-Klasse ist eine statische Klasse. Siehe [static Class Design](../../../docs/standard/design-guidelines/static-class.md).

- Die-Klasse speichert sicherheitsrelevante Geheimnisse in geerbten geschützten Membern.

- Die Klasse erbt viele virtuelle Member, und die Kosten für eine individuelle Versiegelung würden die Vorteile der nicht versiegelten Klasse überwiegen.

- Bei der-Klasse handelt es sich um ein Attribut, das eine sehr schnelle Lauf Zeit Suche erfordert. Versiegelte Attribute haben etwas höhere Leistungsstufen als nicht versiegelte. Siehe [Attribute](../../../docs/standard/design-guidelines/attributes.md).

 ❌ keine geschützten oder virtuellen Member für versiegelte Typen deklarieren.

 Definitionsgemäß können versiegelte Typen nicht von geerbt werden. Dies bedeutet, dass geschützte Member in versiegelten Typen nicht aufgerufen werden können, und virtuelle Methoden für versiegelte Typen können nicht überschrieben werden.

 ✔️ sollten Sie das Versiegeln von Elementen in Erwägung ziehen.

 Probleme, die sich aus der Einführung von virtuellen Membern ergeben können (in [virtuellen](../../../docs/standard/design-guidelines/virtual-members.md)Membern erläutert), gelten auch für außer Kraft setzungen, aber in einem etwas geringeren Maße. Das Versiegeln einer außer Kraft Setzung schützt diese Probleme ab diesem Zeitpunkt in der Vererbungs Hierarchie.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Entwerfen für Erweiterbarkeit](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [Nicht versiegelte Klassen](../../../docs/standard/design-guidelines/unsealed-classes.md)

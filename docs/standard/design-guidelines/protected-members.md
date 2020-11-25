---
title: Geschützte Member
ms.date: 10/22/2008
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
ms.openlocfilehash: a6f36ac4f994fdc3211cac619cc0b20f7b0335b1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730954"
---
# <a name="protected-members"></a>Geschützte Member

Geschützte Member selbst bieten keine Erweiterbarkeit, Sie können jedoch die Erweiterbarkeit durch Unterklassen erhöhen. Sie können verwendet werden, um erweiterte Anpassungsoptionen verfügbar zu machen, ohne die öffentliche Hauptschnittstelle unnötig zu verkomplizieren.

 Frameworkdesigner müssen mit geschützten Membern vorsichtig sein, da der Name "Protected" eine falsche Sicherheit bietet. Jeder ist in der Lage, eine nicht versiegelte Klasse zu unterteilen und auf geschützte Member zuzugreifen. Daher gelten dieselben Verteidigungsmethoden, die für öffentliche Member verwendet werden, für geschützte Member.

 ✔️ sollten Sie die Verwendung geschützter Member für erweiterte Anpassungen in Erwägung gezogen.

 ✔️ werden geschützte Member in nicht versiegelten Klassen als öffentlich für den Zweck der Sicherheits-, Dokumentations-und Kompatibilitäts Analyse behandelt.

 Jeder kann von einer Klasse erben und auf die geschützten Member zugreifen.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Weitere Informationen

- [Framework-Entwurfs Richtlinien](index.md)
- [Entwerfen für Erweiterbarkeit](designing-for-extensibility.md)

---
title: Entwurf statischer Klassen
ms.date: 10/22/2008
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
ms.openlocfilehash: 2ae541898435773ca51dbc425c09a533dbef4e9e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730915"
---
# <a name="static-class-design"></a>Entwurf statischer Klassen

Eine statische Klasse wird als Klasse definiert, die nur statische Member enthält (natürlich neben den Instanzmembern, die von <xref:System.Object?displayProperty=nameWithType> und möglicherweise einem privaten Konstruktor geerbt werden). Einige Sprachen bieten integrierte Unterstützung für statische Klassen. In c# 2,0 und höher, wenn eine Klasse als statisch deklariert wird, ist Sie versiegelt, abstrakt, und keine Instanzmember können überschrieben oder deklariert werden.

 Statische Klassen stellen einen Kompromiss zwischen dem reinen objektorientierten Design und der Einfachheit dar. Sie werden häufig verwendet, um Verknüpfungen zu anderen Vorgängen (z. b. <xref:System.IO.File?displayProperty=nameWithType> ), Inhaber von Erweiterungs Methoden oder Funktionen, für die ein vollständiger objektorientierter Wrapper nicht gerechtfertigt ist (z. b.), bereitzustellen <xref:System.Environment?displayProperty=nameWithType> .

 ✔️ statische Klassen sparsam verwenden.

 Statische Klassen sollten nur als unterstützende Klassen für den objektorientierten Kern des Frameworks verwendet werden.

 ❌ Statische Klassen können nicht als sonstige Bucket behandelt werden.

 ❌ Deklarieren oder überschreiben Sie in statischen Klassen keine Instanzmember.

 ✔️ Deklarieren Sie statische Klassen als versiegelt, abstrakt, und fügen Sie einen privaten Instanzkonstruktor hinzu, wenn Ihre Programmiersprache keine integrierte Unterstützung für statische Klassen hat.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Weitere Informationen

- [Typentwurfs Richtlinien](type.md)
- [Framework-Entwurfs Richtlinien](index.md)

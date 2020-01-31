---
title: Gleichheitsoperatoren
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
ms.openlocfilehash: 34fc8eef5270369419b76899f0dbe1ace106caf6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741696"
---
# <a name="equality-operators"></a>Gleichheitsoperatoren
`operator==` in diesem Abschnitt wird das Überladen von Gleichheits Operatoren und das `operator!=` als Gleichheits Operatoren erläutert.

 ❌ nicht einen der Gleichheits Operatoren und nicht die andere überladen.

 ✔️ Stellen Sie sicher, dass <xref:System.Object.Equals%2A?displayProperty=nameWithType> und die Gleichheits Operatoren genau dieselbe Semantik und ähnliche Leistungsmerkmale aufweisen.

 Dies bedeutet häufig, dass `Object.Equals` überschrieben werden muss, wenn die Gleichheits Operatoren überladen werden.

 ❌ vermeiden, Ausnahmen von Gleichheits Operatoren auszulösen.

 Geben Sie beispielsweise false zurück, wenn eines der Argumente NULL ist, anstatt `NullReferenceException`auszulösen.

## <a name="equality-operators-on-value-types"></a>Gleichheits Operatoren für Werttypen
 ✔️ überladen die Gleichheits Operatoren für Werttypen, wenn die Gleichheit sinnvoll ist.

 In den meisten Programmiersprachen gibt es keine Standard Implementierung von `operator==` für Werttypen.

## <a name="equality-operators-on-reference-types"></a>Gleichheits Operatoren für Verweis Typen
 ❌ vermeiden Sie das Überladen von Gleichheits Operatoren für änderbare Verweis Typen.

 Viele Sprachen verfügen über integrierte Gleichheits Operatoren für Verweis Typen. Die integrierten Operatoren implementieren in der Regel die Verweis Gleichheit, und viele Entwickler sind überrascht, wenn das Standardverhalten in den Wert Gleichheit geändert wird.

 Dieses Problem wird für unveränderliche Verweis Typen behoben, da Unveränderlichkeit das Erkennen des Unterschieds zwischen Verweis Gleichheit und Wert Gleichheit erheblich erschwert.

 ❌ vermeiden Sie das Überladen von Gleichheits Operatoren für Verweis Typen, wenn die Implementierung erheblich langsamer wäre als die Verweis Gleichheit.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Verwendungsrichtlinien](../../../docs/standard/design-guidelines/usage-guidelines.md)

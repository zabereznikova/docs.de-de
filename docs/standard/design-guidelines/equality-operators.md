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
ms.openlocfilehash: bd36b98af25db2921c164ac359188997d379a270
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84280049"
---
# <a name="equality-operators"></a>Gleichheitsoperatoren
In diesem Abschnitt wird das Überladen von Gleichheits Operatoren erläutert und `operator==` `operator!=` als Gleichheits Operatoren bezeichnet.

 ❌Überladen Sie nicht einen der Gleichheits Operatoren und nicht den anderen.

 ✔️ sicherzustellen, dass <xref:System.Object.Equals%2A?displayProperty=nameWithType> und die Gleichheits Operatoren genau dieselbe Semantik und ähnliche Leistungsmerkmale aufweisen.

 Dies bedeutet häufig, dass `Object.Equals` überschrieben werden muss, wenn die Gleichheits Operatoren überladen werden.

 ❌Vermeiden Sie das Auslösen von Ausnahmen von Gleichheits Operatoren.

 Geben Sie beispielsweise false zurück, wenn eines der Argumente NULL ist, anstatt auszulösen `NullReferenceException` .

## <a name="equality-operators-on-value-types"></a>Gleichheits Operatoren für Werttypen
 ✔️ überladen die Gleichheits Operatoren für Werttypen, wenn die Gleichheit sinnvoll ist.

 In den meisten Programmiersprachen gibt es keine Standard Implementierung von `operator==` für Werttypen.

## <a name="equality-operators-on-reference-types"></a>Gleichheits Operatoren für Verweis Typen
 ❌Vermeiden Sie das Überladen von Gleichheits Operatoren für änderbare Verweis Typen.

 Viele Sprachen verfügen über integrierte Gleichheits Operatoren für Verweis Typen. Die integrierten Operatoren implementieren in der Regel die Verweis Gleichheit, und viele Entwickler sind überrascht, wenn das Standardverhalten in den Wert Gleichheit geändert wird.

 Dieses Problem wird für unveränderliche Verweis Typen behoben, da Unveränderlichkeit das Erkennen des Unterschieds zwischen Verweis Gleichheit und Wert Gleichheit erheblich erschwert.

 ❌Vermeiden Sie das Überladen von Gleichheits Operatoren für Verweis Typen, wenn die Implementierung erheblich langsamer wäre als die Verweis Gleichheit.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Framework-Entwurfs Richtlinien](index.md)
- [Verwendungs Richtlinien](usage-guidelines.md)

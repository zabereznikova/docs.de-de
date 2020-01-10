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
ms.openlocfilehash: 31a5ce18f4526b5e3b8411365dff812601de87ad
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709438"
---
# <a name="equality-operators"></a>Gleichheitsoperatoren
`operator==` in diesem Abschnitt wird das Überladen von Gleichheits Operatoren und das `operator!=` als Gleichheits Operatoren erläutert.  
  
 **X DO NOT** die Gleichheitsoperatoren und die andere Überladung.  
  
 **✓ DO** sicher, dass <xref:System.Object.Equals%2A?displayProperty=nameWithType> und die Gleichheitsoperatoren haben genau die gleiche Semantik und ähnliche Leistungsmerkmale.  
  
 Dies bedeutet häufig, dass `Object.Equals` überschrieben werden muss, wenn die Gleichheits Operatoren überladen werden.  
  
 **X AVOID** Auslösen von Ausnahmen von Gleichheitsoperatoren.  
  
 Geben Sie beispielsweise false zurück, wenn eines der Argumente NULL ist, anstatt `NullReferenceException`auszulösen.  
  
## <a name="equality-operators-on-value-types"></a>Gleichheits Operatoren für Werttypen  
 **✓ DO** Überladen von Gleichheitsoperatoren für Werttypen, wenn Gleichheit sinnvoll ist.  
  
 In den meisten Programmiersprachen gibt es keine Standard Implementierung von `operator==` für Werttypen.  
  
## <a name="equality-operators-on-reference-types"></a>Gleichheits Operatoren für Verweis Typen  
 **X AVOID** Überladen von Gleichheitsoperatoren auf änderbare Referenztypen.  
  
 Viele Sprachen verfügen über integrierte Gleichheits Operatoren für Verweis Typen. Die integrierten Operatoren implementieren in der Regel die Verweis Gleichheit, und viele Entwickler sind überrascht, wenn das Standardverhalten in den Wert Gleichheit geändert wird.  
  
 Dieses Problem wird für unveränderliche Verweis Typen behoben, da Unveränderlichkeit das Erkennen des Unterschieds zwischen Verweis Gleichheit und Wert Gleichheit erheblich erschwert.  
  
 **X AVOID** Überladen von Gleichheitsoperatoren für Verweistypen, bei die Implementierung wesentlich langsamer als der Verweisgleichheit wäre.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Verwendungsrichtlinien](../../../docs/standard/design-guidelines/usage-guidelines.md)

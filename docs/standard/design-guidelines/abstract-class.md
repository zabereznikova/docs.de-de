---
title: Entwurf abstrakter Klassen
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
ms.openlocfilehash: 19482199648a8fb9c4b2c796fb1ab5d62c896abc
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709594"
---
# <a name="abstract-class-design"></a>Entwurf abstrakter Klassen
**X DO NOT** öffentliche oder geschützte interne Konstruktoren in abstrakten Typen definieren.  
  
 Konstruktoren sollten nur dann öffentlich sein, wenn Benutzer Instanzen des Typs erstellen müssen. Da es nicht möglich ist, Instanzen eines abstrakten Typs zu erstellen, wurde ein abstrakter Typ mit einem öffentlichen Konstruktor falsch entworfen und ist für die Benutzer irreführend.  
  
 **✓ DO** einer geschützten oder internen-Konstruktor in abstrakten Klassen definieren.  
  
 Ein geschützter Konstruktor ist häufiger und ermöglicht es der Basisklasse, eine eigene Initialisierung durchzuführen, wenn Untertypen erstellt werden.  
  
 Ein interner Konstruktor kann verwendet werden, um konkrete Implementierungen der abstrakten Klasse auf die Assembly zu beschränken, die die Klasse definiert.  
  
 **✓ DO** Geben Sie mindestens einen konkreten Typ, die von jeder abstrakten Klasse erbt, die Sie versenden.  
  
 Dies erleichtert das Überprüfen des Entwurfs der abstrakten Klasse. Beispielsweise ist <xref:System.IO.FileStream?displayProperty=nameWithType> eine Implementierung der <xref:System.IO.Stream?displayProperty=nameWithType> abstrakten Klasse.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Richtlinien für den Entwurf von Typen](../../../docs/standard/design-guidelines/type.md)
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)

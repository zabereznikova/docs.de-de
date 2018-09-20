---
title: Entwurf abstrakter Klassen
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5b9dacc4995a126e1ee3f6062dca796194d4882
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2018
ms.locfileid: "46493489"
---
# <a name="abstract-class-design"></a>Entwurf abstrakter Klassen
**X DO NOT** öffentliche oder geschützte interne Konstruktoren in abstrakten Typen definieren.  
  
 Konstruktoren sollten nur, wenn Benutzer zum Erstellen von Instanzen des Typs müssen öffentlich sein. Da Instanzen eines abstrakten Typs kann nicht erstellt werden, ist ein abstrakter Typ mit einem öffentlichen Konstruktor fehlerhaft entworfene und irreführend, die Benutzer.  
  
 **✓ DO** einer geschützten oder internen-Konstruktor in abstrakten Klassen definieren.  
  
 Ein geschützter Konstruktor wird häufiger verwendet und ermöglicht es einfach die Basisklasse, um seine eigenen Initialisierung auszuführen, wenn Untertypen erstellt werden.  
  
 Ein interner Konstruktor kann verwendet werden, um konkrete Implementierungen der abstrakten Klasse auf die Assembly mit dem Definieren der Klasse zu beschränken.  
  
 **✓ DO** Geben Sie mindestens einen konkreten Typ, die von jeder abstrakten Klasse erbt, die Sie versenden.  
  
 Dies erleichtert das Design der abstrakten Klasse zu überprüfen. Z. B. <xref:System.IO.FileStream?displayProperty=nameWithType> ist eine Implementierung der <xref:System.IO.Stream?displayProperty=nameWithType> abstrakte Klasse.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Richtlinien für den Entwurf von Typen](../../../docs/standard/design-guidelines/type.md)  
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)

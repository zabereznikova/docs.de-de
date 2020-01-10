---
title: Entwurfsrichtlinien für Member
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], about member design guidelines
- members [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], members
- member design guidelines [.NET Framework]
ms.assetid: 0ce93180-1d7b-4f8c-9306-f828b2d66b8f
ms.openlocfilehash: cf4f1d2fee73e3e65dc4d92ea97a62f4a7e4c4e5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709269"
---
# <a name="member-design-guidelines"></a>Entwurfsrichtlinien für Member
Methoden, Eigenschaften, Ereignisse, Konstruktoren und Felder werden zusammen als Member bezeichnet. Member sind letztendlich die Mittel, mit denen Frameworkfunktionen den Endbenutzern eines Frameworks zur Verfügung gestellt werden.  
  
 Mitglieder können virtuell oder nicht virtuell, konkret oder abstrakt, statisch oder eine Instanz sein und mehrere verschiedene Bereiche der Barrierefreiheit haben. Diese ganze Zahl bietet eine unglaubliche Ausdruckskraft, aber gleichzeitig muss der Teil des frameworkdesigners berücksichtigt werden.  
  
 Dieses Kapitel enthält grundlegende Richtlinien, die beim Entwerfen von Membern eines beliebigen Typs befolgt werden sollten.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Überladen von Membern](../../../docs/standard/design-guidelines/member-overloading.md)  
 [Eigenschaftenentwurf](../../../docs/standard/design-guidelines/property.md)  
 [Konstruktorentwurf](../../../docs/standard/design-guidelines/constructor.md)  
 [Ereignisentwurf](../../../docs/standard/design-guidelines/event.md)  
 [Feldentwurf](../../../docs/standard/design-guidelines/field.md)  
 [Erweiterungsmethoden](../../../docs/standard/design-guidelines/extension-methods.md)  
 [Operatorüberladungen](../../../docs/standard/design-guidelines/operator-overloads.md)  
 [Parameterentwurf](../../../docs/standard/design-guidelines/parameter-design.md)  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)

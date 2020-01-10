---
title: Benennen von Ressourcen
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
ms.openlocfilehash: b64a3ef6e12f8ea1abf7efd9c22f2f4333dda5c8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709165"
---
# <a name="naming-resources"></a>Benennen von Ressourcen
Da auf lokalisierbare Ressourcen über bestimmte Objekte verwiesen werden kann, als ob es sich um Eigenschaften handelt, ähneln die Benennungs Richtlinien für Ressourcen den Eigenschafts Richtlinien.  
  
 **✓ DO** PascalCasing in Ressourcenschlüssel verwenden.  
  
 **✓ DO** beschreibenden statt kurzer Bezeichner bereitstellen.  
  
 **X DO NOT** sprachspezifische Schlüsselwörter der wichtigsten CLR-Sprachen verwenden.  
  
 **✓ DO** nur alphanumerische Zeichen und Unterstriche enthalten, Benennen von Ressourcen verwenden.  
  
 **✓ DO** die folgende Namenskonvention für die Ausnahme Nachricht Ressourcen verwenden.  
  
 Der Ressourcen Bezeichner sollte der Name des Ausnahme Typs und ein kurzer Bezeichner der Ausnahme sein:  
  
 `ArgumentExceptionIllegalCharacters`  
 `ArgumentExceptionInvalidName`  
 `ArgumentExceptionFileNameIsMalformed`  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)

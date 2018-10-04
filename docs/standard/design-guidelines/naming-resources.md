---
title: Benennen von Ressourcen
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5b53fc383e6fc9a5f056bab4eabde9979cd734b
ms.sourcegitcommit: 700b9003ea6bdd83a53458bbc436c9b5778344f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2018
ms.locfileid: "48260679"
---
# <a name="naming-resources"></a>Benennen von Ressourcen
Da der lokalisierbare Ressourcen als wären sie Eigenschaften über bestimmte Objekte verwiesen werden können, ähneln die Benennungsrichtlinien für Ressourcen Eigenschaft Richtlinien.  
  
 **✓ DO** PascalCasing in Ressourcenschlüssel verwenden.  
  
 **✓ DO** beschreibenden statt kurzer Bezeichner bereitstellen.  
  
 **X DO NOT** sprachspezifische Schlüsselwörter der wichtigsten CLR-Sprachen verwenden.  
  
 **✓ DO** nur alphanumerische Zeichen und Unterstriche enthalten, Benennen von Ressourcen verwenden.  
  
 **✓ DO** die folgende Namenskonvention für die Ausnahme Nachricht Ressourcen verwenden.  
  
 Der Ressourcenbezeichner sollte der Name des Ausnahmetyps und einem kurzen Bezeichner der Ausnahme sein:  
  
 `ArgumentExceptionIllegalCharacters`  
 `ArgumentExceptionInvalidName`  
 `ArgumentExceptionFileNameIsMalformed`  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
- [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)

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
author: KrzysztofCwalina
ms.openlocfilehash: 44627aafd9ec779625413a0862412a8f6c408109
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756883"
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
  
 *Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)

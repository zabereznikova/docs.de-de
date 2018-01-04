---
title: Benennen von Ressourcen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- names [.NET Framework], localized resources
- localization, naming guidelines
- resource names
- global applications, naming guidelines
- international applications, naming guidelines
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 0387d820cc660bdf6cbafb9d76bbf0184c111881
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="naming-resources"></a>Benennen von Ressourcen
Da lokalisierbare Ressourcen als wären sie Eigenschaften über bestimmte Objekte verwiesen werden können, sind die Benennungsrichtlinien für Ressourcen Eigenschaft Richtlinien ähnlich.  
  
 **Führen Sie ✓** PascalCasing in Ressourcenschlüssel verwenden.  
  
 **Führen Sie ✓** beschreibenden statt kurzer Bezeichner bereitstellen.  
  
 **X nicht** sprachspezifische Schlüsselwörter der wichtigsten CLR-Sprachen verwenden.  
  
 **Führen Sie ✓** nur alphanumerische Zeichen und Unterstriche enthalten, Benennen von Ressourcen verwenden.  
  
 **Führen Sie ✓** die folgende Namenskonvention für die Ausnahme Nachricht Ressourcen verwenden.  
  
 Der Ressourcenbezeichner muss der Typname der Ausnahme sowie einem kurzen Bezeichner der Ausnahme:  
  
 `ArgumentExceptionIllegalCharacters`  
 `ArgumentExceptionInvalidName`  
 `ArgumentExceptionFileNameIsMalformed`  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
 [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)

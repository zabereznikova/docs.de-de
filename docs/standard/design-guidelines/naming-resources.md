---
title: "Benennen von Ressourcen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "[Namen [.NET Framework], lokalisierte Ressourcen"
  - "Lokalisierung Benennungsrichtlinien"
  - "Ressourcennamen"
  - "Globale Anwendungen, die Richtlinien für die Benennung"
  - "Internationale Anwendungen Benennungsrichtlinien"
ms.assetid: 8b0e97f3-7877-44fd-bc76-e05d36d5d79c
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Benennen von Ressourcen
Da lokalisierbare Ressourcen über bestimmte Objekte verwiesen werden können als handele es sich um Eigenschaften, ähneln die Benennungsrichtlinien für Ressourcen Eigenschaft Richtlinien.  
  
 **✓ führen** verwenden Sie PascalCasing in Ressourcenschlüssel.  
  
 **✓ führen** Geben Sie beschreibende Bezeichner statt kurzer Bezeichner.  
  
 **X nicht** sprachspezifische Schlüsselwörter der wichtigsten CLR\-Sprachen verwenden.  
  
 **✓ führen** nur alphanumerische Zeichen und Unterstriche Benennen von Ressourcen verwenden.  
  
 **✓ führen** die folgende Benennungskonvention für Ausnahme Nachricht Ressourcen verwenden.  
  
 Der Ressourcenbezeichner muss dem Namen des Ausnahmetyps und einem kurzen Bezeichner der Ausnahme:  
  
 `ArgumentExceptionIllegalCharacters`   
 `ArgumentExceptionInvalidName`   
 `ArgumentExceptionFileNameIsMalformed`  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)   
 [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)
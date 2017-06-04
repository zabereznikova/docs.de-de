---
title: "Benennen von Parametern | Microsoft Docs"
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
  - "Parameter, Namen"
  - "[Namen [.NET Framework], Parameter"
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Benennen von Parametern
Über das offensichtliche Ursache der Lesbarkeit unbedingt die Richtlinien für Parameternamen befolgen, da der Parameter in der Dokumentation und im Designer angezeigt werden, wenn visuellen Entwurfstools Intellisense und die Klasse durchsuchen Funktionalität bereitstellt.  
  
 **✓ führen** CamelCasing Parameternamen verwenden.  
  
 **✓ führen** beschreibende Parameternamen verwenden.  
  
 **✓ ggf.** mit Namen basierend auf den Typ des Parameters, anstatt die Bedeutung eines Parameters.  
  
### Benennen von Parametern für Operator\-Überladung  
 **✓ führen** verwenden `left` und `right` für binären Operator Überladung Parameternamen, wenn es keine Bedeutung für den Parameter.  
  
 **✓ führen** verwenden `value` für unäre Operator überladen Parameternamen, wenn es keine Bedeutung für den Parameter.  
  
 **✓ ggf.** aussagekräftige Namen für den Operator überladen Parameter aus, wenn dies also mit erheblichem Wert hinzufügt.  
  
 **X nicht** Abkürzungen verwenden oder numerischen Indizes für Operator überladen Parameternamen.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)   
 [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)
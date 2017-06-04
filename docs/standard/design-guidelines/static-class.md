---
title: "Entwurf statischer Klassen | Microsoft Docs"
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
  - "Typentwurfsrichtlinien statische Klassen"
  - "Klassenbibliotheken – Entwurfsrichtlinien [.NET Framework], Klassen"
  - "Statische Klassen [[.NET Framework]"
  - "Statische Klassen [.NET Framework]"
  - "[Klassen [.NET Framework], Entwurfsrichtlinien"
  - "Typentwurfsrichtlinien Klassen"
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Entwurf statischer Klassen
Eine statische Klasse ist definiert als eine Klasse enthält nur statische Member \(natürlich neben geerbt von Instanzmember <xref:System.Object?displayProperty=fullName> und möglicherweise einen privaten Konstruktor\). Einige Sprachen bieten integrierte Unterstützung für statische Klassen. In c\# 2.0 und höher, wenn eine Klasse als statisch deklariert wird, ist versiegelt, abstrakt und keine Instanzmember überschreiben oder deklariert werden können.  
  
 Statische Klassen stellen einen Kompromiss zwischen rein objektorientierten Entwurf und Einfachheit. Tastenkombinationen für andere Vorgänge bereitstellen werden häufig verwendet \(z. B. <xref:System.IO.File?displayProperty=fullName>\), Inhaber von Erweiterungsmethoden oder Funktionen, die für den ein vollständig objektorientierten Wrapper ist \(z. B. <xref:System.Environment?displayProperty=fullName>\).  
  
 **✓ führen** verwenden Sie statische Klassen sparsam.  
  
 Statische Klassen sollten nur als unterstützende Klassen für den objektorientierten Kern des Framework verwendet werden.  
  
 **X nicht** statische Klassen als Bucket für verschiedene Elemente behandeln.  
  
 **X nicht** deklarieren oder Instanzmember in statischen Klassen überschreiben.  
  
 **✓ führen** deklarieren Sie statische Klassen als versiegelt, abstrakt, und fügen Sie einen privaten Instanzkonstruktor hinzu, wenn Ihre Programmiersprache keine integrierten Unterstützung für statische Klassen.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Typentwurfsrichtlinien](../../../docs/standard/design-guidelines/type.md)   
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
---
title: "Strukturentwurf | Microsoft Docs"
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
  - "Klassenbibliotheken – Entwurfsrichtlinien [.NET Framework], Strukturen"
  - "Aufheben der Zuweisung von Strukturen"
  - "Zuweisen von Strukturen"
  - "Strukturen Werttypen"
  - "Strukturentwurf"
  - "Typentwurfsrichtlinien Strukturen"
  - "[Strukturen [.NET Framework], Entwurfsrichtlinien"
ms.assetid: 1f48b2d8-608c-4be6-9ba4-d8f203ed9f9f
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Strukturentwurf
Der allgemeine Typ wird am häufigsten als eine Struktur, die das C\#\-Schlüsselwort bezeichnet. Dieser Abschnitt enthält Richtlinien für den Strukturentwurf der allgemeinen.  
  
 **X nicht** einen Standardkonstruktor für eine Struktur bereitstellen.  
  
 Diese Richtlinien kann Arrays von Strukturen erstellt werden, ohne den Konstruktor für jedes Element des Arrays ausführen zu müssen. Beachten Sie, dass c\# über Standardkonstruktoren verfügen Strukturen nicht zulässt.  
  
 **X nicht** änderbaren Werttypen definieren.  
  
 Änderbare Werttypen haben einige Probleme. Wenn Getter für eine Eigenschaft ein Werttyps zurückgegeben wird, erhält der Aufrufer z. B. eine Kopie. Da die Kopie implizit erstellt wird, Entwickler weiß möglicherweise nicht, dass sie die Kopie und nicht der ursprüngliche Wert veränderliche sind. Außerdem verfügen einige Sprachen \(dynamische Sprachen, insbesondere\) Probleme mit änderbare Werttypen, da auch lokale Variablen beim Dereferenzieren, dazu führen, dass eine Kopie erstellt werden.  
  
 **✓ führen** sicherzustellen, dass ein Zustand, in dem alle Instanzdaten, auf 0 \(null\) festgelegt ist, false oder null \(falls zutreffend\) gültig ist.  
  
 Dies verhindert die versehentliche Erstellung der ungültige Instanzen, wenn ein Array von Strukturen erstellt wird.  
  
 **✓ führen** implementieren <xref:System.IEquatable%601> für Werttypen.  
  
 Die <xref:System.Object.Equals%2A?displayProperty=fullName> \-Methode auf Werttypen Boxing, und die Standardimplementierung ist nicht sehr effizient, da Reflektion verwendet wird.<xref:System.IEquatable%601.Equals%2A> kann viel bessere Leistung und können implementiert werden, damit es keine Boxing verursacht.  
  
 **X nicht** ausdrücklich <xref:System.ValueType>. In der Tat verhindert werden, die meisten Sprachen.  
  
 Im Allgemeinen Strukturen können sehr nützlich sein, jedoch sollte nur verwendet werden, für kleine, einzelne, unveränderliche Werte, die häufig nicht geschachtelt werden.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Typentwurfsrichtlinien](../../../docs/standard/design-guidelines/type.md)   
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)   
 [Auswählen zwischen Klassen und Strukturen](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)
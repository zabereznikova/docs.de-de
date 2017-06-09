---
title: "Ereignisse und R&#252;ckrufe | Microsoft Docs"
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
  - "[Ereignisse [.NET Framework], Erweiterbarkeit"
  - "[Methoden [.NET Framework], Rückruf"
  - "Rückrufmethoden"
  - "Rückrufe"
ms.assetid: 48b55c60-495f-4089-9396-97f9122bba7c
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Ereignisse und R&#252;ckrufe
Rückrufe sind Erweiterungspunkte, mit denen ein Framework wieder in Benutzercode über einen Delegaten aufgerufen. Diese Delegaten werden an das Framework in der Regel über einen Parameter einer Methode übergeben.  
  
 Ereignisse sind ein Sonderfall der Rückrufe, der benutzerfreundliche und einheitliche Syntax unterstützt wird, für den Delegaten \(ein Ereignishandler\) angeben. Außerdem bieten Visual Studio Anweisungsabschluss und Designern Hilfe mit Ereignis\-basierten APIs. \(Siehe [Ereignisentwurf](../../../docs/standard/design-guidelines/event.md).\)  
  
 **✓ ggf.** Verwendung von Rückrufen ermöglichen es Benutzern, Bereitstellen von benutzerdefiniertem Code, der vom Framework ausgeführt werden.  
  
 **✓ ggf.** Ereignisse ermöglichen es Benutzern zum Anpassen des Verhaltens eines Frameworks, ohne die Notwendigkeit für das Verständnis von objektorientierten Entwurf verwenden.  
  
 **✓ führen** einfache Rückrufe Ereignisse vorziehen, da sie mehr zu einem breiteren Spektrum von Entwicklern vertraut sind und in Visual Studio Anweisungsabschluss integriert sind.  
  
 **X vermeiden** Verwendung von Rückrufen in leistungsrelevanten APIs.  
  
 **✓ führen** verwenden Sie die neue `Func<...>`, `Action<...>`, oder `Expression<...>` Typen anstelle von benutzerdefinierten Delegaten, wenn APIs Rückrufe zu definieren.  
  
 `Func<...>` und `Action<...>` generische Delegaten darstellen.`Expression<...>` Stellt Funktionsdefinitionen, die kompiliert und anschließend zur Laufzeit kann jedoch auch aufgerufen werden können werden serialisiert und an remote\-Prozesse übergeben.  
  
 **✓ führen** messen und Verstehen der Leistungseinbußen bei der Verwendung von `Expression<...>`, anstelle von `Func<...>` und `Action<...>` Delegaten.  
  
 `Expression<...>` Typen sind in den meisten Fällen ist logisch äquivalent zu `Func<...>` und `Action<...>` Delegaten. Der Hauptunterschied zwischen ihnen ist, dass die Delegaten in lokalen Prozess Szenarien verwendet werden sollen. Ausdrücke sind für Fälle vorgesehen, in denen es vorteilhaft und zum Auswerten des Ausdrucks in einer remote\-Prozess oder Computer möglich ist.  
  
 **✓ führen** verstehen, dass durch das Aufrufen eines Delegaten wird beliebigen Code ausgeführt wird und bei denen konnte Sicherheit, Richtigkeit und Kompatibilität folgen.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Entwerfen für Erweiterbarkeit](../../../docs/standard/design-guidelines/designing-for-extensibility.md)   
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
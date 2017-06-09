---
title: "Entwurf abstrakter Klassen | Microsoft Docs"
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
  - "Geben Sie Richtlinien für den Entwurf, abstrakte Klassen"
  - "abstrakte Klassen, Entwurfsrichtlinien"
  - "Klassenbibliotheken – Entwurfsrichtlinien [.NET Framework], Klassen"
  - "abstrakte Klassen [[.NET Framework]"
  - "[Klassen [.NET Framework], Entwurfsrichtlinien"
  - "Typentwurfsrichtlinien Klassen"
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# Entwurf abstrakter Klassen
**X nicht** öffentliche oder geschützte interne Konstruktoren in abstrakten Typen definieren.  
  
 Konstruktoren sollten öffentlich sein, nur wenn Benutzer Instanzen des Typs erstellt werden müssen. Da Sie die Instanzen eines abstrakten Datentyps erstellen können, ist ein abstrakter Datentyp mit einem öffentlichen Konstruktor falsch entwickelt und den Benutzern irreführend.  
  
 **✓ führen** definieren Sie eine geschützte oder einen internen Konstruktor in abstrakten Klassen.  
  
 Ein geschützter Konstruktor häufiger und die Basisklasse für die eigene Initialisierung erstellte Untertypen werden kann.  
  
 Ein interner Konstruktor kann verwendet werden, um konkrete Implementierung der abstrakten Klasse auf die Assembly, die die Klasse definiert zu beschränken.  
  
 **✓ führen** Geben Sie mindestens einen konkreten Typ, der von jeder abstrakten Klasse erbt, die Sie versenden.  
  
 Dies erleichtert den Entwurf der abstrakten Klasse überprüft. Z. B.  <xref:System.IO.FileStream?displayProperty=fullName> ist eine Implementierung der <xref:System.IO.Stream?displayProperty=fullName> abstrakte Klasse.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Typentwurfsrichtlinien](../../../docs/standard/design-guidelines/type.md)   
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
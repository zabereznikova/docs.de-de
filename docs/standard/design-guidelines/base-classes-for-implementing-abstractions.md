---
title: "Basisklassen zum Implementieren von Abstraktionen | Microsoft Docs"
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
  - "[Abstraktionen [.NET Framework]"
  - "Basisklassen Abstraktionen"
ms.assetid: 37a2d9a4-9721-482a-a40f-eee2c1d97875
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Basisklassen zum Implementieren von Abstraktionen
Genau genommen wird eine Klasse eine Basisklasse, bei einer anderen Klasse abgeleitet ist. In diesem Abschnitt ist eine Basisklasse jedoch eine Klasse, die hauptsächlich für bieten eine allgemeine Abstraktion oder für andere Klassen wiederverwenden einige Standard\-Implementierung jedoch Vererbung konzipiert. Basisklassen befinden sich normalerweise in der Mitte Vererbungshierarchien zwischen eine Abstraktion der Stamm einer Hierarchie und mehrere benutzerdefinierte Implementierungen unten.  
  
 Sie dienen als Implementierung Hilfsprogramme zum Implementieren von Abstraktionen. Eines der Framework\-Abstraktionen für geordnete Auflistungen von Elementen ist z. B. die <xref:System.Collections.Generic.IList%601> Schnittstelle. Implementieren von <xref:System.Collections.Generic.IList%601> ist nicht trivial, und das Framework bietet daher mehrere Basisklassen, wie z. B. <xref:System.Collections.ObjectModel.Collection%601> und <xref:System.Collections.ObjectModel.KeyedCollection%602>, der als Hilfsmethoden für die Implementierung von benutzerdefinierter Sammlungen dienen.  
  
 Basisklassen sind normalerweise nicht geeignet als Abstraktionen von sich selbst an, da sie meist viel Implementierung enthalten. Zum Beispiel die `Collection<T>` Basisklasse enthält viele der Implementierung, die im Zusammenhang mit der Tatsache, dass sie die nicht generische implementiert `IList` Schnittstelle \(für nicht generische Auflistungen besser integriert\) und die Tatsache, dass es sich um eine Auflistung von Elementen in einer seiner Felder im Arbeitsspeicher gespeichert ist.  
  
 Wie bereits erwähnt Basisklassen können wertvolle Hilfe für Benutzer, die zum Implementieren von Abstraktionen müssen bereitstellen, aber gleichzeitig eine erhebliche Schuld sein. Diese Oberfläche hinzufügen und erhöhen die Tiefe der Vererbungshierarchien und Dienstantwort erschweren das Framework. Aus diesem Grund sollten Basisklassen verwendet werden, nur, wenn sie den Benutzern von Framework erheblichen Nutzen bieten. Sie sollten vermieden werden, wenn sie nur für die Implementierung des Frameworks Mehrwert in denen Fall Delegierung zu einer internen Implementierung anstelle von Vererbung von einer Basisklasse stark berücksichtigt werden soll.  
  
 **✓ ggf.** machen Basisklassen abstrakt, selbst wenn sie keine abstrakten Member enthalten. Dies deutlich kommuniziert, um die Benutzer, die die Klasse dient ausschließlich von der geerbt werden.  
  
 **✓ ggf.** Basisklassen in einem separaten Namespace aus dem Hauptzweig Szenario platzieren. Definitionsgemäß Basisklassen sind für fortgeschrittene Erweiterbarkeitsszenarien vorgesehen und werden daher nicht interessant, die Mehrheit der Benutzer.  
  
 **X vermeiden** naming Basisklassen mit dem Suffix "Basis", wenn die Klasse zur Verwendung in öffentlichen APIs vorgesehen ist.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)   
 [Entwerfen für Erweiterbarkeit](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
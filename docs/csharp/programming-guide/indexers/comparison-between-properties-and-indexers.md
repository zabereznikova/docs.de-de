---
title: "Vergleich zwischen Eigenschaften und Indexern (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Indexer [C#], Im Vergleich zu Eigenschaften"
  - "Eigenschaften [C#], Im Vergleich zu Indexern"
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Vergleich zwischen Eigenschaften und Indexern (C#-Programmierhandbuch)
Indexer sind wie Eigenschaften.  Mit Ausnahme der in der folgenden Tabelle aufgeführten Unterschiede gelten alle für Eigenschaftenaccessoren definierten Regeln auch für Indexeraccessoren.  
  
|Property|Indexer|  
|--------------|-------------|  
|Damit können Methoden wie allgemein zugängliche Datenmember aufgerufen werden.|Damit können Elemente einer internen Auflistung eines Objekts durch die Anwendung der Arraynotation auf das Objekt aufgerufen werden.|  
|Der Zugriff erfolgt über einen einfachen Namen.|Der Zugriff erfolgt über einen Index.|  
|Kann ein statischer Member oder ein Instanzmember sein.|Muss ein Instanzmember sein.|  
|Ein [get](../../../csharp/language-reference/keywords/get.md)\-Accessor einer Eigenschaft weist keine Parameter auf.|Ein `get`\-Accessor eines Indexers hat dieselbe Liste formaler Parameter wie der Indexer.|  
|Ein [set](../../../csharp/language-reference/keywords/set.md)\-Accessor einer Eigenschaft enthält den impliziten `value`\-Parameter.|Ein `set`\-Accessor eines Indexers enthält neben dem [value](../../../csharp/language-reference/keywords/value.md)\-Parameter auch dieselbe Liste formaler Parameter wie der Indexer.|  
|Unterstützt Kurzsyntax mit [Automatisch implementierte Eigenschaften](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).|Unterstützt keine Kurzsyntax.|  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Indexer](../../../csharp/programming-guide/indexers/index.md)   
 [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md)
---
title: Vergleich zwischen Eigenschaften und Indexern (C#-Programmierhandbuch)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- properties [C#], vs. indexers
- indexers [C#], vs. properties
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 102a6a97726fa19fcba0e6f19876a3935e8625f9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="comparison-between-properties-and-indexers-c-programming-guide"></a>Vergleich zwischen Eigenschaften und Indexern (C#-Programmierhandbuch)
Indexer sind wie Eigenschaften. Mit Ausnahme der in der folgenden Tabelle aufgeführten Unterschiede gelten alle für Eigenschaftenaccessoren definierten Regeln auch für Indexeraccessoren.  
  
|Eigenschaft|Indexer|  
|--------------|-------------|  
|Damit können Methoden wie allgemein zugängliche Datenmember aufgerufen werden.|Damit können Elemente einer internen Auflistung eines Objekts durch die Anwendung der Arraynotation auf das Objekt aufgerufen werden.|  
|Der Zugriff erfolgt über einen einfachen Namen.|Der Zugriff erfolgt über einen Index.|  
|Kann ein statischer Member oder ein Instanzmember sein.|Muss ein Instanzmember sein.|  
|Ein [get](../../../csharp/language-reference/keywords/get.md)-Accessor einer Eigenschaft weist keine Parameter auf.|Ein `get`-Accessor eines Indexers hat dieselbe Liste formaler Parameter wie der Indexer.|  
|Ein [set](../../../csharp/language-reference/keywords/set.md)-Accessor einer Eigenschaft enthält den impliziten `value`-Parameter.|Ein `set`-Accessor eines Indexers enthält neben dem [value](../../../csharp/language-reference/keywords/value.md)-Parameter auch dieselbe Liste formaler Parameter wie der Indexer.|  
|Unterstützt Kurzsyntax mit [Auto-Implemented Properties (Automatisch implementierte Eigenschaften)](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).|Unterstützt keine Kurzsyntax.|  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Indexer](../../../csharp/programming-guide/indexers/index.md)  
 [Eigenschaften](../../../csharp/programming-guide/classes-and-structs/properties.md)

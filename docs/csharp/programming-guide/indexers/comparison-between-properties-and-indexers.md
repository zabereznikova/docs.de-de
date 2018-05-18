---
title: Vergleich zwischen Eigenschaften und Indexern (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], vs. indexers
- indexers [C#], vs. properties
ms.assetid: 3358a89f-44a0-4a4d-bf8c-07237a90af39
ms.openlocfilehash: a8b347be33ea6acbdf8a78a7af45fd3d0c27f8fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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

---
title: "Threadsicherheit in regulären Ausdrücken"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework regular expressions, threads
- regular expressions, threads
- searching with regular expressions, threads
- parsing text with regular expressions, threads
- pattern-matching with regular expressions, threads
ms.assetid: 7c4a167b-5236-4cde-a2ca-58646230730f
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 804f83d85206b5f49a0bea290f281b36e18bb847
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="thread-safety-in-regular-expressions"></a>Threadsicherheit in regulären Ausdrücken
Die <xref:System.Text.RegularExpressions.Regex>-Klasse selbst ist threadsicher und nicht änderbar (schreibgeschützt). **Regex**-Objekte können also in jedem Thread erzeugt und von mehreren Threads gemeinsam genutzt werden. Übereinstimmende Methoden können von jedem Thread aufgerufen werden und ändern keinen globalen Zustand.  
  
 Ergebnisobjekte (**Match** und **MatchCollection**), die von **Regex** zurückgegeben werden, sollten allerdings in einem einzelnen Thread verwendet werden. Obwohl viele dieser Objekte logisch nicht änderbar sind, können ihre Implementierungen die Berechnung einiger Ergebnisse zur Verbesserung der Leistung verzögern. Daher müssen Aufrufer den Zugriff darauf serialisieren.  
  
 Wenn **Regex**-Ergebnisobjekte in mehreren Threads gemeinsam genutzt werden müssen, können diese Objekte durch den Aufruf ihrer synchronisierten Methoden in threadsichere Instanzen konvertiert werden. Mit Ausnahme von Enumeratoren sind alle Klassen für reguläre Ausdrücke threadsicher oder können von einer synchronisierten Methode in threadsichere Objekte konvertiert werden.  
  
 Enumeratoren sind die einzige Ausnahme. Eine Anwendung muss Aufrufe von Sammlungsenumeratoren serialisieren. Die Regel ist, dass für eine Sammlung, die in mehr als einem Thread gleichzeitig als Enumeration verwendet werden kann, die Enumeratormethoden im Stammobjekt der Sammlung, die der Enumerator durchläuft, synchronisiert werden müssen.  
  
## <a name="see-also"></a>Siehe auch  
 [Reguläre Ausdrücke in .NET](../../../docs/standard/base-types/regular-expressions.md)

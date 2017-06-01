---
title: "Threadsicherheit in regul&#228;ren Ausdr&#252;cken | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Reguläre Ausdrücke von .NET Framework, Threads"
  - "Analysieren von Text mit regulären Ausdrücken, Threads"
  - "Mustervergleich mit regulären Ausdrücken, Threads"
  - "Reguläre Ausdrücke, Threads"
  - "Suchen mit regulären Ausdrücken, Threads"
ms.assetid: 7c4a167b-5236-4cde-a2ca-58646230730f
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# Threadsicherheit in regul&#228;ren Ausdr&#252;cken
Die <xref:System.Text.RegularExpressions.Regex>\-Klasse selbst ist threadsicher und unveränderlich \(schreibgeschützt\).  Somit können **Regex**\-Objekte von jedem beliebigen Thread erzeugt und von Threads gemeinsam verwendet werden; Suchmethoden können von jedem Thread aufgerufen werden, ohne den globalen Zustand zu verändern.  
  
 Allerdings sollten Ergebnisobjekte \(**Match** und **MatchCollection**\), die von **Regex** zurückgegeben werden, von einem einzigen Thread verwendet werden.  Obwohl viele dieser Objekte logisch unveränderlich sind, könnte durch ihre Implementierung die Berechnung einiger Ergebnisse verzögert werden, um die Leistung zu verbessern. Dies würde dazu führen, dass Aufrufer den Zugriff auf die Objekte serialisieren müssen.  
  
 Wenn **Regex**\-Ergebnisobjekte von mehreren Threads gemeinsam verwendet werden sollen, können diese Objekte durch den Aufruf ihrer synchronisierten Methoden in threadsichere Instanzen konvertiert werden.  Mit Ausnahme von Enumeratoren sind alle Klassen zur Behandlung regulärer Ausdrücke threadsicher oder können über eine synchronisierte Methode in threadsichere Objekte konvertiert werden.  
  
 Enumeratoren sind die einzige Ausnahme.  Eine Anwendung muss Aufrufe von Auflistungsenumeratoren serialisieren.  Wenn eine Auflistung von mehr als einem Thread gleichzeitig durchlaufen werden kann, sollten die Enumeratormethoden mit dem übergeordneten Objekt der Auflistung, die der Enumerator durchläuft, synchronisiert werden.  
  
## Siehe auch  
 [Reguläre Ausdrücke von .NET Framework](../../../docs/standard/base-types/regular-expressions.md)
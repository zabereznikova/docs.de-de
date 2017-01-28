---
title: "Threadsicherheit in regulären Ausdrücken"
description: "Threadsicherheit in regulären Ausdrücken"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: dc64b681-b3aa-4911-8e30-0764a8b6a852
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: ab71ad5ff9148f00f392fddd3c89acbcab874015

---

# <a name="thread-safety-in-regular-expressions"></a>Threadsicherheit in regulären Ausdrücken

Die [Regex](xref:System.Text.RegularExpressions.Regex)-Klasse selbst ist threadsicher und nicht änderbar (schreibgeschützt). [Regex](xref:System.Text.RegularExpressions.Regex)-Objekte können also in jedem Thread erzeugt und von mehreren Threads gemeinsam genutzt werden. Übereinstimmende Methoden können von jedem Thread aufgerufen werden und ändern keinen globalen Zustand.

Ergebnisobjekte ([Match](xref:System.Text.RegularExpressions.Match) und [MatchCollection)](xref:System.Text.RegularExpressions.MatchCollection), die von [Regex](xref:System.Text.RegularExpressions.Regex) zurückgegeben werden, sollten allerdings in einem einzelnen Thread verwendet werden. Obwohl viele dieser Objekte logisch nicht änderbar sind, können ihre Implementierungen die Berechnung einiger Ergebnisse zur Verbesserung der Leistung verzögern. Daher müssen Aufrufer den Zugriff darauf serialisieren.

Wenn [Regex](xref:System.Text.RegularExpressions.Regex)-Ergebnisobjekte in mehreren Threads gemeinsam genutzt werden müssen, können diese Objekte durch den Aufruf ihrer synchronisierten Methoden in threadsichere Instanzen konvertiert werden. Mit Ausnahme von Enumeratoren sind alle Klassen für reguläre Ausdrücke threadsicher oder können von einer synchronisierten Methode in threadsichere Objekte konvertiert werden.

Enumeratoren sind die einzige Ausnahme. Eine Anwendung muss Aufrufe von Sammlungsenumeratoren serialisieren. Die Regel ist, dass für eine Sammlung, die in mehr als einem Thread gleichzeitig als Enumeration verwendet werden kann, die Enumeratormethoden im Stammobjekt der Sammlung, die der Enumerator durchläuft, synchronisiert werden müssen.

## <a name="see-also"></a>Siehe auch

[Reguläre Ausdrücke in .NET](regular-expressions.md)




<!--HONumber=Nov16_HO3-->



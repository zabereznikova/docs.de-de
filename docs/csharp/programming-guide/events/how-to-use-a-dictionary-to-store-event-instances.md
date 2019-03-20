---
title: 'Gewusst wie: Verwenden eines Wörterbuchs zum Speichern von Ereignisinstanzen (C#-Programmierhandbuch)'
ms.custom: seodec18
ms.date: 03/11/2019
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
ms.openlocfilehash: f8522e499887398402f63c7788bbc6c6c4f57782
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2019
ms.locfileid: "57845272"
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a>Gewusst wie: Verwenden eines Wörterbuchs zum Speichern von Ereignisinstanzen (C#-Programmierhandbuch)

Eine Verwendungsmöglichkeit der benutzerdefinierten Ereignisaccessors `add` und `remove` besteht darin, viele Ereignisse verfügbar zu machen, ohne jedem Ereignis ein Feld zuzuordnen, aber stattdessen mit einer <xref:System.Collections.Generic.Dictionary%602>-Instanz die Ereignisinstanzen zu speichern, wie das folgende Beispiel zeigt. Dies ist jedoch nur nützlich, wenn ein Typ viele Ereignisse hat, Sie aber davon ausgehen, dass die meisten Ereignisse nicht abonniert werden.

[!code-csharp[csProgGuideEvents#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#9)]

Diese Implementierung entspricht dem Verhalten für das [Hinzufügen und Entfernen von Delegaten](~/_csharplang/spec/delegates.md#delegate-invocation) in der C#-Sprachspezifikation.

Beachten Sie, dass die [lock](../../language-reference/keywords/lock-statement.md)-Anweisung nur zum *Zugriff* auf das Wörterbuch mit Ereignishandlern dient. Rufen Sie einen Ereignishandler nicht innerhalb des Texts der `lock`-Anweisung auf, da dies zu Deadlocks oder Sperrungskonflikten führen könnte.

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [Ereignisse](../../../csharp/programming-guide/events/index.md)
- [Delegaten](../../../csharp/programming-guide/delegates/index.md)

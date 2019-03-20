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
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a><span data-ttu-id="273cb-102">Gewusst wie: Verwenden eines Wörterbuchs zum Speichern von Ereignisinstanzen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="273cb-102">How to: use a dictionary to store event instances (C# Programming Guide)</span></span>

<span data-ttu-id="273cb-103">Eine Verwendungsmöglichkeit der benutzerdefinierten Ereignisaccessors `add` und `remove` besteht darin, viele Ereignisse verfügbar zu machen, ohne jedem Ereignis ein Feld zuzuordnen, aber stattdessen mit einer <xref:System.Collections.Generic.Dictionary%602>-Instanz die Ereignisinstanzen zu speichern, wie das folgende Beispiel zeigt.</span><span class="sxs-lookup"><span data-stu-id="273cb-103">One use for the `add` and `remove` custom event accessors is to expose many events without allocating a field for each event, but instead using a <xref:System.Collections.Generic.Dictionary%602> instance to store the event instances, as the example below demonstrates.</span></span> <span data-ttu-id="273cb-104">Dies ist jedoch nur nützlich, wenn ein Typ viele Ereignisse hat, Sie aber davon ausgehen, dass die meisten Ereignisse nicht abonniert werden.</span><span class="sxs-lookup"><span data-stu-id="273cb-104">This is only useful if a type has many events, but you expect that most of the events will not be subscribed to.</span></span>

[!code-csharp[csProgGuideEvents#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#9)]

<span data-ttu-id="273cb-105">Diese Implementierung entspricht dem Verhalten für das [Hinzufügen und Entfernen von Delegaten](~/_csharplang/spec/delegates.md#delegate-invocation) in der C#-Sprachspezifikation.</span><span class="sxs-lookup"><span data-stu-id="273cb-105">This implementation conforms to the behavior for [adding and removing delegates](~/_csharplang/spec/delegates.md#delegate-invocation) in the C# language specification.</span></span>

<span data-ttu-id="273cb-106">Beachten Sie, dass die [lock](../../language-reference/keywords/lock-statement.md)-Anweisung nur zum *Zugriff* auf das Wörterbuch mit Ereignishandlern dient.</span><span class="sxs-lookup"><span data-stu-id="273cb-106">Note that the [lock](../../language-reference/keywords/lock-statement.md) statement is used only to *access* the dictionary with event handlers.</span></span> <span data-ttu-id="273cb-107">Rufen Sie einen Ereignishandler nicht innerhalb des Texts der `lock`-Anweisung auf, da dies zu Deadlocks oder Sperrungskonflikten führen könnte.</span><span class="sxs-lookup"><span data-stu-id="273cb-107">Don't invoke an event handler inside the body of the `lock` statement, as it could lead to deadlocks or lock contention.</span></span>

## <a name="see-also"></a><span data-ttu-id="273cb-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="273cb-108">See also</span></span>

- [<span data-ttu-id="273cb-109">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="273cb-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="273cb-110">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="273cb-110">Events</span></span>](../../../csharp/programming-guide/events/index.md)
- [<span data-ttu-id="273cb-111">Delegaten</span><span class="sxs-lookup"><span data-stu-id="273cb-111">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)

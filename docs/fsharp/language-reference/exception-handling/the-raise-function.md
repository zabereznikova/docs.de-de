---
title: 'Ausnahmen: Die raise-Funktion'
description: Erfahren Sie, F# wie die ' Raise '-Funktion verwendet wird, um anzugeben, dass ein Fehler oder eine Ausnahme Bedingung aufgetreten ist.
ms.date: 05/16/2016
ms.openlocfilehash: e0cc8da8310203c537b8081af8a225671bd8c6a3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630291"
---
# <a name="exceptions-the-raise-function"></a>Ausnahmen: Die raise-Funktion

Die `raise` -Funktion wird verwendet, um anzugeben, dass ein Fehler oder eine Ausnahme Bedingung aufgetreten ist. Informationen über den Fehler werden in einem Ausnahme Objekt aufgezeichnet.

## <a name="syntax"></a>Syntax

```fsharp
raise (expression)
```

## <a name="remarks"></a>Hinweise

Die `raise` -Funktion generiert ein Exception-Objekt und initiiert einen Stapel Entwicklungsprozess. Der Stapel Entwicklungsprozess wird vom Common Language Runtime (CLR) verwaltet, sodass das Verhalten dieses Prozesses mit dem Verhalten in jeder anderen .NET-Sprache identisch ist. Der Stapel Entwicklungsprozess ist eine Suche nach einem Ausnahmehandler, der mit der generierten Ausnahme übereinstimmt. Die Suche beginnt im aktuellen `try...with` Ausdruck, sofern vorhanden. Jedes Muster im Block `with` wird in der richtigen Reihenfolge geprüft. Wenn ein übereinstimmender Ausnahmehandler gefunden wird, gilt die Ausnahme als behandelt. Andernfalls wird der Stapel entsperrt und `with` blockiert, bis ein übereinstimmender Handler gefunden wird. Alle `finally` Blöcke, die in der-Aufrufkette gefunden werden, werden auch nacheinander ausgeführt, wenn der Stapel entlädt.

Die `raise` -Funktion `throw` entspricht in C# oder C++. Verwenden `reraise` Sie in einem catch-Handler, um dieselbe Ausnahme in der Aufrufkette weiterzugeben.

Die folgenden Codebeispiele veranschaulichen die Verwendung `raise` der-Funktion, um eine Ausnahme zu generieren.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

Die `raise` -Funktion kann auch verwendet werden, um .NET-Ausnahmen zu verwenden, wie im folgenden Beispiel gezeigt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]

## <a name="see-also"></a>Siehe auch

- [Ausnahmebehandlung](index.md)
- [Ausnahmetypen](exception-types.md)
- [Ausnahmen: Der `try...with` Ausdruck](the-try-with-expression.md)
- [Ausnahmen: Der `try...finally` Ausdruck](the-try-finally-expression.md)
- [Ausnahmen: Die `failwith` -Funktion](the-failwith-function.md)
- [Ausnahmen: Die `invalidArg` -Funktion](the-invalidArg-function.md)

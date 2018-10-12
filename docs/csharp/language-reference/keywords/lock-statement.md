---
title: lock-Anweisung (C#-Referenz)
description: Verwenden Sie die lock-Anweisung von C#, um den Threadzugriff auf eine freigegebene Ressource zu synchronisieren.
ms.date: 08/28/2018
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
ms.openlocfilehash: 2b6fbfb2f81d7745c4effb9ea0087f34cc872a6c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43858355"
---
# <a name="lock-statement-c-reference"></a>lock-Anweisung (C#-Referenz)

Mit der `lock`-Anweisung wird die Sperre für gegenseitigen Ausschluss für ein bestimmtes Objekt abgerufen, ein Anweisungsblock ausgeführt und die Sperre anschließend aufgehoben. Während eine Sperre aufrechterhalten wird, kann der Thread, der die Sperre aufrechterhält, die Sperre abrufen und aufheben. Für jeden anderen Thread wird das Abrufen der Sperre blockiert, und die Sperre wartet auf die Aufhebung.

Die `lock`-Anweisung weist folgendes Format auf:

```csharp
lock (x)
{
    // Your code...
}
```

`x` entspricht einem Ausdruck eines [Verweistyps](reference-types.md). Dieser entspricht exakt Folgendem:

```csharp
object __lockObj = x;
bool __lockWasTaken = false;
try
{
    System.Threading.Monitor.Enter(__lockObj, ref __lockWasTaken);
    // Your code...
}
finally
{
    if (__lockWasTaken) System.Threading.Monitor.Exit(__lockObj);
}
```

Da ein [try...finally](try-finally.md)-Block in diesem Code verwendet wird, wird die Sperre aufgehoben, wenn eine Ausnahme innerhalb des Texts einer `lock`-Anweisung ausgelöst wird.

Sie können das Schlüsselwort [await](await.md) nicht im Text einer `lock`-Anweisung verwenden.

## <a name="remarks"></a>Hinweise

Wenn Sie den Threadzugriff auf freigegebene Ressourcen synchronisieren, sperren Sie eine dedizierte Objektinstanz (z.B. `private readonly object balanceLock = new object();`) oder eine andere Instanz, für die es unwahrscheinlich ist, dass sie von anderen Teilen des Codes als lock-Objekt verwendet wird. Vermeiden Sie, die gleiche lock-Objektinstanz für verschiedene freigegebene Ressourcen zu verwenden, da dies zu einem Deadlock oder Sperrkonflikt führen kann. Vermeiden Sie insbesondere die Verwendung von

- `this` (kann von den Aufrufern als Sperre verwendet werden),
- <xref:System.Type>-Instanzen (kann vom [typeof](typeof.md)-Operator oder der Reflektion abgerufen werden),
- Zeichenfolgeninstanzen, die Zeichenfolgenliterale enthalten,

als lock-Objekte.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine `Account`-Klasse definiert, die den Zugriff auf das private `balance`-Feld synchronisiert, indem eine dedizierte `balanceLock`-Instanz gesperrt wird. Durch Verwendung der gleichen Instanz für die Sperre wird sichergestellt, dass das `balance`-Feld nicht von zwei Threads gleichzeitig aktualisiert werden kann, die zur gleichen Zeit versuchen, die Methoden `Debit` oder `Credit` aufzurufen.

[!code-csharp[lock-statement-example](~/samples/snippets/csharp/keywords/LockStatementExample.cs)]

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.SpinLock?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [C#-Referenz](../index.md)
- [C#-Schlüsselwörter](index.md)
- [Anweisungsschlüsselwörter](statement-keywords.md)
- [Interlocked-Vorgänge](../../../standard/threading/interlocked-operations.md)
- [Übersicht über Synchronisierungsprimitiven](../../../standard/threading/overview-of-synchronization-primitives.md)
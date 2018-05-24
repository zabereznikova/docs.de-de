---
title: fixed-Anweisung (C#-Referenz)
ms.date: 05/10/2018
f1_keywords:
- fixed_CSharpKeyword
- fixed
helpviewer_keywords:
- fixed keyword [C#]
ms.openlocfilehash: e26e7e7f15dd48cf029d5f67bf5ef0de3e19b7bb
ms.sourcegitcommit: 895c7602386a6dfe7ca4facce3d965b27e5c6e87
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2018
---
# <a name="fixed-statement-c-reference"></a>fixed-Anweisung (C#-Referenz)

Die `fixed`-Anweisung verhindert, dass der Garbage Collector eine bewegliche Variable verschiebt. Die `fixed`-Anweisung ist nur in einem [unsicheren (unsafe)](unsafe.md) Kontext zulässig. `fixed` kann auch zum Erstellen eines [Puffers fester Größe](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md) verwendet werden.

Die `fixed`-Anweisung setzt einen Zeiger auf eine verwaltete Variable und „fixiert“ diese Variable während der Ausführung der Anweisung. Zeiger auf verschiebbare verwaltete Variablen sind nur in einem `fixed`-Kontext nützlich. Ohne den `fixed`-Kontext könnte die automatische Speicherbereinigung die Variablen auf unvorhersehbare Weise verschieben. Mit dem C#-Compiler können Sie einer verwalteten Variablen nur in einer `fixed`-Anweisung einen Zeiger zuweisen.

[!code-csharp[Accessing fixed memory](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#1)]

Sie können einen Zeiger mit einem Array, einer Zeichenfolge, einem Puffer fester Größe oder der Adresse einer Variablen initialisieren. Im folgenden Beispiel wird die Verwendung von Adressen, Arrays und Zeichenfolgen von Variablen veranschaulicht. Weitere Informationen zu Puffern fester Größe finden Sie unter [Puffer fester Größe](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).

[!code-csharp[Initializing fixed size buffers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#2)]

Ab C# 7.3 funktioniert die `fixed`-Anweisung mit weiteren Typen, nicht nur mit Arrays, Zeichenfolgen, Puffern mit festgelegter Größe und nicht verwalteten Variablen. Jeder Typ, der eine Methode mit dem Namen `DangerousGetPinnableReference` implementiert, kann angeheftet werden. `DangerousGetPinnableReference` muss eine `ref`-Variable an einen nicht verwalteten Typ zurückgeben. Weitere Informationen erhalten Sie im Artikel zu [Zeigertypen](../../programming-guide/unsafe-code-pointers/pointer-types.md). Die .NET-Typen <xref:System.Span%601?displayProperty=nameWithType> und <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, die in .NET Core 2.0 eingeführt wurden, verwenden dieses Muster und können angeheftet werden. Dies wird im folgenden Beispiel gezeigt:

[!code-csharp[Accessing fixed memory](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#FixedSpan)]

Wenn Sie Typen erstellen, die auch dieses Muster verwenden sollen, finden Sie unter <xref:System.Span%601.DangerousGetPinnableReference?displayProperty=nameWithType> ein Beispiel für die Implementierung des Musters.

Wenn mehrere Zeiger vom selben Typ sind, können sie in einer gemeinsamen Anweisung initialisiert werden:

```csharp
fixed (byte* ps = srcarray, pd = dstarray) {...}
```

Um Zeiger verschiedener Typen zu initialisieren, schachteln Sie einfach `fixed`-Anweisungen, wie im folgenden Beispiel gezeigt.

[!code-csharp[Initializing multiple pointers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#3)]

Nachdem der Code in der Anweisung ausgeführt wird, können beliebige fixierte Variablen gelöst und an die automatische Speicherbereinigung übergeben werden. Aus diesem Grund sollten Sie nicht außerhalb der `fixed`-Anweisung auf diese Variablen verweisen. Die in der `fixed`-Anweisung deklarierten Variablen beziehen sich auf diese Anweisung. Dadurch wird Folgendes vereinfacht:

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
   ...
}
// ps and pd are no longer in scope here.
```

Bei Zeigern, die in `fixed`-Anweisungen initialisiert werden, handelt es sich um readonly-Variablen. Wenn Sie den Zeigerwert ändern möchten, müssen Sie eine zweite Zeigervariable deklarieren und diese ändern. Die in der `fixed`-Anweisung deklarierte Variable kann nicht verändert werden:

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
    byte* pSourceCopy = ps;
    pSourceCopy++; // point to the next element.
    ps++; // invalid: cannot modify ps, as it is declared in the fixed statement.
}
```


Im nicht sicheren Modus können Sie dem Stapel Arbeitsspeicher zuweisen, auf dem der Speicher nicht automatisch bereinigt wird und daher nicht fixiert werden muss. Weitere Informationen finden Sie unter [stackalloc](stackalloc.md).

[!code-csharp[Initializing multiple pointers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#4)]

## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

 [C#-Referenz](../index.md)  
 [C#-Programmierhandbuch](../../programming-guide/index.md)  
 [C#-Schlüsselwörter](index.md)  
 [unsafe](unsafe.md)  
 [Puffer fester Größe](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)

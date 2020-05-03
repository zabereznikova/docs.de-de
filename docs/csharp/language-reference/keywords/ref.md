---
title: ref-Schlüsselwort – C#-Referenz
ms.date: 04/21/2020
f1_keywords:
- ref_CSharpKeyword
- ref
helpviewer_keywords:
- parameters [C#], ref
- ref keyword [C#]
ms.openlocfilehash: 07e1b49605c83908f7b9af25e0cb2599a97257c5
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102072"
---
# <a name="ref-c-reference"></a>ref (C#-Referenz)

Das `ref`-Schlüsselwort gibt einen Wert an, der als Verweis übergeben wird. Es wird in vier unterschiedlichen Kontexten verwendet:

- In einer Methodensignatur und in einem Methodenaufruf, um ein Argument an eine Methode als Verweis zu übergeben. Weitere Informationen finden Sie unter [Übergeben eines Arguments als Verweis](#passing-an-argument-by-reference).
- In einer Methodensignatur, um einen Wert an den Aufrufer als Verweis zurückzugeben. Weitere Informationen finden Sie unter [Verweisrückgabewerte](#reference-return-values).
- In einem Memberkörper, um anzugeben, dass ein Verweisrückgabewert, den der Aufrufer ändern möchte, lokal als Verweis gespeichert ist oder dass eine lokale Variable auf einen anderen Wert per Verweis zugreift. Weitere Informationen finden Sie unter [Lokale ref-Variablen](#ref-locals).
- In einer `struct`-Deklaration, um `ref struct` oder `readonly ref struct` zu deklarieren. Weitere Informationen finden Sie im Abschnitt zur [`ref`-Struktur](../builtin-types/struct.md#ref-struct) des Artikels [Strukturtypen](../builtin-types/struct.md).

## <a name="passing-an-argument-by-reference"></a>Übergeben eines Arguments als Verweis

In der Parameterliste einer Methode gibt das `ref`-Schlüsselwort an, dass ein Argument als Verweis und nicht als Wert übergeben wird. Das `ref`-Schlüsselwort stellt den formalen Parameter als Alias für das Argument dar, das eine Variable sein muss. Anders ausgedrückt, jede Operation mit dem Parameter wird mit dem Argument durchgeführt. Wenn der Aufrufer z. B. einen lokalen Variablenausdruck oder einen Arrayelement-Zugriffsausdruck übergibt und die aufgerufene Methode das Objekt ersetzt, auf das der ref-Parameter verweist, dann verweist die lokale Variable des Aufrufers oder das Arrayelement bei Rückgabe der Methode jetzt auf das neue Objekt.

> [!NOTE]
> Verwechseln Sie nicht das Konzept der Übergabe durch einen Verweis mit dem Konzept der Verweistypen. Die beiden Konzepte sind nicht identisch. Ein Methodenparameter kann durch `ref` geändert werden, unabhängig davon, ob es sich um einen Werttyp oder ein Verweistyp handelt. Es gibt keine Boxing-Konvertierung eines Werttyps, wenn er durch einen Verweis übergeben wird.  

Um einen `ref`-Parameter zu verwenden, müssen sowohl die Methodendefinition als auch die aufrufende Methode explizit das Schlüsselwort `ref` verwenden, wie im folgenden Beispiel gezeigt.  

[!code-csharp-interactive[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#1)]

Ein Argument, das an einen `ref`- oder `in`-Parameter übergeben wird, muss vor der Übergabe initialisiert werden. Dies unterscheidet sich von den [out](out-parameter-modifier.md)-Parametern, deren Argumente nicht explizit initialisiert werden müssen, bevor sie übergeben werden.

Member einer Klasse können keine Signaturen haben, die sich nur durch `ref`, `in` oder `out` voneinander unterscheiden. Es tritt ein Compilerfehler auf, wenn der einzige Unterschied zwischen beiden Member eines Typs der ist, dass einer von ihnen über einen `ref`-Parameter und der andere über einen `out`- oder `in`-Parameter verfügt. Der folgende Code wird z. B. nicht kompiliert.  

```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```

Allerdings können Methoden überladen werden, wenn eine Methode einen `ref`-, `in`- oder `out`-Parameter hat und die andere wie im folgenden Beispiel dargestellt über einen Werteparameter verfügt.
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#2)]
  
 In anderen Situationen, die eine Signaturabstimmung benötigen, z.B. beim Ausblenden oder Überschreiben, sind `in`, `ref` und `out` Bestandteil der Signatur und passen nicht zueinander.  
  
 Eigenschaften sind keine Variablen. Sie sind Methoden und können nicht an `ref`-Parameter übergeben werden.  
  
 Sie können keines der Schlüsselwörter `ref`, `in` und `out` für die folgenden Methodentypen verwenden:  
  
- Asynchrone Methoden, die Sie mit dem [async](async.md)-Modifizierer definieren.  
- Iterator-Methoden, die eine [yield return](yield.md)- oder `yield break`-Anweisung enthalten.

Für [Erweiterungsmethoden](../../programming-guide/classes-and-structs/extension-methods.md) gelten die folgenden Einschränkungen:

- Das `out`-Schlüsselwort kann nicht für das erste Argument einer Erweiterungsmethode verwendet werden.
- Das `ref`-Schlüsselwort kann nicht für das erste Argument einer Erweiterungsmethode verwendet werden, wenn es sich bei dem Argument nicht um eine Struktur handelt oder ein generischer Typ nicht auf eine Struktur beschränkt ist.
- Das `in`-Schlüsselwort kann nur verwendet werden, wenn das erste Argument eine Struktur ist. Das `in`-Schlüsselwort kann nicht für einen generischen Typ verwendet werden – selbst bei einer Beschränkung auf eine Struktur.

## <a name="passing-an-argument-by-reference-an-example"></a>Übergeben eines Arguments per Verweis: Beispiel

In den vorherigen Beispielen wurden Werttypen als Verweis übergeben. Sie können das `ref`-Schlüsselwort auch verwenden, um Verweistypen als Verweis zu übergeben. Die Übergabe eines Verweistyps als Verweis ermöglicht es der aufgerufenen Methode, das Objekt, auf die der Verweisparameter im Aufrufer verweist, zu ersetzen. Der Speicherort des Objekts wird als Wert des Verweisparameters an die Methode übergeben. Wenn Sie den Wert am Speicherort des Parameters ändern (um auf ein neues Objekt zu verweisen), ändern Sie auch den Speicherort, auf den der Aufrufer verweist. Im folgenden Beispiel wird eine Instanz eines Verweistyps als ein `ref`-Parameter übergeben.
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#3)]

Weitere Informationen zum Übergeben von Verweistypen durch einen Wert und durch einen Verweis finden Sie unter [Übergeben von Verweistypparametern](../../programming-guide/classes-and-structs/passing-reference-type-parameters.md).
  
## <a name="reference-return-values"></a>Verweisrückgabewerte

Verweisrückgabewerte (auch ref-Rückgaben genannt) sind Werte, die von einer Methode an den Aufrufer als Verweis zurückgegeben werden. Das bedeutet, dass der Aufrufer den von einer Methode zurückgegebenen Wert ändern kann. Diese Änderung wird im Zustand des Objekts in der aufrufenden Methode wiedergegeben.

Ein Verweisrückgabewert wird definiert durch Verwenden des `ref`-Schlüsselworts:

- In der Methodensignatur. Die folgende Methodensignatur gibt z.B. an, dass die Methode `GetCurrentPrice` den Wert <xref:System.Decimal> nach Verweis zurückgibt.

```csharp
public ref decimal GetCurrentPrice()
```

- Zwischen dem `return`-Token und der Variable, die in einer `return`-Anweisung in der Methode zurückgegeben wird. Zum Beispiel:

```csharp
return ref DecimalArray[0];
```

Zum Ändern des Zustands des Objekts durch den Aufrufer muss der Verweisrückgabewert in einer Variable gespeichert werden, die explizit als [lokale ref-Variable](#ref-locals) definiert ist.

Hier ist ein vollständigeres Beispiel für die Verweisrückgabe, das sowohl die Methodensignatur als auch den Methodentext zeigt.

[!code-csharp[FindReturningRef](~/samples/snippets/csharp/new-in-7/MatrixSearch.cs#FindReturningRef "Find returning by reference")]

Die aufgerufene Methode kann den Rückgabewert auch als `ref readonly` deklarieren, um den Wert als Verweis zurückzugeben, und durchsetzen, dass der aufrufende Code den zurückgegebenen Wert nicht ändern kann. Die aufrufende Methode kann das Kopieren des zurückgegebenen Werts vermeiden, indem sie den Wert in einer lokalen [schreibgeschützten ref-Variablen](#ref-readonly-locals) speichert.

Ein Beispiel finden Sie unter [Beispiel für ref-Rückgaben und lokale ref-Variablen](#a-ref-returns-and-ref-locals-example).

## <a name="ref-locals"></a>Lokale ref-Variablen

Eine lokale ref-Variable wird verwendet, um auf Werte zu verweisen, die mit `return ref` zurückgegeben werden. Eine lokale ref-Variable kann nicht für einen nicht ref-Rückgabewert initialisiert werden. Das heißt, die rechte Seite der Initialisierung muss ein Verweis sein. Jede Änderung am Wert der lokalen ref-Variable wird im Zustand des Objekts wiedergegeben, dessen Methode den Wert als Verweis zurückgegeben hat.

Eine lokale ref-Variable wird mithilfe des `ref`-Schlüsselworts vor der Variablendeklaration definiert sowie unmittelbar vor dem Aufruf der Methode, die den Wert als Verweis zurückgibt.

Die folgende Anweisung definiert z.B. eine lokale ref-Variable, die von der Methode `GetEstimatedValue` zurückgegeben wird:

```csharp
ref decimal estValue = ref Building.GetEstimatedValue();
```

Auch auf Werte können Sie per Verweis zugreifen. In einigen Fällen erhöht dies die Leistung, da ein möglicherweise aufwendiger Kopiervorgang vermieden wird. In der folgenden Anweisung wird z.B. gezeigt, wie ein lokaler Verweiswert definiert wird, mit dem auf einen Wert verwiesen wird.

```csharp
ref VeryLargeStruct reflocal = ref veryLargeStruct;
```

Das Schlüsselwort `ref` muss in beiden Beispielen an beiden Stellen verwendet werden. Andernfalls generiert der Compiler den Fehler CS8172 „Eine by-reference-Variable kann nicht mit einem Wert initialisiert werden“.

Beginnend mit C# 7.3 kann die Iterationsvariable der `foreach`-Anweisung eine lokale ref-Variable oder schreibgeschützte lokale ref-Variable sein. Weitere Informationen finden Sie im Artikel zur [foreach-Anweisung](foreach-in.md).

Ebenfalls beginnend mit C# 7.3 können Sie eine lokale oder schreibgeschützte lokale ref-Variable mit dem [ref-Zuweisungsoperator](../operators/assignment-operator.md#ref-assignment-operator) neu zuweisen.

## <a name="ref-readonly-locals"></a>Lokale schreibgeschützte ref-Variable

Mit einer lokalen schreibgeschützten ref-Variablen können Sie auf Werte verweisen, die von der Methode oder Eigenschaft zurückgegeben werden, die `ref readonly` in der Signatur enthält und `return ref` verwendet. Eine `ref readonly`-Variable kombiniert die Eigenschaften einer lokalen `ref`-Variablen mit einer `readonly`-Variablen: Sie ist ein Alias für den Speicher, dem sie zugewiesen ist, und kann nicht geändert werden.

## <a name="a-ref-returns-and-ref-locals-example"></a>Beispiel für ref-Rückgaben und lokale ref-Variablen

Im folgenden Beispiel wird eine `Book`-Klasse mit zwei <xref:System.String>-Feldern definiert: `Title` und `Author`. Außerdem wird eine `BookCollection`-Klasse definiert, die ein privates Array von `Book`-Objekten enthält. Einzelne Buchobjekte werden durch Aufrufen der `GetBookByTitle`-Methode als Verweis zurückgegeben.

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#4)]

Speichert der Aufrufer den von der `GetBookByTitle`-Methode zurückgegeben Wert als lokale ref-Variable, werden Änderungen, die der Aufrufer am Rückgabewert vornimmt, im `BookCollection`-Objekt wiedergegeben. Dies wird im folgenden Beispiel gezeigt:

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#5)]

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Schreiben von sicherem und effizientem Code](../../write-safe-efficient-code.md)
- [Ref-Rückgabetypen und lokale ref-Variablen](../../programming-guide/classes-and-structs/ref-returns.md)
- [Bedingter ref-Ausdruck](../operators/conditional-operator.md#conditional-ref-expression)
- [Übergeben von Parametern](../../programming-guide/classes-and-structs/passing-parameters.md)
- [Methodenparameter](method-parameters.md)
- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)

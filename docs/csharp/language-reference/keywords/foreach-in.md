---
title: foreach, in (C#-Referenz)
ms.date: 10/11/2017
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: c0b1481988a2e3199fc6d06ca30cb5194ab2f44c
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/18/2018
---
# <a name="foreach-in-c-reference"></a>foreach, in (C#-Referenz)

Mit der `foreach`-Anweisung wird eine Gruppe von eingebetteten Anweisungen für jedes Element in einem Array oder einer Objektauflistung wiederholt, das die Schnittstelle <xref:System.Collections.IEnumerable?displayProperty=nameWithType> oder <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> implementiert. Die [foreach-Anweisung](/dotnet/csharp/language-reference/language-specification/statements#the-foreach-statement) wird verwendet, um die Auflistung zu durchlaufen und dadurch die gewünschten Informationen zu erhalten. Setzen Sie sie nicht ein, um der Auflistung Elemente hinzuzufügen oder aus ihr zu entfernen, um unvorhersehbare Nebeneffekte zu vermeiden. Wenn Sie Elemente zu der Quellauflistung hinzufügen oder daraus entfernen müssen, verwenden Sie eine [for](for.md)-Schleife.
  
 Die Ausführung der eingebetteten Anweisungen wird für jedes Element in dem Array oder der Auflistung fortgesetzt. Nachdem die Iteration alle Elemente in der Auflistung durchlaufen hat, wird die Steuerung an die nächste Anweisung, die auf den `foreach`-Block folgt, übergeben.
  
 Sie können die Schleife an jedem Punkt im `foreach`-Block mit dem Schlüsselwort [break](break.md) unterbrechen oder mit dem Schlüsselwort [continue](continue.md) direkt zum nächsten Durchlauf der Schleife springen.

 Eine `foreach`-Schleife kann durch die Anweisungen [goto](goto.md), [return](return.md) oder [throw](throw.md) beendet werden.

 Weitere Informationen zum `foreach`-Schlüsselwort und zu Codebeispielen finden Sie unter den folgenden Themen:  

 [Verwenden von foreach mit Arrays](../../programming-guide/arrays/using-foreach-with-arrays.md)  

 [Gewusst wie: Zugreifen auf Sammlungsklassen mit foreach](../../programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md)  

## <a name="example"></a>Beispiel

Der folgende Code zeigt drei Beispiele:

> [!TIP]
> Sie können die Beispiele bearbeiten, um mit der Syntax zu experimentieren und verschiedene Verwendungen auszuprobieren, die Ihrem Anwendungsfall eher entsprechen. Klicken Sie auf „Ausführen“, um den Code auszuführen, bearbeiten Sie ihn anschließend, und klicken Sie erneut auf „Ausführen“.

-   eine typische `foreach`-Schleife, die den Inhalt eines Arrays von Ganzzahlen anzeigt

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L12-L26)]

-   eine [for](../../../csharp/language-reference/keywords/for.md)-Schleife, die die gleiche Aufgabe ausführt

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L31-L46)]

-   eine `foreach`-Schleife, die die Anzahl von Elementen im Array enthält

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L51-L69)]
 
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch  

[Die foreach-Anweisung (C#-Spezifikation)](/dotnet/csharp/language-reference/language-specification/statements#the-foreach-statement)

[C#-Referenz](../index.md)

[C#-Programmierhandbuch](../../programming-guide/index.md)

[C#-Schlüsselwörter](index.md)

[Iterationsanweisungen](iteration-statements.md)

[for](for.md)

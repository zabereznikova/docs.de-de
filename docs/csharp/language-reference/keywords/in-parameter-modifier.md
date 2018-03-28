---
title: Modifizierer für in-Parameter (C#-Verweis)
ms.date: 03/06/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- parameters [C#], in
- in parameters [C#]
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9b8b21e2bdc95829c831ee71f24b47986321b7d0
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2018
---
# <a name="in-parameter-modifier-c-reference"></a>Modifizierer für in-Parameter (C#-Verweis)

Das Schlüsselwort `in` bewirkt, dass Argumente per Verweis übergeben werden. Es ähnelt zwar den Schlüsselwörtern [ref](ref.md) oder [out](out-parameter-modifier.md), jedoch können `in`-Argumente nicht von der aufgerufenen Methode verändert werden, `ref`-Argumente hingegen schon. `out`-Argumente müssen hingegen vom Aufrufer verändert werden. Diese Veränderungen können im aufrufenden Kontext überprüft werden.

[!code-csharp-interactive[cs-in-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/InParameterModifier.cs#1)]  

Das vorausgehende Beispiel veranschaulicht, dass der `in`-Bezeichner für die Aufrufsite nicht benötigt wird. Er ist nur in der Methodendeklaration erforderlich.

> [!NOTE] 
> Das `in`-Schlüsselwort kann ebenfalls mit einem generischen Typparameter verwendet werden, um als der Bestandteil einer `foreach`-Anweisung oder einer `join`-Klausel in einer LINQ-Abfrage anzugeben, dass der Typparameter kontravariant ist. Weitere Informationen zur Verwendung des `in`-Schlüsselworts in diesen Kontexten und entsprechende Links finden Sie unter [in](in.md).
  
 Variablen, die als `in`-Argumente übergeben wurden, müssen initialisiert werden, bevor sie in einen Methodenaufruf übergeben werden. Es kann jedoch sein, dass die aufgerufene Methode keinen Wert zuweist oder das Argument ändert.  
  
 Obwohl die Schlüsselwörter `in`, `ref` und `out` unterschiedliche Laufzeitverhalten hervorrufen, gelten sie zum Zeitpunkt der Kompilierung nicht als Teil der Methodensignatur. Aus diesem Grund können die Methoden nicht überladen werden, wenn der einzige Unterschied darin besteht, dass eine Methode ein `ref`- oder `in`-Argument übernimmt und die andere ein `out`-Argument. Der folgende Code wird z. B. nicht kompiliert:  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on in, ref and out".
    public void SampleMethod(in int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
Überladungen sind zwar zulässig, wenn `in` vorhanden ist, es wird dadurch jedoch eine Compilerwarnung generiert:  
  
```csharp
class InOverloads
{
    // Discouraged. Calling SampleMethod(value) is ambiguous.
    public void SampleMethod(in int i) { }
    public void SampleMethod(int i) { }
}
```

Eigenschaften oder Konstanten können als `in`-Parameter übergeben werden, da die aufrufende Methode deren Werte möglicherweise nicht verändern kann.
  
Sie können keines der Schlüsselwörter `in`, `ref` und `out` für die folgenden Methodentypen verwenden:  
  
- Asynchrone Methoden, die Sie mit dem [async](../../../csharp/language-reference/keywords/async.md)-Modifizierer definieren.  
  
- Iterator-Methoden, die eine [yield return](../../../csharp/language-reference/keywords/yield.md)- oder `yield break`-Anweisung enthalten.  

In der Regel deklarieren Sie `in`-Argumente, damit keine Kopiervorgänge durchgeführt werden müssen, die für das Übergeben von Argumenten nach Werten notwendig sind. Dies ist vor allem nützlich, wenn Argumente Werttypen wie Strukturen sind, bei denen Kopiervorgänge aufwendiger sind als Übergaben per Verweis.

> [!WARNING]
>  `in`-Parameter können noch ressourcenintensiver sein, wenn sie falsch verwendet werden. Der Compiler merkt es möglicherweise nicht, wenn Membermethoden den Status der Struktur ändern. Wenn der Compiler nicht sicherstellen kann, dass das Objekt nicht geändert wird, erstellt er defensiv eine Kopie und ruft damit Memberverweise auf. Alle etwaigen Änderungen werden an der Defensivkopie vorgenommen. Es gibt zwei Möglichkeiten, um diese Kopien zu vermeiden: das Übergeben von `in`-Parametern als `in`-Argumente oder das Definieren von Strukturen als `readonly struct`.

## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)  
 [Methodenparameter](../../../csharp/language-reference/keywords/method-parameters.md)  
 [Verweissemantik mit Werttypen](../../../csharp/reference-semantics-with-value-types.md)

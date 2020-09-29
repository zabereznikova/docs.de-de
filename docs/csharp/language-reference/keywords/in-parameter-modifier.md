---
description: Modifizierer für in-Parameter – C#-Verweis
title: Modifizierer für in-Parameter – C#-Verweis
ms.date: 03/19/2020
helpviewer_keywords:
- parameters [C#], in
- in parameters [C#]
ms.openlocfilehash: b9cd308a1eaf2ae8f4e3e89b1a4770933b3978cc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91188407"
---
# <a name="in-parameter-modifier-c-reference"></a>Modifizierer für in-Parameter (C#-Verweis)

Das Schlüsselwort `in` bewirkt, dass Argumente per Verweis übergeben werden. Es stellt den formalen Parameter als Alias für das Argument dar, das eine Variable sein muss. Anders ausgedrückt, jede Operation mit dem Parameter wird mit dem Argument durchgeführt. Es verhält sich ähnlich wie die Schlüsselwörter [ref](ref.md) und [out](out-parameter-modifier.md). Der einzige Unterschied besteht darin, dass `in`-Argumente nicht von der aufgerufenen Methode modifiziert werden können. Obwohl `ref`-Argumente modifiziert werden können, müssen `out`-Argumente von der aufgerufenen Methode geändert werden. Die Änderungen werden im Aufrufkontext angezeigt.

[!code-csharp-interactive[cs-in-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/InParameterModifier.cs#1)]  

Das vorausgehende Beispiel veranschaulicht, dass der `in`-Modifizierer an der Aufrufstelle normalerweise nicht benötigt wird. Er ist nur in der Methodendeklaration erforderlich.

> [!NOTE]
> Das `in`-Schlüsselwort kann ebenfalls mit einem generischen Typparameter verwendet werden, um als der Bestandteil einer `foreach`-Anweisung oder einer `join`-Klausel in einer LINQ-Abfrage anzugeben, dass der Typparameter kontravariant ist. Weitere Informationen zur Verwendung des `in`-Schlüsselworts in diesen Kontexten und entsprechende Links finden Sie unter [in](in.md).
  
Variablen, die als `in`-Argumente übergeben wurden, müssen initialisiert werden, bevor sie in einen Methodenaufruf übergeben werden. Es kann jedoch sein, dass die aufgerufene Methode keinen Wert zuweist oder das Argument ändert.  

Die `in`-Parametermodifizierer steht in C# 7.2 und höher zur Verfügung. Frühere Versionen generieren den Compilerfehler `CS8107` (Das Feature „schreibgeschützte Verweise“ ist in C# 7.0 nicht verfügbar. Verwenden Sie Sprachversion 7.2 oder höher.). Hinweise zum Konfigurieren der Compilersprachversion finden Sie unter [Auswählen der C#-Sprachversion](../configure-language-version.md).

Die Schlüsselwörter `in`, `ref` und `out` werden nicht als Teil der Methodensignatur zum Zwecke der Überladungsauflösung betrachtet. Aus diesem Grund können die Methoden nicht überladen werden, wenn der einzige Unterschied darin besteht, dass eine Methode ein `ref`- oder `in`-Argument übernimmt und die andere ein `out`-Argument. Der folgende Code wird z. B. nicht kompiliert:  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded
    // methods that differ only on in, ref and out".
    public void SampleMethod(in int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
Das Überladen bei vorhandenem `in` ist zulässig:  
  
```csharp
class InOverloads
{
    public void SampleMethod(in int i) { }
    public void SampleMethod(int i) { }
}
```

## <a name="overload-resolution-rules"></a>Regeln zur Überladungsauflösung

Die Regeln zur Auflösung von Methodenüberladungen bei der Übergabe von Argumenten als Wert und durch `in` lassen sich nachvollziehen, wenn die Motivation für `in`-Argumente bekannt ist. Wenn Methoden mit `in`-Parametern definiert werden, kann unter Umständen eine Leistungsoptimierung erzielt werden. Einige `struct`-Typargumente beanspruchen viel Speicherplatz. Wenn dann in Schleifen mit vielen Durchläufen oder kritischen Codepfaden Methoden aufgerufen werden, ist der Aufwand zum Kopieren dieser Strukturen enorm. Durch die Deklaration von `in`-Parametern in Methoden wird festgelegt, dass Argumente sicher als Verweis übergeben werden, da die aufgerufene Methode nicht den Zustand des Arguments ändert. Durch die Übergabe dieser Argumente als Verweis wird ein möglicherweise aufwendiges Kopieren vermieden.

Die Angabe von `in` für Argumente an der Aufrufstelle ist üblicherweise optional. Zwischen der Übergabe eines Arguments als Wert und der Übergabe als Verweis mithilfe des `in`-Modifizierers besteht kein semantischer Unterschied. Der `in`-Modifizierer an der Aufrufstelle ist optional, da nicht kenntlich gemacht werden muss, dass sich der Wert des Arguments ändern kann. Explizit geben Sie den `in`-Modifizierer an der Aufrufstelle an, wenn Sie sicherstellen möchten, dass das Argument als Verweis und nicht als Wert übergeben wird. Die explizite Verwendung von `in` hat die folgenden beiden Auswirkungen:

Erstens wird der Compiler durch die Angabe von `in` an der Aufrufstelle dazu gezwungen, die Methode mit dem übereinstimmenden `in`-Parameter auszuwählen. Wenn dies nicht der Fall ist und sich zwei Methoden nur durch die Angabe von `in` unterscheiden, wird die Methode überladen, für die Argumente als Wert übergeben werden.

Zweitens wird durch `in` festgelegt, dass ein Argument als Verweis übergeben wird. Das mit `in` verwendete Argument muss einen Speicherort darstellen, auf den direkt verwiesen werden kann. Es gelten die gleichen allgemeinen Regeln für `out`- und `ref`-Argumente: Sie können keine Konstanten, normale Eigenschaften oder andere Ausdrücke, die Werte erzeugen, verwenden. Wird `in` an der Aufrufstelle weggelassen, wird der Compiler darüber informiert, dass die Erstellung einer temporären Variable und deren Übergabe als schreibgeschützter Verweis an die Methode zulässig ist. Der Compiler erstellt in diesem Fall eine temporäre Variable, um mehrere Einschränkungen im Zusammenhang mit `in`-Argumenten zu umgehen:

- Eine temporäre Variable ermöglicht als Konstanten zur Kompilierzeit `in`-Parameter.
- Eine temporäre Variable ermöglicht Eigenschaften oder andere Ausdrücke für `in`-Parameter.
- Eine temporäre Variable ermöglicht Argumente, bei denen eine implizite Konvertierung des Argumenttyps in den Parametertyp vorgenommen wird.

In den oben beschriebenen Fällen erstellt der Compiler eine temporäre Variable, die den Wert einer Konstante, einer Eigenschaft oder eines anderen Ausdrucks speichert.

Das folgende Codebeispiel veranschaulicht diese Regeln:

```csharp
static void Method(in int argument)
{
    // implementation removed
}

Method(5); // OK, temporary variable created.
Method(5L); // CS1503: no implicit conversion from long to int
short s = 0;
Method(s); // OK, temporary int created with the value 0
Method(in s); // CS1503: cannot convert from in short to in int
int i = 42;
Method(i); // passed by readonly reference
Method(in i); // passed by readonly reference, explicitly using `in`
```

Gehen wir nun davon aus, dass eine weitere Methode verfügbar ist, für die Argumente als Wert übergeben werden: Wie im folgenden Codebeispiel zu sehen ist, ändern sich die Ergebnisse:

```csharp
static void Method(int argument)
{
    // implementation removed
}

static void Method(in int argument)
{
    // implementation removed
}

Method(5); // Calls overload passed by value
Method(5L); // CS1503: no implicit conversion from long to int
short s = 0;
Method(s); // Calls overload passed by value.
Method(in s); // CS1503: cannot convert from in short to in int
int i = 42;
Method(i); // Calls overload passed by value
Method(in i); // passed by readonly reference, explicitly using `in`
```

Nur beim letzten Methodenaufruf wird das Argument als Verweis übergeben.

> [!NOTE]
> Im obigen Code wird aus Gründen der Einfachheit `int` als Argumenttyp verwendet. Da auf den meisten modernen Computern `int` nicht größer ist als ein Verweis, ergibt sich kein Vorteil daraus, einen einzelnen `int`-Wert als schreibgeschützten Verweis zu übergeben.

## <a name="limitations-on-in-parameters"></a>Einschränkungen für `in`-Parameter

Sie können keines der Schlüsselwörter `in`, `ref` und `out` für die folgenden Methodentypen verwenden:  
  
- Asynchrone Methoden, die Sie mit dem [async](async.md)-Modifizierer definieren.  
- Iterator-Methoden, die eine [yield return](yield.md)- oder `yield break`-Anweisung enthalten.
- Das erste Argument einer Erweiterungsmethode kann nur dann einen `in`-Modifizierer verwenden, wenn dieses Argument eine Struktur ist.
- Das erste Argument einer Erweiterungsmethode, wenn es sich bei diesem Argument um einen generischen Typ handelt (selbst dann, wenn dieser Typ auf eine Struktur beschränkt ist).

## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [Methodenparameter](method-parameters.md)
- [Schreiben von sicherem und effizientem Code](../../write-safe-efficient-code.md)

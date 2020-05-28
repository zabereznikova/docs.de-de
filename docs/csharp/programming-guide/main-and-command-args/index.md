---
title: Main() und Befehlszeilenargumente – C#-Programmierhandbuch
ms.date: 08/02/2017
f1_keywords:
- CS5001
- main_CSharpKeyword
- Main
helpviewer_keywords:
- Main method [C#]
- C# language, command-line arguments
- arguments [C#], command-line
- command line [C#], arguments
- command-line arguments [C#], Main method
ms.assetid: 73a17231-cf96-44ea-aa8a-54807c6fb1f4
ms.openlocfilehash: 723884dd448232777ae2cfeac5bfcf5ea24363b0
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007740"
---
# <a name="main-and-command-line-arguments-c-programming-guide"></a>Main() und Befehlszeilenargumente (C#-Programmierhandbuch)

Die `Main`-Methode ist der Einstiegspunkt einer C#-Anwendung. (Bibliotheken und Dienste erfordern keine `Main`-Methode als Einstiegspunkt.) Wenn die Anwendung gestartet wird, ist die `Main`-Methode die erste Methode, die aufgerufen wird.

In einem C#-Programm kann nur ein Einstiegspunkt vorhanden sein. Wenn Sie mehr als eine Klasse mit einer `Main`-Methode aufweisen, müssen Sie das Programm mit der `-main`-Compileroption kompilieren, um anzugeben, welche `Main`-Methode als Einstiegspunkt verwendet wird. Weitere Informationen finden Sie unter [-main (C#-Compileroptionen)](../../language-reference/compiler-options/main-compiler-option.md).

[!code-csharp[csProgGuideMain#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#17)]

## <a name="overview"></a>Übersicht

- Die `Main`-Methode ist der Einstiegspunkt eines ausführbaren Programms. Hier beginnt und endet die Programmsteuerung.
- `Main` wird innerhalb einer Klasse oder Struktur deklariert. `Main` muss [statisch](../../language-reference/keywords/static.md), aber nicht [öffentlich](../../language-reference/keywords/public.md) sein. (Im Beispiel oben erhält es den Standardzugriff [private](../../language-reference/keywords/private.md).) Die einschließende Klasse oder Struktur muss nicht statisch sein.
- `Main` kann über die Rückgabetypen `void` oder `int` verfügen; seit C# 7.1 sind auch die Rückgabetypen `Task` oder `Task<int>` möglich.
- Wenn – und nur wenn – `Main` einen `Task`- oder `Task<int>`-Wert zurückgibt, darf die Deklaration von `Main` den [`async`](../../language-reference/keywords/async.md)-Modifizierer enthalten. Beachten Sie, dass diese insbesondere eine `async void Main`-Methode ausschließt.
- Die `Main`-Methode kann mit oder ohne `string[]`-Parameter deklariert werden, der die Befehlszeilenargumente enthält. Bei Verwendung von Visual Studio zum Erstellen von Windows-Anwendungen können Sie den Parameter manuell hinzufügen oder die <xref:System.Environment.GetCommandLineArgs>-Methode verwenden, um die [Befehlszeilenargumente](command-line-arguments.md) abzurufen. Parameter werden als mit Null indizierte Befehlszeilenargumente gelesen. Im Gegensatz zu C und C++ wird der Name des Programms nicht als erstes Befehlszeilenargument im `args`-Array behandelt, es ist jedoch das erste Element der <xref:System.Environment.GetCommandLineArgs>-Methode.

Im Folgenden erhalten Sie eine Liste gültiger `Main`-Signaturen:

```csharp
public static void Main() { }
public static int Main() { }
public static void Main(string[] args) { }
public static int Main(string[] args) { }
public static async Task Main() { }
public static async Task<int> Main() { }
public static async Task Main(string[] args) { }
public static async Task<int> Main(string[] args) { }
```

In den vorangehenden Beispielen wird der öffentliche Zugriffsmodifizierer verwendet. Dieses Verhalten ist typisch, aber nicht obligatorisch.

Das Hinzufügen der `async`-Rückgabetypen `Task` und `Task<int>` vereinfacht den Programmcode, wenn Konsolenanwendungen asynchrone Vorgänge in `Main` starten und mit `await` darauf warten müssen.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [Erstellen über die Befehlszeile mit csc.exe](../../language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [C#-Programmierhandbuch](../index.md)
- [Methoden](../classes-and-structs/methods.md)
- [Einblicke in ein C#-Programm](../inside-a-program/index.md)

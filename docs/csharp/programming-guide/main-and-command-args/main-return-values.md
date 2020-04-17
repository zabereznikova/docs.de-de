---
title: Main()-Rückgabewerte – C#-Programmierhandbuch
ms.date: 08/02/2017
helpviewer_keywords:
- Main method [C#], return values
ms.assetid: c2f5a1d8-1676-4bea-bc7e-44a97e72d5bc
ms.openlocfilehash: 7061b6c1988da9f6dfac115ee555a914531df863
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805927"
---
# <a name="main-return-values-c-programming-guide"></a>Main()-Rückgabewerte (C#-Programmierhandbuch)

Die Methode `Main` kann `void` zurückgeben:

 [!code-csharp[csProgGuideMain#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#12)]

Zudem kann `int` zurückgegeben werden:

 [!code-csharp[csProgGuideMain#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#13)]

Wenn der Rückgabewert von `Main` nicht verwendet wird, ermöglicht die Rückgabe von `void` einen etwas einfacheren Code. Die Rückgabe einer Ganzzahl ermöglicht es dem Programm jedoch, Statusinformationen an andere Programme oder Skripts zu übermitteln, die die ausführbare Datei aufrufen. Der Rückgabewert von `Main` wird als Exitcode für den Prozess behandelt. Wenn `void` von `Main` zurückgegeben wird, entspricht der Exitcode implizit `0`. Im folgenden Beispiel wird gezeigt, wie auf den Rückgabewert von `Main` zugegriffen werden kann.

## <a name="example"></a>Beispiel

In diesem Beispiel werden Befehlszeilentools von [.NET Core](../../../core/index.yml) verwendet. Wenn Sie noch nicht mit den Befehlszeilentools von .NET Core vertraut sind, finden Sie weitere Informationen in diesem [Artikel zu den ersten Schritten](../../../core/tutorials/cli-create-console-app.md).

Ändern Sie die Methode `Main` in *program.cs* folgendermaßen:

 [!code-csharp[csProgGuideMain#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#14)]

Wenn ein Programm in Windows ausgeführt wird, wird jeder Wert, der von der Funktion `Main` zurückgegeben wurde, in einer Umgebungsvariable gespeichert. Diese Umgebungsvariable kann abgerufen werden, indem `ERRORLEVEL` aus einer Batchdatei oder `$LastExitCode` aus PowerShell verwendet wird.

Sie können die Anwendung mithilfe des [dotnet CLI](../../../core/tools/dotnet.md)-Befehls `dotnet build` erstellen.

Als nächstes erstellen Sie ein PowerShell-Skript, das die Anwendung ausführt und die Ergebnisse anzeigt. Fügen Sie folgenden Code in eine Textdatei ein und speichern Sie diese als `test.ps1` in dem Ordner, der das Projekt enthält. Führen Sie das PowerShell-Skript aus, indem Sie `test.ps1` in die PowerShell-Eingabeaufforderung eingeben.

Da der Code null zurückgibt, wird die Batchdatei als erfolgreich gemeldet. Wenn Sie jedoch die Datei „MainReturnValTest.cs“ ändern, damit sie einen Wert ungleich null (0) zurückgibt, und das Programm anschließend neu kompilieren, wird eine nachfolgende Ausführung des PowerShell-Skripts einen Fehler melden.

```dotnetcli
dotnet run
```

```powershell
if ($LastExitCode -eq 0) {
    Write-Host "Execution succeeded"
} else
{
    Write-Host "Execution Failed"
}
Write-Host "Return value = " $LastExitCode
```

## <a name="sample-output"></a>Beispielausgabe:

```txt
Execution succeeded
Return value = 0
```

## <a name="async-main-return-values"></a>Asynchrone Hauptrückgabewerte

Asynchrone Hauptrückgabewerte verschieben die Codebausteine, die zum Abrufen von asynchronen Methoden benötigt werden, nach `Main` zu dem Code, der vom Compiler generiert wurde. Bisher mussten Sie dieses Konstrukt schreiben, um asynchronen Code abzurufen und prüfen, ob Ihr Programm ausgeführt wurde, bevor der asynchrone Vorgang abgeschlossen ist:

```csharp
public static void Main()
{
    AsyncConsoleWork().GetAwaiter().GetResult();
}

private static async Task<int> AsyncConsoleWork()
{
    // Main body here
    return 0;
}
```

Dies kann nun durch Folgendes ersetzt werden:

[!code-csharp[AsyncMain](../../../../samples/snippets/csharp/main-arguments/program.cs#AsyncMain)]

Der Vorteil der neuen Syntax ist, dass der Compiler immer den richtigen Code generiert.

## <a name="compiler-generated-code"></a>Vom Compiler generierter Code

Wenn der Einstiegspunkt der Anwendung `Task` oder `Task<int>` zurückgibt, generiert der Compiler einen neuen Eingangspunkt, der die Eingangspunktmethode abruft, die im Anwendungscode deklariert wurde. Unter der Annahme, dass dieser Einstiegspunkt als `$GeneratedMain` bezeichnet wird, generiert der Compiler den folgenden Code für diese Einstiegspunkte:

- `static Task Main()` führt dazu, dass der Compiler das Äquivalent zu `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();` ausgibt
- `static Task Main(string[])` führt dazu, dass der Compiler das Äquivalent zu `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();` ausgibt
- `static Task<int> Main()` führt dazu, dass der Compiler das Äquivalent zu `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();` ausgibt
- `static Task<int> Main(string[])` führt dazu, dass der Compiler das Äquivalent zu `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();` ausgibt

> [!NOTE]
>Wäre im Beispiel der Modifizierer `async` auf die Methode `Main` angewendet worden, hätte der Compiler denselben Code generiert.

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [C#-Referenz](../index.md)
- [Main() und Befehlszeilenargumente](index.md)
- [Vorgehensweise: Anzeigen von Befehlszeilenargumenten](./how-to-display-command-line-arguments.md)

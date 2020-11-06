---
title: Behandeln von E/A-Fehlern in .NET
description: Informationen zum Behandeln von E/A-Fehlern in .NET Fehlercodes Ausnahmen zuordnen, Ausnahmen in E/A-Vorgängen verarbeiten und IOException verarbeiten
ms.date: 08/27/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- I/O, exception handling
- I/O, errors
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: bd7112b3052f246a01e4a36d6d425b37cb6174dd
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188041"
---
# <a name="handling-io-errors-in-net"></a>Behandeln von E/A-Fehlern in .NET

Über die Ausnahmen hinaus, die bei jedem Methodenaufruf ausgelöst werden können (wie etwa eine <xref:System.OutOfMemoryException>, wenn ein System unter Stress steht, oder eine <xref:System.NullReferenceException> aufgrund eines Programmierfehlers), können Methoden des .NET-Dateisystems die folgenden Ausnahmen auslösen:

- <xref:System.IO.IOException?displayProperty=nameWithType>, die Basisklasse aller <xref:System.IO>-Ausnahmetypen. Sie wird für Fehler ausgelöst, deren Rückgabecodes aus dem Betriebssystem sich nicht direkt anderen Ausnahmetypen zuordnen lassen.
- <xref:System.IO.FileNotFoundException?displayProperty=nameWithType>.
- <xref:System.IO.DirectoryNotFoundException?displayProperty=nameWithType>
- <xref:System.IO.DriveNotFoundException??displayProperty=nameWithType>
- <xref:System.IO.PathTooLongException?displayProperty=nameWithType>
- <xref:System.OperationCanceledException?displayProperty=nameWithType>
- <xref:System.UnauthorizedAccessException?displayProperty=nameWithType>
- <xref:System.ArgumentException?displayProperty=nameWithType>, die für ungültige Zeichen in Pfaden für .NET Framework und .NET Core 2.0 sowie frühere Versionen ausgelöst wird.
- <xref:System.NotSupportedException?displayProperty=nameWithType>, die für ungültige Doppelpunkte in .NET Framework ausgelöst wird.
- <xref:System.Security.SecurityException?displayProperty=nameWithType>, die für Anwendungen ausgelöst wird, die mit eingeschränkter Vertrauenswürdigkeit ausgeführt werden und denen lediglich die erforderlichen Berechtigungen für .NET Framework fehlen. (Volle Vertrauenswürdigkeit stellt in .NET Framework den Standard dar.)

## <a name="mapping-error-codes-to-exceptions"></a>Zuordnen von Fehlercodes zu Ausnahmen

Da das Dateisystem eine Betriebssystemressource ist, umschließen E/A-Methoden sowohl in .NET Core als auch in .NET Framework Aufrufe an das zugrundeliegende Betriebssystem. Wenn in Code, der vom Betriebssystem ausgeführt wird, ein E/A-Fehler auftritt, gibt das Betriebssystem Fehlerinformationen zu der .NET-E/A-Methode zurück. Die Methode übersetzt dann die Fehlerinformationen, normalerweise in Form eines Fehlercodes, in einen .NET-Ausnahmetyp. In den meisten Fällen erfolgt dies durch direktes Übersetzen des Fehlercodes in den entsprechenden Ausnahmetyp; es wird keine besondere Zuordnung des Fehlers auf der Grundlage des Kontexts des Methodenaufrufs vorgenommen.

Beispielsweise wird im Windows-Betriebssystem ein Methodenaufruf, der den Fehlercode `ERROR_FILE_NOT_FOUND` (oder 0x02) zurückgibt, einer <xref:System.IO.FileNotFoundException> zugeordnet, und der Fehlercode `ERROR_PATH_NOT_FOUND` (oder 0x03) wird einer <xref:System.IO.DirectoryNotFoundException> zugeordnet.

Die genauen Umstände, unter denen das Betriebssystem bestimmte Fehlercodes zurückgibt, sind aber häufig undokumentiert oder schlecht dokumentiert. Daher können unerwartete Ausnahmen auftreten. Wenn Sie beispielsweise mit einem Verzeichnis anstelle einer Datei arbeiten, könnten Sie annehmen, dass die Angabe eines falschen Verzeichnispfads für den <xref:System.IO.DirectoryInfo.%23ctor%2A>-Konstruktor eine <xref:System.IO.DirectoryNotFoundException> auslöst. Es kann aber ebenso gut eine <xref:System.IO.FileNotFoundException> auslösen.

## <a name="exception-handling-in-io-operations"></a>Ausnahmebehandlung in E/A-Vorgängen

Aufgrund dieses Rückgriffs auf das Betriebssystem können identische Ausnahmebedingungen (wie etwa der Fehler des nicht gefundenen Verzeichnisses in unserem Beispiel) dazu führen, dass eine E/A-Methode irgendeine aus der gesamten Klasse der E/A-Ausnahmen auslöst. Das bedeutet, dass beim Aufrufen von E/A-APIs Ihr Code in der Lage sein sollte, die meisten oder alle diese Ausnahmen zu behandeln, wie in der folgenden Tabelle dargestellt:

| Ausnahmetyp | .NET Core/.NET 5 oder höher | .NET Framework |
|---|---|---|
| <xref:System.IO.IOException> | Ja | Ja |
| <xref:System.IO.FileNotFoundException> | Ja | Ja |
| <xref:System.IO.DirectoryNotFoundException> | Ja | Ja |
| <xref:System.IO.DriveNotFoundException?> | Ja | Ja |
| <xref:System.IO.PathTooLongException> | Ja | Ja |
| <xref:System.OperationCanceledException> | Ja | Ja |
| <xref:System.UnauthorizedAccessException> | Ja | Ja |
| <xref:System.ArgumentException> | .NET Core 2.0 und früher| Ja |
| <xref:System.NotSupportedException> | Nein | Ja |
| <xref:System.Security.SecurityException> | Nein | Eingeschränkte Vertrauenswürdigkeit |

## <a name="handling-ioexception"></a>Behandlung von IOException

Als Basisklasse für Ausnahmen im Namespace <xref:System.IO> wird <xref:System.IO.IOException> auch für jeden Fehlercode ausgelöst, der sich keinem vordefinierten Ausnahmetyp zuordnen lässt. Das bedeutet, dass sie von jedem E/A-Vorgang ausgelöst werden kann.

> [!IMPORTANT]
> Da <xref:System.IO.IOException> die Basisklasse der anderen Ausnahmetypen im Namespace <xref:System.IO> ist, sollten Sie sie nach der Behandlung der anderen Ausnahmen im E/A-Zusammenhang in einem `catch`-Block behandeln.

Seit .NET Core 2.1 wurden darüber hinaus die Gültigkeitsprüfungen von Pfaden (um beispielsweise sicherzustellen, dass keine ungültigen Zeichen in einem Pfad vorhanden sind) entfernt, und die Runtime löst eine Ausnahme aus, die von einem Fehlercode des Betriebssystems anstelle seines eigenen Validierungscodes zugeordnet wurde. In diesem Fall ist die Ausnahme, die mit der größten Wahrscheinlichkeit ausgelöst wird, <xref:System.IO.IOException>; allerdings könnte auch jeder andere Ausnahmetyp ausgelöst werden.

Beachten Sie, dass Sie in Ihrem Fehlerbehandlungscode die <xref:System.IO.IOException> immer zuletzt behandeln sollten. Da sie die Basisklasse aller anderen EA-Ausnahmen bildet, werden sonst die Catch-Blöcke von abgeleiteten Klassen nicht ausgewertet.

Im Fall einer <xref:System.IO.IOException> können Sie zusätzliche Fehlerinformationen aus der Eigenschaft [IOException.HResult](xref:System.Exception.HResult) abrufen. Um den HResult-Wert in einen Win32-Fehlercode zu konvertieren, entfernen Sie die oberen 16 Bits des 32-Bit-Werts. In der folgenden Tabelle sind Fehlercodes aufgelistet, die von einer <xref:System.IO.IOException> umschlossen werden können.

| HResult | Konstante | Beschreibung |
| --- | --- | --- |
| ERROR_SHARING_VIOLATION | 32 | Der Dateiname fehlt, oder die Datei oder das Verzeichnis wird verwendet. |
| ERROR_FILE_EXISTS | 80 | Die Datei ist bereits vorhanden. |
| ERROR_INVALID_PARAMETER | 87 | Ein der Methode übergebenes Argument ist ungültig. |
| ERROR_ALREADY_EXISTS | 183 | Die Datei oder das Verzeichnis ist bereits vorhanden. |

Sie können diese mithilfe einer `When`-Klausel in einer catch-Anweisung behandeln, wie im folgenden Beispiel dargestellt.

[!code-csharp[io-exception-handling](~/samples/snippets/standard/io/io-exceptions/cs/io-exceptions.cs)]
[!code-vb[io-exception-handling](~/samples/snippets/standard/io/io-exceptions/vb/io-exceptions.vb)]

## <a name="see-also"></a>Siehe auch

- [Behandeln und Auslösen von Ausnahmen in .NET](../exceptions/index.md)
- [Ausnahmebehandlung (Task Parallel Library)](../parallel-programming/exception-handling-task-parallel-library.md)
- [Bewährte Methoden für Ausnahmen](../exceptions/best-practices-for-exceptions.md)
- [Gewusst wie: Verwenden spezifischer Ausnahmen in einem Catch-Block](../exceptions/how-to-use-specific-exceptions-in-a-catch-block.md)

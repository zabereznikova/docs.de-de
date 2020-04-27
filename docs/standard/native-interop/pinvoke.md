---
title: Plattformaufruf (P/Invoke)
description: Erfahren Sie, wie Sie native Funktionen über P/Invoke in .Net aufrufen.
ms.date: 01/18/2019
ms.openlocfilehash: fa8b43edfba50fbc620f257c4e7caf1673f83235
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706304"
---
# <a name="platform-invoke-pinvoke"></a>Plattformaufruf (P/Invoke)

P/Invoke ist eine Technologie, die Ihnen den Zugriff auf Strukturen, Rückrufe und Funktionen in nicht verwalteten Bibliotheken von verwaltetem Code aus ermöglicht. Der Großteil der P/Invoke-API ist in zwei Namespaces enthalten: `System` und `System.Runtime.InteropServices`. Über diese beiden Namespaces können Sie auf die Tools zugreifen, die beschreiben, wie Sie mit der nativen Komponente kommunizieren möchten.

Beginnen wir mit dem gängigsten Beispiel, dem Aufruf nicht verwalteter Funktionen im Ihrem verwalteten Code. Wir zeigen ein Meldungsfeld aus einer Befehlszeilenanwendung:

[!code-csharp[MessageBox](~/samples/snippets/standard/interop/pinvoke/messagebox.cs)]

Das obige Beispiel ist recht einfach, zeigt jedoch, was zum Aufrufen nicht verwalteter Funktionen von verwaltetem Code aus erforderlich ist. Gehen wir das Beispiel schrittweise durch:

- Zeile 1 zeigt die using-Anweisung für `System.Runtime.InteropServices`. Dies ist der Namespace, der alle benötigten Elemente enthält.
- In Zeile 7 wird das `DllImport`-Attribut eingeführt. Dieses Attribut ist äußerst wichtig, da es der Runtime mitteilt, dass die nicht verwaltete DLL geladen werden soll. Die übergebene Zeichenfolge ist die DLL, in der sich unsere Zielfunktion befindet. Zusätzlich gibt sie an, welcher [Zeichensatz](./charset.md) für das Marshallen der Zeichenfolgen verwendet werden soll. Schließlich gibt sie an, dass diese Funktion [SetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-setlasterror) aufruft und dass die Laufzeit diesen Fehlercode abfangen muss, damit der Benutzer ihn über <xref:System.Runtime.InteropServices.Marshal.GetLastWin32Error?displayProperty=nameWithType> abrufen kann.
- Zeile 8 ist der Kern der P/Invoke-Funktion. Sie definiert eine verwaltete Methode, die **genau dieselbe Signatur** aufweist wie die nicht verwaltete Methode. Wie Sie sehen, enthält die Deklaration ein neues Schlüsselwort, `extern`. Dieses teilt der Runtime mit, dass es sich um eine externe Methode handelt und dass die Runtime die Methode bei Aufruf in der im `DllImport`-Attribut angegebenen DLL findet.

Der Rest des Beispiels besteht nur aus dem Aufruf der Methode, der wie bei jeder anderen verwalteten Methode erfolgt.

Das Beispiel ist für macOS ähnlich. Der Name der Bibliothek im `DllImport`-Attribut muss geändert werden, da macOS ein anderes Schema für die Benennung dynamischer Bibliotheken verwendet. Das folgende Beispiel verwendet die `getpid(2)`-Funktion, um die Prozess-ID der Anwendung abzurufen und in der Konsole auszugeben.

[!code-csharp[getpid macOS](~/samples/snippets/standard/interop/pinvoke/getpid-macos.cs)]

Bei Linux ist es ähnlich. Der Funktionsname ist identisch, da es sich bei `getpid(2)` um einen standardmäßigen [POSIX](https://en.wikipedia.org/wiki/POSIX)-Systemaufruf handelt.

[!code-csharp[getpid Linux](~/samples/snippets/standard/interop/pinvoke/getpid-linux.cs)]

## <a name="invoking-managed-code-from-unmanaged-code"></a>Aufrufen von verwaltetem Code von nicht verwaltetem Code aus

Die Runtime ermöglicht den Kommunikationsfluss in beide Richtungen, sodass Sie verwalteten Code mithilfe von Funktionszeigern aus nativen Funktionen zurückrufen können. Einem Funktionszeiger in verwaltetem Code kommt ein **Delegat** am nächsten. Dieser wird verwendet, um Rückrufe von nativem Code an verwalteten Code zu ermöglichen.

Dieses Feature wird ähnlich dem oben beschriebenen Verfahren von verwaltetem zu nativem Code verwendet. Für einen bestimmten Rückruf definieren Sie einen Delegaten, der der Signatur entspricht, und übergeben Sie ihn an die externe Methode. Die Runtime übernimmt alles Weitere.

[!code-csharp[EnumWindows](~/samples/snippets/standard/interop/pinvoke/enumwindows.cs)]

Bevor wir unser Beispiel durchgehen, sollten wir die Signaturen der nicht verwalteten Funktionen betrachten, mit denen wir arbeiten müssen. Die Funktion, die wir zum Auflisten aller Fenster aufrufen möchten, weist folgende Signatur auf: `BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`

Der erste Parameter ist ein Rückruf. Dieser Rückruf besitzt die folgende Signatur: `BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`

Schauen wir uns jetzt das Beispiel an:

- Zeile 9 im Beispiel definiert einen Delegaten, der der Signatur des Rückrufs von nicht verwaltetem Code aus entspricht. Beachten Sie, wie die Typen LPARAM und HWND über `IntPtr` im verwalteten Code dargestellt werden.
- In den Zeilen 13 und 14 wird die `EnumWindows`-Funktion über die user32.dll-Bibliothek eingeführt.
- In den Zeilen 17 bis 20 wird der Delegat implementiert. In diesem einfachen Beispiel möchten wir nur das Handle an die Konsole ausgeben.
- Abschließend wird in Zeile 24 die externe Methode aufgerufen und an den Delegaten übergeben.

Die Beispiele für Linux und macOS werden im Folgenden angezeigt. Hierfür verwenden wir die `ftw`-Funktion, die in `libc` zu finden ist, der C-Bibliothek. Anhand dieser Funktion werden die Verzeichnishierarchien durchlaufen. Sie verwendet einen Zeiger auf eine Funktion als einen ihrer Parameter. Diese Funktion besitzt die folgende Signatur: `int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`.

[!code-csharp[ftw Linux](~/samples/snippets/standard/interop/pinvoke/ftw-linux.cs)]

Im macOS-Beispiel wird die gleiche Funktion verwendet. Der einzige Unterschied ist das Argument für das `DllImport`-Attribut, da macOS `libc` an einer anderen Stelle speichert.

[!code-csharp[ftw macOS](~/samples/snippets/standard/interop/pinvoke/ftw-macos.cs)]

Beide oben aufgeführten Beispiele hängen von Parametern ab, und in beiden Fällen werden die Parameter als verwaltete Typen angegeben. Die Runtime reagiert demgemäß und verarbeitet diese in ihren Entsprechungen auf der anderen Seite. Weitere Informationen dazu, wie Typen in nativen Code auf unserer Seite gemarshallt werden, finden Sie unter [Marshalling von Typen](type-marshaling.md).

## <a name="more-resources"></a>Weitere Ressourcen

- [PInvoke.NET-Wiki](https://www.pinvoke.net/) ist eine ausgezeichnete Wiki-Seite mit Informationen zu gängigen Windows-APIs und deren Aufruf.
- [Native und .NET-Interoperabilität](/cpp/dotnet/native-and-dotnet-interoperability)
- [Mono-Dokumentation zu P/Invoke](https://www.mono-project.com/docs/advanced/pinvoke/)

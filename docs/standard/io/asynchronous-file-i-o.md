---
title: Asynchrone Datei-E/A
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- streams, synchronous streams
- asynchronous I/O
- synchronous I/O
- streams, asynchronous streams
- I/O [.NET Framework], asynchronous I/O
- Stream class, synchronous I/O
- data streams, asynchronous streams
- Stream class, asynchronous I/O
- multiple I/O requests
- data streams, synchronous streams
ms.assetid: dbdd55e7-d6b9-4f9e-8abb-ab0edd4457f7
ms.openlocfilehash: 66e7d01f37a1119b9d2076a9131aa40f26d15625
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708190"
---
# <a name="asynchronous-file-io"></a>Asynchrone Datei-E/A

Mithilfe von asynchronen Vorgängen können Sie ressourcenintensive E/A-Vorgänge auszuführen, ohne den Hauptthread zu blockieren. Diese Überlegungen zur Leistung sind insbesondere in einer Windows 8.x Store-App oder Desktop-App wichtig, bei der ein zeitaufwendiger Streamingvorgang den UI-Thread blockieren kann und es dann den Anschein hat, dass Ihre App nicht funktioniert.

Ab .NET Framework 4.5 enthalten die E/A-Typen asynchrone Methoden, um asynchrone Vorgänge zu vereinfachen. Eine asynchrone Methode enthält `Async` in ihrem Namen, z. B. <xref:System.IO.Stream.ReadAsync%2A>, <xref:System.IO.Stream.WriteAsync%2A>, <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.FlushAsync%2A>, <xref:System.IO.TextReader.ReadLineAsync%2A>und <xref:System.IO.TextReader.ReadToEndAsync%2A>. Diese asynchronen Methoden werden für Streamklassen wie <xref:System.IO.Stream>, <xref:System.IO.FileStream>und <xref:System.IO.MemoryStream>sowie für Klassen implementiert, die für das Lesen und das Schreiben in Streams verwendet werden, z. B. <xref:System.IO.TextReader> und <xref:System.IO.TextWriter>.

In .NET Framework 4 und vorherigen Versionen müssen Sie Methoden wie <xref:System.IO.Stream.BeginRead%2A> und <xref:System.IO.Stream.EndRead%2A> verwenden, um asynchrone E/A-Vorgänge zu implementieren. Diese Methoden sind in .NET Framework 4.5 weiterhin verfügbar, um Legacycode zu unterstützen; allerdings können Sie mithilfe der asynchronen Methoden leichter asynchrone E/A-Vorgänge implementieren.

C# und Visual Basic verfügen jeweils über zwei Schlüsselwörter für asynchrone Programmierung:

- Der`Async` -Modifizierer (Visual Basic) bzw. `async` -Modifizierer (C#), der verwendet wird, um eine Methode zu kennzeichnen, die einen asynchronen Vorgang enthält.

- Der`Await` -Operator (Visual Basic) bzw. `await` -Operator (C#), der auf das Ergebnis einer asynchronen Methode angewendet wird.

Um asynchrone E/A-Vorgänge zu implementieren, verwenden Sie diese Schlüsselwörter in Verbindung mit den asynchronen Methoden, wie in den folgenden Beispielen gezeigt. Weitere Informationen finden Sie unter [Asynchrone Programmierung mit Async und Await (C#)](../../csharp/programming-guide/concepts/async/index.md) oder [Asynchrone Programmierung mit Async und Await (Visual Basic)](../../visual-basic/programming-guide/concepts/async/index.md).

Das folgende Beispiel zeigt, wie mithilfe von zwei <xref:System.IO.FileStream> -Objekten Dateien asynchron aus einem Verzeichnis in ein anderes kopiert werden. Beachten Sie, dass der <xref:System.Web.UI.WebControls.Button.Click> -Ereignishandler für das <xref:System.Windows.Controls.Button> -Steuerelement mit dem `async` -Modifizierer markiert wird, da er eine asynchrone Methode aufruft.

[!code-csharp[Asynchronous_File_IO_async#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Asynchronous_File_IO_async/cs/example.cs#1)]
[!code-vb[Asynchronous_File_IO_async#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Asynchronous_File_IO_async/vb/example.vb#1)]

Das folgende Beispiel ähnelt dem vorherigen, allerdings werden <xref:System.IO.StreamReader> - und <xref:System.IO.StreamWriter> -Objekte verwendet, um den Inhalt einer Textdatei asynchron zu lesen und zu schreiben.

[!code-csharp[Asynchronous_File_IO_async#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Asynchronous_File_IO_async/cs/example2.cs#2)]
[!code-vb[Asynchronous_File_IO_async#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Asynchronous_File_IO_async/vb/example2.vb#2)]

Das folgende Beispiel zeigt die CodeBehind-Datei und die XAML-Datei, die verwendet werden, um eine Datei als <xref:System.IO.Stream> in einer Windows 8.x Store-App zu öffnen und ihren Inhalt unter Verwendung einer Instanz der <xref:System.IO.StreamReader>-Klasse zu lesen. Im Beispiel werden asynchrone Methoden verwendet, um die Datei als Stream zu öffnen und ihren Inhalt zu lesen.

[!code-csharp[System.IO.WindowsRuntimeStorageExtensions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/cs/blankpage.xaml.cs#2)]
[!code-vb[System.IO.WindowsRuntimeStorageExtensions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/vb/blankpage.xaml.vb#2)]

[!code-xaml[System.IO.WindowsRuntimeStorageExtensions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/cs/blankpage.xaml#1)]

## <a name="see-also"></a>Siehe auch

- <xref:System.IO.Stream>
- [Datei- und Stream-E/A](index.md)
- [Asynchrone Programmierung mit Async und Await (C#)](../../csharp/programming-guide/concepts/async/index.md)
- [Asynchrone Programmierung mit „Async“ und „Await“ (Visual Basic)](../../visual-basic/programming-guide/concepts/async/index.md)

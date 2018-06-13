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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 270ae5a8cfa7c69c7caa0896dfe23b84db48f659
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33575517"
---
# <a name="asynchronous-file-io"></a>Asynchrone Datei-E/A
Mithilfe von asynchronen Vorgängen können Sie ressourcenintensive E/A-Vorgänge auszuführen, ohne den Hauptthread zu blockieren. Diese Überlegungen zur Leistung sind insbesondere in einer [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] -App oder [!INCLUDE[desktop_appname](../../../includes/desktop-appname-md.md)] -App wichtig, bei der ein zeitaufwendiger Streamvorgang den UI-Thread blockieren kann und es dann den Anschein hat, dass Ihre App nicht funktioniert.  
  
 Ab [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]enthalten die E/A-Typen asynchrone Methoden, um asynchrone Vorgänge zu vereinfachen. Eine asynchrone Methode enthält `Async` in ihrem Namen, z. B. <xref:System.IO.Stream.ReadAsync%2A>, <xref:System.IO.Stream.WriteAsync%2A>, <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.FlushAsync%2A>, <xref:System.IO.TextReader.ReadLineAsync%2A>und <xref:System.IO.TextReader.ReadToEndAsync%2A>. Diese asynchronen Methoden werden für Streamklassen wie <xref:System.IO.Stream>, <xref:System.IO.FileStream>und <xref:System.IO.MemoryStream>sowie für Klassen implementiert, die für das Lesen und das Schreiben in Streams verwendet werden, z. B. <xref:System.IO.TextReader> und <xref:System.IO.TextWriter>.  
  
 In .NET Framework 4 und vorherigen Versionen müssen Sie Methoden wie <xref:System.IO.Stream.BeginRead%2A> und <xref:System.IO.Stream.EndRead%2A> verwenden, um asynchrone E/A-Vorgänge zu implementieren. Diese Methoden sind weiterhin verfügbar in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] , um Legacycode zu unterstützen; allerdings können Sie mithilfe der asynchronen Methoden leichter asynchrone E/A-Vorgänge implementieren.  
  
 Ab [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]stellt Visual Studio zwei Schlüsselwörter für asynchrone Programmierung bereit:  
  
 Der`Async` -Modifizierer (Visual Basic) bzw. `async` -Modifizierer (C#), der verwendet wird, um eine Methode zu kennzeichnen, die einen asynchronen Vorgang enthält.  
  
 Der`Await` -Operator (Visual Basic) bzw. `await` -Operator (C#), der auf das Ergebnis einer asynchronen Methode angewendet wird.  
  
 Um asynchrone E/A-Vorgänge zu implementieren, verwenden Sie diese Schlüsselwörter in Verbindung mit den asynchronen Methoden, wie in den folgenden Beispielen gezeigt. Weitere Informationen finden Sie unter [Asynchrone Programmierung mit Async und Await](https://msdn.microsoft.com/library/db854f91-ccef-4035-ae4d-0911fde808c7).  
  
 Das folgende Beispiel zeigt, wie mithilfe von zwei <xref:System.IO.FileStream> -Objekten Dateien asynchron aus einem Verzeichnis in ein anderes kopiert werden. Beachten Sie, dass der <xref:System.Web.UI.WebControls.Button.Click> -Ereignishandler für das <xref:System.Windows.Controls.Button> -Steuerelement mit dem `async` -Modifizierer markiert wird, da er eine asynchrone Methode aufruft.  
  
 [!code-csharp[Asynchronous_File_IO_async#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Asynchronous_File_IO_async/cs/example.cs#1)]
 [!code-vb[Asynchronous_File_IO_async#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Asynchronous_File_IO_async/vb/example.vb#1)]  
  
 Das folgende Beispiel ähnelt dem vorherigen, allerdings werden <xref:System.IO.StreamReader> - und <xref:System.IO.StreamWriter> -Objekte verwendet, um den Inhalt einer Textdatei asynchron zu lesen und zu schreiben.  
  
 [!code-csharp[Asynchronous_File_IO_async#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Asynchronous_File_IO_async/cs/example2.cs#2)]
 [!code-vb[Asynchronous_File_IO_async#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Asynchronous_File_IO_async/vb/example2.vb#2)]  
  
 Im folgenden Beispiel werden die Code-Behind-Datei und die XAML-Datei gezeigt, mit denen eine Datei als ein <xref:System.IO.Stream> in einer App [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] geöffnet wird und der Inhalt mithilfe einer Instanz der <xref:System.IO.StreamReader> -Klasse gelesen wird. Im Beispiel werden asynchrone Methoden verwendet, um die Datei als Stream zu öffnen und ihren Inhalt zu lesen.  
  
 [!code-csharp[System.IO.WindowsRuntimeStorageExtensions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/cs/blankpage.xaml.cs#2)]
 [!code-vb[System.IO.WindowsRuntimeStorageExtensions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/vb/blankpage.xaml.vb#2)]  
  
 [!code-xaml[System.IO.WindowsRuntimeStorageExtensions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/cs/blankpage.xaml#1)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IO.Stream>  
 [Datei- und Stream-E/A](../../../docs/standard/io/index.md)  
 [Asynchrone Programmierung mit Async und Await](https://msdn.microsoft.com/library/db854f91-ccef-4035-ae4d-0911fde808c7)

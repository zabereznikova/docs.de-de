---
title: 'Vorgehensweise: Konvertieren von .NET Framework- und Windows-Runtime-Streams (nur unter Windows)'
ms.date: 01/14/2019
dev_langs:
- csharp
- vb
ms.assetid: 23a763ea-8348-4244-9f8c-a4280b870b47
ms.openlocfilehash: ee36845f19ef4a7c3923b1032ab6eb45d2f60733
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830817"
---
# <a name="how-to-convert-between-net-framework-and-windows-runtime-streams-windows-only"></a>Vorgehensweise: Konvertieren von .NET Framework- und Windows-Runtime-Streams (nur unter Windows)

.NET Framework für UWP-Apps ist ein Bestandteil der Vollversion des .NET Framework. Aufgrund der Sicherheitsanforderungen und anderer Anforderungen an UWP-Apps können Sie nicht alle .NET Framework-APIs zum Öffnen und Lesen von Dateien verwenden. Weitere Informationen finden Sie unter [.NET for UWP apps overview (Übersicht zu .NET Framework für UWP-Apps)](/previous-versions/windows/apps/br230302(v=vs.140)). Sie können die .NET Framework-APIs jedoch für andere Streambearbeitungsvorgänge verwenden. Zur Bearbeitung dieser Streams können Sie einen .NET Framework-Streamtyp wie <xref:System.IO.MemoryStream> oder <xref:System.IO.FileStream> in einen Windows-Runtime-Stream wie <xref:Windows.Storage.Streams.IInputStream>, <xref:Windows.Storage.Streams.IOutputStream> oder <xref:Windows.Storage.Streams.IRandomAccessStream> konvertieren oder umgekehrt.

Die <xref:System.IO.WindowsRuntimeStreamExtensions?displayProperty=nameWithType>-Klasse enthält Methoden, die diese Konvertierungen vereinfachen. Es gibt jedoch grundlegende Unterschiede zwischen Streams in .NET Framework und der Windows-Runtime, die sich auf die Ergebnisse der Verwendung dieser Methoden auswirken. Dies wird in den folgenden Abschnitten erläutert:

## <a name="convert-from-a-windows-runtime-to-a-net-framework-stream"></a>Konvertieren eines Windows-Runtime-Streams in einen .NET Framework-Stream
Konvertieren Sie einen Windows-Runtime-Stream mit einer der folgenden <xref:System.IO.WindowsRuntimeStreamExtensions?displayProperty=nameWithType>-Methoden in einen .NET Framework-Stream:

- <xref:System.IO.WindowsRuntimeStreamExtensions.AsStream%2A?displayProperty=nameWithType> konvertiert einen Random-Access-Stream in der Windows-Runtime in einen verwalteten Stream in .NET für UWP-Apps.
  
- <xref:System.IO.WindowsRuntimeStreamExtensions.AsStreamForWrite%2A?displayProperty=nameWithType> konvertiert einen Ausgabestream in der Windows-Runtime in einen verwalteten Stream in .NET für UWP-Apps.
  
- <xref:System.IO.WindowsRuntimeStreamExtensions.AsStreamForRead%2A?displayProperty=nameWithType> konvertiert einen Eingabestream in der Windows-Runtime in einen verwalteten Stream in .NET für UWP-Apps.

Für die Windows-Runtime gibt es Streamtypen, die nur das Lesen, nur das Schreiben oder Lesen und Schreiben unterstützen. Diese Funktionen bleiben erhalten, wenn Sie einen Windows-Runtime-Stream in einen .NET Framework-Stream konvertieren. Wenn Sie einen Windows-Runtime-Stream in einen .NET Framework-Stream bzw. zurück konvertieren, erhalten Sie darüber hinaus die ursprüngliche Windows-Runtime-Instanz zurück.

Es wird empfohlen, die Konvertierungsmethode zu verwenden, die zu den Funktionen des Windows-Runtime-Streams passt, den Sie konvertieren möchten. Da jedoch <xref:Windows.Storage.Streams.IRandomAccessStream> lesbar und schreibbar ist (es werden sowohl <xref:Windows.Storage.Streams.IOutputStream> als auch <xref:Windows.Storage.Streams.IInputStream> implementiert), ist es egal, welche Konvertierungsmethode Sie verwenden. Die Funktionen des ursprünglichen Streams bleiben stets erhalten. Wenn Sie beispielsweise <xref:System.IO.WindowsRuntimeStreamExtensions.AsStreamForRead%2A?displayProperty=nameWithType> zum Konvertieren von <xref:Windows.Storage.Streams.IRandomAccessStream> verwenden, wird der konvertierte .NET Framework-Stream nicht auf den Schreibschutz eingeschränkt. Er ist dann auch schreibbar.

## <a name="example-convert-windows-runtime-random-access-to-net-framework-stream"></a>Beispiel: Konvertieren eines Windows-Runtime-Streams mit wahlfreiem Zugriff in einen .NET Framework-Stream
Verwenden Sie die <xref:System.IO.WindowsRuntimeStreamExtensions.AsStream%2A?displayProperty=nameWithType>-Methode, um einen Windows-Runtime-Random-Access-Stream in einen .NET Framework-Stream zu konvertieren.

Im folgenden Codebeispiel werden Sie dazu aufgefordert, eine Datei auszuwählen, die anschließend mithilfe von Windows-Runtime-APIs geöffnet und in einen .NET Framework-Stream konvertiert wird. Dabei wird der Stream gelesen und als Textblock ausgegeben. Üblicherweise sollten Sie den Stream mit .NET Framework-APIs bearbeiten, bevor die Ergebnisse ausgegeben werden.

Damit dieses Beispiel ausgeführt werden kann, müssen Sie eine XAML-App für die UWP erstellen, die den Textblock `TextBlock1` und die Schaltfläche `Button1` enthält. Weisen Sie das Klickereignis für die Schaltfläche der im Beispiel gezeigten `button1_Click`-Methode zu.

  [!code-csharp[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/cs/mainpage1.xaml.cs)]
  [!code-vb[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/vb/mainpage1.xaml.vb)]

## <a name="convert-from-a-net-framework-to-a-windows-runtime-stream"></a>Konvertieren eines .NET Framework-Streams in einen Windows-Runtime-Stream
Konvertieren Sie einen .NET Framework-Stream mit einer der folgenden <xref:System.IO.WindowsRuntimeStreamExtensions?displayProperty=nameWithType>-Methoden in einen Windows-Runtime-Stream:

- <xref:System.IO.WindowsRuntimeStreamExtensions.AsInputStream%2A?displayProperty=nameWithType> konvertiert einen verwalteten Stream in .NET für UWP-Apps in einen Eingabestream in der Windows-Runtime.
  
- <xref:System.IO.WindowsRuntimeStreamExtensions.AsOutputStream%2A?displayProperty=nameWithType> konvertiert einen verwalteten Stream in .NET für UWP-Apps in einen Ausgabestream in der Windows-Runtime.
  
- Mit <xref:System.IO.WindowsRuntimeStreamExtensions.AsRandomAccessStream%2A?displayProperty=nameWithType> wird ein in .NET für UWP-Apps verwalteter Stream in einen Stream mit wahlfreiem Zugriff konvertiert, den die Windows-Runtime für Lese- und Schreibvorgänge verwenden kann.

Wenn Sie einen .NET Framework-Stream in einen Windows-Runtime-Stream konvertieren, hängen die Funktionen des konvertierten Streams vom ursprünglichen Stream ab. Wenn z. B. der ursprüngliche Stream sowohl Lese- als auch Schreibvorgänge unterstützt und Sie <xref:System.IO.WindowsRuntimeStreamExtensions.AsInputStream%2A?displayProperty=nameWithType> zum Konvertieren des Streams aufrufen, ist der zurückgegebene Typ ein `IRandomAccessStream`. Der `IRandomAccessStream` implementiert `IInputStream` und `IOutputStream` und unterstützt Lese- und Schreibvorgänge.

.NET Framework-Streams unterstützen selbst nach der Konvertierung keine Klonvorgänge. Wenn Sie einen .NET Framework-Stream in einen Windows-Runtime-Stream konvertieren und <xref:Windows.Storage.Streams.InMemoryRandomAccessStream.GetInputStreamAt%2A> oder <xref:Windows.Storage.Streams.IRandomAccessStream.GetOutputStreamAt%2A> aufrufen, wodurch <xref:Windows.Storage.Streams.RandomAccessStreamOverStream.CloneStream%2A> oder <xref:Windows.Storage.Streams.RandomAccessStreamOverStream.CloneStream%2A> direkt aufgerufen wird, wird eine Ausnahme ausgelöst.

## <a name="example-convert-net-framework-to-windows-runtime-random-access-stream"></a>Beispiel: Konvertieren eines .NET Framework-Streams in einen Windows-Runtime-Stream mit wahlfreiem Zugriff

Sie können wie im folgenden Beispiel gezeigt einen .NET Framework-Stream mithilfe der Methode <xref:System.IO.WindowsRuntimeStreamExtensions.AsRandomAccessStream%2A> in einen Windows-Runtime-Stream mit wahlfreiem Zugriff konvertieren:

> [!IMPORTANT]
> Stellen Sie sicher, dass der von Ihnen verwendete .NET Framework-Stream Suchvorgänge unterstützt, oder kopieren Sie ihn in einen Stream, der dies unterstützt. Um dies zu ermitteln, können Sie die <xref:System.IO.Stream.CanSeek%2A?displayProperty=nameWithType> -Eigenschaft verwenden.

Um dieses Beispiel auszuführen, müssen Sie eine XAML-App für die UWP erstellen, die für .NET Framework 4.5.1 konzipiert ist und einen Textblock mit dem Namen `TextBlock2` und eine Schaltfläche mit dem Namen `Button2` enthält. Weisen Sie das Klickereignis für die Schaltfläche der im Beispiel gezeigten `button2_Click`-Methode zu.

  [!code-csharp[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/cs/mainpage2.xaml.cs)]
  [!code-vb[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/vb/mainpage2.xaml.vb)]

## <a name="see-also"></a>Siehe auch

- [Schnellstart: Lesen und Schreiben von Dateien (Windows)](/previous-versions/windows/apps/hh464978(v=win.10))  
- [.NET für Windows Store-Apps – Übersicht](/previous-versions/windows/apps/br230302(v=vs.140))  
- [.NET für Windows Store-Apps – APIs](/previous-versions/br230232(v=vs.120))

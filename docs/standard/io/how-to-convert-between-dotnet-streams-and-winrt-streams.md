---
title: 'Gewusst wie: Konvertieren zwischen .NET Framework-Streams und Windows-Runtime-Streams'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 23a763ea-8348-4244-9f8c-a4280b870b47
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f67f88cd7f690e56664fa45878d1c9ac1f8a6b6b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33577560"
---
# <a name="how-to-convert-between-net-framework-streams-and-windows-runtime-streams"></a>Gewusst wie: Konvertieren zwischen .NET Framework-Streams und Windows-Runtime-Streams
.NET Framework für Windows Store-Apps ist eine Teilmenge der Vollversion von .NET Framework. Aufgrund der Sicherheitsanforderungen und anderer Anforderungen an Windows Store-Apps können Sie nicht den vollständigen Satz von .NET Framework-APIs zum Öffnen und Lesen von Dateien verwenden. Weitere Informationen finden Sie unter [.NET für Windows Store-Apps – Übersicht](http://msdn.microsoft.com/library/windows/apps/br230302.aspx). Sie können die .NET Framework-APIs jedoch für andere Streambearbeitungsvorgänge verwenden. Um diese Streams zu bearbeiten, müssen Sie möglicherweise einen .NET Framework-Streamtyp wie <xref:System.IO.MemoryStream> oder <xref:System.IO.FileStream>in einen Windows-Runtime-Stream wie [IInputStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.iinputstream.aspx), [IOutputStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.ioutputstream.aspx)oder [IRandomAccessStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.irandomaccessstream.aspx)konvertieren oder umgekehrt.  
  
 Die <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions>--> `System.IO.WindowsRuntimeStreamExtensions` -Klasse enthält Methoden, die diese Konvertierungen vereinfachen. Es gibt jedoch grundlegende Unterschiede zwischen Streams in .NET Framework und der Windows-Runtime, die sich auf die Ergebnisse der Verwendung dieser Methoden auswirken. Die Details werden in den folgenden Abschnitten beschrieben.  
  
<a name="BKMK_ConvertingfromaWindowsRuntimestreamtoaNETFrameworkstream"></a>   
## <a name="converting-from-a-windows-runtime-stream-to-a-net-framework-stream"></a>Konvertieren eines Windows-Runtime-Streams in einen .NET Framework-Stream  
 Sie können einen Windows-Runtime-Stream mit einer der folgenden <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions>--> `System.IO.WindowsRuntimeStreamExtensions` -Methoden in einen .NET Framework-Stream konvertieren:  
  
 <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions.AsStream%2A> --> `System.IO.WindowsRuntimeStreamExtensions.AsStream`  
 Konvertiert einen Random-Access-Stream in der Windows-Runtime in einen verwalteten Stream in .NET für Windows Store-Apps.  
  
 <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions.AsStreamForWrite%2A> --> `System.IO.WindowsRuntimeStreamExtensions.AsStreamForWrite`
 Konvertiert einen Ausgabestream in der Windows-Runtime in einen verwalteten Stream in .NET für Windows Store-Apps.  
  
 <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions.AsStreamForRead%2A> --> `System.IO.WindowsRuntimeStreamExtensions.AsStreamForRead`  
 Konvertiert einen Eingabestream in der Windows-Runtime in einen verwalteten Stream in .NET für Windows Store-Apps.  
  
 Die Windows-Runtime bietet Streamtypen, die Schreibschutz, Leseschutz oder Lesen und Schreiben unterstützen. Diese Funktionen werden auch beibehalten, wenn Sie einen Windows-Runtime-Stream in einen .NET Framework-Stream konvertieren. Wenn Sie einen Windows-Runtime-Stream in einen .NET Framework-Stream bzw. zurück konvertieren, erhalten Sie darüber hinaus die ursprüngliche Windows-Runtime-Instanz zurück. Es wird empfohlen, diejenige Konvertierungsmethode zu verwenden, die mit den Funktionen des Windows-Runtime-Streams übereinstimmt, den Sie konvertieren möchten. Da jedoch [IRandomAccessStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.irandomaccessstream.aspx) lesbar und schreibbar ist (es werden sowohl [IOutputStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.ioutputstream.aspx) als auch [IInputStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.iinputstream.aspx)implementiert), können Sie jede Konvertierungsmethode verwenden, und die Funktionen des ursprünglichen Streams werden beibehalten. Wenn Sie beispielsweise <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions.AsStreamForRead%2A> --> `System.IO.WindowsRuntimeStreamExtensions.AsStreamForRead` zum Konvertieren von [IRandomAccessStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.irandomaccessstream.aspx) verwenden, wird der konvertierte .NET Framework-Stream nicht auf den Schreibschutz eingeschränkt, sondern ist auch schreibbar.  
  
#### <a name="to-convert-from-a-windows-runtime-random-access-stream-to-a-net-framework-stream"></a>So konvertieren Sie einen Windows-Runtime-Random-Access-Stream in einen .NET Framework-Stream  
  
-   Verwenden Sie die <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions.AsStream%2A> --> `System.IO.WindowsRuntimeStreamExtensions.AsStream` -Methode.  
  
     Das folgende Codebeispiel zeigt, wie der Benutzer aufgefordert wird, eine Datei auszuwählen, sie mit Windows-Runtime-APIs zu öffnen und sie dann in einen .NET Framework-Stream zu konvertieren, der gelesen und in einen Textblock ausgegeben wird. In diesem Szenario würden Sie den Stream in der Regel mit .NET Framework-APIs bearbeiten, bevor Sie die Ergebnisse ausgeben.  
  
     Um dieses Beispiel auszuführen, müssen Sie eine Windows Store XAML-App erstellen, die den Textblock `TextBlock1` und die Schaltfläche  `Button1`enthält. Das Click-Ereignis für die Schaltfläche muss der im Beispiel gezeigten `button1_Click` -Methode zugeordnet sein.  
  
     [!code-csharp[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/cs/mainpage.xaml.cs#imports)]
     [!code-vb[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/vb/mainpage.xaml.vb#imports)]  
    [!code-csharp[System.IO.WindowsRuntimeStreamExtensionsEx#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/cs/mainpage.xaml.cs#1)]
    [!code-vb[System.IO.WindowsRuntimeStreamExtensionsEx#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/vb/mainpage.xaml.vb#1)]  
  
<a name="BKMK_ConvertingfromaNETFrameworkstreamtoaWindowsRuntimestream"></a>   
## <a name="converting-from-a-net-framework-stream-to-a-windows-runtime-stream"></a>Konvertieren eines .NET Framework-Streams in einen Windows-Runtime-Stream  
 Sie können einen .NET Framework-Stream mit einer der folgenden <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions>--> `System.IO.WindowsRuntimeStreamExtensions` -Methoden in einen Windows-Runtime-Stream konvertieren:  
  
 <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions.AsInputStream%2A> --> `System.IO.WindowsRuntimeStreamExtensions.AsInputStream`  
 Konvertiert einen verwalteten Stream in .NET für Windows Store-Apps in einen Eingabestream in der Windows-Runtime.  
  
<!--zz <xref:System.IO.WindowsRuntimeStreamExtensions.AsOutputStream%2A>  --> `System.IO.WindowsRuntimeStreamExtensions.AsOutputStream`
 Konvertiert einen verwalteten Stream in .NET für Windows Store-Apps in einen Ausgabestream in der Windows-Runtime.  
  
 [AsRandomAccessStream](../../../docs/standard/cross-platform/windowsruntimestreamextensions-asrandomaccessstream-method.md)  
 Konvertiert einen verwalteten Stream in .NET für Windows Store-Apps in einen Random-Access-Stream, der zum Lesen oder Schreiben in die Windows-Runtime verwendet werden kann.  
  
 Wenn Sie einen .NET Framework-Stream in einen Windows-Runtime-Stream konvertieren, hängen die Funktionen des konvertierten Streams vom ursprünglichen Stream ab. Wenn z. B. der ursprüngliche Stream sowohl Lesen als auch Schreiben unterstützt und Sie <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions.AsInputStream%2A> --> `System.IO.WindowsRuntimeStreamExtensions.AsInputStream` zum Konvertieren des Streams aufrufen, ist der zurückgegebene Typ ein `IRandomAccessStream`, der  `IInputStream` und `IOutputStream`implementiert und Lesen und Schreiben unterstützt.  
  
 .NET Framework-Streams unterstützen selbst nach der Konvertierung kein Klonen. Wenn Sie also einen .NET Framework-Stream in einen Windows-Runtime-Stream konvertieren und [GetInputStreamAt](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.inmemoryrandomaccessstream.getinputstreamat.aspx) oder [GetOutputStreamAt](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.irandomaccessstream.getoutputstreamat.aspx)aufrufen, die [CloneStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.randomaccessstreamoverstream.clonestream.aspx) aufrufen, oder [CloneStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.randomaccessstreamoverstream.clonestream.aspx) direkt aufrufen, tritt eine Ausnahme auf.  
  
#### <a name="to-convert-from-a-net-framework-stream-to-a-windows-runtime-random-access-stream"></a>So konvertieren Sie einen .NET Framework-Stream in einen Windows-Runtime-Random-Access-Stream  
  
-   Verwenden Sie die [AsRandomAccessStream](../../../docs/standard/cross-platform/windowsruntimestreamextensions-asrandomaccessstream-method.md) -Methode, wie im folgenden Beispiel gezeigt.  
  
    > [!IMPORTANT]
    >  Stellen Sie sicher, dass der von Ihnen verwendete .NET Framework-Stream Suchvorgänge unterstützt, oder kopieren Sie ihn in einen Stream, der dies unterstützt. Um dies zu ermitteln, können Sie die <xref:System.IO.Stream.CanSeek%2A?displayProperty=nameWithType>-Eigenschaft verwenden.  
  
     Um dieses Beispiel auszuführen, müssen Sie eine Windows Store XAML-App erstellen, die auf .NET Framework 4.5.1 abzielt und einen Textblock mit dem Namen `TextBlock2` und eine Schaltfläche mit dem Namen `Button2`enthält. Das Click-Ereignis für die Schaltfläche muss der in diesem Beispiel gezeigten `button2_Click` -Methode zugeordnet sein.  
  
     [!code-csharp[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/cs/mainpage.xaml.cs#imports)]
     [!code-vb[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/vb/mainpage.xaml.vb#imports)]  
    [!code-csharp[System.IO.WindowsRuntimeStreamExtensionsEx#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/cs/mainpage.xaml.cs#2)]
    [!code-vb[System.IO.WindowsRuntimeStreamExtensionsEx#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/vb/mainpage.xaml.vb#2)]  
  
## <a name="see-also"></a>Siehe auch  
 [Schnellstart: Lesen und Schreiben einer Datei (Windows)](https://msdn.microsoft.com/library/windows/apps/hh464978.aspx)  
 [.NET für Windows Store-Apps – Übersicht](http://msdn.microsoft.com/library/windows/apps/br230302.aspx)  
 [.NET für Windows Store-Apps – unterstützte APIs](https://msdn.microsoft.com/library/windows/apps/br230232.aspx)

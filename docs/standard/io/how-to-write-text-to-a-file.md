---
title: "Gewusst wie: Schreiben von Text in eine Datei | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Schreiben von Text in Dateien"
  - "E/A [.NET Framework], Schreiben von Text in Dateien"
  - "Streams, Schreiben von Text in Dateien"
  - "Datenströme, Schreiben von Text in Dateien"
ms.assetid: 060cbe06-2adf-4337-9e7b-961a5c840208
caps.latest.revision: 29
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 29
---
# Gewusst wie: Schreiben von Text in eine Datei
Dieses Thema veranschaulicht verschiedene Arten, wie Sie Text in eine Datei für .NET Framework\-Anwendungen oder [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]\-Apps schreiben können. Die folgenden Klassen und Methoden werden in der Regel zum Schreiben von Text in eine Datei verwendet:  
  
-   <xref:System.IO.StreamWriter> enthält Methoden zum synchronen \(<xref:System.IO.StreamWriter.Write%2A> oder <xref:System.IO.TextWriter.WriteLine%2A>\) oder asynchronen \(<xref:System.IO.StreamWriter.WriteAsync%2A> und <xref:System.IO.StreamWriter.WriteLineAsync%2A>\) Schreiben in eine Datei.  
  
-   <xref:System.IO.File> wird für .NET Framework\-Anwendungen verwendet. Sie stellt statische Methoden zum Schreiben von Text in eine Datei \(<xref:System.IO.File.WriteAllLines%2A> und <xref:System.IO.File.WriteAllText%2A>\) oder zum Anfügen von Text an eine Datei \(<xref:System.IO.File.AppendAllLines%2A>, <xref:System.IO.File.AppendAllText%2A> oder <xref:System.IO.File.AppendText%2A>\) bereit.  
  
-   [FileIO](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.aspx) wird mit [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]\-Apps verwendet. Sie enthält asynchrone Methoden zum Schreiben von Text in eine Datei \([WriteLinesAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.writelinesasync.aspx) oder [WriteTextAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.writetextasync.aspx)\) bzw. zum Anfügen von Text an eine Datei \([AppendLinesAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.appendlinesasync.aspx) oder [AppendTextAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.appendtextasync.aspx)\).  
  
 Die Beispiele sind einfach gehalten, um nicht von der ausgeführten Aufgabe abzulenken. Aus diesem Grund wird in den Beispielen, falls überhaupt, nur eine geringe Fehlerüberprüfung und Ausnahmebehandlung durchgeführt. Reale Anwendungen umfassen im Allgemeinen eine robustere Fehlerüberprüfung und Ausnahmebehandlung.  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie Text mithilfe der <xref:System.IO.StreamWriter>\-Klasse zeilenweise in eine neue Datei schreiben. Die neue Textdatei wird im Ordner "Eigene Dateien" des Benutzers gespeichert. Da das <xref:System.IO.StreamWriter>\-Objekt in einer `using`\-Anweisung deklariert und instanziiert wird, wird die <xref:System.IO.StreamWriter.Dispose%2A>\-Methode zum automatischen Leeren und Schließen des Datenstroms aufgerufen.  
  
 <!-- TODO: review snippet reference [!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#writeline)]  -->
 <!-- TODO: review snippet reference [!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#writeline)]  -->  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie Text mithilfe der <xref:System.IO.StreamWriter>\-Klasse an eine vorhandene Datei angefügt wird. Dabei wird die Textdatei aus dem vorherigen Beispiel verwendet.  
  
 <!-- TODO: review snippet reference [!code-csharp[Conceptual.BasicIO.TextFiles#AppendText](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#appendtext)]  -->
 <!-- TODO: review snippet reference [!code-vb[Conceptual.BasicIO.TextFiles#AppendText](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#appendtext)]  -->  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie Sie Text mithilfe der <xref:System.IO.StreamWriter>\-Klasse asynchron in eine neue Datei schreiben. Zum Aufrufen der <xref:System.IO.StreamWriter.WriteAsync%2A>\-Methode muss sich der Methodenaufruf innerhalb einer `async`\-Methode befinden. Die neue Textdatei wird im Ordner "Eigene Dateien" des Benutzers gespeichert.  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#WriteAsync](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#writeasync)]
 [!code-vb[Conceptual.BasicIO.TextFiles#WriteAsync](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#writeasync)]  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie Sie mithilfe der <xref:System.IO.File>\-Klasse Text in eine neue Datei schreiben und neue Textzeilen an diese Datei anfügen. Durch die Methoden <xref:System.IO.File.WriteAllText%2A> und <xref:System.IO.File.AppendAllLines%2A> wird die Datei automatisch geöffnet und geschlossen. Wenn der für die <xref:System.IO.File.WriteAllText%2A>\-Methode angegebene Pfad bereits vorhanden ist, wird die Datei überschrieben.  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#WriteFile](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#writefile)]
 [!code-vb[Conceptual.BasicIO.TextFiles#WriteFile](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#writefile)]  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie Benutzereingaben asynchron in eine Textdatei in einer [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]\-App geschrieben werden. Aus Sicherheitsgründen muss in der Regel ein [FileOpenPicker](http://msdn.microsoft.com/library/windows/apps/windows.storage.pickers.fileopenpicker.aspx)\-Steuerelement verwendet werden, wenn eine Datei von einer [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]\-App geöffnet wird. In diesem Beispiel wird `FileOpenPicker` nach Textdateien gefiltert.  
  
```xaml  
<Page  
    x:Class="OpenFileWindowsStore.MainPage"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    xmlns:local="using:OpenFileWindowsStore"  
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"  
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
    mc:Ignorable="d">  
  
    <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">  
        <Button Content="save text to a file" HorizontalAlignment="Left" Margin="103,417,0,0" VerticalAlignment="Top"   
                Width="329" Height="86" FontSize="35" Click="Button_Click"/>  
        <TextBox Name="UserInputTextBox"  FontSize="18" HorizontalAlignment="Left" Margin="106,146,0,0"   
                 TextWrapping="Wrap" Text="Write some text here, and select a file to write it to." VerticalAlignment="Top"   
                 Height="201" Width="558" AcceptsReturn="True"/>  
        <TextBlock Name="StatusTextBox" HorizontalAlignment="Left" Margin="106,570,0,147" TextWrapping="Wrap" Text="Status:"   
                   VerticalAlignment="Center" Height="51" Width="1074" FontSize="18" />  
    </Grid>  
</Page>  
```  
  
 [!code-csharp[OpenFileWindowsStore#Code](../../../samples/snippets/csharp/VS_Snippets_CLR/openfilewindowsstore/cs/mainpage.xaml.cs#code)]
 [!code-vb[OpenFileWindowsStore#Code](../../../samples/snippets/visualbasic/VS_Snippets_CLR/openfilewindowsstore/vb/mainpage.xaml.vb#code)]  
  
## Siehe auch  
 <xref:System.IO.StreamWriter>   
 <xref:System.IO.File.CreateText%2A?displayProperty=fullName>   
 [Gewusst wie: Auflisten von Verzeichnissen und Dateien](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)   
 [Gewusst wie: Lesen und Schreiben einer neu erstellten Datendatei](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)   
 [Gewusst wie: Öffnen und Anfügen an eine Protokolldatei](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)   
 [Gewusst wie: Lesen aus einer Textdatei](../../../docs/standard/io/how-to-read-text-from-a-file.md)   
 [Datei\- und Stream\-E\/A](../../../docs/standard/io/index.md)
---
title: "Gewusst wie: Lesen und Schreiben einer neu erstellten Datendatei | Microsoft Docs"
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
  - "BinaryReader-Klasse, Beispiele"
  - "BinaryWriter-Klasse, Beispiele"
  - "E/A [.NET Framework], Lesen von Daten"
  - "E/A [.NET Framework], Schreiben von Daten"
  - "Streams, Lesen und Schreiben von Daten"
ms.assetid: e209d949-31e8-44ea-8e38-87f9093f3093
caps.latest.revision: 16
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: Lesen und Schreiben einer neu erstellten Datendatei
Die <xref:System.IO.BinaryWriter>\-Klasse und die <xref:System.IO.BinaryReader?displayProperty=fullName>\-Klasse werden eher zum Schreiben und Lesen von Daten als von Zeichenfolgen verwendet.  Im folgenden Beispiel wird gezeigt, wie Daten in einen neuen, leeren Dateistream mit dem Namen `Test.data` geschrieben und daraus gelesen werden.  Nach dem Erstellen der Datendatei im aktuellen Verzeichnis werden die zugeordneten <xref:System.IO.BinaryWriter>\- und <xref:System.IO.BinaryReader>\-Objekte erstellt. Das <xref:System.IO.BinaryWriter>\-Objekt wird zum Schreiben der ganzen Zahlen 0 bis 10 in `Test.data` verwendet, wodurch der Dateizeiger am Ende der Datei verbleibt.  Nach dem Zurücksetzen des Dateizeigers auf seinen Ursprung liest das <xref:System.IO.BinaryReader>\-Objekt den angegebenen Inhalt aus.  
  
## Beispiel  
 [!code-cpp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CPP/source6.cpp#7)]
 [!code-csharp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CS/source6.cs#7)]
 [!code-vb[System.IO.BinaryReaderWriter#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/VB/source6.vb#7)]  
  
## Robuste Programmierung  
 Wenn sich `Test.data` bereits im aktuellen Verzeichnis befindet, wird eine <xref:System.IO.IOException>\-Ausnahme ausgelöst.  Verwenden Sie die Dateimodusoption <xref:System.IO.FileMode?displayProperty=fullName>, wenn Sie den Dateistream initialisieren, um immer eine neue Datei zu erstellen, ohne eine Ausnahme auszulösen.  
  
## Siehe auch  
 <xref:System.IO.BinaryReader>   
 <xref:System.IO.BinaryWriter>   
 <xref:System.IO.FileStream>   
 <xref:System.IO.FileStream.Seek%2A?displayProperty=fullName>   
 <xref:System.IO.SeekOrigin>   
 [Gewusst wie: Auflisten von Verzeichnissen und Dateien](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)   
 [Gewusst wie: Öffnen und Anfügen an eine Protokolldatei](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)   
 [Gewusst wie: Lesen aus einer Textdatei](../../../docs/standard/io/how-to-read-text-from-a-file.md)   
 [Gewusst wie: Schreiben von Text in eine Datei](../../../docs/standard/io/how-to-write-text-to-a-file.md)   
 [Gewusst wie: Lesen von Zeichen aus einer Zeichenfolge](../../../docs/standard/io/how-to-read-characters-from-a-string.md)   
 [Gewusst wie: Schreiben von Zeichen in eine Zeichenfolge](../../../docs/standard/io/how-to-write-characters-to-a-string.md)   
 [Datei\- und Stream\-E\/A](../../../docs/standard/io/index.md)
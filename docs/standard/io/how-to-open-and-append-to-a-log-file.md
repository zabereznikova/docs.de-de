---
title: "Gewusst wie: &#214;ffnen und Anf&#252;gen an eine Protokolldatei | Microsoft Docs"
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
  - "Protokolldateien, Öffnen"
  - "Streams, Öffnen von und Anhängen an Protokolldateien"
  - "Protokolldateien, Anhängen an"
  - "E/A [.NET Framework], Protokolldateien"
ms.assetid: 74423362-1721-49cb-aa0a-e04005f72a06
caps.latest.revision: 15
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: &#214;ffnen und Anf&#252;gen an eine Protokolldatei
<xref:System.IO.StreamWriter> und <xref:System.IO.StreamReader> schreiben Zeichen in Streams bzw. lesen Zeichen daraus.  Im folgenden Codebeispiel wird die Datei `log.txt` für die Eingabe geöffnet oder, falls nicht vorhanden, erstellt. Anschließend werden Informationen an das Ende der Datei angefügt.  Danach wird der Inhalt der Datei für die Anzeige in die Standardausgabe geschrieben.  In einer Alternative zu diesem Beispiel können die Informationen als einzelne Zeichenfolge oder einzelnes Zeichenfolgenarray gespeichert werden, und mithilfe der <xref:System.IO.File.WriteAllText%2A>\-Methode oder der <xref:System.IO.File.WriteAllLines%2A>\-Methode kann dann die gleiche Funktionalität erzielt werden.  
  
> [!NOTE]
>  Visual Basic\-Benutzer können zum Erstellen von oder Schreiben in Protokolldateien die von der <xref:Microsoft.VisualBasic.Logging.Log>\-Klasse oder der <xref:Microsoft.VisualBasic.FileIO.FileSystem>\-Klasse bereitgestellten Methoden und Eigenschaften verwenden.  
  
## Beispiel  
 [!code-csharp[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source2.cs#2)]
 [!code-vb[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source2.vb#2)]  
  
## Siehe auch  
 <xref:System.IO.StreamWriter>   
 <xref:System.IO.StreamReader>   
 <xref:System.IO.File.AppendText%2A?displayProperty=fullName>   
 <xref:System.IO.File.OpenText%2A?displayProperty=fullName>   
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=fullName>   
 [Gewusst wie: Auflisten von Verzeichnissen und Dateien](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)   
 [Gewusst wie: Lesen und Schreiben einer neu erstellten Datendatei](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)   
 [Gewusst wie: Lesen aus einer Textdatei](../../../docs/standard/io/how-to-read-text-from-a-file.md)   
 [Gewusst wie: Schreiben von Text in eine Datei](../../../docs/standard/io/how-to-write-text-to-a-file.md)   
 [Gewusst wie: Lesen von Zeichen aus einer Zeichenfolge](../../../docs/standard/io/how-to-read-characters-from-a-string.md)   
 [Gewusst wie: Schreiben von Zeichen in eine Zeichenfolge](../../../docs/standard/io/how-to-write-characters-to-a-string.md)   
 [Datei\- und Stream\-E\/A](../../../docs/standard/io/index.md)
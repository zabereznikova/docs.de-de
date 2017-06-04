---
title: "Gewusst wie: Schreiben von Zeichen in eine Zeichenfolge | Microsoft Docs"
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
  - "Datenströme, Schreiben von Zeichen in eine Zeichenfolge"
  - "Schreiben von Zeichen in Zeichenfolgen"
  - "Streams, Schreiben von Zeichen in Zeichenfolgen"
  - "E/A [.NET Framework], Schreiben von Zeichen in Zeichenfolgen"
ms.assetid: 1222cbeb-0760-44bf-9888-914a2a37174b
caps.latest.revision: 17
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 17
---
# Gewusst wie: Schreiben von Zeichen in eine Zeichenfolge
Die folgenden Codebeispiele schreiben Zeichen synchron und asynchron aus einem Zeichenarray in eine Zeichenfolge.  
  
## Beispiel  
 Im folgenden Beispiel wird 5 Zeichen synchron aus einem Array einer Zeichenfolge.  
  
 [!code-csharp[Conceptual.StringBuilder#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/example2.cs#9)]
 [!code-vb[Conceptual.StringBuilder#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/example2.vb#9)]  
  
## Beispiel  
 Im folgenden Beispiel werden alle Zeichen asynchron von einem Steuerelement <xref:System.Windows.Controls.TextBox> und speichert sie in ein Array.  Anschließend schreibt asynchron jeden Buchstaben oder Leerzeichen in einer eigenen Zeile, die von ein Zeilenumbruchzeichen auf ein <xref:System.Windows.Controls.TextBlock>\-Steuerelement folgen.  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source2.cs#2)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source2.vb#2)]  
  
## Siehe auch  
 <xref:System.IO.StringWriter>   
 <xref:System.IO.StringWriter.Write%2A?displayProperty=fullName>   
 <xref:System.Text.StringBuilder>   
 [Datei\- und Stream\-E\/A](../../../docs/standard/io/index.md)   
 [Asynchrone Datei\-E\/A](../../../docs/standard/io/asynchrone-datei-e-a.md)   
 [Gewusst wie: Auflisten von Verzeichnissen und Dateien](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)   
 [Gewusst wie: Lesen und Schreiben einer neu erstellten Datendatei](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)   
 [Gewusst wie: Öffnen und Anfügen an eine Protokolldatei](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)   
 [Gewusst wie: Lesen aus einer Textdatei](../../../docs/standard/io/how-to-read-text-from-a-file.md)   
 [Gewusst wie: Schreiben von Text in eine Datei](../../../docs/standard/io/how-to-write-text-to-a-file.md)   
 [Gewusst wie: Lesen von Zeichen aus einer Zeichenfolge](../../../docs/standard/io/how-to-read-characters-from-a-string.md)
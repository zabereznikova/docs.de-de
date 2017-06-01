---
title: "Gewusst wie: Lesen von Zeichen aus einer Zeichenfolge | Microsoft Docs"
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
  - "Lesen von Zeichen aus Zeichenfolgen"
  - "Datenströme, Lesen von Zeichen aus einer Zeichenfolge"
  - "E/A [.NET Framework], Lesen von Zeichen aus Zeichenfolgen"
  - "Lesen von Daten, Zeichenfolgen"
  - "Ströme, Lesen von Zeichen aus einer Zeichenfolge"
ms.assetid: 27ea5e52-6db8-42d8-980a-50bcfc7fd270
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Lesen von Zeichen aus einer Zeichenfolge
Die folgenden Codebeispiele zeigen, wie Zeichen synchron und asynchron von einer Zeichenfolge.  
  
## Beispiel  
 In diesem Beispiel liest 13 Zeichen synchron aus einer Zeichenfolge, speichert sie in einem Array und zeigt diese Zeichen an.  Es liest dann die verbleibenden Zeichen in der Zeichenfolge, speichert sie im Array beginnend am Element 6. und zeigt den Inhalt des Arrays an.  
  
 [!code-cpp[Conceptual.StringReader#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.stringreader/cpp/source.cpp#1)]
 [!code-csharp[Conceptual.StringReader#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source.cs#1)]
 [!code-vb[Conceptual.StringReader#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source.vb#1)]  
  
## Beispiel  
 Im folgenden Beispiel werden alle Zeichen asynchron von einem Steuerelement <xref:System.Windows.Controls.TextBox> und speichert sie in ein Array.  Anschließend schreibt asynchron jeden Buchstaben oder Leerzeichen in einer eigenen Zeile, die von ein Zeilenumbruchzeichen auf ein <xref:System.Windows.Controls.TextBlock>\-Steuerelement folgen.  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source2.cs#2)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source2.vb#2)]  
  
## Siehe auch  
 <xref:System.IO.StringReader>   
 <xref:System.IO.StringReader.Read%2A?displayProperty=fullName>   
 [Asynchrone Datei\-E\/A](../../../docs/standard/io/asynchrone-datei-e-a.md)   
 [NIB: How to: Create a Directory Listing](http://msdn.microsoft.com/de-de/4d2772b1-b991-4532-a8a6-6ef733277e69)   
 [Gewusst wie: Lesen und Schreiben einer neu erstellten Datendatei](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)   
 [Gewusst wie: Öffnen und Anfügen an eine Protokolldatei](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)   
 [Gewusst wie: Lesen aus einer Textdatei](../../../docs/standard/io/how-to-read-text-from-a-file.md)   
 [Gewusst wie: Schreiben von Text in eine Datei](../../../docs/standard/io/how-to-write-text-to-a-file.md)   
 [Gewusst wie: Schreiben von Zeichen in eine Zeichenfolge](../../../docs/standard/io/how-to-write-characters-to-a-string.md)   
 [Datei\- und Stream\-E\/A](../../../docs/standard/io/index.md)
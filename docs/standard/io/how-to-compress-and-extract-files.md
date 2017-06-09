---
title: "Gewusst wie: Komprimieren und Extrahieren von Dateien | Microsoft Docs"
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
  - "E/A [.NET Framework], Komprimierung"
  - "Komprimierung"
  - "Komprimieren von Dateien"
ms.assetid: e9876165-3c60-4c84-a272-513e47acf579
caps.latest.revision: 19
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 19
---
# Gewusst wie: Komprimieren und Extrahieren von Dateien
Der <xref:System.IO.Compression>\-Namespace enthält die folgenden Typen für das Komprimieren und Dekomprimieren von Dateien und Streams.  Sie können diese Typen auch verwenden, um den Inhalt einer komprimierten Datei zu lesen und zu ändern:  
  
-   <xref:System.IO.Compression.ZipFile>  
  
-   <xref:System.IO.Compression.ZipArchive>  
  
-   <xref:System.IO.Compression.ZipArchiveEntry>  
  
-   <xref:System.IO.Compression.DeflateStream>  
  
-   <xref:System.IO.Compression.GZipStream>  
  
 Die folgenden Beispiele zeigen einige der Aufgaben, die Sie beim Arbeiten, ausführen können mit komprimierten Dateien.  
  
## Beispiel  
 Dieses Beispiel zeigt, wie eine komprimierte Datei erstellt und extrahiert, die eine Dateinamenerweiterung .zip hat, indem die <xref:System.IO.Compression.ZipFile>\-Klasse verwendet.  Es komprimiert der Inhalt eines Ordner in eine neue ZIP\-Datei und dann Auszüge, die zu einem neuen Ordner entsprechen.  Um die <xref:System.IO.Compression.ZipFile>\-Klasse zu verwenden, müssen Sie die `System.IO.Compression.FileSystem` \- Assembly im Projekt verweisen.  
  
 [!code-csharp[System.IO.Compression.ZipFile#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.zipfile/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipFile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.zipfile/vb/program1.vb#1)]  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie durch den Inhalt einer vorhandenen ZIP\-Datei und der Auszugdateien durchläuft, die eine Erweiterung .txt\- haben.  Es verwendet die <xref:System.IO.Compression.ZipArchive>\-Klasse, um auf eine vorhandene ZIP\-Datei zuzugreifen und die <xref:System.IO.Compression.ZipArchiveEntry>\-Klasse, um die einzelnen Einträge in der komprimierten Datei zu überprüfen.  Es wird eine Erweiterungsmethode \(<xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A>\) für das <xref:System.IO.Compression.ZipArchiveEntry>\-Objekt.  Die Erweiterungsmethode ist in der <xref:System.IO.Compression.ZipFileExtensions?displayProperty=fullName>\-Klasse verfügbar.  Um die <xref:System.IO.Compression.ZipFileExtensions>\-Klasse zu verwenden, müssen Sie die `System.IO.Compression.FileSystem` \- Assembly im Projekt verweisen.  
  
 [!code-csharp[System.IO.Compression.ZipArchive#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchive/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchive#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchive/vb/program1.vb#1)]  
  
## Beispiel  
 Im folgenden Beispiel verwendet die <xref:System.IO.Compression.ZipArchive>\-Klasse, um auf eine vorhandene ZIP\-Datei zuzugreifen und fügt eine neue Datei der komprimierten Datei hinzu.  Die neue Datei ruft komprimiertes ab, wenn Sie die vorhandene ZIP\-Datei hinzufügen.  
  
 [!code-csharp[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/cs/program1.cs#1)]
 [!code-vb[System.IO.Compression.ZipArchiveMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.compression.ziparchivemode/vb/program1.vb#1)]  
  
## Beispiel  
 Sie können die <xref:System.IO.Compression.GZipStream> und <xref:System.IO.Compression.DeflateStream>\-Klassen auch verwenden, um Daten komprimieren und dekomprimieren.  Sie verwenden den gleichen Komprimierungsalgorithmus.  Komprimierte <xref:System.IO.Compression.GZipStream>\-Objekte, die in eine Datei geschrieben werden, die eine Erweiterung von .gz verfügt, können dekomprimiert werden, indem viele allgemeine Tools sowie zu den Methoden, die von <xref:System.IO.Compression.GZipStream> bereitgestellt werden.  In diesem Beispiel wird veranschaulicht, wie ein Dateiverzeichnis mit der <xref:System.IO.Compression.GZipStream>\-Klasse komprimiert und dekomprimiert wird.  
  
 [!code-csharp[IO.Compression.GZip1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.Compression.GZip1/CS/gziptest.cs#1)]
 [!code-vb[IO.Compression.GZip1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.Compression.GZip1/VB/gziptest.vb#1)]  
  
## Siehe auch  
 <xref:System.IO.Compression.ZipArchive>   
 <xref:System.IO.Compression.ZipFile>   
 <xref:System.IO.Compression.ZipArchiveEntry>   
 <xref:System.IO.Compression.DeflateStream>   
 <xref:System.IO.Compression.GZipStream>   
 [Datei\- und Stream\-E\/A](../../../docs/standard/io/index.md)
---
title: "Erstellen von Streams | Microsoft Docs"
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
  - "Streams, Basisstreams"
  - "E/A [.NET Framework], Erstellen von Streams"
  - "Stream-Klasse, Erstellen von Streams"
  - "Basisstreams"
  - "Streams, Sicherungsspeicher"
ms.assetid: da761658-a535-4f26-a452-b30df47f73d5
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 10
---
# Erstellen von Streams
Ein Sicherungsspeicher ist ein Speichermedium, z. B. eine Festplatte oder ein Hauptspeicher.  Jeder einzelne Sicherungsspeicher implementiert seinen eigenen Stream als eine Implementierung der <xref:System.IO.Stream>\-Klasse.  Jeder Streamtyp schreibt Bytes in seinen jeweiligen Sicherungsspeicher bzw. liest sie daraus.  Streams, die eine Verbindung zu Sicherungsspeichern herstellen, werden Basisstreams genannt.  Basisstreams verfügen über Konstruktoren, die mit den erforderlichen Parametern ausgestattet sind, um eine Verbindung zum Sicherungsspeicher herzustellen.  Die Konstruktoren von <xref:System.IO.FileStream> geben z. B. einen Pfadparameter an, der u. a. die Art der gemeinsamen Nutzung einer Datei durch Prozesse festlegt.  
  
 Der Entwurf der <xref:System.IO>\-Klassen ermöglicht einen vereinfachten Aufbau von Streams.  Basisstreams können mit einem oder mehreren Pass\-Through\-Streams verknüpft werden, welche die gewünschte Funktionalität bereitstellen.  Ein Lese\- oder Schreibprogramm kann an das Ende der Kette angehängt werden, wodurch das Lesen und Schreiben der bevorzugten Typen vereinfacht wird.  
  
 Im folgenden Codebeispiel wird ein **FileStream** anhand der vorhandenen Datei `MyFile.txt` erstellt, um die Datei `MyFile.txt` zu puffern. \(Beachten Sie, dass **FileStreams** standardmäßig gepuffert werden.\) Anschließend wird ein <xref:System.IO.StreamReader> erstellt. Dieser liest Zeichen aus dem **FileStream**, der wiederum dem **StreamReader** als dessen Konstruktorargument übergeben wird.  <xref:System.IO.StreamReader.ReadLine%2A> setzt den Lesevorgang so lange fort, bis <xref:System.IO.StreamReader.Peek%2A> keine weiteren Zeichen mehr findet.  
  
 [!code-cpp[System.IO.StreamReader#20](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source2.cpp#20)]
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
 Im folgenden Codebeispiel wird ein **FileStream** anhand der vorhandenen Datei `MyFile.txt` erstellt, um die Datei `MyFile.txt` zu puffern. \(Beachten Sie, dass **FileStreams** standardmäßig gepuffert werden.\) Anschließend wird ein **BinaryReader** erstellt. Dieser liest Bytes aus dem **FileStream**, der wiederum dem **BinaryReader** als dessen Konstruktorargument übergeben wird.  <xref:System.IO.BinaryReader.ReadByte%2A> setzt den Lesevorgang so lange fort, bis <xref:System.IO.BinaryReader.PeekChar%2A> keine weiteren Bytes mehr findet.  
  
 [!code-cpp[System.IO.StreamReader#21](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.StreamReader/CPP/source3.cpp#21)]
 [!code-csharp[System.IO.StreamReader#21](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source3.cs#21)]
 [!code-vb[System.IO.StreamReader#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source3.vb#21)]  
  
## Siehe auch  
 <xref:System.IO.StreamReader>   
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=fullName>   
 <xref:System.IO.StreamReader.Peek%2A?displayProperty=fullName>   
 <xref:System.IO.FileStream>   
 <xref:System.IO.BinaryReader>   
 <xref:System.IO.BinaryReader.ReadByte%2A?displayProperty=fullName>   
 <xref:System.IO.BinaryReader.PeekChar%2A?displayProperty=fullName>
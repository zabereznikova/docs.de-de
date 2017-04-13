---
title: "Gewusst wie: Lesen bzw. Schreiben von Dateien im isolierten Speicher | Microsoft Docs"
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
  - "Datenspeicherung mit dem isolierten Speicher, Lesen und Schreiben in Dateien"
  - "Datenspeicher, Lesen und Schreiben in Dateien"
  - "Dateien, Isolierter Speicher"
  - "Isolierter Speicher, Lesen und Schreiben in Dateien"
  - "Lesen von Daten"
  - "Lesen von Dateien im Speicher"
  - "Speicher, Lesen und Schreiben in Dateien"
  - "Speichern von Daten mit dem isolierten Speicher, Lesen und Schreiben in Dateien"
  - "Schreiben in Dateien im Speicher"
ms.assetid: f977ebdc-1b55-475a-bc3d-3376470b08ae
caps.latest.revision: 15
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Lesen bzw. Schreiben von Dateien im isolierten Speicher
So von oder Schreiben, einer Datei in einem isolierten Speicher lesen, ein <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>\-Objekt mit einem Streamreader \(<xref:System.IO.StreamReader>\-Objekt\) verwenden oder Writer \(<xref:System.IO.StreamWriter>\-Objekt\) übertragen.  
  
## Beispiel  
 Im folgenden Codebeispiel wird ein isolierter Speicher und überprüft, ob eine Datei mit dem Namen TestStore.txt, im Speicher vorhanden ist.  Wenn es nicht vorhanden ist, erstellt es die Datei und schreibt "Hello Isolated Storage" in die Datei.  Wenn TestStore.txt vorhanden ist, wird im Beispielcode aus der Datei.  
  
 [!code-csharp[Conceptual.IsolatedStorage#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source5.cs#5)]
 [!code-vb[Conceptual.IsolatedStorage#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source5.vb#5)]  
  
## Siehe auch  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>   
 <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>   
 <xref:System.IO.FileMode?displayProperty=fullName>   
 <xref:System.IO.FileAccess?displayProperty=fullName>   
 <xref:System.IO.StreamReader?displayProperty=fullName>   
 <xref:System.IO.StreamWriter?displayProperty=fullName>   
 [Datei\- und Stream\-E\/A](../../../docs/standard/io/index.md)   
 [Isolierte Speicherung](../../../docs/standard/io/isolated-storage.md)
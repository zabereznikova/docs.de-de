---
title: "Gewusst wie: Erstellen von Dateien und Verzeichnissen in isoliertem Speicher | Microsoft Docs"
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
  - "Verzeichnisse [.NET Framework], Isolierter Speicher"
  - "Dateien [.NET Framework], Isolierter Speicher"
  - "Isolierter Speicher, Erstellen von Dateien und Verzeichnissen"
  - "Datenspeicher, Erstellen von Dateien und Verzeichnissen"
  - "Datenspeicherung mit dem isolierten Speicher, Erstellen von Dateien und Verzeichnissen"
  - "Speicher, Erstellen von Dateien und Verzeichnissen"
  - "Speichern von Daten mit dem isolierten Speicher, Erstellen von Dateien und Verzeichnissen"
ms.assetid: 2ca4d2a4-809b-4f00-bc08-bf4a64d3a5c3
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Erstellen von Dateien und Verzeichnissen in isoliertem Speicher
Nachdem Sie einen isolierten Speicher erhalten haben, können Sie Verzeichnisse und Dateien zum Speichern von Daten erstellt.  Datei\- und Verzeichnisnamen werden im Speicher in Bezug auf den Stamm des virtuellen Dateisystems angegeben.  
  
 Um ein Verzeichnis zu erstellen, verwenden Sie die Instanzmethode <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=fullName>.  Wenn Sie ein Unterverzeichnis eines Verzeichnisses angeben, das nicht vorhanden ist, werden beide Verzeichnisse erstellt.  Wenn Sie ein Verzeichnis an, das bereits vorhanden ist, kehrt die Methode zurück, ohne ein Verzeichnis, und es wird keine Ausnahme ausgelöst.  Wenn Sie jedoch einen Verzeichnisnamen angeben, der ungültige Zeichen enthält, wird eine <xref:System.IO.IsolatedStorage.IsolatedStorageException> Ausnahme ausgelöst.  
  
 Um eine Datei zu erstellen, verwenden Sie die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=fullName>\-Methode.  
  
 Im Windows\-Betriebssystem können isolierte Speicherdatei\- und Verzeichnisnamen keine Groß\-\/Kleinschreibung berücksichtigt.  Das bedeutet, dass, wenn Sie eine Datei namens `ThisFile.txt` erstellen, und erstellen Sie dann eine andere Datei, die dem Namen `THISFILE.TXT`, wird nur eine Datei erstellt.  Die ursprüngliche Groß\- bzw. Kleinschreibung des Dateinamens wird zum Zweck der Anzeige beibehalten.  
  
## Beispiel  
 Im folgenden Codebeispiel wird das Erstellen von Dateien und Verzeichnissen in einem isolierten Speicher veranschaulicht.  
  
 [!code-csharp[Conceptual.IsolatedStorage#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source.cs#1)]
 [!code-vb[Conceptual.IsolatedStorage#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source.vb#1)]  
  
## Siehe auch  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>   
 <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>   
 [Isolierte Speicherung](../../../docs/standard/io/isolated-storage.md)
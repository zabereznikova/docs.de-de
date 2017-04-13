---
title: "Gewusst wie: L&#246;schen von Dateien und Verzeichnissen in isoliertem Speicher | Microsoft Docs"
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
  - "Datenspeicherung mit dem isolierten Speicher, Löschen von Dateien und Verzeichnissen"
  - "Verzeichnisse [.NET Framework], Isolierter Speicher"
  - "Dateien [.NET Framework], Isolierter Speicher"
  - "Isolierter Speicher, Löschen von Dateien und Verzeichnissen"
  - "Datenspeicher, Löschen von Dateien und Verzeichnissen"
  - "Speicher, Erstellen von Dateien und Verzeichnissen"
  - "Löschen von Dateien in der isolierten Speicherdatei"
  - "Speichern von Daten mit dem isolierten Speicher, Löschen von Dateien und Verzeichnissen"
  - "Löschen von Verzeichnissen in der isolierten Speicherdatei"
ms.assetid: 8fcc0dea-435b-4d40-ba4d-ba056265c202
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: L&#246;schen von Dateien und Verzeichnissen in isoliertem Speicher
Sie können Verzeichnisse und Dateien in einer Datei der isolierten Speicherung löschen.  Innerhalb eines Speichers sind Datei\- und Verzeichnisnamen Betriebssystemabhängiges element und wie werden relativ zum Stamm des virtuellen Dateisystems angegeben.  Sie können nicht unter Windows\-Betriebssystemen die Groß\-\/Kleinschreibung beachtet.  
  
 Die <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=fullName>\-Klasse stellt zwei Methoden zum Löschen von Verzeichnissen und Dateien: <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> und <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A>.  Eine <xref:System.IO.IsolatedStorage.IsolatedStorageException> \- Ausnahme wird ausgelöst, wenn Sie versuchen, eine Datei oder ein Verzeichnis zu löschen, das nicht vorhanden ist.  Wenn Sie ein Platzhalterzeichen im Namen hinzufügen, löst <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> eine <xref:System.IO.IsolatedStorage.IsolatedStorageException> Ausnahme und <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A> löst eine <xref:System.ArgumentException> Ausnahme aus.  
  
 Die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A>\-Methode schlägt fehl, wenn das Verzeichnis Dateien oder Unterverzeichnisse enthält.  Sie können die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> und <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A>\-Methoden verwenden, um die vorhandenen Dateien und Verzeichnisse abzurufen.  Weitere Informationen über das Suchen im virtuellen Dateisystem eines Speichers, finden Sie unter [Gewusst wie: Suchen von vorhandenen Dateien und Verzeichnissen im isolierten Speicher](../../../docs/standard/io/how-to-find-existing-files-and-directories-in-isolated-storage.md).  
  
## Beispiel  
 Im folgenden Codebeispiel werden diverse Verzeichnisse und Dateien erst erstellt und dann gelöscht.  
  
 [!code-cpp[Conceptual.IsolatedStorage#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.IsolatedStorage#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source4.cs#4)]
 [!code-vb[Conceptual.IsolatedStorage#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source4.vb#4)]  
  
## Siehe auch  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=fullName>   
 [Isolierte Speicherung](../../../docs/standard/io/isolated-storage.md)
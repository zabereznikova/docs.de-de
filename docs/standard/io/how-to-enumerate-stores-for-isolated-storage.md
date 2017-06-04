---
title: "Gewusst wie: Auflisten von Speichern f&#252;r isolierten Speicher | Microsoft Docs"
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
  - "Auflisten von Speichern"
  - "Datenspeicherung mit isoliertem Speicher, Auflisten von Speichern"
  - "Speichern von Daten mit isolierten Speicher, Auflisten von Speichern"
  - "Speicher, auflisten"
  - "Isolierter Speicher, Auflisten von Speichern"
  - "Datenspeicher, auflisten"
ms.assetid: 0fcf279a-f241-48f0-8034-2e3d331f1fcb
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Auflisten von Speichern f&#252;r isolierten Speicher
Sie können alle isolierten Speicher für den aktuellen Benutzer auflisten, indem Sie die statische <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A?displayProperty=fullName>\-Methode.  Diese Methode setzt einen <xref:System.IO.IsolatedStorage.IsolatedStorageScope>\-Wert und gibt ein <xref:System.IO.IsolatedStorage.IsolatedStorageFile> \- Enumerator zurück.  Zum Auflisten, müssen Sie die <xref:System.Security.Permissions.IsolatedStorageFilePermission> \- Berechtigung die den <xref:System.Security.Permissions.IsolatedStorageContainment>\-Wert angibt.  Wenn Sie die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A>\-Methode mit dem <xref:System.IO.IsolatedStorage.IsolatedStorageScope>\-Wert aufrufen, wird ein Array <xref:System.IO.IsolatedStorage.IsolatedStorageFile>\-Objekte zurück, die für den aktuellen Benutzer definiert werden.  
  
## Beispiel  
 Im folgenden Codebeispiel wird ein Speicher aufgerufen, der nach Benutzer und Assembly isoliert ist, mehrere Dateien erstellt und die Dateien abruft, indem die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A>\-Methode.  
  
 [!code-csharp[Conceptual.IsolatedStorage#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source2.cs#2)]
 [!code-vb[Conceptual.IsolatedStorage#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source2.vb#2)]  
  
## Siehe auch  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>   
 [Isolierte Speicherung](../../../docs/standard/io/isolated-storage.md)
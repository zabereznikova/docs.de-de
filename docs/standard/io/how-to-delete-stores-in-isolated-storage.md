---
title: "Gewusst wie: L&#246;schen von Speichern im isolierten Speicher | Microsoft Docs"
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
  - "Speicher, Löschen"
  - "Datenspeicher, Löschen"
  - "Löschen von Speichern"
  - "Entfernen von Speichern"
  - "Isolierter Speicher, Löschen von Speichern"
  - "Speichern von Daten mit dem isolierten Speicher, Löschen von Speichern"
  - "Datenspeicherung mit dem isolierten Speicher, Löschen von Speichern"
ms.assetid: 3947e333-5af6-4601-b2f1-24d4d6129cf3
caps.latest.revision: 14
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: L&#246;schen von Speichern im isolierten Speicher
Die <xref:System.IO.IsolatedStorage.IsolatedStorageFile>\-Klasse stellt zwei Methoden zum Löschen von isolierten Speicherdateien zur Verfügung:  
  
-   Die Instanzmethode <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove> akzeptiert keine Argumente und löscht den Speicher, von dem sie aufgerufen wird. Für diesen Vorgang sind keine Berechtigungen erforderlich. Jeder Code, der auf den Speicher zugreifen kann, kann beliebige oder sogar alle Daten darin löschen.  
  
-   Die statische Methode <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%28System.IO.IsolatedStorage.IsolatedStorageScope%29> akzeptiert den Enumerationswert <xref:System.IO.IsolatedStorage.IsolatedStorageScope> als Argument und löscht alle Speicher für den Benutzer, der den Code ausführt. Für diesen Vorgang ist die <xref:System.Security.Permissions.IsolatedStorageFilePermission>\-Berechtigung für den <xref:System.Security.Permissions.IsolatedStorageContainment>\-Wert erforderlich.  
  
## Beispiel  
 Im folgenden Codebeispiel wird die Verwendung der statischen und der Instanzmethode <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%2A> veranschaulicht. Die Klasse ruft zwei Speicher ab; einer ist für Benutzer und Assembly und der andere für Benutzer, Domäne und Assembly isoliert. Der für Benutzer, Domäne und Assembly isolierte Speicher wird dann durch Aufrufen der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove>\-Methode der isolierten Speicherdatei `isoStore1` gelöscht. Anschließend werden alle verbleibenden Speicher für den Benutzer durch Aufrufen der statischen Methode <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%28System.IO.IsolatedStorage.IsolatedStorageScope%29> gelöscht.  
  
 [!code-cpp[Conceptual.IsolatedStorage#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source3.cpp#3)]
 [!code-csharp[Conceptual.IsolatedStorage#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source3.cs#3)]
 [!code-vb[Conceptual.IsolatedStorage#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source3.vb#3)]  
  
## Siehe auch  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>   
 [Isolierte Speicherung](../../../docs/standard/io/isolated-storage.md)
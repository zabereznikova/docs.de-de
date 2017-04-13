---
title: "Gewusst wie: Suchen von vorhandenen Dateien und Verzeichnissen im isolierten Speicher | Microsoft Docs"
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
  - "Speicher, Suchen von Dateien und Verzeichnissen"
  - "Suchen von Dateien in der isolierten Speicherdatei"
  - "Verzeichnisse [.NET Framework], Isolierter Speicher"
  - "Isolierter Speicher, Suchen von Dateien und Verzeichnissen"
  - "Datenspeicherung mit dem isolierten Speicher, Suchen von Dateien und Verzeichnissen"
  - "Dateien [.NET Framework], Isolierter Speicher"
  - "Datenspeicher, Suchen von Dateien und Verzeichnissen"
  - "Suchen von Verzeichnissen in der isolierten Speicherdatei"
  - "Speichern von Daten mit dem isolierten Speicher, Suchen von Dateien und Verzeichnissen"
ms.assetid: eb28458a-6161-4e7a-9ada-30ef93761b5c
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Suchen von vorhandenen Dateien und Verzeichnissen im isolierten Speicher
Um für ein Verzeichnis im isolierten Speicher zu suchen, verwenden Sie die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A?displayProperty=fullName>\-Methode.  Diese Methode akzeptiert eine Zeichenfolge, die ein Suchmuster darstellt.  Sie können auch Platzhalterzeichen des EinzelZeichens \(?\) und des MULTIZeichens \(\*\) im Suchmuster verwenden, jedoch müssen die Platzhalterzeichen im abschließenden Teil des Namens vorkommen.  Beispielsweise ist `directory1/*ect*` eine gültige Suchzeichenfolge, `*ect*/directory2` ist jedoch nicht.  
  
 Um nach einer Datei suchen, verwenden Sie die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A?displayProperty=fullName>\-Methode.  Die Einschränkung für Platzhalterzeichen in Suchzeichenfolgen, die auch auf <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> bezieht, tritt bei <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> auf.  
  
 Keine dieser Methoden ist rekursiv; die <xref:System.IO.IsolatedStorage.IsolatedStorageFile>\-Klasse stellt keine Methoden zum Auflisten aller Verzeichnisse und Dateien in Ihrem Speicher.  Allerdings werden rekursive Methoden im folgenden Codebeispiel gezeigt.  
  
## Beispiel  
 Im folgenden Codebeispiel wird das Erstellen von Dateien und Verzeichnissen in einem isolierten Speicher veranschaulicht.  Zunächst wird ein Speicher, der für Benutzer isoliert, Domäne und Assembly in die Variable `isoStore` abgerufen und angezeigt.  Die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A>\-Methode wird verwendet, um verschiedene Verzeichnisse zu installieren, und der <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream.%23ctor%28System.String%2CSystem.IO.FileMode%2CSystem.IO.IsolatedStorage.IsolatedStorageFile%29> konstruktor werden einige Dateien in diesen Verzeichnissen.  Der Code durchläuft dann die Ergebnisse der `GetAllDirectories`\-Methode.  Diese Methode verwendet <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A>, um alle Verzeichnisnamen im aktuellen Verzeichnis zu suchen.  Diese Namen werden in einem Array gespeichert, und ruft sich `GetAllDirectories` auf und übergibt jedes Verzeichnis, das dies gefunden hat.  Daher werden alle Verzeichnisnamen in einem Array zurückgegeben.  Anschließend wird durch den Code die `GetAllFiles`\-Methode aufgerufen.  Diese Methode ruft `GetAllDirectories`, um die Namen aller Verzeichnisse auf und es dann jedes Verzeichnis nach Dateien, mithilfe der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A>\-Methode.  Das Ergebnis wird zur Darstellung in einem Array zurückgegeben.  
  
 [!code-cpp[Conceptual.IsolatedStorage#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source8.cpp#9)]
 [!code-csharp[Conceptual.IsolatedStorage#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source8.cs#9)]
 [!code-vb[Conceptual.IsolatedStorage#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source8.vb#9)]  
  
## Siehe auch  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>   
 [Isolierte Speicherung](../../../docs/standard/io/isolated-storage.md)
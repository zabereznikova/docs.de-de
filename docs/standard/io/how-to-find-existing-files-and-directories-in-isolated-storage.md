---
title: 'Gewusst wie: Suchen von vorhandenen Dateien und Verzeichnissen im isolierten Speicher'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- stores, finding files and directories
- locating files in isolated storage file
- directories [.NET Framework], isolated storage
- isolated storage, finding files and directories
- data storage using isolated storage, finding files and directories
- files [.NET Framework], isolated storage
- data stores, finding files and directories
- locating directories in isolated storage file
- storing data using isolated storage, finding files and directories
ms.assetid: eb28458a-6161-4e7a-9ada-30ef93761b5c
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 656c390358b6f6a671cf3ef11ea7be75f897d21c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-find-existing-files-and-directories-in-isolated-storage"></a>Gewusst wie: Suchen von vorhandenen Dateien und Verzeichnissen im isolierten Speicher
Um ein Verzeichnis im isolierten Speicher zu suchen, verwenden die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A?displayProperty=nameWithType> Methode. Diese Methode akzeptiert eine Zeichenfolge, die einem Suchmuster darstellt. Sie können einzelne Zeichen (?) und mehrere Zeichen (*) verwenden Platzhalterzeichen in das Suchmuster, aber die Platzhalterzeichen müssen in den letzten Teil des Namens angezeigt werden. Beispielsweise `directory1/*ect*` ist eine gültige Suchzeichenfolge aber `*ect*/directory2` nicht.  
  
 Um nach einer Datei zu suchen, verwenden die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A?displayProperty=nameWithType> Methode. Die Einschränkung für die Platzhalterzeichen in Suchzeichenfolgen, die für gilt <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> gilt auch für <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A>.  
  
 Keines dieser Methoden ist rekursiv; die <xref:System.IO.IsolatedStorage.IsolatedStorageFile> Klasse stellt keine Methoden für das Auflisten aller Verzeichnisse oder Dateien in Ihrem Speicher bereit. Allerdings werden rekursive Methoden im folgenden Codebeispiel wird angezeigt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie Dateien und Verzeichnissen in einem isolierten Speicher zu erstellen. Zunächst ein, die für Benutzer, Domäne und Assembly isolierten Speicher abgerufen und platziert Sie der `isoStore` Variable. Die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A> Methode wird verwendet, um ein paar andere Verzeichnisse einzurichten und die <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream.%23ctor%28System.String%2CSystem.IO.FileMode%2CSystem.IO.IsolatedStorage.IsolatedStorageFile%29> Konstruktor einige Dateien in diese Verzeichnisse erstellt. Der Code durchläuft dann die Ergebnisse der `GetAllDirectories` Methode. Diese Methode verwendet <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> zum Namen der Verzeichnisse im aktuellen Verzeichnis zu suchen. Diese Namen werden in einem Array gespeichert und dann `GetAllDirectories` selbst aufruft, übergibt jedes gefundenen Verzeichnis. Daher werden alle Verzeichnisnamen in einem Array zurückgegeben. Als Nächstes ruft der Code die `GetAllFiles` Methode. Diese Methode ruft `GetAllDirectories` so ermitteln Sie die Namen aller Verzeichnisse, und klicken Sie dann prüft jedes Verzeichnis für Dateien mithilfe der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> Methode. Das Ergebnis wird in einem Array für die Anzeige zurückgegeben.  
  
 [!code-cpp[Conceptual.IsolatedStorage#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source8.cpp#9)]
 [!code-csharp[Conceptual.IsolatedStorage#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source8.cs#9)]
 [!code-vb[Conceptual.IsolatedStorage#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source8.vb#9)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 [Isolierter Speicher](../../../docs/standard/io/isolated-storage.md)

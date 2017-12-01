---
title: "Gewusst wie: Löschen von Dateien und Verzeichnissen in isoliertem Speicher"
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
- data storage using isolated storage, deleting files and directories
- directories [.NET Framework], isolated storage
- files [.NET Framework], isolated storage
- isolated storage, deleting files and directories
- data stores, deleting files and directories
- stores, creating files and directories
- deleting files within isolated stage file
- storing data using isolated storage, deleting files and directories
- deleting directories within isolated stage file
ms.assetid: 8fcc0dea-435b-4d40-ba4d-ba056265c202
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 971f27cd25cbe4be3ca3fad6283ab32d4f6db0ac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-delete-files-and-directories-in-isolated-storage"></a>Gewusst wie: Löschen von Dateien und Verzeichnissen in isoliertem Speicher
Sie können Verzeichnisse und Dateien in eine isolierte Speicherdatei löschen. In einem Speicher Datei- und Verzeichnisnamen sind abhängig vom Betriebssystem und sind relativ zum Stamm des virtuellen Dateisystems angegeben. Sie sind nicht auf Windows-Betriebssystemen Groß-/Kleinschreibung.  
  
 Die <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType> -Klasse stellt zwei Methoden zum Löschen von Verzeichnissen und Dateien: <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> und <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A>. Ein <xref:System.IO.IsolatedStorage.IsolatedStorageException> Ausnahme wird ausgelöst, wenn Sie versuchen, löschen eine Datei oder ein Verzeichnis, das nicht existiert. Wenn Sie ein Platzhalterzeichen in den Namen aufnehmen <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> löst ein <xref:System.IO.IsolatedStorage.IsolatedStorageException> Ausnahme und <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A> löst eine <xref:System.ArgumentException> Ausnahme.  
  
 Die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> Methode schlägt fehl, wenn das Verzeichnis Dateien oder Unterverzeichnisse enthält. Sie können die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> und <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> Methoden, um die vorhandenen Dateien und Verzeichnisse abzurufen. Weitere Informationen zum Suchen nach virtuellen Dateisystem eines Speichers finden Sie unter [wie: Suchen von vorhandenen Dateien und Verzeichnissen in isoliertem Speicher](../../../docs/standard/io/how-to-find-existing-files-and-directories-in-isolated-storage.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird erstellt und löscht dann mehrere Verzeichnisse und Dateien.  
  
 [!code-cpp[Conceptual.IsolatedStorage#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.IsolatedStorage#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source4.cs#4)]
 [!code-vb[Conceptual.IsolatedStorage#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source4.vb#4)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType>  
 [Isolierter Speicher](../../../docs/standard/io/isolated-storage.md)

---
title: 'Gewusst wie: Löschen von Dateien und Verzeichnissen in isoliertem Speicher'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data storage using isolated storage, deleting files and directories
- directories [.NET], isolated storage
- files [.NET], isolated storage
- isolated storage, deleting files and directories
- data stores, deleting files and directories
- stores, creating files and directories
- deleting files within isolated stage file
- storing data using isolated storage, deleting files and directories
- deleting directories within isolated stage file
ms.assetid: 8fcc0dea-435b-4d40-ba4d-ba056265c202
ms.openlocfilehash: 7797f319ca3b143bac6a4e68eaf820e966f1560e
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2020
ms.locfileid: "93187943"
---
# <a name="how-to-delete-files-and-directories-in-isolated-storage"></a>Gewusst wie: Löschen von Dateien und Verzeichnissen in isoliertem Speicher
Sie können Verzeichnisse und Dateien in einer isolierten Speicherdatei löschen. In einem Speicher sind Datei- und Verzeichnisnamen abhängig und werden relativ zum Stamm des virtuellen Dateisystems angegeben. In Windows-Betriebssystemen wird bei ihnen nicht zwischen Groß- und Kleinschreibung unterschieden.  
  
 Die <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType>-Klasse stellt zwei Methoden zum Löschen von Verzeichnissen und Dateien bereit: <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> und <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A>. Eine <xref:System.IO.IsolatedStorage.IsolatedStorageException>-Ausnahme wird ausgelöst, wenn Sie versuchen, Dateien oder Verzeichnisse zu löschen, die nicht existieren. Wenn Sie ein Platzhalterzeichen in den Namen aufnehmen, löst <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> eine <xref:System.IO.IsolatedStorage.IsolatedStorageException>-Ausnahme aus, und <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A> eine <xref:System.ArgumentException>-Ausnahme.  
  
 Bei der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A>-Methode tritt ein Fehler auf, wenn das Verzeichnis Dateien oder Unterverzeichnisse enthält. Mit der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A>- und <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A>-Methode können Sie vorhandene Dateien und Verzeichnisse abrufen. Weitere Informationen zum Durchsuchen des virtuellen Dateisystems eines Speichers finden Sie unter [Gewusst wie: Suchen von vorhandenen Dateien und Verzeichnissen im isolierten Speicher](how-to-find-existing-files-and-directories-in-isolated-storage.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel werden mehrere Verzeichnisse und Dateien erstellt und dann gelöscht.  
  
 [!code-cpp[Conceptual.IsolatedStorage#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.IsolatedStorage#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source4.cs#4)]
 [!code-vb[Conceptual.IsolatedStorage#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source4.vb#4)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType>
- [Isolierter Speicher](isolated-storage.md)

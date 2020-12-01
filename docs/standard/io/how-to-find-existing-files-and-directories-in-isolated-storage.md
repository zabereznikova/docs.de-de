---
title: 'Gewusst wie: Suchen von vorhandenen Dateien und Verzeichnissen im isolierten Speicher'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- stores, finding files and directories
- locating files in isolated storage file
- directories [.NET], isolated storage
- isolated storage, finding files and directories
- data storage using isolated storage, finding files and directories
- files [.NET], isolated storage
- data stores, finding files and directories
- locating directories in isolated storage file
- storing data using isolated storage, finding files and directories
ms.assetid: eb28458a-6161-4e7a-9ada-30ef93761b5c
ms.openlocfilehash: 43685a6ecb92510ad8d80c472a1c774d46cbb5f7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734633"
---
# <a name="how-to-find-existing-files-and-directories-in-isolated-storage"></a>Gewusst wie: Suchen von vorhandenen Dateien und Verzeichnissen im isolierten Speicher

Um ein Verzeichnis im isolierten Speicher zu suchen, verwenden Sie die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A?displayProperty=nameWithType>-Methode. Diese Methode akzeptiert eine Zeichenfolge, die ein Suchmuster darstellt. Sie können Platzhalterzeichen für einzelne Zeichen (?) und mehrere Zeichen (\*) im Suchmuster verwenden, aber die Platzhalterzeichen müssen im letzten Teil des Namens angezeigt werden. Beispielsweise ist `directory1/*ect*` eine gültige Suchzeichenfolge, `*ect*/directory2` aber nicht.  
  
 Um eine Datei zu suchen, verwenden Sie die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A?displayProperty=nameWithType>-Methode. Die für <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> geltende Einschränkung für Platzhalterzeichen in Suchzeichenfolgen gilt auch für <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A>.  
  
 Keine dieser Methoden ist rekursiv; die <xref:System.IO.IsolatedStorage.IsolatedStorageFile>-Klasse stellt keine Methoden für das Auflisten aller Verzeichnisse oder Dateien in Ihrem Speicher bereit. Allerdings werden rekursive Methoden im folgenden Codebeispiel gezeigt.  
  
## <a name="example"></a>Beispiel  

 Das folgende Codebeispiel zeigt das Erstellen von Dateien und Verzeichnissen in einem isolierten Speicher. Zunächst wird ein für Benutzer, Domäne und Assembly isolierter Speicher abgerufen und in der `isoStore`-Variablen platziert. Mit der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A>-Methode werden ein paar andere Verzeichnisse eingerichtet, und der <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream.%23ctor%28System.String%2CSystem.IO.FileMode%2CSystem.IO.IsolatedStorage.IsolatedStorageFile%29>-Konstruktor erstellt einige Dateien in diesen Verzeichnissen. Der Code durchläuft dann die Ergebnisse der `GetAllDirectories`-Methode. Diese Methode sucht mit <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> alle Verzeichnisnamen im aktuellen Verzeichnis. Diese Namen werden in einem Array gespeichert, und dann ruft `GetAllDirectories` sich selbst auf und übergibt jedes gefundene Verzeichnis. Als Ergebnis werden alle Verzeichnisnamen in einem Array zurückgegeben. Als Nächstes ruft der Code die `GetAllFiles`-Methode auf. Diese Methode ruft `GetAllDirectories` auf, um die Namen aller Verzeichnisse zu ermitteln, und prüft dann jedes Verzeichnis mithilfe der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A>-Methode auf Dateien. Das Ergebnis wird in einem Array für die Anzeige zurückgegeben.  
  
 [!code-cpp[Conceptual.IsolatedStorage#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source8.cpp#9)]
 [!code-csharp[Conceptual.IsolatedStorage#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source8.cs#9)]
 [!code-vb[Conceptual.IsolatedStorage#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source8.vb#9)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- [Isolierter Speicher](isolated-storage.md)

---
title: 'Vorgehensweise: Erstellen von Dateien und Verzeichnissen in isoliertem Speicher'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- directories [.NET Framework], isolated storage
- files [.NET Framework], isolated storage
- isolated storage, creating files and directories
- data stores, creating files and directories
- data storage using isolated storage, creating files and directories
- stores, creating files and directories
- storing data using isolated storage, creating files and directories
ms.assetid: 2ca4d2a4-809b-4f00-bc08-bf4a64d3a5c3
ms.openlocfilehash: d5e086e77ab6309fa0757ef32b620e0fdbc1f627
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413039"
---
# <a name="how-to-create-files-and-directories-in-isolated-storage"></a>Vorgehensweise: Erstellen von Dateien und Verzeichnissen in isoliertem Speicher
Nachdem Sie einen isolierten Speicher abgerufen haben, können Sie Verzeichnisse und Dateien zum Speichern von Daten erstellen. In einem Speicher sind Datei- und Verzeichnisnamen relativ zum Stamm des virtuellen Dateisystems angegeben.  
  
 Um ein Verzeichnis zu erstellen, verwenden Sie die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=nameWithType>-Instanzmethode. Wenn Sie ein Unterverzeichnis eines nicht vorhandenen Verzeichnisses angeben, werden beide Verzeichnisse erstellt. Wenn Sie ein bereits vorhandenes Verzeichnis angeben, erfolgt die Rückgabe durch die Methode, ohne dass ein Verzeichnis erstellt wird, und es wird keine Ausnahme ausgelöst. Wenn Sie jedoch einen Verzeichnisnamen angeben, der ungültige Zeichen enthält, wird eine <xref:System.IO.IsolatedStorage.IsolatedStorageException>-Ausnahme ausgelöst.  
  
 Um eine Datei zu erstellen, verwenden Sie die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=nameWithType>-Methode.  
  
 Im Windows-Betriebssystem wird bei Namen von Dateien und Verzeichnissen im isolierten Speicher nicht zwischen Groß- und Kleinschreibung unterschieden. Wenn Sie also eine Datei mit dem Namen `ThisFile.txt` und eine andere Datei mit dem Namen `THISFILE.TXT` erstellen, wird nur eine Datei erstellt. Die ursprüngliche Groß-/Kleinschreibung des Dateinamens wird zu Anzeigezwecken beibehalten.  

 Beim Erstellen isolierter Speicherdateien wird eine <xref:System.IO.IsolatedStorage.IsolatedStorageException> ausgelöst, wenn der Pfad ein Verzeichnis enthält, das nicht vorhanden ist.
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel zeigt das Erstellen von Dateien und Verzeichnissen in einem isolierten Speicher.  
  
 [!code-csharp[Conceptual.IsolatedStorage#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source.cs#1)]
 [!code-vb[Conceptual.IsolatedStorage#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>
- [Isolierter Speicher](isolated-storage.md)

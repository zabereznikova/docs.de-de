---
title: 'Vorgehensweise: Kopieren, Löschen und Verschieben von Dateien und Ordnern – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
ms.openlocfilehash: 498f266597032a4c35dbc8783994095b5c08fc3d
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53240241"
---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a>Vorgehensweise: Kopieren, Löschen und Verschieben von Dateien und Ordnern (C#-Programmierhandbuch)
Die folgenden Beispiele veranschaulichen, wie Dateien und Ordner mithilfe der Klassen <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType> und <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> aus dem Namespace <xref:System.IO?displayProperty=nameWithType> synchron kopiert, verschoben und gelöscht werden können. Diese Beispiele stellen keine Statusanzeige oder irgendeine andere Benutzeroberfläche bereit. Informationen zum Bereitstellen eines standardmäßigen Statusdialogfelds finden Sie unter [Vorgehensweise: Bereitstellen eines Statusdialogfelds für Dateivorgänge](how-to-provide-a-progress-dialog-box-for-file-operations.md).  
  
 Verwenden Sie <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> zum Bereitstellen von Ereignissen, mit denen Sie bei Vorgängen auf mehreren Dateien den Status berechnen können. Eine weitere Möglichkeit ist die Verwendung eines Plattformaufrufs, um die relevanten dateibezogenen Methoden in der Windows-Shell aufzurufen. Weitere Informationen dazu, wie Sie diese Dateivorgänge asynchron ausführen, finden Sie unter [Asynchrone Datei-E/A](../../../standard/io/asynchronous-file-i-o.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie Dateien und Verzeichnisse kopieren.  
  
 [!code-csharp[csFilesandFolders#7](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_1.cs)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie Dateien und Verzeichnisse verschieben.  
  
 [!code-csharp[csFilesandFolders#8](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_2.cs)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie Dateien und Verzeichnisse löschen.  
  
 [!code-csharp[csFilesandFolders#9](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_3.cs)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IO?displayProperty=nameWithType>  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [Das Dateisystem und die Registrierung (C#-Programmierhandbuch)](index.md)  
- [Vorgehensweise: Bereitstellen eines Statusdialogfelds für Dateioperationen](how-to-provide-a-progress-dialog-box-for-file-operations.md)  
- [Datei- und Stream-E/A](../../../standard/io/index.md)  
- [Allgemeine E/A-Aufgaben](../../../standard/io/common-i-o-tasks.md)

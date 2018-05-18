---
title: 'Gewusst wie: Kopieren, Löschen und Verschieben von Dateien und Ordnern (C#-Programmierhandbuch)'
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
ms.openlocfilehash: 5debb2cbfa5ada45447e280169b9fe66d1a15a53
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a>Gewusst wie: Kopieren, Löschen und Verschieben von Dateien und Ordnern (C#-Programmierhandbuch)
Die folgenden Beispiele veranschaulichen, wie Dateien und Ordner mithilfe der Klassen <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType> und <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> aus dem Namespace <xref:System.IO?displayProperty=nameWithType> synchron kopiert, verschoben und gelöscht werden können. Diese Beispiele stellen keine Statusanzeige oder irgendeine andere Benutzeroberfläche bereit. Informationen zur Bereitstellung eines standardmäßigen Fortschrittsdialogfelds finden Sie unter [Vorgehensweise: Bereitstellen eines Statusdialogfelds für Dateioperationen](how-to-provide-a-progress-dialog-box-for-file-operations.md).  
  
 Verwenden Sie <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> zum Bereitstellen von Ereignissen, mit denen Sie bei Vorgängen auf mehreren Dateien den Status berechnen können. Eine weitere Möglichkeit ist die Verwendung eines Plattformaufrufs, um die relevanten dateibezogenen Methoden in der Windows-Shell aufzurufen. Weitere Informationen dazu, wie Sie diese Dateivorgänge asynchron ausführen, finden Sie unter [Asynchrone Datei-E/A](https://msdn.microsoft.com/library/kztecsys).  
  
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
 <xref:System.IO?displayProperty=nameWithType>  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Das Dateisystem und die Registrierung (C#-Programmierhandbuch)](index.md)  
 [Gewusst wie: Bereitstellen eines Statusdialogfelds für Dateioperationen](how-to-provide-a-progress-dialog-box-for-file-operations.md)  
 [Datei- und Stream-E/A](https://msdn.microsoft.com/library/k3352a4t)  
 [Allgemeine E/A-Aufgaben](https://msdn.microsoft.com/library/ms404278)

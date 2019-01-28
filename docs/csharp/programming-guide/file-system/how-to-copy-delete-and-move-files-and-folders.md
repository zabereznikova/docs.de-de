---
title: 'Vorgehensweise: Kopieren, Löschen und Verschieben von Dateien und Ordnern – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
ms.openlocfilehash: 3e6c08050186642ceec4e2301524919379e12aaa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527704"
---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a><span data-ttu-id="6cbf5-102">Vorgehensweise: Kopieren, Löschen und Verschieben von Dateien und Ordnern (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="6cbf5-102">How to: Copy, Delete, and Move Files and Folders (C# Programming Guide)</span></span>
<span data-ttu-id="6cbf5-103">Die folgenden Beispiele veranschaulichen, wie Dateien und Ordner mithilfe der Klassen <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType> und <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> aus dem Namespace <xref:System.IO?displayProperty=nameWithType> synchron kopiert, verschoben und gelöscht werden können.</span><span class="sxs-lookup"><span data-stu-id="6cbf5-103">The following examples show how to copy, move, and delete files and folders in a synchronous manner by using the <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType>, and <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> classes from the <xref:System.IO?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="6cbf5-104">Diese Beispiele stellen keine Statusanzeige oder irgendeine andere Benutzeroberfläche bereit.</span><span class="sxs-lookup"><span data-stu-id="6cbf5-104">These examples do not provide a progress bar or any other user interface.</span></span> <span data-ttu-id="6cbf5-105">Informationen zum Bereitstellen eines standardmäßigen Statusdialogfelds finden Sie unter [Vorgehensweise: Bereitstellen eines Statusdialogfelds für Dateivorgänge](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span><span class="sxs-lookup"><span data-stu-id="6cbf5-105">If you want to provide a standard progress dialog box, see [How to: Provide a Progress Dialog Box for File Operations](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span></span>  
  
 <span data-ttu-id="6cbf5-106">Verwenden Sie <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> zum Bereitstellen von Ereignissen, mit denen Sie bei Vorgängen auf mehreren Dateien den Status berechnen können.</span><span class="sxs-lookup"><span data-stu-id="6cbf5-106">Use <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> to provide events that will enable you to calculate the progress when operating on multiple files.</span></span> <span data-ttu-id="6cbf5-107">Eine weitere Möglichkeit ist die Verwendung eines Plattformaufrufs, um die relevanten dateibezogenen Methoden in der Windows-Shell aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="6cbf5-107">Another approach is to use platform invoke to call the relevant file-related methods in the Windows Shell.</span></span> <span data-ttu-id="6cbf5-108">Weitere Informationen dazu, wie Sie diese Dateivorgänge asynchron ausführen, finden Sie unter [Asynchrone Datei-E/A](../../../standard/io/asynchronous-file-i-o.md).</span><span class="sxs-lookup"><span data-stu-id="6cbf5-108">For information about how to perform these file operations asynchronously, see [Asynchronous File I/O](../../../standard/io/asynchronous-file-i-o.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6cbf5-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6cbf5-109">Example</span></span>  
 <span data-ttu-id="6cbf5-110">Im folgenden Beispiel wird gezeigt, wie Sie Dateien und Verzeichnisse kopieren.</span><span class="sxs-lookup"><span data-stu-id="6cbf5-110">The following example shows how to copy files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#7](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="6cbf5-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6cbf5-111">Example</span></span>  
 <span data-ttu-id="6cbf5-112">Im folgenden Beispiel wird gezeigt, wie Sie Dateien und Verzeichnisse verschieben.</span><span class="sxs-lookup"><span data-stu-id="6cbf5-112">The following example shows how to move files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#8](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="6cbf5-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6cbf5-113">Example</span></span>  
 <span data-ttu-id="6cbf5-114">Im folgenden Beispiel wird gezeigt, wie Sie Dateien und Verzeichnisse löschen.</span><span class="sxs-lookup"><span data-stu-id="6cbf5-114">The following example shows how to delete files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#9](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="6cbf5-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6cbf5-115">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="6cbf5-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="6cbf5-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="6cbf5-117">Das Dateisystem und die Registrierung (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="6cbf5-117">File System and the Registry (C# Programming Guide)</span></span>](index.md)
- [<span data-ttu-id="6cbf5-118">Vorgehensweise: Bereitstellen eines Statusdialogfelds für Dateioperationen</span><span class="sxs-lookup"><span data-stu-id="6cbf5-118">How to: Provide a Progress Dialog Box for File Operations</span></span>](how-to-provide-a-progress-dialog-box-for-file-operations.md)
- [<span data-ttu-id="6cbf5-119">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="6cbf5-119">File and Stream I/O</span></span>](../../../standard/io/index.md)
- [<span data-ttu-id="6cbf5-120">Allgemeine E/A-Aufgaben</span><span class="sxs-lookup"><span data-stu-id="6cbf5-120">Common I/O Tasks</span></span>](../../../standard/io/common-i-o-tasks.md)

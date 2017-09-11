---
title: "Gewusst wie: Kopieren, Löschen und Verschieben von Dateien und Ordnern (C#-Programmierhandbuch)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a4cfec46e0af0056a0de20a1ed83a370cd010055
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a><span data-ttu-id="98e13-102">Gewusst wie: Kopieren, Löschen und Verschieben von Dateien und Ordnern (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="98e13-102">How to: Copy, Delete, and Move Files and Folders (C# Programming Guide)</span></span>
<span data-ttu-id="98e13-103">Die folgenden Beispiele veranschaulichen, wie Dateien und Ordner mithilfe der Klassen <xref:System.IO.File?displayProperty=fullName>, <xref:System.IO.Directory?displayProperty=fullName>, <xref:System.IO.FileInfo?displayProperty=fullName> und <xref:System.IO.DirectoryInfo?displayProperty=fullName> aus dem Namespace <xref:System.IO?displayProperty=fullName> synchron kopiert, verschoben und gelöscht werden können.</span><span class="sxs-lookup"><span data-stu-id="98e13-103">The following examples show how to copy, move, and delete files and folders in a synchronous manner by using the <xref:System.IO.File?displayProperty=fullName>, <xref:System.IO.Directory?displayProperty=fullName>, <xref:System.IO.FileInfo?displayProperty=fullName>, and <xref:System.IO.DirectoryInfo?displayProperty=fullName> classes from the <xref:System.IO?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="98e13-104">Diese Beispiele stellen keine Statusanzeige oder irgendeine andere Benutzeroberfläche bereit.</span><span class="sxs-lookup"><span data-stu-id="98e13-104">These examples do not provide a progress bar or any other user interface.</span></span> <span data-ttu-id="98e13-105">Informationen zur Bereitstellung eines standardmäßigen Fortschrittsdialogfelds finden Sie unter [Vorgehensweise: Bereitstellen eines Statusdialogfelds für Dateioperationen](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span><span class="sxs-lookup"><span data-stu-id="98e13-105">If you want to provide a standard progress dialog box, see [How to: Provide a Progress Dialog Box for File Operations](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span></span>  
  
 <span data-ttu-id="98e13-106">Verwenden Sie <xref:System.IO.FileSystemWatcher?displayProperty=fullName> zum Bereitstellen von Ereignissen, mit denen Sie bei Vorgängen auf mehreren Dateien den Status berechnen können.</span><span class="sxs-lookup"><span data-stu-id="98e13-106">Use <xref:System.IO.FileSystemWatcher?displayProperty=fullName> to provide events that will enable you to calculate the progress when operating on multiple files.</span></span> <span data-ttu-id="98e13-107">Eine weitere Möglichkeit ist die Verwendung eines Plattformaufrufs, um die relevanten dateibezogenen Methoden in der Windows-Shell aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="98e13-107">Another approach is to use platform invoke to call the relevant file-related methods in the Windows Shell.</span></span> <span data-ttu-id="98e13-108">Weitere Informationen dazu, wie Sie diese Dateivorgänge asynchron ausführen, finden Sie unter [Asynchrone Datei-E/A](https://msdn.microsoft.com/library/kztecsys).</span><span class="sxs-lookup"><span data-stu-id="98e13-108">For information about how to perform these file operations asynchronously, see [Asynchronous File I/O](https://msdn.microsoft.com/library/kztecsys).</span></span>  
  
## <a name="example"></a><span data-ttu-id="98e13-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="98e13-109">Example</span></span>  
 <span data-ttu-id="98e13-110">Im folgenden Beispiel wird gezeigt, wie Sie Dateien und Verzeichnisse kopieren.</span><span class="sxs-lookup"><span data-stu-id="98e13-110">The following example shows how to copy files and directories.</span></span>  
  
 <span data-ttu-id="98e13-111">[!code-cs[csFilesandFolders#7](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="98e13-111">[!code-cs[csFilesandFolders#7](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="98e13-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="98e13-112">Example</span></span>  
 <span data-ttu-id="98e13-113">Im folgenden Beispiel wird gezeigt, wie Sie Dateien und Verzeichnisse verschieben.</span><span class="sxs-lookup"><span data-stu-id="98e13-113">The following example shows how to move files and directories.</span></span>  
  
 <span data-ttu-id="98e13-114">[!code-cs[csFilesandFolders#8](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="98e13-114">[!code-cs[csFilesandFolders#8](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="98e13-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="98e13-115">Example</span></span>  
 <span data-ttu-id="98e13-116">Im folgenden Beispiel wird gezeigt, wie Sie Dateien und Verzeichnisse löschen.</span><span class="sxs-lookup"><span data-stu-id="98e13-116">The following example shows how to delete files and directories.</span></span>  
  
 <span data-ttu-id="98e13-117">[!code-cs[csFilesandFolders#9](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="98e13-117">[!code-cs[csFilesandFolders#9](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98e13-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98e13-118">See Also</span></span>  
 <span data-ttu-id="98e13-119"><xref:System.IO?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="98e13-119"><xref:System.IO?displayProperty=fullName></span></span>   
 <span data-ttu-id="98e13-120">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="98e13-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="98e13-121">[Das Dateisystem und die Registrierung (C#-Programmierhandbuch)](index.md) </span><span class="sxs-lookup"><span data-stu-id="98e13-121">[File System and the Registry (C# Programming Guide)](index.md) </span></span>  
 <span data-ttu-id="98e13-122">[Vorgehensweise: Bereitstellen eines Statusdialogfelds für Dateioperationen](how-to-provide-a-progress-dialog-box-for-file-operations.md) </span><span class="sxs-lookup"><span data-stu-id="98e13-122">[How to: Provide a Progress Dialog Box for File Operations](how-to-provide-a-progress-dialog-box-for-file-operations.md) </span></span>  
 <span data-ttu-id="98e13-123">[Datei- und Stream-E/A](https://msdn.microsoft.com/library/k3352a4t) </span><span class="sxs-lookup"><span data-stu-id="98e13-123">[File and Stream I/O](https://msdn.microsoft.com/library/k3352a4t) </span></span>  
 [<span data-ttu-id="98e13-124">Allgemeine E/A-Aufgaben</span><span class="sxs-lookup"><span data-stu-id="98e13-124">Common I/O Tasks</span></span>](https://msdn.microsoft.com/library/ms404278)


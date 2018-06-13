---
title: Die Datei ist zu groß, um in ein Bytearray geladen zu werden
ms.date: 07/20/2015
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
ms.openlocfilehash: 1b04d47cab77269a0ce84ef77c162a4401d99d9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585924"
---
# <a name="file-is-too-large-to-read-into-a-byte-array"></a><span data-ttu-id="45ea2-102">Die Datei ist zu groß, um in ein Bytearray geladen zu werden</span><span class="sxs-lookup"><span data-stu-id="45ea2-102">File is too large to read into a byte array</span></span>
<span data-ttu-id="45ea2-103">Die Größe der Datei, die Sie in ein Bytearray lesen überschreitet 4 GB.</span><span class="sxs-lookup"><span data-stu-id="45ea2-103">The size of the file you are attempting to read into a byte array exceeds 4 GB.</span></span> <span data-ttu-id="45ea2-104">Die `My.Computer.FileSystem.ReadAllBytes` Methode eine Datei, die diese Größe überschreitet kann nicht gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="45ea2-104">The `My.Computer.FileSystem.ReadAllBytes` method cannot read a file that exceeds this size.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="45ea2-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="45ea2-105">To correct this error</span></span>  
  
-   <span data-ttu-id="45ea2-106">Verwenden einer <xref:System.IO.StreamReader> zum Lesen der Datei.</span><span class="sxs-lookup"><span data-stu-id="45ea2-106">Use a <xref:System.IO.StreamReader> to read the file.</span></span> <span data-ttu-id="45ea2-107">Weitere Informationen finden Sie unter [Grundlagen der .NET Framework-Datei-e/a und dem Dateisystem (Visual Basic)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).</span><span class="sxs-lookup"><span data-stu-id="45ea2-107">For more information, see [Basics of .NET Framework File I/O and the File System (Visual Basic)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45ea2-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45ea2-108">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>  
 <xref:System.IO.StreamReader>  
 [<span data-ttu-id="45ea2-109">Dateizugriff mit Visual Basic</span><span class="sxs-lookup"><span data-stu-id="45ea2-109">File Access with Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)  
 [<span data-ttu-id="45ea2-110">Gewusst wie: Lesen von Text aus Dateien mit einem StreamReader</span><span class="sxs-lookup"><span data-stu-id="45ea2-110">How to: Read Text from Files with a StreamReader</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)

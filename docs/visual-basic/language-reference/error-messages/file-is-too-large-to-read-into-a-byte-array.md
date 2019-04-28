---
title: Die Datei ist zu groß, um in ein Bytearray geladen zu werden
ms.date: 07/20/2015
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
ms.openlocfilehash: 0c7d35e08eeb42e35c4c40e47434a64393d829b1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61800879"
---
# <a name="file-is-too-large-to-read-into-a-byte-array"></a><span data-ttu-id="0563a-102">Die Datei ist zu groß, um in ein Bytearray geladen zu werden</span><span class="sxs-lookup"><span data-stu-id="0563a-102">File is too large to read into a byte array</span></span>
<span data-ttu-id="0563a-103">Die Größe der Datei, die Sie versuchen, ein Bytearray eingelesen überschreitet Zustand 4 GB.</span><span class="sxs-lookup"><span data-stu-id="0563a-103">The size of the file you are attempting to read into a byte array exceeds 4 GB.</span></span> <span data-ttu-id="0563a-104">Die `My.Computer.FileSystem.ReadAllBytes` Methode eine Datei, die diese Größe überschreitet kann nicht gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="0563a-104">The `My.Computer.FileSystem.ReadAllBytes` method cannot read a file that exceeds this size.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0563a-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="0563a-105">To correct this error</span></span>  
  
- <span data-ttu-id="0563a-106">Verwenden einer <xref:System.IO.StreamReader> zum Lesen der Datei.</span><span class="sxs-lookup"><span data-stu-id="0563a-106">Use a <xref:System.IO.StreamReader> to read the file.</span></span> <span data-ttu-id="0563a-107">Weitere Informationen finden Sie unter [Grundlagen der .NET Framework-Datei-e/a und dem Dateisystem (Visual Basic)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).</span><span class="sxs-lookup"><span data-stu-id="0563a-107">For more information, see [Basics of .NET Framework File I/O and the File System (Visual Basic)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0563a-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0563a-108">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>
- <xref:System.IO.StreamReader>
- [<span data-ttu-id="0563a-109">Dateizugriff mit Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0563a-109">File Access with Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)
- [<span data-ttu-id="0563a-110">Vorgehensweise: Lesen von Text aus Dateien mit einem StreamReader</span><span class="sxs-lookup"><span data-stu-id="0563a-110">How to: Read Text from Files with a StreamReader</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)

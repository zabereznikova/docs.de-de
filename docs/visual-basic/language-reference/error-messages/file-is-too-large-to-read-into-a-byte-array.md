---
title: Die Datei ist zu groß, um in ein Bytearray geladen zu werden
ms.date: 07/20/2015
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
ms.openlocfilehash: 89459aaf766a70f69008f847dda7ac6e2a1e41d1
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874183"
---
# <a name="file-is-too-large-to-read-into-a-byte-array"></a><span data-ttu-id="60144-102">Die Datei ist zu groß, um in ein Bytearray geladen zu werden</span><span class="sxs-lookup"><span data-stu-id="60144-102">File is too large to read into a byte array</span></span>

<span data-ttu-id="60144-103">Die Größe der Datei, die Sie in ein Bytearray einlesen möchten, überschreitet 4 GB.</span><span class="sxs-lookup"><span data-stu-id="60144-103">The size of the file you are attempting to read into a byte array exceeds 4 GB.</span></span> <span data-ttu-id="60144-104">Die- `My.Computer.FileSystem.ReadAllBytes` Methode kann eine Datei nicht lesen, die diese Größe überschreitet.</span><span class="sxs-lookup"><span data-stu-id="60144-104">The `My.Computer.FileSystem.ReadAllBytes` method cannot read a file that exceeds this size.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="60144-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="60144-105">To correct this error</span></span>  
  
- <span data-ttu-id="60144-106">Verwenden <xref:System.IO.StreamReader> Sie, um die Datei zu lesen.</span><span class="sxs-lookup"><span data-stu-id="60144-106">Use a <xref:System.IO.StreamReader> to read the file.</span></span> <span data-ttu-id="60144-107">Weitere Informationen finden Sie unter [Grundlagen der .NET Framework Datei-e/a und des Dateisystems (Visual Basic)](../../developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).</span><span class="sxs-lookup"><span data-stu-id="60144-107">For more information, see [Basics of .NET Framework File I/O and the File System (Visual Basic)](../../developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60144-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="60144-108">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>
- <xref:System.IO.StreamReader>
- [<span data-ttu-id="60144-109">Dateizugriff mit Visual Basic</span><span class="sxs-lookup"><span data-stu-id="60144-109">File Access with Visual Basic</span></span>](../../developing-apps/programming/drives-directories-files/file-access.md)
- [<span data-ttu-id="60144-110">Vorgehensweise: Lesen von Text aus Dateien mit StreamReader</span><span class="sxs-lookup"><span data-stu-id="60144-110">How to: Read Text from Files with a StreamReader</span></span>](../../developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)

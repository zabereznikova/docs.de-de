---
title: Die Codierung kann nicht auf 'Nothing' festgelegt werden
ms.date: 07/20/2015
ms.assetid: 59f7c731-8291-4a85-bf51-c225e48cdc84
ms.openlocfilehash: 30b0b4a29fbdf931aa62263b75d1fa946e87b145
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2019
ms.locfileid: "58028444"
---
# <a name="encoding-cannot-be-set-to-nothing"></a><span data-ttu-id="958d9-102">Die Codierung kann nicht auf 'Nothing' festgelegt werden</span><span class="sxs-lookup"><span data-stu-id="958d9-102">Encoding cannot be set to Nothing</span></span>
<span data-ttu-id="958d9-103">Fehler bei einem Lese- oder Schreibversuch aus einer bzw. in eine Datei, da der Parameter `encoding` auf `Nothing` festgelegt wurde; es ist jedoch ein gültiger Wert erforderlich.</span><span class="sxs-lookup"><span data-stu-id="958d9-103">An attempt to read from or write to a file has failed because the parameter `encoding` has been set to `Nothing` but requires a valid value.</span></span>  
  
 <span data-ttu-id="958d9-104"><xref:System.Text.Encoding> wird verwendet, um zu bestimmen, welche Codierung beim Schreiben in eine Datei verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="958d9-104"><xref:System.Text.Encoding> is used to determine what encoding to use when writing to a file.</span></span> <span data-ttu-id="958d9-105">Der Standardwert ist UTF-8.</span><span class="sxs-lookup"><span data-stu-id="958d9-105">The default is UTF-8.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="958d9-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="958d9-106">To correct this error</span></span>  
  
-   <span data-ttu-id="958d9-107">Geben Sie einen gültigen Wert für den `encoding` -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="958d9-107">Supply a valid value for the `encoding` parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="958d9-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="958d9-108">See also</span></span>

- [<span data-ttu-id="958d9-109">Dateicodierungen</span><span class="sxs-lookup"><span data-stu-id="958d9-109">File Encodings</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)
- [<span data-ttu-id="958d9-110">Lesen aus Dateien</span><span class="sxs-lookup"><span data-stu-id="958d9-110">Reading from Files</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
- [<span data-ttu-id="958d9-111">Schreiben in Dateien</span><span class="sxs-lookup"><span data-stu-id="958d9-111">Writing to Files</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
- [<span data-ttu-id="958d9-112">My.Computer.FileSystem.ReadAllText</span><span class="sxs-lookup"><span data-stu-id="958d9-112">My.Computer.FileSystem.ReadAllText</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A)
- [<span data-ttu-id="958d9-113">My.Computer.FileSystem.WriteAllText</span><span class="sxs-lookup"><span data-stu-id="958d9-113">My.Computer.FileSystem.WriteAllText</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A)

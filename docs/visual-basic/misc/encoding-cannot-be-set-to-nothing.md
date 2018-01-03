---
title: Die Codierung kann nicht auf 'Nothing' festgelegt werden
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 59f7c731-8291-4a85-bf51-c225e48cdc84
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 42baef6e0634849004290dce3db32e47f103282d
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="encoding-cannot-be-set-to-nothing"></a><span data-ttu-id="b19e6-102">Die Codierung kann nicht auf 'Nothing' festgelegt werden</span><span class="sxs-lookup"><span data-stu-id="b19e6-102">Encoding cannot be set to Nothing</span></span>
<span data-ttu-id="b19e6-103">Fehler bei einem Lese- oder Schreibversuch aus einer bzw. in eine Datei, da der Parameter `encoding` auf `Nothing` festgelegt wurde; es ist jedoch ein gültiger Wert erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b19e6-103">An attempt to read from or write to a file has failed because the parameter `encoding` has been set to `Nothing` but requires a valid value.</span></span>  
  
 <span data-ttu-id="b19e6-104"><xref:System.Text.Encoding> wird verwendet, um zu bestimmen, welche Codierung beim Schreiben in eine Datei verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b19e6-104"><xref:System.Text.Encoding> is used to determine what encoding to use when writing to a file.</span></span> <span data-ttu-id="b19e6-105">Der Standardwert ist UTF-8.</span><span class="sxs-lookup"><span data-stu-id="b19e6-105">The default is UTF-8.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b19e6-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="b19e6-106">To correct this error</span></span>  
  
-   <span data-ttu-id="b19e6-107">Geben Sie einen gültigen Wert für den `encoding` -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="b19e6-107">Supply a valid value for the `encoding` parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b19e6-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b19e6-108">See Also</span></span>  
 [<span data-ttu-id="b19e6-109">Dateicodierungen</span><span class="sxs-lookup"><span data-stu-id="b19e6-109">File Encodings</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)  
 [<span data-ttu-id="b19e6-110">Lesen aus Dateien</span><span class="sxs-lookup"><span data-stu-id="b19e6-110">Reading from Files</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)  
 [<span data-ttu-id="b19e6-111">Schreiben in Dateien</span><span class="sxs-lookup"><span data-stu-id="b19e6-111">Writing to Files</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)  
 [<span data-ttu-id="b19e6-112">My.Computer.FileSystem.ReadAllText</span><span class="sxs-lookup"><span data-stu-id="b19e6-112">My.Computer.FileSystem.ReadAllText</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A)  
 [<span data-ttu-id="b19e6-113">My.Computer.FileSystem.WriteAllText</span><span class="sxs-lookup"><span data-stu-id="b19e6-113">My.Computer.FileSystem.WriteAllText</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A)

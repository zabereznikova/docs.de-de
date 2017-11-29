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
ms.openlocfilehash: daa3567e47f170c64b45cbb9e49d7fa0026b8903
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="encoding-cannot-be-set-to-nothing"></a><span data-ttu-id="0f459-102">Die Codierung kann nicht auf 'Nothing' festgelegt werden</span><span class="sxs-lookup"><span data-stu-id="0f459-102">Encoding cannot be set to Nothing</span></span>
<span data-ttu-id="0f459-103">Fehler bei einem Lese- oder Schreibversuch aus einer bzw. in eine Datei, da der Parameter `encoding` auf `Nothing` festgelegt wurde; es ist jedoch ein gültiger Wert erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0f459-103">An attempt to read from or write to a file has failed because the parameter `encoding` has been set to `Nothing` but requires a valid value.</span></span>  
  
 <span data-ttu-id="0f459-104"><xref:System.Text.Encoding> wird verwendet, um zu bestimmen, welche Codierung beim Schreiben in eine Datei verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0f459-104"><xref:System.Text.Encoding> is used to determine what encoding to use when writing to a file.</span></span> <span data-ttu-id="0f459-105">Der Standardwert ist UTF-8.</span><span class="sxs-lookup"><span data-stu-id="0f459-105">The default is UTF-8.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0f459-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="0f459-106">To correct this error</span></span>  
  
-   <span data-ttu-id="0f459-107">Geben Sie einen gültigen Wert für den `encoding` -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="0f459-107">Supply a valid value for the `encoding` parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f459-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f459-108">See Also</span></span>  
 [<span data-ttu-id="0f459-109">Dateicodierungen</span><span class="sxs-lookup"><span data-stu-id="0f459-109">File Encodings</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)  
 [<span data-ttu-id="0f459-110">Lesen aus Dateien</span><span class="sxs-lookup"><span data-stu-id="0f459-110">Reading from Files</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)  
 [<span data-ttu-id="0f459-111">Schreiben in Dateien</span><span class="sxs-lookup"><span data-stu-id="0f459-111">Writing to Files</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)  
 [<span data-ttu-id="0f459-112">My.Computer.FileSystem.ReadAllText-Methode</span><span class="sxs-lookup"><span data-stu-id="0f459-112">My.Computer.FileSystem.ReadAllText Method</span></span>](http://msdn.microsoft.com/en-us/3a7ac8be-fb1d-4087-bc65-167d6754d57f)  
 [<span data-ttu-id="0f459-113">My.Computer.FileSystem.WriteAllText-Methode</span><span class="sxs-lookup"><span data-stu-id="0f459-113">My.Computer.FileSystem.WriteAllText Method</span></span>](http://msdn.microsoft.com/en-us/f507460c-87d9-4504-b74f-3ff825c7d5c4)

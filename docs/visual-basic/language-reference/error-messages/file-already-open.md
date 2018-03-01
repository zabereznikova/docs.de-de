---
title: "Die Datei ist bereits geöffnet."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3305831e840510e3f0b5bcb8bf847e39ea3ee4ba
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="file-already-open"></a><span data-ttu-id="d1d6f-102">Die Datei ist bereits geöffnet.</span><span class="sxs-lookup"><span data-stu-id="d1d6f-102">File already open</span></span>
<span data-ttu-id="d1d6f-103">Manchmal muss eine Datei geschlossen werden, bevor eine andere `FileOpen` oder anderer Vorgang ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="d1d6f-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="d1d6f-104">Zu den möglichen Ursachen für diesen Fehler gehören:</span><span class="sxs-lookup"><span data-stu-id="d1d6f-104">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="d1d6f-105">Eine sequenzielle Ausgabemodus `FileOpen` Vorgang ausgeführt wurde, für eine Datei, die bereits geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="d1d6f-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>  
  
-   <span data-ttu-id="d1d6f-106">Eine Anweisung verweist auf eine geöffnete Datei.</span><span class="sxs-lookup"><span data-stu-id="d1d6f-106">A statement refers to an open file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d1d6f-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="d1d6f-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="d1d6f-108">Schließen Sie die Datei, bevor die Anweisung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d1d6f-108">Close the file before executing the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1d6f-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1d6f-109">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>

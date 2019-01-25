---
title: Die Datei ist bereits geöffnet.
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: cda72e03eb5c2469b8106957a0c50fbfa5314549
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54567034"
---
# <a name="file-already-open"></a><span data-ttu-id="295f4-102">Die Datei ist bereits geöffnet.</span><span class="sxs-lookup"><span data-stu-id="295f4-102">File already open</span></span>
<span data-ttu-id="295f4-103">Manchmal muss eine Datei geschlossen werden, bevor Sie einen anderen `FileOpen` oder andere Vorgänge ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="295f4-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="295f4-104">Zu den möglichen Ursachen für diesen Fehler gehören:</span><span class="sxs-lookup"><span data-stu-id="295f4-104">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="295f4-105">Eine sequenzielle Ausgabemodus `FileOpen` Vorgang wurde ausgeführt, für eine Datei, die bereits geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="295f4-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>  
  
-   <span data-ttu-id="295f4-106">Eine Anweisung verweist auf eine geöffnete Datei.</span><span class="sxs-lookup"><span data-stu-id="295f4-106">A statement refers to an open file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="295f4-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="295f4-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="295f4-108">Schließen Sie die Datei, bevor die Anweisung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="295f4-108">Close the file before executing the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="295f4-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="295f4-109">See also</span></span>
- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>

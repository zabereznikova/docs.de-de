---
title: Die Datei ist bereits geöffnet.
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: e565dbd6352a8f76290f3f58d62e2e14a18ef45f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58823505"
---
# <a name="file-already-open"></a><span data-ttu-id="587c6-102">Die Datei ist bereits geöffnet.</span><span class="sxs-lookup"><span data-stu-id="587c6-102">File already open</span></span>
<span data-ttu-id="587c6-103">Manchmal muss eine Datei geschlossen werden, bevor Sie einen anderen `FileOpen` oder andere Vorgänge ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="587c6-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="587c6-104">Zu den möglichen Ursachen für diesen Fehler gehören:</span><span class="sxs-lookup"><span data-stu-id="587c6-104">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="587c6-105">Eine sequenzielle Ausgabemodus `FileOpen` Vorgang wurde ausgeführt, für eine Datei, die bereits geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="587c6-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>  
  
-   <span data-ttu-id="587c6-106">Eine Anweisung verweist auf eine geöffnete Datei.</span><span class="sxs-lookup"><span data-stu-id="587c6-106">A statement refers to an open file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="587c6-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="587c6-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="587c6-108">Schließen Sie die Datei, bevor die Anweisung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="587c6-108">Close the file before executing the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="587c6-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="587c6-109">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>

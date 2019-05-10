---
title: Die Datei ist bereits geöffnet.
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 8ec878e04b0128c997c5be51d2c714d55abcde8c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665121"
---
# <a name="file-already-open"></a><span data-ttu-id="d1537-102">Die Datei ist bereits geöffnet.</span><span class="sxs-lookup"><span data-stu-id="d1537-102">File already open</span></span>
<span data-ttu-id="d1537-103">Manchmal muss eine Datei geschlossen werden, bevor Sie einen anderen `FileOpen` oder andere Vorgänge ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="d1537-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="d1537-104">Zu den möglichen Ursachen für diesen Fehler gehören:</span><span class="sxs-lookup"><span data-stu-id="d1537-104">Among the possible causes of this error are:</span></span>  
  
- <span data-ttu-id="d1537-105">Eine sequenzielle Ausgabemodus `FileOpen` Vorgang wurde ausgeführt, für eine Datei, die bereits geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="d1537-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>  
  
- <span data-ttu-id="d1537-106">Eine Anweisung verweist auf eine geöffnete Datei.</span><span class="sxs-lookup"><span data-stu-id="d1537-106">A statement refers to an open file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d1537-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="d1537-107">To correct this error</span></span>  
  
1. <span data-ttu-id="d1537-108">Schließen Sie die Datei, bevor die Anweisung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d1537-108">Close the file before executing the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1537-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1537-109">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>

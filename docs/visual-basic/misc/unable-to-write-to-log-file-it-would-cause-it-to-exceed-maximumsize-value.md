---
title: In der Protokolldatei kann nicht geschrieben werden, weil dies dazu führen würde, dass sie den MaximumSize-Wert überschreitet.
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_FileExceedsMaximumSize
ms.assetid: 61747a9c-e460-424b-a365-73cdba9dd428
ms.openlocfilehash: 587b35282c7e78da1fdf4ccf9d08214e5665119c
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59298603"
---
# <a name="unable-to-write-to-log-file-because-writing-to-it-would-cause-it-to-exceed-maximumsize-value"></a><span data-ttu-id="f23c3-102">In der Protokolldatei kann nicht geschrieben werden, weil dies dazu führen würde, dass sie den MaximumSize-Wert überschreitet.</span><span class="sxs-lookup"><span data-stu-id="f23c3-102">Unable to write to log file because writing to it would cause it to exceed MaximumSize value</span></span>
<span data-ttu-id="f23c3-103">Die <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> -Klasse konnte aus folgendem Grund nicht in die Protokolldatei schreiben:</span><span class="sxs-lookup"><span data-stu-id="f23c3-103">The <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class could not write to the log file because:</span></span>  
  
-   <span data-ttu-id="f23c3-104">Die Größe der Protokolldatei (in Bytes) ist größer als der Wert der <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="f23c3-104">The log file size (in bytes) is greater than the value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> property</span></span>  
  
     <span data-ttu-id="f23c3-105">- und -</span><span class="sxs-lookup"><span data-stu-id="f23c3-105">—and—</span></span>  
  
-   <span data-ttu-id="f23c3-106">Der Wert der <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> -Eigenschaft ist <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>.</span><span class="sxs-lookup"><span data-stu-id="f23c3-106">The value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> property was <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f23c3-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="f23c3-107">To correct this error</span></span>  
  
1. <span data-ttu-id="f23c3-108">Archivieren Sie die vorhandenen Protokolle, und entfernen Sie diese vom Computer, damit das <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> -Objekt neue Protokolle erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="f23c3-108">Archive the existing logs and remove them from the computer to allow the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> object to create new logs.</span></span>  
  
2. <span data-ttu-id="f23c3-109">Ändern Sie den Wert der <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> -Eigenschaft, um größere Protokolle zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="f23c3-109">Change the value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> property to allow for larger logs.</span></span>  
  
3. <span data-ttu-id="f23c3-110">Legen Sie die <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> -Eigenschaft auf <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> fest, um Nachrichten ohne Warnung zu verwerfen, wenn das Protokoll zu groß ist.</span><span class="sxs-lookup"><span data-stu-id="f23c3-110">Set the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> property to <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> to discard messages without warning if the log is too large.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f23c3-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f23c3-111">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- [<span data-ttu-id="f23c3-112">My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="f23c3-112">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [<span data-ttu-id="f23c3-113">My.Application.Info.DirectoryPath</span><span class="sxs-lookup"><span data-stu-id="f23c3-113">My.Application.Info.DirectoryPath</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)

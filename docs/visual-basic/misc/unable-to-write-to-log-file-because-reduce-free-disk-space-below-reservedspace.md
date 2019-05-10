---
title: Die Protokolldatei kann nicht geschrieben werden, weil das Schreiben in diese Datei dazu führen würde, dass der freie Speicherplatz auf dem Datenträger unter den ReservedSpace-Wert absinkt.
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_ReservedSpaceEncroached
ms.assetid: 95832e70-4ecc-47aa-90c1-f35c4d468151
ms.openlocfilehash: dc7e97bfc5aa3963e1edcd204f5b81d21edab579
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2019
ms.locfileid: "64913246"
---
# <a name="unable-to-write-to-log-file-because-writing-to-it-would-reduce-free-disk-space-below-reservedspace-value"></a><span data-ttu-id="8a121-102">Die Protokolldatei kann nicht geschrieben werden, weil das Schreiben in diese Datei dazu führen würde, dass der freie Speicherplatz auf dem Datenträger unter den ReservedSpace-Wert absinkt.</span><span class="sxs-lookup"><span data-stu-id="8a121-102">Unable to write to log file because writing to it would reduce free disk space below ReservedSpace value</span></span>
<span data-ttu-id="8a121-103">Die <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> -Klasse konnte aus diesem Grund nicht in die Protokolldatei schreiben:</span><span class="sxs-lookup"><span data-stu-id="8a121-103">The <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class could not write to the log file because:</span></span>  
  
- <span data-ttu-id="8a121-104">Die Menge des freien Speicherplatzes (in Byte) ist kleiner als der Wert der <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A> -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8a121-104">The amount of free disk space (in bytes) is less than the value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A> property</span></span>  
  
     <span data-ttu-id="8a121-105">- und -</span><span class="sxs-lookup"><span data-stu-id="8a121-105">—and—</span></span>  
  
- <span data-ttu-id="8a121-106">Der Wert der <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> -Eigenschaft ist <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>.</span><span class="sxs-lookup"><span data-stu-id="8a121-106">The value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> property was <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8a121-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="8a121-107">To correct this error</span></span>  
  
1. <span data-ttu-id="8a121-108">Archivieren Sie die vorhandenen Protokolle, und entfernen Sie diese vom Computer, damit das <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> -Objekt neue Protokolle erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="8a121-108">Archive the existing logs and remove them from the computer to allow the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> object to create new logs.</span></span>  
  
2. <span data-ttu-id="8a121-109">Ändern Sie den Wert der <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A> -Eigenschaft in einen kleinere Zahl, um weniger Speicherplatz auf dem Datenträger zu reservieren.</span><span class="sxs-lookup"><span data-stu-id="8a121-109">Change the value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A> property to a smaller number to reserve less disk space.</span></span>  
  
3. <span data-ttu-id="8a121-110">Legen Sie die <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> -Eigenschaft auf <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> fest, um Nachrichten ohne Warnung zu verwerfen, wenn nicht genügend freier Speicherplatz verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="8a121-110">Set the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> property to <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> to discard messages without warning if there is not enough free disk space.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a121-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a121-111">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- [<span data-ttu-id="8a121-112">My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="8a121-112">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [<span data-ttu-id="8a121-113">My.Application.Info.DirectoryPath</span><span class="sxs-lookup"><span data-stu-id="8a121-113">My.Application.Info.DirectoryPath</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)

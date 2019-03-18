---
title: Die Protokolldatei kann nicht geschrieben werden, weil das Schreiben in diese Datei dazu führen würde, dass der freie Speicherplatz auf dem Datenträger unter den ReservedSpace-Wert absinkt.
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_ReservedSpaceEncroached
ms.assetid: 95832e70-4ecc-47aa-90c1-f35c4d468151
ms.openlocfilehash: 30c2f90d1c5e03db4ffc289ad3a1a6bc9f7fa689
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2019
ms.locfileid: "58026476"
---
# <a name="unable-to-write-to-log-file-because-writing-to-it-would-reduce-free-disk-space-below-reservedspace-value"></a>Die Protokolldatei kann nicht geschrieben werden, weil das Schreiben in diese Datei dazu führen würde, dass der freie Speicherplatz auf dem Datenträger unter den ReservedSpace-Wert absinkt.
Die <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> -Klasse konnte aus diesem Grund nicht in die Protokolldatei schreiben:  
  
-   Die Menge des freien Speicherplatzes (in Byte) ist kleiner als der Wert der <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A> -Eigenschaft  
  
     - und -  
  
-   Der Wert der <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> -Eigenschaft ist <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Archivieren Sie die vorhandenen Protokolle, und entfernen Sie diese vom Computer, damit das <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> -Objekt neue Protokolle erstellen kann.  
  
2.  Ändern Sie den Wert der <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A> -Eigenschaft in einen kleinere Zahl, um weniger Speicherplatz auf dem Datenträger zu reservieren.  
  
3.  Legen Sie die <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> -Eigenschaft auf <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> fest, um Nachrichten ohne Warnung zu verwerfen, wenn nicht genügend freier Speicherplatz verfügbar ist.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- [My.Application.Log](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [My.Application.Info.DirectoryPath](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)

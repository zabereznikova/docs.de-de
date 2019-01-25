---
title: ETW-Konfliktereignisse – .NET
ms.date: 03/30/2017
helpviewer_keywords:
- contention events [.NET Framework]
- ETW, contention events (CLR)
ms.assetid: 6933e753-2f2a-425b-ae84-42138c957d76
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 95f56a6c8b51c58ed36d5d0de428bf57b728009c
ms.sourcegitcommit: 5dcfeb59179e81071f54840d4902cbe00b184294
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2019
ms.locfileid: "54857644"
---
# <a name="contention-etw-events"></a>ETW-Konfliktereignisse

Konfliktereignisse werden immer dann ausgelöst, wenn es Konflikte bei <xref:System.Threading.Monitor?displayProperty=nameWithType>-Sperren oder nativen Sperren gibt, die von der Laufzeit verwendet werden. Konflikte treten auf, wenn ein Thread auf eine Sperre wartet, während ein anderer Thread die Sperre besitzt.

Die folgende Tabelle zeigt das Schlüsselwort, unter dem Konfliktereignisse ausgelöst werden, und die Ebene der Ereignisse. Weitere Informationen finden Sie unter [CLR-ETW-Schlüsselwörter und-Ebenen](clr-etw-keywords-and-levels.md).

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`ContentionKeyword` (0x4000)|Information (4)|

Die folgende Tabelle zeigt die Ereignisinformationen:

|event|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`ContentionStart_V1`|81|Konflikt startet. Dieses Ereignis enthält die Spinzeit vor dem Abruf einer Sperre eines Threads nicht. Dies wird nur ausgelöst, wenn der Thread darauf wartet, eine Sperre abzurufen.|
|`ContentionStop`|91|Konflikt endet.|

Die folgende Tabelle zeigt die Ereignisdaten:

|Feldname|Datentyp|Beschreibung|
|----------------|---------------|-----------------|
|Flags|win:UInt8|0 für verwaltet. 1 für nativ.|
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR.|

## <a name="see-also"></a>Siehe auch

- [CLR-ETW-Ereignisse](clr-etw-events.md)

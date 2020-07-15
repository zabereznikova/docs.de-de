---
title: 'Konflikt-ETW-Ereignisse: .net'
description: Hier finden Sie Details zu etw-Konflikt Ereignissen, die ausgelöst werden, wenn Konflikte zwischen System. Threading. Monitor-sperren oder System eigenen Sperren auftreten, die von der Laufzeit verwendet werden.
ms.date: 03/30/2017
helpviewer_keywords:
- contention events [.NET Framework]
- ETW, contention events (CLR)
ms.assetid: 6933e753-2f2a-425b-ae84-42138c957d76
ms.openlocfilehash: a36b091e0896562fffdb66e895d70049ce0667d7
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309598"
---
# <a name="contention-etw-events"></a>Etw-konfliktereignisse

Konfliktereignisse werden immer dann ausgelöst, wenn es Konflikte bei <xref:System.Threading.Monitor?displayProperty=nameWithType>-Sperren oder nativen Sperren gibt, die von der Laufzeit verwendet werden. Konflikte treten auf, wenn ein Thread auf eine Sperre wartet, während ein anderer Thread die Sperre besitzt.

Die folgende Tabelle zeigt das Schlüsselwort, unter dem Konfliktereignisse ausgelöst werden, und die Ebene der Ereignisse. Weitere Informationen finden Sie unter [CLR-ETW-Schlüsselwörter und-Ebenen](clr-etw-keywords-and-levels.md).

|Schlüsselwort zum Auslösen des Ereignisses|Ebene|
|-----------------------------------|-----------|
|`ContentionKeyword` (0x4000)|Information (4)|

In der folgenden Tabelle werden die Ereignis Informationen angezeigt:

|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|
|-----------|--------------|-----------------|
|`ContentionStart_V1`|81|Konflikt startet. Dieses Ereignis enthält die Spinzeit vor dem Abruf einer Sperre eines Threads nicht. Dies wird nur ausgelöst, wenn der Thread darauf wartet, eine Sperre abzurufen.|
|`ContentionStop`|91|Konflikt endet.|

In der folgenden Tabelle werden die Ereignisdaten angezeigt:

|Feldname|Datentyp|BESCHREIBUNG|
|----------------|---------------|-----------------|
|Flags|win:UInt8|0 für verwaltet. 1 für nativ.|
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR.|

## <a name="see-also"></a>Weitere Informationen

- [CLR-ETW-Ereignisse](clr-etw-events.md)

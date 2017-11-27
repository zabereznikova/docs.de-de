---
title: ICorDebugProcess5::EnumerateHeapRegions-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.EnumerateHeapRegions
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::EnumerateHeapRegions
helpviewer_keywords:
- EnumerateHeapRegions method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeapRegions method [.NET Framework debugging]
ms.assetid: b1edba68-9c36-4f69-be9f-678ce0b33480
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1365ed5fd8cf308716b16d78e79a26584bd966c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess5enumerateheapregions-method"></a>ICorDebugProcess5::EnumerateHeapRegions-Methode
Ruft einen Enumerator für die Speicherbereiche des verwalteten Heaps.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnumerateHeapRegions(  
   [out] ICorDebugHeapSegmentEnum **ppRegions  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppRegions`  
 [out] Ein Zeiger auf die Adresse des ein [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) Schnittstellenobjekts, das einen Enumerator für die Bereiche des Arbeitsspeichers ist in der Objekte im verwalteten Heap befinden.  
  
## <a name="remarks"></a>Hinweise  
 Vor dem Aufruf der `ICorDebugProcess5::EnumerateHeapRegions` -Methode, die Sie aufrufen sollte die [icordebugprocess5:: Getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) Methode und überprüfen Sie den Wert von der `areGCStructuresValid` Feld des zurückgegebenen [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) Objekt, um sicherzustellen, dass die Garbage Collection-Heap in seinem aktuellen Status aufzählbar ist. Darüber hinaus die `ICorDebugProcess5::EnumerateHeapRegions` -Methode zurückkehrt `E_FAIL` , wenn Sie zu früh in der Lebensdauer des Prozesses anfügen, bevor Speicher Regionen werden erstellt.  
  
 Diese Methode wird sichergestellt, dass alle Speicherbereiche aufzählen, die verwaltete Objekte enthalten kann, aber es kann nicht garantiert, dass verwaltete Objekte eigentlich in dieser Regionen befinden. Die [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) Auflistungsobjekt kann leer oder reservierte Speicherbereiche enthalten.  
  
 Die [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) -Schnittstellenobjekt ist eine standard-Enumerator ICorDebugEnum-Schnittstelle, die Ihnen ermöglicht, Auflisten von abgeleitet [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) Objekte. Jede [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) Objekt enthält Informationen zu der Speicherbereich, der einem bestimmten Segment, zusammen mit der Generierung der Objekte in diesem Segment.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugProcess5-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

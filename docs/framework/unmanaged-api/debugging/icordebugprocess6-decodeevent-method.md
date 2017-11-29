---
title: ICorDebugProcess6::DecodeEvent-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 1453bc0c-6e0d-4d5a-b176-22607f8a3e6c
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c0186fb91a4c47f1988af58577cee1b7a64987a3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess6decodeevent-method"></a>ICorDebugProcess6::DecodeEvent-Methode
Decodiert verwaltete Debug-Ereignisse, die in den Nutzdaten der speziell gestalteten systemeigenen Ausnahme-Debug-Ereignissen gekapselt sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT DecodeEvent(  
        [in, length_is(countBytes), size_is(countBytes)]  const BYTE pRecord[],  
        [in] DWORD countBytes,  
        [in] CorDebugRecordFormat format,  
        [in] DWORD dwFlags,   
        [in] DWORD dwThreadId,   
        [out] ICorDebugDebugEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pRecord`  
 [in] Ein Zeiger auf ein Byte-Array aus einem systemeigenen Ausnahme-Debug-Ereignis, das Informationen über ein verwaltetes Debug-Ereignis enthält.  
  
 `countBytes`  
 [in] Die Anzahl der Elemente im `pRecord`-Bytearray.  
  
 `format`  
 [in] Ein [CorDebugRecordFormat](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md) Enumerationsmember, der das Format der nicht verwalteten Debug-Ereignis angibt.  
  
 `dwFlags`  
 [in] Ein Bitfeld, das von der Zielarchitektur abhängt und zusätzliche Informationen über das Debug-Ereignis enthält. Für Windows-Systemen kann es ein Mitglied der [CorDebugDecodeEventFlagsWindows](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md) Enumeration.  
  
 `dwThreadId`  
 [in] Die Betriebssystem-ID des Threads, in dem die Ausnahme ausgelöst wurde.  
  
 `ppEvent`  
 [out] Ein Zeiger auf die Adresse des ein [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) -Objekt, das ein decodiertes verwaltetes Debug-Ereignis darstellt.  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Methode ist nur in Verbindung mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugProcess6-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

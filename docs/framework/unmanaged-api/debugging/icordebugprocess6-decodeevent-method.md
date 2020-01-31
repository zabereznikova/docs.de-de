---
title: ICorDebugProcess6::DecodeEvent-Methode
ms.date: 03/30/2017
ms.assetid: 1453bc0c-6e0d-4d5a-b176-22607f8a3e6c
ms.openlocfilehash: be30b1ff79c2aceb97eb4ad42052da7dd162f5d3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792284"
---
# <a name="icordebugprocess6decodeevent-method"></a>ICorDebugProcess6::DecodeEvent-Methode
Decodiert verwaltete Debug-Ereignisse, die in den Nutzdaten der speziell gestalteten systemeigenen Ausnahme-Debug-Ereignissen gekapselt sind.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DecodeEvent(  
        [in, length_is(countBytes), size_is(countBytes)]  const BYTE pRecord[],  
        [in] DWORD countBytes,  
        [in] CorDebugRecordFormat format,  
        [in] DWORD dwFlags,   
        [in] DWORD dwThreadId,   
        [out] ICorDebugDebugEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `pRecord`  
 [in] Ein Zeiger auf ein Byte-Array aus einem systemeigenen Ausnahme-Debug-Ereignis, das Informationen über ein verwaltetes Debug-Ereignis enthält.  
  
 `countBytes`  
 [in] Die Anzahl der Elemente im `pRecord`-Bytearray.  
  
 `format`  
 in Ein [cordebugrecordformat](cordebugrecordformat-enumeration.md) -Enumerationsmember, der das Format des nicht verwalteten Debug-Ereignisses angibt.  
  
 `dwFlags`  
 [in] Ein Bitfeld, das von der Zielarchitektur abhängt und zusätzliche Informationen über das Debug-Ereignis enthält. Bei Windows-Systemen kann es ein Member der [cordebugdecodeeventflagswindows](cordebugdecodeeventflagswindows-enumeration.md) -Enumeration sein.  
  
 `dwThreadId`  
 [in] Die Betriebssystem-ID des Threads, in dem die Ausnahme ausgelöst wurde.  
  
 `ppEvent`  
 vorgenommen Ein Zeiger auf die Adresse eines [icordebugdebugevent](icordebugdebugevent-interface.md) -Objekts, das ein decodierte verwaltetes Debugereignis darstellt.  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugProcess6-Schnittstelle](icordebugprocess6-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)

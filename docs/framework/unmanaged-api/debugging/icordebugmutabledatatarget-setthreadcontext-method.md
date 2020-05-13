---
title: ICorDebugMutableDataTarget::SetThreadContext Method
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
ms.openlocfilehash: a6df6bf030ad339f5d02b95cd191b30db60aa167
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210149"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a>ICorDebugMutableDataTarget::SetThreadContext Method
Legt den Kontext (Registerwerte) für einen Thread fest.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwThreadID`  
 [in] Der vom Betriebssystem definierte Threadbezeichner.  
  
 `contextSize`  
 [in] Die Größe des zu schreibenden `pContext`-Puffers.  
  
 `pContext`  
 [in] Ein Zeiger auf die zu schreibenden Bytes.  
  
## <a name="remarks"></a>Hinweise  
 Die `SetThreadContext`-Methode aktualisiert den aktuellen Kontext für den Thread, der durch das vom Betriebssystem definierte `dwThreadID`-Argument angegeben wird. Das Format des Kontext Datensatzes wird von der durch die [ICorDebugDataTarget:: GetPlatform](icordebugdatatarget-getplatform-method.md) -Methode festgelegten Plattform bestimmt. Unter Windows handelt es sich hierbei um eine [Kontext](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) Struktur.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugMutableDataTarget-Schnittstelle](icordebugmutabledatatarget-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)

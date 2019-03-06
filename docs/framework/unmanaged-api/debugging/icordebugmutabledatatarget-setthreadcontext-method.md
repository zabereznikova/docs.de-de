---
title: ICorDebugMutableDataTarget::SetThreadContext Method
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbbe4dcec29ba85c64b6e22a4348c56e80daf623
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479188"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a>ICorDebugMutableDataTarget::SetThreadContext Method
Legt den Kontext (Registerwerte) für einen Thread fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
 Die `SetThreadContext`-Methode aktualisiert den aktuellen Kontext für den Thread, der durch das vom Betriebssystem definierte `dwThreadID`-Argument angegeben wird. Das Format des Kontextdatensatzes wird von der Plattform erkennbar bestimmt die [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) Methode. Auf Windows, dies ist eine [Kontext](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) Struktur.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorDebugMutableDataTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

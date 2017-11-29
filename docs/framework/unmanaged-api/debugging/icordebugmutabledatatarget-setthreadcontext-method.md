---
title: ICorDebugMutableDataTarget::SetThreadContext Method
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8c43ef5405ed582cc55af69d7f41887c0615965f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a>ICorDebugMutableDataTarget::SetThreadContext Method
Legt den Kontext (Registerwerte) für einen Thread fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
#### <a name="parameters"></a>Parameter  
 `dwThreadID`  
 [in] Der vom Betriebssystem definierte Threadbezeichner.  
  
 `contextSize`  
 [in] Die Größe des zu schreibenden `pContext`-Puffers.  
  
 `pContext`  
 [in] Ein Zeiger auf die zu schreibenden Bytes.  
  
## <a name="remarks"></a>Hinweise  
 Die `SetThreadContext`-Methode aktualisiert den aktuellen Kontext für den Thread, der durch das vom Betriebssystem definierte `dwThreadID`-Argument angegeben wird. Das Format des Kontextdatensatzes wird von der Plattform erkennbar bestimmt die [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) Methode. Unter Windows ist dies ein [Kontext](http://msdn.microsoft.com/library/windows/desktop/ms679284.aspx) Struktur.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugMutableDataTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

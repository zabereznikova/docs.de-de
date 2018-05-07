---
title: ICorDebugDataTarget::GetThreadContext-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetThreadContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetThreadContext
helpviewer_keywords:
- ICorDebugDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: c8954268-1821-4b23-b665-dbb55f2af31b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ab2fbf6bb08a33158ea450f0f19eca50e280d8c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a>ICorDebugDataTarget::GetThreadContext-Methode
Gibt den aktuellen Kontext des Threads für den angegebenen Thread zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
#### <a name="parameters"></a>Parameter  
 `dwThreadID`  
 [in] Der Bezeichner des Threads, dessen Kontext abgerufen werden. Der Bezeichner wird vom Betriebssystem definiert.  
  
 `contextFlags`  
 [in] Eine bitweise Kombination von plattformabhängigen Flags, die angeben, welche Teile des Kontexts gelesen werden soll.  
  
 `contextSize`  
 [in] Die Größe des `pContext`.  
  
 `pContext`  
 [out] Der Puffer, in der Kontext des Threads gespeichert werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Auf Windows-Plattformen `pContext` muss ein `CONTEXT` -Struktur (in "Winnt.h" definiert), die für den Computertyp gemäß geeignet ist die [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) Methode. `contextFlags` benötigen Sie die gleichen Werte wie die `ContextFlags` Feld der `CONTEXT` Struktur. Die `CONTEXT` Struktur ist prozessorspezifische; die Datei "Winnt.h" Weitere Informationen finden Sie unter.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugDataTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)

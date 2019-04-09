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
ms.openlocfilehash: 2db073f6bde3ded27f8e1aa41bfcb87e764745f1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59174966"
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a>ICorDebugDataTarget::GetThreadContext-Methode
Gibt den Kontext des aktuellen Threads für den angegebenen Thread an.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwThreadID`  
 [in] Der Bezeichner des Threads, dessen Kontext wird abgerufen werden sollen. Der Bezeichner wird vom Betriebssystem definiert.  
  
 `contextFlags`  
 [in] Eine bitweise Kombination der plattformabhängige-Flags, die angeben, welche Teile des Kontexts gelesen werden soll.  
  
 `contextSize`  
 [in] Die Größe des `pContext`.  
  
 `pContext`  
 [out] Der Puffer, in der Kontext des Threads gespeichert werden.  
  
## <a name="remarks"></a>Hinweise  
 Auf Windows-Plattformen `pContext` muss eine `CONTEXT` -Struktur (in "Winnt.h" definiert), die für die Computer den vom angegebenen geeignet ist die [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) Methode. `contextFlags` müssen die gleichen Werte wie die `ContextFlags` Feld der `CONTEXT` Struktur. Die `CONTEXT` Struktur ist, macht prozessorspezifische; die Datei "Winnt.h" Weitere Informationen finden Sie unter.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugDataTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)

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
ms.openlocfilehash: faacea6a2f04ef20025fd33adb4ce76eaf54f32c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679740"
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a>ICorDebugDataTarget::GetThreadContext-Methode

Gibt den aktuellen Thread Kontext für den angegebenen Thread zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
## <a name="parameters"></a>Parameter  

 `dwThreadID`  
 in Der Bezeichner des Threads, dessen Kontext abgerufen werden soll. Der Bezeichner wird vom Betriebssystem definiert.  
  
 `contextFlags`  
 in Eine bitweise Kombination von Platt Form abhängigen Flags, die angeben, welche Teile des Kontexts gelesen werden sollen.  
  
 `contextSize`  
 [in] Die Größe des `pContext`.  
  
 `pContext`  
 vorgenommen Der Puffer, in dem der Thread Kontext gespeichert wird.  
  
## <a name="remarks"></a>Hinweise  

 Auf Windows-Plattformen `pContext` muss eine `CONTEXT` Struktur (in Winnt. h definiert) sein, die für den Computertyp geeignet ist, der durch die [ICorDebugDataTarget:: GetPlatform](icordebugdatatarget-getplatform-method.md) -Methode angegeben wird. `contextFlags` muss die gleichen Werte wie das- `ContextFlags` Feld der- `CONTEXT` Struktur aufweisen. Die `CONTEXT` -Struktur ist Prozessor spezifisch. Weitere Informationen finden Sie in der Datei "Winnt. h".  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugDataTarget-Schnittstelle](icordebugdatatarget-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)

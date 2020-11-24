---
title: ICorDebugRegisterSet::GetThreadContext-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetThreadContext
helpviewer_keywords:
- GetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetThreadContext method [.NET Framework debugging]
ms.assetid: 0f63400b-dc1c-48d6-b51a-75c3f7f28e03
topic_type:
- apiref
ms.openlocfilehash: a7d78daf74d3cc01c2313f092bce53950dbd7bfb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681222"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a>ICorDebugRegisterSet::GetThreadContext-Methode

Ruft den Kontext des aktuellen Threads ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `contextSize`  
 in Die Größe des Arrays in Bytes `context` .  
  
 `context`  
 [in, out] Ein Bytearray, das die Win32- `CONTEXT` Struktur für die aktuelle Plattform zusammensetzt.  
  
## <a name="remarks"></a>Hinweise  

 Der Debugger sollte diese Funktion anstelle der Win32-Funktion aufzurufen `GetThreadContext` , da der Thread sich in einem "geversteckten" Zustand befinden kann, in dem der Kontext vorübergehend geändert wurde. Die zurückgegebenen Daten sind eine Win32- `CONTEXT` Struktur für die aktuelle Plattform.  
  
 Für nicht blattrahmen sollten Clients überprüfen, welche Register gültig sind, indem Sie [icorunbugregisterset:: GetRegistersAvailable](icordebugregisterset-getregistersavailable-method.md)verwenden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugRegisterSet-Schnittstelle](icordebugregisterset-interface.md)
- [ICorDebugRegisterSet2-Schnittstelle](icordebugregisterset2-interface.md)

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
ms.openlocfilehash: 3eace2d91b3bb6e637a659b8b49a31450ebc2c42
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783729"
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
  
## <a name="parameters"></a>Parameters  
 `dwThreadID`  
 in Der Bezeichner des Threads, dessen Kontext abgerufen werden soll. Der Bezeichner wird vom Betriebssystem definiert.  
  
 `contextFlags`  
 in Eine bitweise Kombination von Platt Form abhängigen Flags, die angeben, welche Teile des Kontexts gelesen werden sollen.  
  
 `contextSize`  
 [in] Die Größe des `pContext`.  
  
 `pContext`  
 vorgenommen Der Puffer, in dem der Thread Kontext gespeichert wird.  
  
## <a name="remarks"></a>Hinweise  
 Auf Windows-Plattformen muss `pContext` eine `CONTEXT` Struktur (definiert in "Winnt. h") sein, die für den Computertyp geeignet ist, der durch die [ICorDebugDataTarget:: GetPlatform](icordebugdatatarget-getplatform-method.md) -Methode angegeben wird. `contextFlags` müssen die gleichen Werte wie das `ContextFlags` Feld der `CONTEXT` Struktur aufweisen. Die `CONTEXT`-Struktur ist Prozessor spezifisch. Ausführliche Informationen finden Sie in der Datei "Winnt. h".  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugDataTarget-Schnittstelle](icordebugdatatarget-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)

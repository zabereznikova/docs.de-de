---
title: ICorDebugDataTarget::GetThreadContext-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugDataTarget.GetThreadContext Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugDataTarget::GetThreadContext
helpviewer_keywords:
- ICorDebugDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: c8954268-1821-4b23-b665-dbb55f2af31b
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 543956bb42d7477456426d7327f14b059b23d759
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
 Auf Windows-Plattformen `pContext` muss ein `CONTEXT` -Struktur (in "Winnt.h" definiert), die für den Computertyp gemäß geeignet ist die [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) Methode. `contextFlags`benötigen Sie die gleichen Werte wie die `ContextFlags` Feld der `CONTEXT` Struktur. Die `CONTEXT` Struktur ist prozessorspezifische; die Datei "Winnt.h" Weitere Informationen finden Sie unter.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugDataTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)

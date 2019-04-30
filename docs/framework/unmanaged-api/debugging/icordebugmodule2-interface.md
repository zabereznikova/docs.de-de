---
title: ICorDebugModule2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugModule2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2
helpviewer_keywords:
- ICorDebugModule2 interface [.NET Framework debugging]
ms.assetid: 0847e64f-fdbe-4c96-8168-da20fdc84d80
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3fb1bf3f61c78f4eb157b93363b1c06b25bee04
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987947"
---
# <a name="icordebugmodule2-interface"></a>ICorDebugModule2-Schnittstelle

Fungiert als logische Erweiterung von der ICorDebugModule-Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ApplyChanges-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)|Wendet die Änderungen in den Metadaten und die Änderungen in der Microsoft intermediate Language (MSIL)-Code an den laufenden Prozess an.|  
|[GetJITCompilerFlags-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-getjitcompilerflags-method.md)|Ruft die Flags ab, die steuern, die just-in-Time (JIT)-Kompilierung für diese `ICorDebugModule2`.|  
|[ResolveAssembly-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-resolveassembly-method.md)|Löst die Assembly, die vom angegebenen Metadatentoken verwiesen wird.|  
|[SetJITCompilerFlags-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)|Legt die Flags, die steuern, die JIT-Kompilierung für diese `ICorDebugModule2`.|  
|[SetJMCStatus-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjmcstatus-method.md)|Wird von der Status nur mein Code (JMC) alle Methoden, die alle Klassen in diesem `ICorDebugModule2` auf den angegebenen Wert, mit Ausnahme der `pTokens` Array, das auf den entgegengesetzten Wert festgelegt.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

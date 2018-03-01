---
title: ICorDebugModule2 Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a3d62619fd83264bdc774cc1f09f4d98492d0a57
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodule2-interface1"></a>ICorDebugModule2 Schnittstelle1
Fungiert als logische Erweiterung von ICorDebugModule-Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ApplyChanges-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)|Wendet die Änderungen in den Metadaten und die Änderungen in der Microsoft intermediate Language (MSIL)-Code an den laufenden Prozess an.|  
|[GetJITCompilerFlags-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-getjitcompilerflags-method.md)|Ruft die Flags ab, die die Just-in-Time (JIT)-Kompilierung für diese steuern `ICorDebugModule2`.|  
|[ResolveAssembly-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-resolveassembly-method.md)|Löst die Assembly auf, die vom angegebenen Metadatentoken verwiesen wird.|  
|[SetJITCompilerFlags-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)|Legt die Flags, die steuern, die JIT-Kompilierung für diese `ICorDebugModule2`.|  
|[SetJMCStatus-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjmcstatus-method.md)|Legt den Status nur mein Code (JMC) aller Methoden aller Klassen in diesem `ICorDebugModule2` auf den angegebenen Wert, mit Ausnahme derjenigen in den `pTokens` -Array, das auf den entgegengesetzten Wert festgelegt.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

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
ms.openlocfilehash: a3a1b658f4ab05c7029de907882fe5ab2513ccd8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127889"
---
# <a name="icordebugmodule2-interface"></a>ICorDebugModule2-Schnittstelle

Dient als logische Erweiterung der ICorDebugModule-Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ApplyChanges-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)|Wendet die Änderungen an den Metadaten und den Änderungen im MSIL-Code (Microsoft Intermediate Language) auf den laufenden Prozess an.|  
|[GetJITCompilerFlags-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-getjitcompilerflags-method.md)|Ruft die Flags ab, die die JIT-Kompilierung (Just-in-Time) für dieses `ICorDebugModule2`steuern.|  
|[ResolveAssembly-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-resolveassembly-method.md)|Löst die Assembly auf, auf die vom angegebenen Metadatentoken verwiesen wird.|  
|[SetJITCompilerFlags-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)|Legt die Flags fest, die die JIT-Kompilierung für dieses `ICorDebugModule2`steuern.|  
|[SetJMCStatus-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjmcstatus-method.md)|Legt den nur eigenen Code (JMC)-Status aller Methoden aller Klassen in diesem `ICorDebugModule2` auf den angegebenen Wert fest, mit Ausnahme derjenigen im `pTokens` Array, die auf den umgekehrten Wert festgelegt werden.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

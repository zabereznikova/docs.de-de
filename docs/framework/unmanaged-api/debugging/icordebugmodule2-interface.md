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
ms.openlocfilehash: 32774aacecf3e56510bc6f0670538a44fde794c9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792987"
---
# <a name="icordebugmodule2-interface"></a>ICorDebugModule2-Schnittstelle

Dient als logische Erweiterung der ICorDebugModule-Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[ApplyChanges-Methode](icordebugmodule2-applychanges-method.md)|Wendet die Änderungen an den Metadaten und den Änderungen im MSIL-Code (Microsoft Intermediate Language) auf den laufenden Prozess an.|  
|[GetJITCompilerFlags-Methode](icordebugmodule2-getjitcompilerflags-method.md)|Ruft die Flags ab, die die JIT-Kompilierung (Just-in-Time) für dieses `ICorDebugModule2`steuern.|  
|[ResolveAssembly-Methode](icordebugmodule2-resolveassembly-method.md)|Löst die Assembly auf, auf die vom angegebenen Metadatentoken verwiesen wird.|  
|[SetJITCompilerFlags-Methode](icordebugmodule2-setjitcompilerflags-method.md)|Legt die Flags fest, die die JIT-Kompilierung für dieses `ICorDebugModule2`steuern.|  
|[SetJMCStatus-Methode](icordebugmodule2-setjmcstatus-method.md)|Legt den nur eigenen Code (JMC)-Status aller Methoden aller Klassen in diesem `ICorDebugModule2` auf den angegebenen Wert fest, mit Ausnahme derjenigen im `pTokens` Array, die auf den umgekehrten Wert festgelegt werden.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](debugging-interfaces.md)

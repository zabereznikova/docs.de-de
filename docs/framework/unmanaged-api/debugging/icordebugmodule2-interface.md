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
ms.openlocfilehash: 2b8e6048dd6b8df71ac3dddcc4397f6d512127c7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695880"
---
# <a name="icordebugmodule2-interface"></a>ICorDebugModule2-Schnittstelle

Dient als logische Erweiterung der ICorDebugModule-Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[ApplyChanges-Methode](icordebugmodule2-applychanges-method.md)|Wendet die Änderungen an den Metadaten und den Änderungen im MSIL-Code (Microsoft Intermediate Language) auf den laufenden Prozess an.|  
|[GetJITCompilerFlags-Methode](icordebugmodule2-getjitcompilerflags-method.md)|Ruft die Flags ab, die die JIT-Kompilierung (Just-in-Time) für dieses Steuerelement steuern `ICorDebugModule2` .|  
|[ResolveAssembly-Methode](icordebugmodule2-resolveassembly-method.md)|Löst die Assembly auf, auf die vom angegebenen Metadatentoken verwiesen wird.|  
|[SetJITCompilerFlags-Methode](icordebugmodule2-setjitcompilerflags-method.md)|Legt die Flags fest, die die JIT-Kompilierung für dieses Steuern `ICorDebugModule2` .|  
|[SetJMCStatus-Methode](icordebugmodule2-setjmcstatus-method.md)|Legt den JMC-Status (nur eigenen Code) aller Methoden aller-Klassen in diesem `ICorDebugModule2` auf den angegebenen Wert fest, mit Ausnahme der Werte im- `pTokens` Array, die auf den umgekehrten Wert festgelegt werden.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)

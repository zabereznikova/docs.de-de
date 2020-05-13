---
title: ICorDebugModule2::SetJITCompilerFlags-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.SetJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJITCompilerFlags
helpviewer_keywords:
- ICorDebugModule2::SetJITCompilerFlags method [.NET Framework debugging]
- SetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: ea574c84-c622-4589-9a14-b55771af5e06
topic_type:
- apiref
ms.openlocfilehash: f73919634ba15dfd16694676d1389875fc2d79bc
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210188"
---
# <a name="icordebugmodule2setjitcompilerflags-method"></a>ICorDebugModule2::SetJITCompilerFlags-Methode
Legt die Flags fest, die die Just-in-time (JIT)-Kompilierung dieses ICorDebugModule2 steuern.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetJITCompilerFlags (  
    [in] DWORD dwFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwFlags`  
 in Eine bitweise Kombination der [cordbugjitcompilerflags-Enumerationswerte](cordebugjitcompilerflags-enumeration.md) .  
  
## <a name="remarks"></a>Hinweise  
 Wenn der `dwFlags` Wert ungültig ist, `SetJITCompilerFlags` schlägt die Methode fehl.  
  
 Die- `SetJITCompilerFlags` Methode kann nur innerhalb des [ICorDebugManagedCallback:: LoadModule](icordebugmanagedcallback-loadmodule-method.md) -Rückrufs für dieses Modul aufgerufen werden. Wenn versucht wird, Sie nach dem Übermitteln des Rückrufs aufzurufen, `ICorDebugManagedCallback::LoadModule` schlägt fehl.  
  
 "Bearbeiten und Fortfahren" wird auf den Plattformen 64-Bit oder Win9x nicht unterstützt. Wenn Sie also die `SetJITCompilerFlags` -Methode auf einer dieser beiden Plattformen mit dem in festgelegten CORDEBUG_JIT_ENABLE_ENC Flag aufzurufen, `dwFlags` `SetJITCompilerFlags` schlagen die-Methode und alle Methoden, die für "Bearbeiten und Fortfahren" spezifisch sind, wie z. b. [ICorDebugModule2:: ApplyChanges](icordebugmodule2-applychanges-method.md), fehl.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

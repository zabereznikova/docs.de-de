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
ms.openlocfilehash: 2358cee1b3a9aa50fb1f0e61d558f164a39aa86c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137364"
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
 in Eine bitweise Kombination der [cordbugjitcompilerflags-Enumerationswerte](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) .  
  
## <a name="remarks"></a>Hinweise  
 Wenn der `dwFlags` Wert ungültig ist, tritt bei der `SetJITCompilerFlags` Methode ein Fehler auf.  
  
 Die `SetJITCompilerFlags`-Methode kann nur innerhalb des [ICorDebugManagedCallback:: LoadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md) -Rückrufs für dieses Modul aufgerufen werden. Wenn versucht wird, Sie nach dem Übermitteln des `ICorDebugManagedCallback::LoadModule` Rückrufs aufzurufen, schlägt fehl.  
  
 "Bearbeiten und Fortfahren" wird auf den Plattformen 64-Bit oder Win9x nicht unterstützt. Wenn Sie die `SetJITCompilerFlags`-Methode auf einer dieser beiden Plattformen mit dem in `dwFlags`festgelegten CORDEBUG_JIT_ENABLE_ENC-Flag aufzurufen, schlagen die `SetJITCompilerFlags`-Methode und alle Methoden, die für "Bearbeiten und Fortfahren" spezifisch sind, z. b. " [ICorDebugModule2:: ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)", fehl.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 114f4ff261d9612a81d17bf5b3df2f87323f77f2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764202"
---
# <a name="icordebugmodule2setjitcompilerflags-method"></a>ICorDebugModule2::SetJITCompilerFlags-Methode
Legt die Flags, die just-in-Time (JIT)-Kompilierung für dieses ICorDebugModule2 steuern.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetJITCompilerFlags (  
    [in] DWORD dwFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwFlags`  
 [in] Eine bitweise Kombination der [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) -Enumerationswerte fest.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die `dwFlags` Wert ist ungültig, die `SetJITCompilerFlags` Methode fehl.  
  
 Die `SetJITCompilerFlags` Methode kann aufgerufen werden, nur von innerhalb der [ICorDebugManagedCallback:: LoadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md) Rückruf für dieses Modul. Versucht, sie aufzurufen, nachdem die `ICorDebugManagedCallback::LoadModule` Rückruf übermittelt wurde, fehl.  
  
 Bearbeiten und Fortfahren wird auf 64-Bit- oder Win9x-Plattformen nicht unterstützt. Aus diesem Grund Aufrufen der `SetJITCompilerFlags` Methode entweder mit dem CORDEBUG_JIT_ENABLE_ENC-Flag festlegen, die dieser beiden Plattformen `dwFlags`, `SetJITCompilerFlags` -Methode und alle spezifischen Methoden zu bearbeiten und fortfahren, wie z. B. [ICorDebugModule2:: ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md), schlägt fehl.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

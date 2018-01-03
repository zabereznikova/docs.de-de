---
title: ICorDebugProcess2::SetDesiredNGENCompilerFlags-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess2.SetDesiredNGENCompilerFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess2::SetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags method [.NET Framework debugging]
- SetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: 98320175-7c5e-4dbb-8683-86fa82e2641f
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f8c5ac4fab96ac7ec3a2b086dbc34763dde08dc2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a>ICorDebugProcess2::SetDesiredNGENCompilerFlags-Methode
Legt die Flags, die in einem vorkompilierten Abbild in der Reihenfolge für die Laufzeit das Abbild in den aktuellen Prozess lädt eingebettet werden müssen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pdwFlags`  
 [in] Der Wert der [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) Enumeration, der angibt, die Compilerflags verwendet wird, um das richtige Bild für die vorkompilierte auszuwählen.  
  
## <a name="remarks"></a>Hinweise  
 Die `SetDesiredNGENCompilerFlags` -Methode gibt die Flags, die in einem vorkompilierten Abbild eingebettet sein müssen, damit die Laufzeit das Abbild in diesem Prozess geladen werden. Die Flags, die von dieser Methode festgelegte dienen nur, um das richtige vorkompilierte Abbild auszuwählen. Wenn kein solches Image vorhanden ist, wird die Common Language Runtime die Microsoft intermediate Language (MSIL)-Image und der Just-in-Time (JIT)-Compiler stattdessen geladen. In diesem Fall muss der Debugger weiterhin verwenden die [ICorDebugModule2:: SetJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md) Methode, um die Flags für die JIT-Kompilierung wie gewünscht festgelegt.  
  
 Wenn ein Image geladen wird, aber einige JIT-Kompilierung für erfolgen muss sich das Bild (das der Fall sein wird, wenn das Bild Generika enthält), die vom angegebenen Compilerflags die `SetDesiredNGENCompilerFlags` Methode gilt für die zusätzliche JIT-Kompilierung.  
  
 Die `SetDesiredNGENCompilerFlags` -Methode muss aufgerufen werden, während die [ICorDebugManagedCallback:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) Rückruf. Versucht, rufen Sie die `SetDesiredNGENCompilerFlags` Methode danach schlägt fehl. Darüber hinaus versuchen, Flags festzulegen, die entweder nicht definiert, der `CorDebugJITCompilerFlags` fehl, Enumeration oder sind nicht zulässig für den angegebenen Prozess.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [ICorDebugManagedCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)

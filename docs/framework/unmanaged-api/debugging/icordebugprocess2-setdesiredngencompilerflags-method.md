---
title: ICorDebugProcess2::SetDesiredNGENCompilerFlags-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.SetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags method [.NET Framework debugging]
- SetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: 98320175-7c5e-4dbb-8683-86fa82e2641f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e061c3f3dc95e63339d6fd5f82b3cb4d38a4b6c6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206706"
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a>ICorDebugProcess2::SetDesiredNGENCompilerFlags-Methode
Legt die Flags, die in einem vorkompilierten Abbild in der Reihenfolge für die Laufzeit beim Laden von Images in den aktuellen Prozess eingebettet werden müssen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pdwFlags`  
 [in] Der Wert der [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) Enumeration, der angibt, die Compilerflags verwendet, um das richtige vorkompilierte Abbild auszuwählen.  
  
## <a name="remarks"></a>Hinweise  
 Die `SetDesiredNGENCompilerFlags` -Methode gibt die Flags, die in einem vorkompilierten Abbild eingebettet werden müssen, damit die Laufzeit dieses Abbild in diesen Prozess geladen werden. Die Flags, die von dieser Methode festgelegte werden verwendet, nur für die richtige vorkompilierte Abbild auszuwählen. Wenn kein solches Image vorhanden ist, wird die Laufzeit die Microsoft intermediate Language (MSIL)-Image und der just-in-Time-Compiler (JIT) stattdessen geladen werden. In diesem Fall muss der Debugger weiterhin verwenden die [ICorDebugModule2:: SetJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md) Methode, um die Flags für die JIT-Kompilierung wie gewünscht festgelegt.  
  
 Wenn ein Image geladen wird, aber einige JIT-Kompilierung erfolgen muss für das Bild (das der Fall sein wird, wenn das Bild Generika enthält), die vom angegebenen Compilerflags der `SetDesiredNGENCompilerFlags` Methode gilt für die zusätzliche JIT-Kompilierung.  
  
 Die `SetDesiredNGENCompilerFlags` -Methode muss aufgerufen werden, während die [ICorDebugManagedCallback:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) Rückruf. Versucht, rufen Sie die `SetDesiredNGENCompilerFlags` Methode danach schlägt fehl. Darüber hinaus versuchen, Flags festzulegen, die entweder nicht definiert, der `CorDebugJITCompilerFlags` Enumeration sind nicht zulässig, für den Prozess ein Fehler auf.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [ICorDebugManagedCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)

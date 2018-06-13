---
title: ICorDebugEval::CallFunction-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CallFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CallFunction
helpviewer_keywords:
- ICorDebugEval::CallFunction method [.NET Framework debugging]
- CallFunction method [.NET Framework debugging]
ms.assetid: 7f470c5c-e1c0-4d8d-aad8-830f113ae751
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 86d48461c601b53d4461331a11a0e0ac7ddc6e7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412546"
---
# <a name="icordebugevalcallfunction-method"></a>ICorDebugEval::CallFunction-Methode
Richtet einen Aufruf der angegebenen Funktion.  
  
 Diese Methode ist veraltet in .NET Framework, Version 2.0. Verwendung [ICorDebugEval2:: CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) stattdessen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CallFunction (  
    [in] ICorDebugFunction  *pFunction,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pFunction`  
 [in] Ein Zeiger auf ein ICorDebugFunction-Objekt, das die aufzurufende Funktion angibt.  
  
 `nArgs`  
 [in] Die Anzahl von Argumenten für die Funktion.  
  
 `ppArgs`  
 [in] Ein Array von Zeigern, von denen jedes auf ICorDebugValue-Objekts verweist, der angibt, ein Argument an die Funktion übergeben werden.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Funktion virtuell ist, wird `CallFunction` virtuellen Dispatch führt. Wenn die Funktion in einer anderen Anwendungsdomäne ist, wird ein Übergang erfolgen, solange alle Argumente in der Anwendungsdomäne ebenfalls enthalten sind.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** WindowSee [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** 1.1, 1.0  
  
## <a name="see-also"></a>Siehe auch  
 [CallParameterizedFunction-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)

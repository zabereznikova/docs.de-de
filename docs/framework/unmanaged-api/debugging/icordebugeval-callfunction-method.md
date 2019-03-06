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
ms.openlocfilehash: 66e51dc15f7d44ede26634571fa04c58e9735694
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364150"
---
# <a name="icordebugevalcallfunction-method"></a>ICorDebugEval::CallFunction-Methode

Richtet einen Aufruf der angegebenen Funktion.

Diese Methode ist in .NET Framework, Version 2.0, veraltet. Verwendung [ICorDebugEval2:: CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md) stattdessen.

## <a name="syntax"></a>Syntax

```cpp
HRESULT CallFunction (
    [in] ICorDebugFunction  *pFunction,
    [in] ULONG32            nArgs,
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]
);
```

## <a name="parameters"></a>Parameter

`pFunction`\
[in] Zeiger auf ein ICorDebugFunction-Objekt, das die aufzurufende Funktion angibt.

`nArgs`\
[in] Die Anzahl der Argumente für die Funktion.

`ppArgs`\
[in] Ein Array von Zeigern, von denen jeder zu einem ICorDebugValue-Objekt verweist, der angibt, ein Argument an die Funktion übergeben werden.

## <a name="remarks"></a>Hinweise

Wenn die Funktion virtuell, `CallFunction` virtuellen Dispatch führt. Wenn die Funktion in einer anderen Anwendungsdomäne ist, wird ein Übergang erfolgen, solange alle Argumente in dieser Anwendungsdomäne ebenfalls enthalten sind.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** CorDebug.idl, CorDebug.h

**Bibliothek:** CorGuids.lib

**.NET Framework-Versionen:** 1.1, 1.0

## <a name="see-also"></a>Siehe auch

- [CallParameterizedFunction-Methode](icordebugeval2-callparameterizedfunction-method.md)
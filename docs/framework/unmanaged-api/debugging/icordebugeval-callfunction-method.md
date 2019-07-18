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
ms.openlocfilehash: 65225281fe3abaa20e69e96f4cd4d2a4b03a87ce
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65629939"
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

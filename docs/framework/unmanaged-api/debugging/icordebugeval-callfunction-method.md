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
ms.openlocfilehash: 4ac26ef4449dc02230f26b1247616b4587d217b7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73085156"
---
# <a name="icordebugevalcallfunction-method"></a>ICorDebugEval::CallFunction-Methode

Richtet einen Rückruf für die angegebene Funktion ein.

Diese Methode ist in der .NET Framework Version 2,0 veraltet. Verwenden Sie stattdessen [ICorDebugEval2:: CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md) .

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
in Zeiger auf ein ICorDebug Function-Objekt, das die aufzurufende Funktion angibt.

`nArgs`\
in Die Anzahl von Argumenten für die Funktion.

`ppArgs`\
in Ein Array von Zeigern, von denen jedes auf ein ICorDebug Value-Objekt verweist, das ein Argument angibt, das an die Funktion übergeben werden soll.

## <a name="remarks"></a>Hinweise

Wenn die Funktion virtuell ist, führt `CallFunction` eine virtuelle Dispatch aus. Wenn sich die Funktion in einer anderen Anwendungsdomäne befindet, tritt ein Übergang auf, solange sich alle Argumente auch in dieser Anwendungsdomäne befinden.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** CorDebug.idl, CorDebug.h

**Bibliothek:** CorGuids.lib

**.NET Framework Versionen:** 1,1, 1,0

## <a name="see-also"></a>Siehe auch

- [CallParameterizedFunction-Methode](icordebugeval2-callparameterizedfunction-method.md)

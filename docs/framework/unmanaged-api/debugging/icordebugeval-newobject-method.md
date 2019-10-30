---
title: ICorDebugEval::NewObject-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewObject
helpviewer_keywords:
- NewObject method [.NET Framework debugging]
- ICorDebugEval::NewObject method [.NET Framework debugging]
ms.assetid: ce3025e8-defa-4c5e-8298-f49d71fa5736
topic_type:
- apiref
ms.openlocfilehash: 68a7e911c2bd1798ea8f34f6a6e24299fe68775d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137623"
---
# <a name="icordebugevalnewobject-method"></a>ICorDebugEval::NewObject-Methode
Ordnet eine neue Objektinstanz zu und ruft die angegebene Konstruktormethode auf.  
  
 Diese Methode ist in der .NET Framework Version 2,0 veraltet. Verwenden Sie stattdessen [ICorDebugEval2:: NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) .  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT NewObject (  
    [in] ICorDebugFunction  *pConstructor,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pConstructor`  
 in Der aufzurufende Konstruktor.  
  
 `nArgs`  
 [in] Die Größe des `ppArgs`-Arrays.  
  
 `ppArgs`  
 in Ein Array von ICorDebugValue-Objekten, von denen jedes ein Argument darstellt, das an den Konstruktor übergeben werden soll.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** 1,1, 1,0  
  
## <a name="see-also"></a>Siehe auch

- [NewParameterizedObject-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)

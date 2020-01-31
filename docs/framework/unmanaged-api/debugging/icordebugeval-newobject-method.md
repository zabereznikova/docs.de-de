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
ms.openlocfilehash: 38cc98f1bfd966d1f764e43b30003a2bae66297d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793473"
---
# <a name="icordebugevalnewobject-method"></a>ICorDebugEval::NewObject-Methode
Ordnet eine neue Objektinstanz zu und ruft die angegebene Konstruktormethode auf.  
  
 Diese Methode ist in der .NET Framework Version 2,0 veraltet. Verwenden Sie stattdessen [ICorDebugEval2:: NewParameterizedObject](icordebugeval2-newparameterizedobject-method.md) .  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT NewObject (  
    [in] ICorDebugFunction  *pConstructor,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `pConstructor`  
 in Der aufzurufende Konstruktor.  
  
 `nArgs`  
 [in] Die Größe des `ppArgs`-Arrays.  
  
 `ppArgs`  
 in Ein Array von ICorDebugValue-Objekten, von denen jedes ein Argument darstellt, das an den Konstruktor übergeben werden soll.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** 1,1, 1,0  
  
## <a name="see-also"></a>Siehe auch

- [NewParameterizedObject-Methode](icordebugeval2-newparameterizedobject-method.md)

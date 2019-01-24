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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ff4f86105fd1dfbd12360c01046492f3a6dbdcd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54589893"
---
# <a name="icordebugevalnewobject-method"></a>ICorDebugEval::NewObject-Methode
Reserviert eine neue Objektinstanz, und der angegebene Konstruktor-Methode aufgerufen.  
  
 Diese Methode ist in .NET Framework, Version 2.0, veraltet. Verwendung [ICorDebugEval2:: NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) stattdessen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT NewObject (  
    [in] ICorDebugFunction  *pConstructor,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pConstructor`  
 [in] Der Konstruktor aufgerufen werden soll.  
  
 `nArgs`  
 [in] Die Größe des `ppArgs`-Arrays.  
  
 `ppArgs`  
 [in] Ein Array von ICorDebugValue-Objekten, von denen jeder ein Argument an den Konstruktor zu übergebenden darstellt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** 1.1, 1.0  
  
## <a name="see-also"></a>Siehe auch
- [NewParameterizedObject-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)

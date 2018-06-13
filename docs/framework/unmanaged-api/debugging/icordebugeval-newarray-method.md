---
title: ICorDebugEval::NewArray-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewArray
helpviewer_keywords:
- NewArray method [.NET Framework debugging]
- ICorDebugEval::NewArray method [.NET Framework debugging]
ms.assetid: cc79a67d-5368-434d-a943-209db90491b9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38b00d903fdd7301415a8df7642e12366178fd10
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413939"
---
# <a name="icordebugevalnewarray-method"></a>ICorDebugEval::NewArray-Methode
Ordnet ein neues Array mit den angegebenen Elementtyp und Dimensionen an.  
  
 Diese Methode ist veraltet in .NET Framework, Version 2.0. Verwendung [ICorDebugEval2:: NewParameterizedArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) stattdessen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT NewArray (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [in] ULONG32            rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `elementType`  
 [in] Der Wert der CorElementType-Enumeration, die den Elementtyp des Arrays angibt.  
  
 `pElementClass`  
 [in] Ein Zeiger auf eine ICorDebugClass-Objekt, das die Klasse des Elements angibt. Dieser Wert kann null sein, wenn der Elementtyp ein primitiver Typ ist.  
  
 `rank`  
 [in] Die Anzahl der Dimensionen des Arrays. In .NET Framework 2.0 muss dieser Wert 1 sein.  
  
 `dims`  
 [in] Die Größe der einzelnen Dimensionen des Arrays in Bytes.  
  
 `lowBounds`  
 [in] Optional. Die untere Grenze der einzelnen Dimensionen des Arrays. Wenn dieser Wert ausgelassen wird, wird eine Untergrenze von 0 (null) für jede Dimension angenommen.  
  
## <a name="remarks"></a>Hinweise  
 Das Array wird immer in der Anwendungsdomäne erstellt, in dem der Thread gerade ausgeführt wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** 1.1, 1.0

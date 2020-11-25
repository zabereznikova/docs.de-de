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
ms.openlocfilehash: ef6cbe2cef3c52d9a4b47ff77e8aeb5159e89c76
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729758"
---
# <a name="icordebugevalnewarray-method"></a>ICorDebugEval::NewArray-Methode

Ordnet ein neues Array vom angegebenen Elementtyp und den angegebenen Dimensionen zu.  
  
 Diese Methode ist in der .NET Framework Version 2,0 veraltet. Verwenden Sie stattdessen [ICorDebugEval2:: NewParameterizedArray](icordebugeval2-newparameterizedarray-method.md) .  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT NewArray (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [in] ULONG32            rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `elementType`  
 in Ein Wert der CorElementType-Enumeration, der den Elementtyp des Arrays angibt.  
  
 `pElementClass`  
 in Ein Zeiger auf ein ICorDebugClass-Objekt, das die-Klasse des-Elements angibt. Dieser Wert kann NULL sein, wenn der Elementtyp ein primitiver Typ ist.  
  
 `rank`  
 in Die Anzahl der Dimensionen des Arrays. In der .NET Framework 2,0 muss dieser Wert 1 lauten.  
  
 `dims`  
 in Die Größe der einzelnen Dimensionen des Arrays in Bytes.  
  
 `lowBounds`  
 [in] Optional. Die untere Grenze jeder Dimension des Arrays. Wenn dieser Wert weggelassen wird, wird für jede Dimension eine untere Grenze von 0 (null) angenommen.  
  
## <a name="remarks"></a>Hinweise  

 Das Array wird immer in der Anwendungsdomäne erstellt, in der der Thread gerade ausgeführt wird.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** 1,1, 1,0

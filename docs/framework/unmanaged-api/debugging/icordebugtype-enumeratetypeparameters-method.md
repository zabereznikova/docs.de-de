---
title: ICorDebugType::EnumerateTypeParameters-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugType.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 1ee1f6e6-1bd7-4ebb-83b8-ff9a08ca03de
topic_type:
- apiref
ms.openlocfilehash: 3717497ab6e72f0ce67f688813ee7264206e8c84
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727951"
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a>ICorDebugType::EnumerateTypeParameters-Methode

Ruft einen Schnittstellen Zeiger auf eine icordebugtypeenumeration ab, die die <xref:System.Type> Parameter der Klasse enthält, auf die von diesem ICorDebugType verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `ppTyParEnum`  
 vorgenommen Ein Zeiger auf die Adresse eines- `ICorDebugTypeEnum` Parameters, der die Parameter des Typs enthält.  
  
## <a name="remarks"></a>Hinweise  

 Sie können verwenden, `EnumerateTypeParameters` Wenn der von [ICorDebugType:: GetType](icordebugtype-gettype-method.md) zurückgegebene CorElementType-Wert ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR oder ELEMENT_TYPE_FNPTR ist. Die Anzahl der Parameter und deren Reihenfolge hängt vom Typ ab:  
  
- ELEMENT_TYPE_CLASS oder ELEMENT_TYPE_VALUETYPE: die Anzahl von Typparametern, die in der enthalten sind, die von `ICorDebugTypeEnum` dieser Methode zurückgegeben wird, hängt von der Anzahl der formalen Typparameter für die entsprechende Klasse ab. Wenn der Typ z. b. ist `class Dict<String,int32>` , gibt `EnumerateTypeParameters` ein zurück `ICorDebugTypeEnum` , das-Objekte enthält, die `String` und nacheinander darstellen `int32` .  
  
- ELEMENT_TYPE_FNPTR: die Anzahl der Typparameter, die in der enthalten sind, `ICorDebugTypeEnum` ist ein Wert größer als die Anzahl der von der Funktion akzeptierten Argumente. Der erste in der enthaltene Typparameter `ICorDebugTypeEnum` ist der Rückgabetyp für die Funktion, und die nachfolgenden Typparameter sind die Parameter der Funktion.  
  
- ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF oder ELEMENT_TYPE_PTR: ein Typparameter wird zurückgegeben. Wenn der Typ z. b. ein Arraytyp wie ist `int32[]` , gibt `EnumerateTypeParameters` einen zurück, der `ICorDebugTypeEnum` ein Objekt enthält, das darstellt `int32` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

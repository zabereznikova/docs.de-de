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
ms.openlocfilehash: b2c381d093069f5ee86be1b19d75f5c2d69ad9fa
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791312"
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a>ICorDebugType::EnumerateTypeParameters-Methode
Ruft einen Schnittstellen Zeiger auf eine icordebugtypeenumeration ab, die die <xref:System.Type> Parameter der Klasse enthält, auf die von diesem ICorDebugType verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `ppTyParEnum`  
 vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugTypeEnum`, der die Parameter des Typs enthält.  
  
## <a name="remarks"></a>Hinweise  
 Sie können `EnumerateTypeParameters` verwenden, wenn der von [ICorDebugType:: GetType](icordebugtype-gettype-method.md) zurückgegebene Wert von "CorElementType" ELEMENT_TYPE_CLASS, ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_PTR oder ELEMENT_TYPE_FNPTR ist. Die Anzahl der Parameter und deren Reihenfolge hängt vom Typ ab:  
  
- ELEMENT_TYPE_CLASS oder ELEMENT_TYPE_VALUETYPE: die Anzahl der Typparameter in der `ICorDebugTypeEnum`, die von dieser Methode zurückgegeben wird, hängt von der Anzahl der formalen Typparameter für die entsprechende Klasse ab. Wenn der Typ z. b. `class Dict<String,int32>`ist, gibt `EnumerateTypeParameters` eine `ICorDebugTypeEnum` zurück, die-Objekte enthält, die `String` und `int32` nacheinander darstellen.  
  
- ELEMENT_TYPE_FNPTR: die Anzahl der Typparameter, die in der `ICorDebugTypeEnum` enthalten sind, ist ein Wert größer als die Anzahl der von der Funktion akzeptierten Argumente. Der erste Typparameter, der in der `ICorDebugTypeEnum` enthalten ist, ist der Rückgabetyp für die Funktion, und die nachfolgenden Typparameter sind die Parameter der Funktion.  
  
- ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF oder ELEMENT_TYPE_PTR: ein Typparameter wird zurückgegeben. Wenn der Typ z. b. ein Arraytyp ist, z. b. `int32[]`, gibt`EnumerateTypeParameters` einen `ICorDebugTypeEnum` zurück, der ein Objekt enthält, das `int32`darstellt.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

---
title: ICorDebugEval2::NewParameterizedArray-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedArray
helpviewer_keywords:
- ICorDebugEval2::NewParameterizedArray method [.NET Framework debugging]
- NewParameterizedArray method [.NET Framework debugging]
ms.assetid: 45efb8ba-c4de-4109-945f-e734d376b43c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 973f975885bbbf5cbed74adef7b9f4f423c42583
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753653"
---
# <a name="icordebugeval2newparameterizedarray-method"></a>ICorDebugEval2::NewParameterizedArray-Methode
Ordnet ein neues Array mit den angegebenen Elementtyp und Dimensionen an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT NewParameterizedArray(  
    [in] ICorDebugType          *pElementType,  
    [in] ULONG32                rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pElementType`  
 [in] Ein Zeiger auf ein ICorDebugType-Objekt, das den Typ des im Array gespeicherten Elements darstellt.  
  
 `rank`  
 [in] Die Anzahl der Dimensionen des Arrays. In .NET Framework, Version 2.0 muss dieser Wert als 1 sein.  
  
 `dims`  
 [in] Die Größe der einzelnen Dimensionen des Arrays in Bytes.  
  
 `lowBounds`  
 [in] Optional. Die untere Grenze der einzelnen Dimensionen des Arrays. Wenn dieser Wert ausgelassen wird, wird eine Untergrenze von 0 (null) für jede Dimension ausgegangen.  
  
## <a name="remarks"></a>Hinweise  
 Die Elemente des Arrays können es sich um Instanzen eines generischen Typs sein. Das Array wird immer in der Anwendungsdomäne erstellt, in dem der Thread gerade ausgeführt wird. In .NET Framework 2.0, den Wert der `rank` muss 1 sein.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

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
ms.openlocfilehash: 552d2fa8a7c35066e32fb9f8e9455b3092b1e65b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413279"
---
# <a name="icordebugeval2newparameterizedarray-method"></a>ICorDebugEval2::NewParameterizedArray-Methode
Ordnet ein neues Array mit den angegebenen Elementtyp und Dimensionen an.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT NewParameterizedArray(  
    [in] ICorDebugType          *pElementType,  
    [in] ULONG32                rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pElementType`  
 [in] Ein Zeiger auf ein ICorDebugType-Objekt, das den Typ des im Array gespeicherten Elements darstellt.  
  
 `rank`  
 [in] Die Anzahl der Dimensionen des Arrays. In .NET Framework, Version 2.0 muss dieser Wert 1 sein.  
  
 `dims`  
 [in] Die Größe der einzelnen Dimensionen des Arrays in Bytes.  
  
 `lowBounds`  
 [in] Optional. Die untere Grenze der einzelnen Dimensionen des Arrays. Wenn dieser Wert ausgelassen wird, wird eine Untergrenze von 0 (null) für jede Dimension angenommen.  
  
## <a name="remarks"></a>Hinweise  
 Die Elemente des Arrays möglicherweise Instanzen eines generischen Typs. Das Array wird immer in der Anwendungsdomäne erstellt, in dem der Thread gerade ausgeführt wird. In .NET Framework 2.0, den Wert des `rank` muss 1 sein.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

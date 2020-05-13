---
title: ICorDebugType::GetFirstTypeParameter-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetFirstTypeParameter
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetFirstTypeParameter
helpviewer_keywords:
- ICorDebugType::GetFirstTypeParameter method [.NET Framework debugging]
- GetFirstTypeParameter method [.NET Framework debugging]
ms.assetid: 35bb594f-af6a-4349-83fe-e98702674e03
topic_type:
- apiref
ms.openlocfilehash: da0097daea183c76f97f0b1966b313e1cb5a557b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379950"
---
# <a name="icordebugtypegetfirsttypeparameter-method"></a>ICorDebugType::GetFirstTypeParameter-Methode
Ruft einen Schnittstellen Zeiger auf einen ICorDebugType ab, der den ersten <xref:System.Type> Parameter des Typs darstellt, der durch diesen dargestellt wird `ICorDebugType` .  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetFirstTypeParameter (  
    [out] ICorDebugType   **value  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `value`  
 vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugType` Objekts, das den ersten Parameter darstellt.  
  
## <a name="remarks"></a>Hinweise  
 `GetFirstTypeParameter`kann in Fällen aufgerufen werden, in denen die zusätzlichen Informationen über den Typ höchstens einen Typparameter umfassen. Insbesondere kann Sie verwendet werden, wenn der Typ eine ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF oder ELEMENT_TYPE_PTR ist, wie durch die [ICorDebugType:: GetType](icordebugtype-gettype-method.md) -Methode angegeben.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

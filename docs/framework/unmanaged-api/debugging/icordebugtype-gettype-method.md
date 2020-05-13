---
title: ICorDebugType::GetType-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetType
helpviewer_keywords:
- ICorDebugType::GetType method [.NET Framework debugging]
- GetType method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: d6e64534-4d47-4ad0-a340-7590e07e2b4a
topic_type:
- apiref
ms.openlocfilehash: ac42c6254182ea775377a448a54d527b234c97dc
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379923"
---
# <a name="icordebugtypegettype-method"></a>ICorDebugType::GetType-Methode
Ruft einen korelementtype-Wert ab, der den systemeigenen Typ des Common Language Runtime (CLR) beschreibt, der <xref:System.Type> durch diesen ICorDebugType dargestellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ty`  
 vorgenommen Ein Zeiger auf einen Wert der- `CorElementType` Enumeration, der die CLR angibt <xref:System.Type> , die dieser `ICorDebugType` darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Wert von `ty` entweder ELEMENT_TYPE_CLASS oder ELEMENT_TYPE_VALUETYPE ist, kann die [ICorDebugType:: GetClass](icordebugtype-getclass-method.md) -Methode aufgerufen werden, um den nicht instanziierten Typ für einen generischen Typ abzurufen. andernfalls dürfen Sie nicht aufrufen `ICorDebugType::GetClass` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

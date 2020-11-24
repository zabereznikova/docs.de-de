---
title: ICorDebugType::GetClass-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetClass
helpviewer_keywords:
- ICorDebugType::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: 2644f48b-db3c-429f-ae62-76f1c98a1af5
topic_type:
- apiref
ms.openlocfilehash: 1cb9729f175a2e82e88386b0694467c6fe05636a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684459"
---
# <a name="icordebugtypegetclass-method"></a>ICorDebugType::GetClass-Methode

Ruft einen Schnittstellen Zeiger auf eine ICorDebugClass ab, die den nicht instanziierten generischen Typ darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `ppClass`  
 vorgenommen Ein Zeiger auf die Adresse einer `ICorDebugClass` Schnittstelle, die den nicht instanziierten generischen Typ darstellt.  
  
## <a name="remarks"></a>Hinweise  

 `GetClass` kann nur unter bestimmten Bedingungen aufgerufen werden. Rufen Sie [ICorDebugType:: GetType](icordebugtype-gettype-method.md) auf, bevor Sie aufrufen `GetClass` . Wenn `ICorDebugType::GetType` einen CorElementType-Wert zurückgibt, der ELEMENT_TYPE_CLASS oder ELEMENT_TYPE_VALUETYPE ist, `GetClass` kann aufgerufen werden, um den nicht instanziierten Typ für einen generischen Typ zu erhalten.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

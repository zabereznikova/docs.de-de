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
ms.openlocfilehash: 878a57514af34730049864f17f4853c1237904c2
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379961"
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
 `GetClass`kann nur unter bestimmten Bedingungen aufgerufen werden. Rufen Sie [ICorDebugType:: GetType](icordebugtype-gettype-method.md) auf, bevor Sie aufrufen `GetClass` . Wenn `ICorDebugType::GetType` einen CorElementType-Wert zurückgibt, der ELEMENT_TYPE_CLASS oder ELEMENT_TYPE_VALUETYPE ist, `GetClass` kann aufgerufen werden, um den nicht instanziierten Typ für einen generischen Typ zu erhalten.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

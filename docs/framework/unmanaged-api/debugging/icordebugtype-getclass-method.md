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
ms.openlocfilehash: d403a8bfba3599a60d8af72307590f5a569480dd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791297"
---
# <a name="icordebugtypegetclass-method"></a>ICorDebugType::GetClass-Methode
Ruft einen Schnittstellen Zeiger auf eine ICorDebugClass ab, die den nicht instanziierten generischen Typ darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `ppClass`  
 vorgenommen Ein Zeiger auf die Adresse einer `ICorDebugClass`-Schnittstelle, die den nicht instanziierten generischen Typ darstellt.  
  
## <a name="remarks"></a>Hinweise  
 `GetClass` können nur unter bestimmten Bedingungen aufgerufen werden. Rufen Sie [ICorDebugType:: GetType](icordebugtype-gettype-method.md) auf, bevor Sie `GetClass`aufrufen. Wenn `ICorDebugType::GetType` einen CorElementType-Wert zurückgibt, der ELEMENT_TYPE_CLASS oder ELEMENT_TYPE_VALUETYPE ist, können `GetClass` aufgerufen werden, um den nicht instanziierten Typ für einen generischen Typ zu erhalten.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

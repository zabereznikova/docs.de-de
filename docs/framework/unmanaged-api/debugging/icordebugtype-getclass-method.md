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
ms.openlocfilehash: 3a895f432ed640cc35a492df0c91cece34893062
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122365"
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
 vorgenommen Ein Zeiger auf die Adresse einer `ICorDebugClass`-Schnittstelle, die den nicht instanziierten generischen Typ darstellt.  
  
## <a name="remarks"></a>Hinweise  
 `GetClass` können nur unter bestimmten Bedingungen aufgerufen werden. Rufen Sie [ICorDebugType:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) auf, bevor Sie `GetClass`aufrufen. Wenn `ICorDebugType::GetType` einen CorElementType-Wert zurückgibt, der "ELEMENT_TYPE_CLASS" oder "ELEMENT_TYPE_VALUETYPE" ist, können `GetClass` aufgerufen werden, um den nicht instanziierten Typ für einen generischen Typ zu erhalten.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

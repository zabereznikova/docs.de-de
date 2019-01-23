---
title: ICorDebugValue::GetAddress-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetAddress
helpviewer_keywords:
- ICorDebugValue::GetAddress method [.NET Framework debugging]
- GetAddress method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: a247c792-45e1-4538-9e1f-b46acca4a463
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b88c49ba93ff3c4cc3f5c7a656dfa5da6e82109e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559840"
---
# <a name="icordebugvaluegetaddress-method"></a>ICorDebugValue::GetAddress-Methode
Ruft die Adresse des Objekts "ICorDebugValue", der gerade gedebuggt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pAddress`  
 [out] Zeiger auf eine `CORDB_ADDRESS` Objekt, das die Adresse des Wertobjekts angibt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Wert nicht verfügbar ist, wird 0 (null) zurückgegeben. Dies kann passieren, wenn der Wert, zumindest teilweise in Registern ist oder in einem Garbage Collector-Handle (`GCHandle`).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch


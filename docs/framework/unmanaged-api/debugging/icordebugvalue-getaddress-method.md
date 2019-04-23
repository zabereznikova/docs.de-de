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
ms.openlocfilehash: ac550ee7b1d66612557b30d15c275c90cf09b8af
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59187333"
---
# <a name="icordebugvaluegetaddress-method"></a>ICorDebugValue::GetAddress-Methode
Ruft die Adresse des Objekts "ICorDebugValue", der gerade gedebuggt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
## <a name="parameters"></a>Parameter  
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

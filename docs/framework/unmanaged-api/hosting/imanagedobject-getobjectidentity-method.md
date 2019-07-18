---
title: IManagedObject::GetObjectIdentity-Methode
ms.date: 03/30/2017
api_name:
- IManagedObject.GetObjectIdentity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetObjectIdentity
helpviewer_keywords:
- GetObjectIdentity method [.NET Framework hosting]
- IManagedObject::GetObjectIdentity method [.NET Framework hosting]
ms.assetid: b862ff3e-e480-4cdf-84e2-e1013334a467
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 291246169a5cc2c95b117bc55bc269791885b2ea
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749094"
---
# <a name="imanagedobjectgetobjectidentity-method"></a>IManagedObject::GetObjectIdentity-Methode
Ruft die Identität dieser verwalteten Objekts.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetObjectIdentity (  
    [out] BSTR*   pBSTRGUID,  
    [out] int*    AppDomainID,  
    [out] CCW_PTR pCCW  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pBSTRGUID`  
 [out] Ein Zeiger auf die GUID des Prozesses, in dem sich das Objekt befindet.  
  
 `AppDomainID`  
 [out] Ein Zeiger auf die ID der Anwendungsdomäne des Objekts.  
  
 `pCCW`  
 [out] Ein Zeiger auf den Index des Objekts, in der klassischen COM-V-Tabelle.  
  
## <a name="remarks"></a>Hinweise  
 In der klassischen COM-V-Tabelle enthält die Identität eines verwalteten Objekts GUID-Prozessen, Anwendungsdomänen-ID und der Index des Objekts.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IManagedObject-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)

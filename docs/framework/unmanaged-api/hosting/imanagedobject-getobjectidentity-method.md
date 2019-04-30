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
ms.openlocfilehash: 6d014d2900ea790f84331ed933143513ae9e63f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61943513"
---
# <a name="imanagedobjectgetobjectidentity-method"></a>IManagedObject::GetObjectIdentity-Methode
Ruft die Identität dieser verwalteten Objekts.  
  
## <a name="syntax"></a>Syntax  
  
```  
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

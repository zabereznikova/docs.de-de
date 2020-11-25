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
ms.openlocfilehash: fc74b84bccceb1772bf3642e51ec88c562ce5dce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730712"
---
# <a name="imanagedobjectgetobjectidentity-method"></a>IManagedObject::GetObjectIdentity-Methode

Ruft die Identität dieses verwalteten Objekts ab.  
  
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
 vorgenommen Ein Zeiger auf die GUID des Prozesses, in dem sich das Objekt befindet.  
  
 `AppDomainID`  
 vorgenommen Ein Zeiger auf die ID der Anwendungsdomäne des Objekts.  
  
 `pCCW`  
 vorgenommen Ein Zeiger auf den Index des Objekts in der klassischen com-Tabelle.  
  
## <a name="remarks"></a>Hinweise  

 Die Identität eines verwalteten Objekts umfasst die Prozess-GUID, die Anwendungs Domänen-ID und den Index des Objekts in der klassischen com-Tabelle.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IManagedObject-Schnittstelle](imanagedobject-interface.md)

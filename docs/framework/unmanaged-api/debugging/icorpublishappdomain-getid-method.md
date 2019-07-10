---
title: ICorPublishAppDomain::GetID-Methode
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetID
helpviewer_keywords:
- GetID method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetID method [.NET Framework debugging]
ms.assetid: 229437e3-1465-4bd8-8846-9804b2488133
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b1a557191c5649f2ed87cf4f4dfdb4167133e597
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774261"
---
# <a name="icorpublishappdomaingetid-method"></a>ICorPublishAppDomain::GetID-Methode
Ruft den eindeutigen Bezeichner für diese [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `puId`  
 [out] Ein Zeiger auf den Bezeichner der Anwendungsdomäne.  
  
## <a name="remarks"></a>Hinweise  
 Der Bezeichner ist nur im Bereich des enthaltenden Prozesses eindeutig.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorPub.idl, CorPub.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorPublishAppDomain-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)

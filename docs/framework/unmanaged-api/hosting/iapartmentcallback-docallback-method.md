---
title: IApartmentCallback::DoCallback-Methode
ms.date: 03/30/2017
api_name:
- IApartmentCallback.DoCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- DoCallback
helpviewer_keywords:
- IApartmentCallback::DoCallback method [.NET Framework hosting]
- DoCallback method [.NET Framework hosting]
ms.assetid: 8edad30c-30ff-4bee-813c-75525a82fc93
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ba1dc2a1ec8b0b3b5ec25036cab6362237efe98f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430755"
---
# <a name="iapartmentcallbackdocallback-method"></a>IApartmentCallback::DoCallback-Methode
Führt die angegebene Funktion innerhalb eines Apartments aus.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pFunc`  
 [in] Ein Zeiger auf die Funktion, die in dem Apartment ausgeführt werden.  
  
 `pData`  
 [in] Ein Zeiger auf das Argument der Funktion.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IApartmentCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)

---
title: IGCHost::Collect-Methode
ms.date: 03/30/2017
api_name:
- IGCHost.Collect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Collect
helpviewer_keywords:
- Collect method, IGCHost interface [.NET Framework hosting]
- IGCHost::Collect method [.NET Framework hosting]
ms.assetid: fc7d9448-3186-494d-9f0d-ea39717e9a82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9c4fa79f4918412720592bce449a001a349ae657
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766565"
---
# <a name="igchostcollect-method"></a>IGCHost::Collect-Methode
Erzwingt, dass eine Collection für die angegebene Generation, unabhängig vom Status des aktuellen Garbagecollection durchgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `Generation`  
 [in] Die Objektgeneration, für den die Garbagecollection ausgeführt werden soll. Der Wert-1 gibt an, dass alle Generationen eine Garbagecollection unterzogen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** GCHost.idl, GCHost.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IGCHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)

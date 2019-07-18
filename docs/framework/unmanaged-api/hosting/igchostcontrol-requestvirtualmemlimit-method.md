---
title: IGCHostControl::RequestVirtualMemLimit-Methode
ms.date: 03/30/2017
api_name:
- IGCHostControl.RequestVirtualMemLimit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RequestVirtualMemLimit
helpviewer_keywords:
- IGCHostControl::RequestVirtualMemLimit method [.NET Framework hosting]
- RequestVirtualMemLimit method [.NET Framework hosting]
ms.assetid: f4984a8c-4c0e-4460-9aa1-d022b3621228
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbb0b6191c74c2b7ebdc8267701f246c17b016f9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779523"
---
# <a name="igchostcontrolrequestvirtualmemlimit-method"></a>IGCHostControl::RequestVirtualMemLimit-Methode
Fordert den Host zum Ändern der Grenzen des virtuellen Speichers an.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT RequestVirtualMemLimit (  
    [in] SIZE_T       sztMaxVirtualMemMB,  
    [in, out] SIZE_T* psztNewMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `sztMaxVirtualMemMB`  
 [in] Die angeforderte Größe des Arbeitsspeichers, die zugeordnet werden.  
  
 `psztNewMaxVirtualMemMB`  
 [in, out] Ein Zeiger auf die tatsächliche Größe des belegten Arbeitsspeichers.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IGCHostControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)

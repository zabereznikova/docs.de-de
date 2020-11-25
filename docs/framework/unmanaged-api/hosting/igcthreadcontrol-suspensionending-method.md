---
title: IGCThreadControl::SuspensionEnding-Methode
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionEnding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionEnding
helpviewer_keywords:
- IGCThreadControl::SuspensionEnding method [.NET Framework hosting]
- SuspensionEnding method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 70814265-c734-4ddc-9502-fe8b28d2b414
topic_type:
- apiref
ms.openlocfilehash: 4638672b1d64a9ea07618212cc514d00996470eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721672"
---
# <a name="igcthreadcontrolsuspensionending-method"></a>IGCThreadControl::SuspensionEnding-Methode

Benachrichtigt den Host, dass die Laufzeit Threads nach einem Garbage Collection oder einer anderen Unterbrechung fortsetzt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SuspensionEnding (  
    [in] DWORD Generation  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `Generation`  
 in Die Generierung, auf der ein Garbage Collection ausgeführt wurde.  
  
## <a name="remarks"></a>Hinweise  

 Planen Sie keine Threads während des `SuspensionEnding` Rückrufs neu.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IGCThreadControl-Schnittstelle](igcthreadcontrol-interface.md)

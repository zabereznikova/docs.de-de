---
title: IGCHost::GetThreadStats-Methode
ms.date: 03/30/2017
api_name:
- IGCHost.GetThreadStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetThreadStats
helpviewer_keywords:
- IGCHost::GetThreadStats method [.NET Framework hosting]
- GetThreadStats method [.NET Framework hosting]
ms.assetid: 826baa9b-9218-4736-a509-7ab193b125a0
topic_type:
- apiref
ms.openlocfilehash: c48b580e632d67db5a9826c210415adab1bdba96
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95670068"
---
# <a name="igchostgetthreadstats-method"></a>IGCHost::GetThreadStats-Methode

Ruft die Statistiken pro Thread für Garbage Collection ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetThreadStats (  
    [in] DWORD *pFiberCookie,  
    [in, out] COR_GC_THREAD_STATS *pStats  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pFiberCookie`  
 in Ein Zeiger auf ein Fiber Cookie, das den Thread angibt, für den die Statistiken abgerufen werden sollen.  
  
 `pStats`  
 [in, out] Ein Zeiger auf eine [COR_GC_THREAD_STATS](cor-gc-thread-stats-structure.md) -Struktur, die die Garbage Collection Statistiken für den angegebenen Thread enthält.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Gchost. idl, gchost. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IGCHost-Schnittstelle](igchost-interface.md)

---
title: ICorPublishProcess::EnumAppDomains-Methode
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.EnumAppDomains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::EnumAppDomains
helpviewer_keywords:
- EnumAppDomains method [.NET Framework debugging]
- ICorPublishProcess::EnumAppDomains method [.NET Framework debugging]
ms.assetid: 7da621fc-e7d0-4c00-9439-5c93619d7414
topic_type:
- apiref
ms.openlocfilehash: aa76bf511ff1e1710a7ff86ad2ac97665969f2bf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140439"
---
# <a name="icorpublishprocessenumappdomains-method"></a>ICorPublishProcess::EnumAppDomains-Methode
Ruft einen Enumerator für die Anwendungs Domänen in dem Prozess ab, auf den von diesem [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumAppDomains (  
    [out] ICorPublishAppDomainEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppEnum`  
 vorgenommen Ein Zeiger auf die Adresse einer [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) -Instanz, die Iterationen durch die Auflistung von Anwendungs Domänen in diesem Prozess ermöglicht.  
  
## <a name="remarks"></a>Hinweise  
 Die Liste der Anwendungs Domänen basiert auf einer Momentaufnahme der Anwendungs Domänen, die vorhanden sind, wenn die `EnumAppDomains`-Methode aufgerufen wird. Diese Methode kann mehrmals aufgerufen werden, um eine neue aktuelle Liste zu erstellen. Bei nachfolgenden Aufrufen dieser Methode werden vorhandene Listen nicht beeinträchtigt.  
  
 Wenn der Prozess beendet wurde, wird `EnumAppDomains` mit einem HRESULT-Wert von CORDBG_E_PROCESS_TERMINATED fehlschlagen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Corpub. idl, Corpub. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorPublishProcess-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)

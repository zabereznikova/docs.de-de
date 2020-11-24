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
ms.openlocfilehash: 2acf8fb507ab617e066a31c9c2657b1ef0d18e47
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693280"
---
# <a name="icorpublishprocessenumappdomains-method"></a>ICorPublishProcess::EnumAppDomains-Methode

Ruft einen Enumerator für die Anwendungs Domänen in dem Prozess ab, auf den von diesem [ICorPublishProcess](icorpublishprocess-interface.md)verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumAppDomains (  
    [out] ICorPublishAppDomainEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `ppEnum`  
 vorgenommen Ein Zeiger auf die Adresse einer [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) -Instanz, die Iterationen durch die Auflistung von Anwendungs Domänen in diesem Prozess ermöglicht.  
  
## <a name="remarks"></a>Hinweise  

 Die Liste der Anwendungs Domänen basiert auf einer Momentaufnahme der Anwendungs Domänen, die beim Aufrufen der- `EnumAppDomains` Methode vorhanden sind. Diese Methode kann mehrmals aufgerufen werden, um eine neue aktuelle Liste zu erstellen. Bei nachfolgenden Aufrufen dieser Methode werden vorhandene Listen nicht beeinträchtigt.  
  
 Wenn der Prozess beendet wurde, `EnumAppDomains` schlägt mit dem HRESULT-Wert CORDBG_E_PROCESS_TERMINATED fehl.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Corpub. idl, Corpub. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorPublishProcess-Schnittstelle](icorpublishprocess-interface.md)

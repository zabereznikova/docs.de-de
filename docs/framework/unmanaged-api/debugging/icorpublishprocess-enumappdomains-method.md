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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6f8f73eab1ee6e28a75263e06523a2b04ce62d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54510558"
---
# <a name="icorpublishprocessenumappdomains-method"></a>ICorPublishProcess::EnumAppDomains-Methode
Ruft einen Enumerator für die Anwendungsdomänen im Prozess, der von diesem verwiesen wird [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnumAppDomains (  
    [out] ICorPublishAppDomainEnum   **ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppEnum`  
 [out] Ein Zeiger auf die Adresse einer [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) -Instanz, die Iteration durch die Auflistung von Anwendungsdomänen in diesem Prozess ermöglicht.  
  
## <a name="remarks"></a>Hinweise  
 Die Liste der Anwendungsdomänen basiert darauf, dass eine Momentaufnahme der Anwendungsdomänen, die vorhanden sind bei der `EnumAppDomains` Methode wird aufgerufen. Diese Methode kann mehr als einmal aufgerufen werden, um eine neue auf dem neuesten Stand Liste zu erstellen. Vorhandene Listen werden durch nachfolgende Aufrufe dieser Methode nicht betroffen.  
  
 Wenn der Prozess beendet wurde, `EnumAppDomains` mit HRESULT-Wert CORDBG_E_PROCESS_TERMINATED fehl.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorPub.idl, CorPub.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorPublishProcess-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)

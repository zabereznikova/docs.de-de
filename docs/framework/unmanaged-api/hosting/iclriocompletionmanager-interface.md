---
title: ICLRIoCompletionManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager
helpviewer_keywords:
- ICLRIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c6c3ace6-e5e7-4450-8cc5-a9a48208c493
topic_type:
- apiref
ms.openlocfilehash: b63d4269a8d48ee49016a4c51d63bf81bdba8da2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141027"
---
# <a name="iclriocompletionmanager-interface"></a>ICLRIoCompletionManager-Schnittstelle
Implementiert eine Rückruf Methode, die es dem Host ermöglicht, den Common Language Runtime (CLR) über den Status der angegebenen e/a-Anforderungen zu benachrichtigen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[OnComplete-Methode](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|Benachrichtigt die CLR über den Status einer e/a-Anforderung, die mithilfe eines Aufrufes der [IHostIoCompletionManager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) -Methode durchgeführt wurde.|  
  
## <a name="remarks"></a>Hinweise  
 Der Host implementiert die e/a-Abschluss Abstraktion mithilfe der [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) -Schnittstelle. Die CLR führt e/a-Anforderungen über diese Schnittstelle aus, und der Host benachrichtigt die Laufzeit über das Ergebnis dieser Anforderungen mithilfe der `ICLRIoCompletionManager`-Schnittstelle.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IHostIoCompletionManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [IHostThreadPoolManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)

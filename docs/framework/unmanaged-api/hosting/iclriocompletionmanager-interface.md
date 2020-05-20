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
ms.openlocfilehash: 822b51531b7afc1c824c74b9580d9208e347e13b
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703552"
---
# <a name="iclriocompletionmanager-interface"></a>ICLRIoCompletionManager-Schnittstelle
Implementiert eine Rückruf Methode, die es dem Host ermöglicht, den Common Language Runtime (CLR) über den Status der angegebenen e/a-Anforderungen zu benachrichtigen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[OnComplete-Methode](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|Benachrichtigt die CLR über den Status einer e/a-Anforderung, die mithilfe eines Aufrufes der [IHostIoCompletionManager:: Bind](ihostiocompletionmanager-bind-method.md) -Methode durchgeführt wurde.|  
  
## <a name="remarks"></a>Hinweise  
 Der Host implementiert die e/a-Abschluss Abstraktion mithilfe der [IHostIoCompletionManager](ihostiocompletionmanager-interface.md) -Schnittstelle. Die CLR führt e/a-Anforderungen über diese Schnittstelle aus, und der Host benachrichtigt die Laufzeit über das Ergebnis dieser Anforderungen mithilfe der- `ICLRIoCompletionManager` Schnittstelle.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IHostIoCompletionManager-Schnittstelle](ihostiocompletionmanager-interface.md)
- [IHostThreadPoolManager-Schnittstelle](ihostthreadpoolmanager-interface.md)
- [Hostingschnittstellen](hosting-interfaces.md)

---
title: ICLRRuntimeInfo::IsLoadable-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoadable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoadable
helpviewer_keywords:
- IsLoadable method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoadable method [.NET Framework hosting]
ms.assetid: 205ca53b-e78e-49b2-9a46-2a7823e96b8c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 586882ad7577c367576da9b32e6d3b8fe2f806c3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501213"
---
# <a name="iclrruntimeinfoisloadable-method"></a>ICLRRuntimeInfo::IsLoadable-Methode
Gibt an, ob der aktuelle Prozess, die Berücksichtigung die Runtime, die dieser Schnittstelle zugeordnet geladen werden kann anderen Laufzeiten, die bereits in den Prozess geladen werden können.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
## <a name="parameters"></a>Parameter  
 `pbLoadable`  
 [out] `true` , wenn diese Runtime in den aktuellen Prozess geladen ist, andernfalls möglicherweise `false`.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_POINTER|`pbLoadable` ist NULL.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn eine andere Laufzeit bereits in den Prozess geladen wird und die Laufzeit, die dieser Schnittstelle zugeordnet zur in-Process-Seite-an-Seite-Ausführung geladen werden kann `pbLoadable` gibt `true`. Wenn die Seite-an-Seite in-Process, die zwei Laufzeiten ausgeführt werden können `pbLoadable` gibt `false`. Die common Language Runtime (CLR), Version 4 kann z. B. Seite-an-Seite im gleichen Prozess mit CLR, Version 2.0 oder CLR-Version 1.1 ausführen. CLR, Version 1.1 und der CLR, Version 2.0 kann nicht jedoch in-Process-Seite-an-Seite ausführen.  
  
 Wenn keine Laufzeiten, die in den Prozess geladen sind, gibt diese Methode immer `true`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICLRRuntimeInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)

---
title: ICLRRuntimeInfo::IsLoadable-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1d3825f8dc529cf9c5fbfc44ae70008695e32054
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimeinfoisloadable-method"></a>ICLRRuntimeInfo::IsLoadable-Methode
Gibt an, ob der aktuelle Prozess ein, und berücksichtigt die Runtime diese Schnittstelle zugeordneten geladen werden kann anderen Laufzeiten, die bereits in den Prozess geladen werden können.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pbLoadable`  
 [out] `true` Wenn diese Laufzeit, in den aktuellen Prozess geladen ist, andernfalls werden konnte `false`.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_POINTER|`pbLoadable` ist NULL.|  
  
## <a name="remarks"></a>Hinweise  
 Falls bereits einer anderen Laufzeit in den Prozess geladen wird und die Common Language Runtime diese Schnittstelle zugeordneten werden, für die Ausführung des prozessinternen Seite-an-Seite geladen kann, `pbLoadable` gibt `true`. Wenn die Seite-an-Seite in-Process, die zwei Laufzeiten ausgeführt werden können `pbLoadable` gibt `false`. Die common Language Runtime (CLR) Version 4 kann z. B. nebeneinander im selben Prozess mit CLR, Version 2.0 oder CLR, Version 1.1 ausführen. CLR, Version 1.1 und CLR, Version 2.0 kann nicht in-Process-Seite-an-Seite ausführen.  
  
 Wenn keine Laufzeiten in den Prozess geladen sind, gibt diese Methode immer `true`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRRuntimeInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)

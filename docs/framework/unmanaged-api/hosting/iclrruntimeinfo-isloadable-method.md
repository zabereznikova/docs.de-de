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
ms.openlocfilehash: 9339bb974c261e62502c760dfaf45651573cbe1a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136373"
---
# <a name="iclrruntimeinfoisloadable-method"></a>ICLRRuntimeInfo::IsLoadable-Methode
Gibt an, ob die dieser Schnittstelle zugeordnete Laufzeit in den aktuellen Prozess geladen werden kann, wobei andere Laufzeiten berücksichtigt werden, die möglicherweise bereits in den Prozess geladen wurden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT IsLoadable(  
        [out, retval] BOOL *pbLoadable);  
```  
  
## <a name="parameters"></a>Parameter  
 `pbLoadable`  
 [out] `true`, wenn diese Laufzeit in den aktuellen Prozess geladen werden konnte. Andernfalls `false`.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_POINTER|`pbLoadable` ist NULL.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn eine andere Laufzeit bereits in den Prozess geladen wurde und die Laufzeit, die dieser Schnittstelle zugeordnet ist, für die Prozess interne parallele Ausführung geladen werden kann, `pbLoadable` `true`zurückgegeben. Wenn die beiden Laufzeiten nicht parallel ausgeführt werden können, gibt `pbLoadable` `false`zurück. Beispielsweise kann die Common Language Runtime (CLR) Version 4 parallel in demselben Prozess ausgeführt werden wie CLR-Version 2,0 oder CLR-Version 1,1. Die CLR-Version 1,1 und die CLR-Version 2,0 können jedoch nicht parallel ausgeführt werden.  
  
 Wenn keine Laufzeiten in den Prozess geladen werden, gibt diese Methode immer `true`zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRRuntimeInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)

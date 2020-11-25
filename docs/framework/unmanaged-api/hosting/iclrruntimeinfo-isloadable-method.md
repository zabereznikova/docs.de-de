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
ms.openlocfilehash: 2236e815211168d8e7105375b75f30128f7f209a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714968"
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
 [out] `true` , wenn diese Laufzeit in den aktuellen Prozess geladen werden konnte. andernfalls `false` .  
  
## <a name="return-value"></a>Rückgabewert  

 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_POINTER|`pbLoadable` ist NULL.|  
  
## <a name="remarks"></a>Hinweise  

 Wenn eine andere Laufzeit bereits in den Prozess geladen wurde und die Laufzeit, die dieser Schnittstelle zugeordnet ist, für die Prozess interne parallele Ausführung geladen werden kann, wird `pbLoadable` zurückgegeben `true` . Wenn die beiden Laufzeiten nicht parallel ausgeführt werden können, wird `pbLoadable` zurückgegeben `false` . Beispielsweise kann die Common Language Runtime (CLR) Version 4 parallel in demselben Prozess ausgeführt werden wie CLR-Version 2,0 oder CLR-Version 1,1. Die CLR-Version 1,1 und die CLR-Version 2,0 können jedoch nicht parallel ausgeführt werden.  
  
 Wenn keine Laufzeiten in den Prozess geladen werden, gibt diese Methode immer zurück `true` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRRuntimeInfo-Schnittstelle](iclrruntimeinfo-interface.md)
- [Hosten von Schnittstellen](hosting-interfaces.md)
- [Hosting](index.md)

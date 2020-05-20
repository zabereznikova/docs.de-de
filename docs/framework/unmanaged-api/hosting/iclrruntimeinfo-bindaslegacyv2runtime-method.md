---
title: ICLRRuntimeInfo::BindAsLegacyV2Runtime-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.BindAsLegacyV2Runtime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime
helpviewer_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime method [.NET Framework hosting]
- BindAsLegacyV2Runtime method [.NET Framework hosting]
ms.assetid: 65fd55ac-4a24-4479-9384-a2e8013bfb2b
topic_type:
- apiref
ms.openlocfilehash: 4390f379e5092cc59d123631f5e6d8da82e2bd7f
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703894"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a>ICLRRuntimeInfo::BindAsLegacyV2Runtime-Methode
Bindet die aktuelle Laufzeit für alle Entscheidungen zur Aktivierung der Richtlinie für Legacy-Common Language Runtime (CLR), Version 2.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs zurück:  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Die Bindung wurde erfolgreich ausgeführt, oder diese Laufzeit war bereits als Common Language Runtime für die CLR Version 2-Aktivierungs Richtlinie gebunden.|  
|CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND|Eine andere Laufzeit wurde bereits an die Legacy-Aktivierungs Richtlinie der CLR-Version 2 gebunden.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn die aktuelle Laufzeit bereits für alle Richtlinien zur Aktivierung der Common Language Runtime (CLR, Version 2) gebunden ist (z. b. durch Verwendung des- `useLegacyV2RuntimeActivationPolicy` Attributs für das [ \< Startup->-Element](../../configure-apps/file-schema/startup/startup-element.md) in der Konfigurationsdatei), gibt diese Methode kein Fehler Ergebnis zurück. stattdessen wird das Ergebnis S_OK, genauso wie es wäre, wenn die Methode die Legacy Aktivierungs Richtlinie erfolgreich gebunden hätte.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRRuntimeInfo-Schnittstelle](iclrruntimeinfo-interface.md)
- [Hostingschnittstellen](hosting-interfaces.md)
- [Hosting](index.md)
- [\<Start>-Element](../../configure-apps/file-schema/startup/startup-element.md)

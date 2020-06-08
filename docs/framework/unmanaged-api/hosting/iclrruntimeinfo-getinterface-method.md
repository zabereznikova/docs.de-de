---
title: ICLRRuntimeInfo::GetInterface-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetInterface
helpviewer_keywords:
- GetInterface method [.NET Framework hosting]
- ICLRRuntimeInfo::GetInterface method [.NET Framework hosting]
ms.assetid: cc7b0e5b-48c3-4509-8ebb-611ddb1f7ec2
topic_type:
- apiref
ms.openlocfilehash: 9cf9d48bf50ffc1fc56270c13215acfef6d9c3af
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504055"
---
# <a name="iclrruntimeinfogetinterface-method"></a>ICLRRuntimeInfo::GetInterface-Methode
Lädt die CLR in den aktuellen Prozess und gibt Lauf Zeit Schnittstellen Zeiger zurück, z. [b. ICLRRuntimeHost](iclrruntimehost-interface.md), [ICLRStrongName](iclrstrongname-interface.md)und [IMetaDataDispenserEx](../metadata/imetadatadispenser-interface.md).  
  
 Diese Methode ersetzt alle *- `CorBindTo` Funktionen im Abschnitt [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md) .  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetInterface(  
[in]  REFCLSID rclsid,  
[in]  REFIID   riid,  
[out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a>Parameter  
 `rclsid`  
 in Die CLSID-Schnittstelle für die Co-Klasse.  
  
 `riid`  
 in Die IID der angeforderten `rclsid` Schnittstelle.  
  
 `ppUnk`  
 vorgenommen Ein Zeiger auf die abgefragte Schnittstelle.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_POINTER|`ppUnk` ist NULL.|  
|E_OUTOFMEMORY|Es ist nicht genügend Arbeitsspeicher verfügbar, um die Anforderung zu verarbeiten.|  
|CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND|Eine andere Laufzeit wurde bereits an die Legacy-Aktivierungs Richtlinie der CLR-Version 2 gebunden.|  
  
## <a name="remarks"></a>Bemerkungen  
 Diese Methode bewirkt, dass die CLR geladen, aber nicht initialisiert wird.  
  
 In der folgenden Tabelle werden die unterstützten Kombinationen für `rclsid` und angezeigt `riid` .  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|CLSID_CorMetaDataDispenser|IID_IMetaDataDispenser IID_IMetaDataDispenserEx|  
|CLSID_CorMetaDataDispenserRuntime|IID_IMetaDataDispenser IID_IMetaDataDispenserEx|  
|CLSID_CorRuntimeHost|IID_ICorRuntimeHost|  
|CLSID_CLRRuntimeHost|IID_ICLRRuntimeHost|  
|CLSID_TypeNameFactory|IID_ITypeNameFactory|  
|CLSID_CLRDebuggingLegacy|IID_ICorDebug|  
|||  
|CLSID_CLRStrongName|IID_ICLRStrongName|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICLRRuntimeInfo-Schnittstelle](iclrruntimeinfo-interface.md)
- [Hosten von Schnittstellen](hosting-interfaces.md)
- [Hosting](index.md)

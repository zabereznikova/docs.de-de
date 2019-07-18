---
title: ICLRMetaHostPolicy::GetRequestedRuntime-Methode
ms.date: 03/30/2017
api_name:
- ICLRMetaHostPolicy.GetRequestedRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHostPolicy::GetRequestedRuntime
helpviewer_keywords:
- GetRequestedRuntime method [.NET Framework hosting]
- ICLRMetaHostPolicy::GetRequestedRuntime method [.NET Framework hosting]
ms.assetid: 59ec1832-9cc1-4b5c-983d-03407e51de56
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 73d5c98500c510630b1f8d6081b654a6dbd88a5b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771799"
---
# <a name="iclrmetahostpolicygetrequestedruntime-method"></a>ICLRMetaHostPolicy::GetRequestedRuntime-Methode

Stellt auf Basis einer Hostingrichtlinie, einer verwalteten Assembly, einer Versionszeichenfolge und eines Konfigurationsstreams eine Schnittstelle mit einer bevorzugten Version der Common Language Runtime (CLR) bereit. Diese Methode nicht geladen werden oder aktiviert die CLR, sondern gibt einfach die [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) -Schnittstelle, die das Richtlinienergebnis darstellt. Diese Methode ersetzt die [GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md), [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md), [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md), [CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md), und [GetCORRequiredVersion](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md) Methoden.

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetRequestedRuntime(
    [in]  METAHOST_POLICY_FLAGS dwPolicyFlags,
    [in]  LPCWSTR pwzBinary,
    [in]  IStream *pCfgStream,
    [in, out, size_is(*pcchVersion)] LPWSTR pwzVersion,
    [in, out]  DWORD *pcchVersion,
    [out, size_is(*pcchImageVersion)] LPWSTR pwzImageVersion,
    [in, out]  DWORD *pcchImageVersion,
    [out] DWORD *pdwConfigFlags,
    [in]  REFIID  riid
    [out, iid_is(riid), retval] LPVOID *ppRuntime);
```

## <a name="parameters"></a>Parameter

|Name|Beschreibung|
|----------|-----------------|
|`dwPolicyFlags`|[in] erforderlich. Gibt einen Member der [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) Enumeration, der eine Bindungsrichtlinie und eine beliebige Anzahl von Modifizierern darstellt. Die einzige Richtlinie, die derzeit verfügbaren [METAHOST_POLICY_HIGHCOMPAT](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md).<br /><br /> Modifizierer sind [METAHOST_POLICY_EMULATE_EXE_LAUNCH](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md), [METAHOST_POLICY_APPLY_UPGRADE_POLICY](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md), [METAHOST_POLICY_SHOW_ERROR_DIALOG](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md), [METAHOST_POLICY_USE_PROCESS_IMAGE_PATH](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md), und [METAHOST_POLICY_ENSURE_SKU_SUPPORTED](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md).|
|`pwzBinary`|[in] Optional. Gibt den Pfad der Assemblydatei an.|
|`pCfgStream`|[in] Optional. Gibt die Konfigurationsdatei als einen <xref:System.Runtime.InteropServices.ComTypes.IStream?displayProperty=nameWithType> an.|
|`pwzVersion`|[in, out] Optional. Gibt die bevorzugte CLR-Version an, die geladen werden soll, oder gibt diese zurück.|
|`pcchVersion`|[in, out] Erforderlich. Gibt die erwartete Größe von `pwzVersion` als Eingabe an, um Pufferüberläufe zu vermeiden. Wenn `pwzVersion` gleich NULL ist, enthält `pcchVersion` die erwartete Größe von `pwzVersion`, wenn `GetRequestedRuntime` beendet wird, um die Vorabbelegung zu ermöglichen; andernfalls enthält `pcchVersion` die Anzahl der in `pwzVersion` geschriebenen Zeichen.|
|`pwzImageVersion`|[out] Optional. Wenn `GetRequestedRuntime` zurückgibt, enthält die CLR Version entspricht der [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) -Schnittstelle, die zurückgegeben wird.|
|`pcchImageVersion`|[in, out] Optional. Gibt die Größe von `pwzImageVersion` als Eingabe an, um Pufferüberläufe zu vermeiden. Wenn `pwzImageVersion` gleich NULL ist, enthält `pcchImageVersion` die erforderliche Größe von `pwzImageVersion`, wenn `GetRequestedRuntime` beendet wird, um die Vorabbelegung zu ermöglichen.|
|`pdwConfigFlags`|[out] Optional. Wenn `GetRequestedRuntime` mithilfe einer Konfigurationsdatei während des Bindungsvorgangs, bei der Ausgabe `pdwConfigFlags` enthält eine [METAHOST_CONFIG_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-config-flags-enumeration.md) Wert, der angibt, ob die [ \<Start >](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) Element verfügt über die `useLegacyV2RuntimeActivationPolicy` -Attributsatz und der Wert des Attributs. Anwenden der [METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK](../../../../docs/framework/unmanaged-api/hosting/metahost-config-flags-enumeration.md) -Maske auf `pdwConfigFlags` um die Werte zu erhalten, die relevant für `useLegacyV2RuntimeActivationPolicy`.|
|`riid`|[in] Gibt den Schnittstellenbezeichner "IID_ICLRRuntimeInfo" für die angeforderte [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstelle.|
|`ppRuntime`|[out] Wenn `GetRequestedRuntime` zurückgibt, enthält einen Zeiger auf den entsprechenden [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstelle.|

## <a name="remarks"></a>Hinweise

Wenn diese Methode erfolgreich ist, hat sie den Nebeneffekt, zusätzliche Flags mit den aktuellen Standardstartflags der zurückgegebenen Laufzeitschnittstelle zu kombinieren, dies allerdings nur dann, wenn ein oder mehrere der folgenden Elemente im Konfigurationsstream innerhalb des `<configuration><runtime>`-Abschnitts vorhanden sind:

- `<gcServer enabled="true"/>` bewirkt, dass `STARTUP_SERVER_GC` festgelegt wird.

- `<etwEnable enabled="true"/>` bewirkt, dass `STARTUP_ETW` festgelegt wird.

- `<appDomainResourceMonitoring enabled="true"/>` bewirkt, dass `STARTUP_ARM` festgelegt wird.

Der sich ergebende Standard-`STARTUP_FLAGS`-Wert ist die bitweise ODER-Kombination der Werte, die von der vorangehenden Liste festgelegt wurden, mit den Standardstartflags.

## <a name="return-value"></a>Rückgabewert

Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.

|HRESULT|Beschreibung|
|-------------|-----------------|
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|
|E_POINTER|`pwzVersion` ist ungleich NULL, und `pcchVersion` ist gleich NULL.<br /><br /> - oder - <br /><br /> `pwzImageVersion` ist ungleich NULL, und `pcchImageVersion` ist gleich NULL.|
|E_INVALIDARG|`dwPolicyFlags` gibt nicht `METAHOST_POLICY_HIGHCOMPAT` an.|
|ERROR_INSUFFICIENT_BUFFER|`pwzVersion` ist nicht genügend Arbeitsspeicher zugewiesen.<br /><br /> - oder - <br /><br /> `pwzImageVersion` ist nicht genügend Arbeitsspeicher zugewiesen.|
|CLR_E_SHIM_RUNTIMELOAD|`dwPolicyFlags` enthält METAHOST_POLICY_APPLY_UPGRADE_POLICY und sowohl `pwzVersion` als auch `pcchVersion` sind gleich NULL.|

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** MetaHost.h

**Bibliothek:** Als Ressource in MSCorEE.dll enthalten

**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [ICLRMetaHostPolicy-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)
- [In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)

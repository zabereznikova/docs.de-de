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
ms.openlocfilehash: 37167b7a9aefa6cd9d5e4df043e8bbc1b0514261
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504120"
---
# <a name="iclrmetahostpolicygetrequestedruntime-method"></a>ICLRMetaHostPolicy::GetRequestedRuntime-Methode

Stellt auf Basis einer Hostingrichtlinie, einer verwalteten Assembly, einer Versionszeichenfolge und eines Konfigurationsstreams eine Schnittstelle mit einer bevorzugten Version der Common Language Runtime (CLR) bereit. Diese Methode lädt oder aktiviert die CLR nicht, sondern gibt einfach die [iclrruntimeingefo](iclrruntimeinfo-interface.md) -Schnittstelle zurück, die das Richtlinien Ergebnis darstellt. Diese Methode ersetzt die Methoden [GetRequestedRuntimeInfo](getrequestedruntimeinfo-function.md), [GetRequestedRuntimeVersion](getrequestedruntimeversion-function.md), [CorBindToRuntimeHost](corbindtoruntimehost-function.md), [CorBindToRuntimeByCfg](corbindtoruntimebycfg-function.md)und [getcorrequirements dversion](getcorrequiredversion-function.md) .

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

|Name|BESCHREIBUNG|
|----------|-----------------|
|`dwPolicyFlags`|[in] erforderlich. Gibt einen Member der [METAHOST_POLICY_FLAGS](metahost-policy-flags-enumeration.md) Enumeration an, die eine Bindungs Richtlinie und eine beliebige Anzahl von modifiziererelementen darstellt. Die einzige Richtlinie, die derzeit verfügbar ist, ist [METAHOST_POLICY_HIGHCOMPAT](metahost-policy-flags-enumeration.md).<br /><br /> Modifiziererer schließen [METAHOST_POLICY_EMULATE_EXE_LAUNCH](metahost-policy-flags-enumeration.md), [METAHOST_POLICY_APPLY_UPGRADE_POLICY](metahost-policy-flags-enumeration.md), [METAHOST_POLICY_SHOW_ERROR_DIALOG](metahost-policy-flags-enumeration.md), [METAHOST_POLICY_USE_PROCESS_IMAGE_PATH](metahost-policy-flags-enumeration.md)und [METAHOST_POLICY_ENSURE_SKU_SUPPORTED](metahost-policy-flags-enumeration.md)ein.|
|`pwzBinary`|[in] Optional. Gibt den Pfad der Assemblydatei an.|
|`pCfgStream`|[in] Optional. Gibt die Konfigurationsdatei als einen <xref:System.Runtime.InteropServices.ComTypes.IStream?displayProperty=nameWithType> an.|
|`pwzVersion`|[in, out] Optional. Gibt die bevorzugte CLR-Version an, die geladen werden soll, oder gibt diese zurück.|
|`pcchVersion`|[in, out] Erforderlich. Gibt die erwartete Größe von `pwzVersion` als Eingabe an, um Pufferüberläufe zu vermeiden. Wenn `pwzVersion` gleich NULL ist, enthält `pcchVersion` die erwartete Größe von `pwzVersion`, wenn `GetRequestedRuntime` beendet wird, um die Vorabbelegung zu ermöglichen; andernfalls enthält `pcchVersion` die Anzahl der in `pwzVersion` geschriebenen Zeichen.|
|`pwzImageVersion`|[out] Optional. Wenn `GetRequestedRuntime` zurückgibt, enthält die CLR-Version, die der zurückgegebenen [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) -Schnittstelle entspricht.|
|`pcchImageVersion`|[in, out] Optional. Gibt die Größe von `pwzImageVersion` als Eingabe an, um Pufferüberläufe zu vermeiden. Wenn `pwzImageVersion` gleich NULL ist, enthält `pcchImageVersion` die erforderliche Größe von `pwzImageVersion`, wenn `GetRequestedRuntime` beendet wird, um die Vorabbelegung zu ermöglichen.|
|`pdwConfigFlags`|[out] Optional. Wenn `GetRequestedRuntime` während des Bindungs Vorgangs eine Konfigurationsdatei verwendet, enthält bei der Rückgabe `pdwConfigFlags` einen [METAHOST_CONFIG_FLAGS](metahost-config-flags-enumeration.md) Wert, der angibt, ob für das [\<startup>](../../configure-apps/file-schema/startup/startup-element.md) Element das `useLegacyV2RuntimeActivationPolicy` Attribut festgelegt ist, und den Wert des Attributs. Wenden Sie die [METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK](metahost-config-flags-enumeration.md) Maske auf an `pdwConfigFlags` , um die für relevanten Werte zu erhalten `useLegacyV2RuntimeActivationPolicy` .|
|`riid`|in Gibt den Schnittstellen Bezeichner IID_ICLRRuntimeInfo für die angeforderte [iclrruntimeingefo](iclrruntimeinfo-interface.md) -Schnittstelle an.|
|`ppRuntime`|vorgenommen `GetRequestedRuntime`Enthält bei der Rückgabe einen Zeiger auf die entsprechende [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) -Schnittstelle.|

## <a name="remarks"></a>Bemerkungen

Wenn diese Methode erfolgreich ist, hat sie den Nebeneffekt, zusätzliche Flags mit den aktuellen Standardstartflags der zurückgegebenen Laufzeitschnittstelle zu kombinieren, dies allerdings nur dann, wenn ein oder mehrere der folgenden Elemente im Konfigurationsstream innerhalb des `<configuration><runtime>`-Abschnitts vorhanden sind:

- `<gcServer enabled="true"/>` bewirkt, dass `STARTUP_SERVER_GC` festgelegt wird.

- `<etwEnable enabled="true"/>` bewirkt, dass `STARTUP_ETW` festgelegt wird.

- `<appDomainResourceMonitoring enabled="true"/>` bewirkt, dass `STARTUP_ARM` festgelegt wird.

Der sich ergebende Standard-`STARTUP_FLAGS`-Wert ist die bitweise ODER-Kombination der Werte, die von der vorangehenden Liste festgelegt wurden, mit den Standardstartflags.

## <a name="return-value"></a>Rückgabewert

Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.

|HRESULT|BESCHREIBUNG|
|-------------|-----------------|
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|
|E_POINTER|`pwzVersion` ist ungleich NULL, und `pcchVersion` ist gleich NULL.<br /><br /> Oder<br /><br /> `pwzImageVersion` ist ungleich NULL, und `pcchImageVersion` ist gleich NULL.|
|E_INVALIDARG|`dwPolicyFlags` gibt nicht `METAHOST_POLICY_HIGHCOMPAT` an.|
|ERROR_INSUFFICIENT_BUFFER|`pwzVersion` ist nicht genügend Arbeitsspeicher zugewiesen.<br /><br /> Oder<br /><br /> `pwzImageVersion` ist nicht genügend Arbeitsspeicher zugewiesen.|
|CLR_E_SHIM_RUNTIMELOAD|`dwPolicyFlags` enthält METAHOST_POLICY_APPLY_UPGRADE_POLICY und sowohl `pwzVersion` als auch `pcchVersion` sind gleich NULL.|

## <a name="requirements"></a>Requirements (Anforderungen)

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** MetaHost. h

**Bibliothek:** Als Ressource in Mscoree. dll enthalten

**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]

## <a name="see-also"></a>Weitere Informationen:

- [ICLRMetaHostPolicy-Schnittstelle](iclrmetahostpolicy-interface.md)
- [In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [Hosten von Schnittstellen](hosting-interfaces.md)
- [Hosting](index.md)

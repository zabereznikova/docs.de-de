---
title: METAHOST_POLICY_FLAGS-Enumeration
ms.date: 03/30/2017
api_name:
- METAHOST_POLICY_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- METAHOST_POLICY_FLAGS
helpviewer_keywords:
- METAHOST_POLICY_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 3bb4b526-0118-42e2-ba59-c95648528ce9
topic_type:
- apiref
ms.openlocfilehash: 048286fb9e1af34cd964fb5b21892778f9575d2c
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75938193"
---
# <a name="metahost_policy_flags-enumeration"></a>METAHOST_POLICY_FLAGS-Enumeration
Stellt Bindungs Richtlinien bereit, die den meisten Lauf Zeit Hosts gemeinsam sind. Diese Enumeration wird von der [ICLRMetaHostPolicy:: GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) -Methode verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum {  
    METAHOST_POLICY_HIGHCOMPAT              = 0x00,  
    METAHOST_POLICY_APPLY_UPGRADE_POLICY    = 0x08,  
    METAHOST_POLICY_EMULATE_EXE_LAUNCH      = 0x10,  
    METAHOST_POLICY_SHOW_ERROR_DIALOG       = 0x20,  
    METAHOST_POLICY_USE_PROCESS_IMAGE_PATH  = 0x40,  
    METAHOST_POLICY_ENSURE_SKU_SUPPORTED    = 0x80,  
    METAHOST_POLICY_IGNORE_ERROR_MODE       = 0x1000  
  
} METAHOST_POLICY_FLAGS;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`METAHOST_POLICY_HIGHCOMPAT`|Definiert die Richtlinie für hohe Kompatibilität, bei der keine Common Language Runtime (CLR) berücksichtigt werden, die in den aktuellen Prozess geladen werden. Stattdessen werden nur die installierten clrs und die Einstellungen der Komponente, die von der Assemblydatei selbst abgeleitet sind, die deklarierte integrierte Version oder die Konfigurationsdatei berücksichtigt.|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|Wendet die Upgraderichtlinie auf das Versions Bindungs Ergebnis an, wenn keine genaue Entsprechung gefunden wurde, basierend auf dem Inhalt HKEY_LOCAL_MACHINE \Software\Microsoft\\. Netframework\policy\upgrades. Dies hat die gleiche Wirkung wie [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|Bindungs Ergebnisse werden zurückgegeben, als ob das Bild, das für den-Rückruf bereitgestellt wird, in einem neuen Prozess gestartet wurde. Zurzeit ignoriert `GetRequestedRuntime` den Satz von Lade baren Laufzeiten und bindet Sie an den Satz installierter Laufzeiten. Mit diesem Flag kann ein Host ermitteln, an welche Laufzeit eine exe-Datei beim Start gebunden wird.|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|Wenn `GetRequestedRuntime` keine Laufzeit finden kann, die mit den Eingabe Parametern kompatibel ist, wird ein Fehler Dialogfeld angezeigt. Beginnend mit dem .NET Framework 4,5 kann dieses Dialogfeld "Fehler" in Form eines Windows-Features angezeigt werden, in dem Sie gefragt werden, ob der Benutzer die entsprechende Funktion aktivieren möchte.|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|`GetRequestedRuntime` verwendet das Prozess Image (und die entsprechende Konfigurationsdatei) als zusätzliche Eingabe für den Bindungsprozess. Standardmäßig wird `GetRequestedRuntime` nicht auf den Prozess Image Pfad (in der Regel die exe-Datei, die zum Starten des Prozesses verwendet wurde) zurückgreifen, wenn die Laufzeit bestimmt wird, an die die Bindung erfolgen soll.|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|`GetRequestedRuntime` müssen prüfen, ob die entsprechende SKU installiert ist, wenn in der Konfigurationsdatei keine Informationen verfügbar sind. Dadurch können Anwendungen, die keine Konfigurationsdateien aufweisen, auf kleineren SKUs ordnungsgemäß fehlschlagen als die Standardinstallation der .NET Framework. Standardmäßig überprüft `GetRequestedRuntime` nicht, ob die entsprechende SKU installiert ist, es sei denn, das SKU-Attribut ist in der Konfigurationsdatei `<supportedRuntime />` Element angegeben.|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|`GetRequestedRuntime` sollte SEM_FAILCRITICALERRORS ignorieren (durch Aufrufen der [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) -Funktion festgelegt) und das Fehler Dialogfeld anzeigen. Standardmäßig SEM_FAILCRITICALERRORS unterdrückt das Fehler Dialogfeld. Möglicherweise wurde sie von einem anderen Prozess geerbt, und der automatische Fehler ist in Ihrem Szenario nicht erwünscht.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [GetRequestedRuntime-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)

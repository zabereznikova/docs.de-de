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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be6aaf33331f432d1f3104962fa4e88c68534f03
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54729895"
---
# <a name="metahostpolicyflags-enumeration"></a>METAHOST_POLICY_FLAGS-Enumeration
Enthält Bindungsrichtlinien für die, die für die meisten Laufzeithosts gelten. Diese Enumeration wird verwendet, durch die [ICLRMetaHostPolicy:: GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) Methode.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
|`METAHOST_POLICY_HIGHCOMPAT`|Definiert die hohe Kompatibilität-Richtlinie, die keine common Language Runtime (CLR) halten, die in den aktuellen Prozess geladen wird. Stattdessen betrachtet sie als nur die installierten CLRs und die Einstellungen der Komponente, wie von der Assemblydatei selbst, die deklarierten integriert-mit-Version oder die Konfigurationsdatei abgeleitet.|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|Das Ergebnis der Version Bind Upgraderichtlinie gilt, wenn eine genaue Übereinstimmung basierend auf den Inhalt der HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft nicht gefunden wird,\\. NETFramework\Policy\Upgrades. Dies hat dieselbe Wirkung wie das [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|Bindungsergebnisse werden zurückgegeben, als ob das Abbild bereitgestellt, um den Aufruf in einen neuen Prozess gestartet wurden. Derzeit `GetRequestedRuntime` ignoriert den Satz von ladbare Laufzeiten und für die Festlegung installierter Runtimes bindet. Dieses Flag ermöglicht, einen Host aus, um zu bestimmen, welche Laufzeit eine EXE-Datei gebunden wird, wenn er gestartet wird.|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|Ein Fehlerdialogfeld wird angezeigt, wenn `GetRequestedRuntime` kann eine Runtime ermitteln, die mit den Eingabeparametern kompatibel ist. Beginnend mit der [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], das Dialogfeld "Fehler" dauert des Formulars eines Dialogfelds Windows-Funktion mit der Frage, ob der Benutzer das entsprechende Feature aktivieren möchten.|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|`GetRequestedRuntime` wird das Bild (und alle entsprechenden Konfigurationsdatei) als zusätzliche Eingabe an den Bindungsprozess verwendet. In der Standardeinstellung `GetRequestedRuntime` kein Fallback auf den Prozess-Image-Pfad (in der Regel die EXE-Datei, die zum Starten des Prozesses verwendet wurde) beim Bestimmen der Laufzeit zum Binden an.|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|`GetRequestedRuntime` müssen überprüfen, ob die entsprechende SKU installiert wird, wenn keine Informationen verfügbar, in der Konfigurationsdatei sind. Dadurch können Anwendungen, die keine Konfigurationsdateien, um auf kleineren SKUs als die standardmäßige Installation von .NET Framework ordnungsgemäß abgebrochen haben. In der Standardeinstellung `GetRequestedRuntime` überprüft nicht, ob die entsprechende SKU installiert ist, es sei denn, das SKU-Attribut in der Konfigurationsdatei angegeben ist `<supportedRuntime />` Element.|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|`GetRequestedRuntime` müssen überprüfen, ob die entsprechende SKU installiert wird, wenn keine Informationen verfügbar, in der Konfigurationsdatei sind. Dadurch können Anwendungen, die keine Konfigurationsdateien, um auf kleineren SKUs als die standardmäßige Installation von .NET Framework ordnungsgemäß abgebrochen haben. In der Standardeinstellung `GetRequestedRuntime` überprüft nicht, ob die entsprechende SKU installiert ist, es sei denn, das SKU-Attribut in der Konfigurationsdatei angegeben ist `<supportedRuntime />` Element.|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|`GetRequestedRuntime` SEM_FAILCRITICALERRORS ignorieren soll (das wird festgelegt, durch den Aufruf der [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) Funktion), und zeigen Sie im Dialogfeld "Fehler". Standardmäßig unterdrückt SEM_FAILCRITICALERRORS das Fehlerdialogfeld. Es wurde von einem anderen Prozess geerbt, und der automatische Fehler ist möglicherweise in Ihrem Szenario nicht erwünscht.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Metahost.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [GetRequestedRuntime-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)

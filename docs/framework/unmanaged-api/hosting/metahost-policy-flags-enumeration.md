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
ms.openlocfilehash: f980fb1336adaf43091e41b9e42ea008b00c033f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447277"
---
# <a name="metahostpolicyflags-enumeration"></a>METAHOST_POLICY_FLAGS-Enumeration
Stellt Bindungsrichtlinien für die, die für die meisten Laufzeithosts gelten. Diese Enumeration wird verwendet, durch die [ICLRMetaHostPolicy:: GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) Methode.  
  
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
|`METAHOST_POLICY_HIGHCOMPAT`|Definiert die hohe Kompatibilität-Richtlinie, die nicht common Language Runtime (CLR) betrachtet wird, die in den aktuellen Prozess geladen wird. Stattdessen, betrachtet er nur die installierten CLRs und die Einstellungen der Komponente, wie die Assemblydatei selbst, die deklarierten erstellt für Version oder die Konfigurationsdatei abgeleitet.|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|Das Ergebnis der Version Bind Upgraderichtlinie betrifft, wenn eine genaue Übereinstimmung nicht gefunden wird, basierend auf den Inhalt der HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework\Policy\Upgrades. Dies hat dieselbe Wirkung wie das [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|Bindungsergebnisse werden zurückgegeben, als ob das Abbild bereitgestellt, um den Aufruf in einen neuen Prozess gestartet wurden. Derzeit `GetRequestedRuntime` ignoriert den Satz von ladbaren Laufzeiten und mit der Menge der installierten Laufzeiten bindet. Dieses Flag ermöglicht es einen Host, um zu bestimmen, welcher Laufzeitversion eine EXE-Datei gebunden wird, wenn er gestartet wird.|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|Ein Fehlerdialogfeld wird angezeigt, wenn `GetRequestedRuntime` wurde eine Laufzeit gefunden, die mit den Eingabeparametern kompatibel ist. Beginnend mit der [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], diesem Fehlerdialogfeld dauert das Formular eines Dialogfelds Windows-Funktion mit der Frage, ob der Benutzer für das entsprechende Feature aktivieren möchten.|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|`GetRequestedRuntime` verwendet die Prozess-Image (und alle entsprechenden Konfigurationsdatei) als zusätzliche Eingabe, um des Bindungsvorgangs. Standardmäßig `GetRequestedRuntime` liegt nicht zurück auf den Prozess-Image-Pfad (in der Regel die EXE-Datei, die zum Starten des Prozesses verwendet wurde) beim Bestimmen der Laufzeit zum Binden an.|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|`GetRequestedRuntime` muss überprüfen, ob die entsprechende SKU installiert wird, wenn keine Informationen in der Konfigurationsdatei verfügbar sind. Dadurch können Anwendungen, die keine Konfigurationsdateien ordnungsgemäß auf kleinere SKUs als die standardmäßige Installation von .NET Framework ein Fehler auf. Standardmäßig `GetRequestedRuntime` überprüft nicht, ob die entsprechende SKU installiert ist, es sei denn, das SKU-Attribut in der Konfigurationsdatei angegeben wird `<supportedRuntime />` Element.|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|`GetRequestedRuntime` muss überprüfen, ob die entsprechende SKU installiert wird, wenn keine Informationen in der Konfigurationsdatei verfügbar sind. Dadurch können Anwendungen, die keine Konfigurationsdateien ordnungsgemäß auf kleinere SKUs als die standardmäßige Installation von .NET Framework ein Fehler auf. Standardmäßig `GetRequestedRuntime` überprüft nicht, ob die entsprechende SKU installiert ist, es sei denn, das SKU-Attribut in der Konfigurationsdatei angegeben wird `<supportedRuntime />` Element.|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|`GetRequestedRuntime` SEM_FAILCRITICALERRORS zu ignorieren (die festgelegt wird, durch Aufrufen der [SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkId=255242) Funktion), und zeigen Sie im Dialogfeld "Fehler". Standardmäßig wird die SEM_FAILCRITICALERRORS das Fehlerdialogfeld unterdrückt. Es wurde von einem anderen Prozess geerbt, und die automatische Fehler ist möglicherweise nicht erwünscht, in Ihrem Szenario.|  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Metahost.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hosten von Enumerationen](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
 [GetRequestedRuntime-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)

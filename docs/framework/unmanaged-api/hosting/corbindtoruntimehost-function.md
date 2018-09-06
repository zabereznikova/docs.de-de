---
title: CorBindToRuntimeHost-Funktion
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeHost
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeHost
helpviewer_keywords:
- CorBindToRuntimeHost function [.NET Framework hosting]
ms.assetid: 5c826ba3-8258-49bc-a417-78807915fcaf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1952121a6c0c735926944c839c3c7e8a8db5fb53
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43723193"
---
# <a name="corbindtoruntimehost-function"></a>CorBindToRuntimeHost-Funktion
Ermöglicht es Hosts, eine angegebene Version der Common Language Runtime (CLR) in einen Prozess zu laden.  
  
 Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CorBindToRuntimeHost (  
    [in] LPCWSTR       pwszVersion,   
    [in] LPCWSTR       pwszBuildFlavor,   
    [in] LPCWSTR       pwszHostConfigFile,   
    [in] VOID*         pReserved,   
    [in] DWORD         startupFlags,   
    [in] REFCLSID      rclsid,   
    [in] REFIID        riid,   
    [out] LPVOID FAR  *ppv  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pwszVersion`  
 [in] Eine Zeichenfolge, welche die Version der zu ladenden CLR beschreibt.  
  
 Eine Versionsnummer in .NET Framework besteht aus vier Teilen, die durch Punkte getrennt sind: *"Hauptversion.Nebenversion.Build.Revision"*. Die als `pwszVersion` übergebene Zeichenfolge muss mit dem Buchstaben "v" beginnen, auf den die ersten drei Teile der Versionsnummer folgen (z. B. "v1.0.1529").  
  
 Einige Versionen der CLR werden mit einer Richtlinienanweisung installiert, welche die Kompatibilität mit früheren Versionen der CLR angibt. In der Standardeinstellung wertet das Startmodul `pwszVersion` anhand von Richtlinienanweisungen aus und lädt die neueste Version der Common Language Runtime, die mit der angeforderten Version kompatibel ist. Ein Host kann erzwingen, dass das Startmodul die Richtlinienauswertung überspringt und genau die in `pwszVersion` angegebene Version lädt, indem für `startupFlags` der Wert STARTUP_LOADER_SAFEMODE übergeben wird.  
  
 Wenn `pwszVersion``null,` ist, wird keine Version der CLR geladen. Stattdessen wird "CLR_E_SHIM_RUNTIMELOAD" zurückgegeben, womit angegeben wird, dass die Laufzeit nicht geladen werden konnte.  
  
 `pwszBuildFlavor`  
 [in] Eine Zeichenfolge, die angibt, ob der Serverbuild oder der Arbeitsstationsbuild der CLR geladen werden soll. Gültige Werte sind `svr` und `wks`. Der Serverbuild wurde so optimiert, dass mehrere Prozessoren zur Ausführung der Garbage Collection genutzt werden können. Der Arbeitsstationsbuild wurde für die Ausführung von Clientanwendungen auf einem Computer mit einem einzelnen Prozessor optimiert.  
  
 Wenn `pwszBuildFlavor` nastaven NA hodnotu null, das Arbeitsstationsbuild geladen wird. Bei Ausführung auf einem Computer mit einem Prozessor wird immer das Arbeitsstationsbuild geladen, auch wenn `pwszBuildFlavor` nastaven NA hodnotu `svr`. Jedoch wenn `pwszBuildFlavor` nastaven NA hodnotu `svr` und die gleichzeitige Garbagecollection angegeben wird (finden Sie in der Beschreibung der `startupFlags` Parameter), wird das Serverbuild geladen.  
  
> [!NOTE]
>  Die gleichzeitige Garbage Collection wird nicht in Anwendungen unterstützt, die den WOW64 x86-Emulator auf 64-Bit-Systemen mit einer Implementierung der Intel Itanium-Architektur (früher als IA-64 bezeichnet) ausführen. Weitere Informationen zur Verwendung von WOW64 auf 64-Bit-Windows-Systemen finden Sie unter [Ausführen von 32-Bit-Anwendungen](/windows/desktop/WinProg64/running-32-bit-applications).  
  
 `pwszHostConfigFile`  
 [in] Der Name einer Hostkonfigurationsdatei, welche die zu ladende Version der CLR angibt. Wenn der Dateiname keinen vollqualifizierten Pfad enthält, wird angenommen, dass sich die Datei in demselben Verzeichnis befindet wie die ausführbare Datei, die den Aufruf ausgeführt hat.  
  
 `pReserved`  
 [in] Für zukünftige Erweiterungen reserviert.  
  
 `startupFlags`  
 [in] Ein Satz von Flags, welche die gleichzeitige Garbage Collection, domänenneutralen Code und das Verhalten des `pwszVersion`-Parameters steuern. Wenn kein Flag festgelegt ist, gilt als Standardwert die Einzeldomäne. Eine Liste der unterstützten Werte finden Sie unter den [STARTUP_FLAGS-Enumeration](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md).  
  
 `rclsid`  
 [in] Die `CLSID` der Co-Klasse, die entweder implementiert die [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) oder [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) Schnittstelle. Unterstützte Werte sind "CLSID_CorRuntimeHost" oder "CLSID_CLRRuntimeHost".  
  
 `riid`  
 [in] Die `IID` der angeforderten Schnittstelle. Unterstützte Werte sind "IID_ICorRuntimeHost" oder "IID_ICLRRuntimeHost".  
  
 `ppv`  
 [out] Ein Schnittstellenzeiger auf die Version der Common Language Runtime, die geladen wurde.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** mscoree  
  
 **Bibliothek:** "Mscoree.dll"  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [CorBindToCurrentRuntime-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [CorBindToRuntime-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 [CorBindToRuntimeByCfg-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 [CorBindToRuntimeEx-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [ICorRuntimeHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)

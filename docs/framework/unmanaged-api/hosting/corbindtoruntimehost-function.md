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
ms.openlocfilehash: 7ba35823ccb670ad0201d1950687dc83cc9ba64a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673738"
---
# <a name="corbindtoruntimehost-function"></a>CorBindToRuntimeHost-Funktion

Ermöglicht es Hosts, eine angegebene Version der Common Language Runtime (CLR) in einen Prozess zu laden.  
  
 Diese Funktion wurde im .NET Framework 4 als veraltet markiert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
  
## <a name="parameters"></a>Parameter  

 `pwszVersion`  
 [in] Eine Zeichenfolge, welche die Version der zu ladenden CLR beschreibt.  
  
 Eine Versionsnummer im .NET Framework besteht aus vier Teilen, die durch Zeiträume getrennt sind: *Major. Minor. Build. Revision*. Die als `pwszVersion` übergebene Zeichenfolge muss mit dem Buchstaben "v" beginnen, auf den die ersten drei Teile der Versionsnummer folgen (z. B. "v1.0.1529").  
  
 Einige Versionen der CLR werden mit einer Richtlinienanweisung installiert, welche die Kompatibilität mit früheren Versionen der CLR angibt. In der Standardeinstellung wertet das Startmodul `pwszVersion` anhand von Richtlinienanweisungen aus und lädt die neueste Version der Common Language Runtime, die mit der angeforderten Version kompatibel ist. Ein Host kann erzwingen, dass das Startmodul die Richtlinienauswertung überspringt und genau die in `pwszVersion` angegebene Version lädt, indem für `startupFlags` der Wert STARTUP_LOADER_SAFEMODE übergeben wird.  
  
 Wenn `pwszVersion``null,` ist, wird keine Version der CLR geladen. Stattdessen wird "CLR_E_SHIM_RUNTIMELOAD" zurückgegeben, womit angegeben wird, dass die Laufzeit nicht geladen werden konnte.  
  
 `pwszBuildFlavor`  
 [in] Eine Zeichenfolge, die angibt, ob der Serverbuild oder der Arbeitsstationsbuild der CLR geladen werden soll. Gültige Werte sind `svr` und `wks`. Der Serverbuild wurde so optimiert, dass mehrere Prozessoren zur Ausführung der Garbage Collection genutzt werden können. Der Arbeitsstationsbuild wurde für die Ausführung von Clientanwendungen auf einem Computer mit einem einzelnen Prozessor optimiert.  
  
 Wenn `pwszBuildFlavor` auf NULL festgelegt ist, wird der Arbeitsstations Build geladen. Bei der Ausführung auf einem Computer mit einem einzelnen Prozessor wird der Arbeitsstations Build immer geladen, auch wenn `pwszBuildFlavor` auf festgelegt ist `svr` . Wenn jedoch `pwszBuildFlavor` auf festgelegt ist `svr` und gleichzeitige Garbage Collection angegeben ist (siehe Beschreibung des `startupFlags` Parameters), wird der Serverbuild geladen.  
  
> [!NOTE]
> Die gleichzeitige Garbage Collection wird nicht in Anwendungen unterstützt, die den WOW64 x86-Emulator auf 64-Bit-Systemen mit einer Implementierung der Intel Itanium-Architektur (früher als IA-64 bezeichnet) ausführen. Weitere Informationen zur Verwendung von WOW64 auf 64-Bit-Windows-Systemen finden Sie unter [Ausführen von 32-Bit-Anwendungen](/windows/desktop/WinProg64/running-32-bit-applications).  
  
 `pwszHostConfigFile`  
 [in] Der Name einer Hostkonfigurationsdatei, welche die zu ladende Version der CLR angibt. Wenn der Dateiname keinen vollqualifizierten Pfad enthält, wird angenommen, dass sich die Datei in demselben Verzeichnis befindet wie die ausführbare Datei, die den Aufruf ausgeführt hat.  
  
 `pReserved`  
 [in] Für zukünftige Erweiterungen reserviert.  
  
 `startupFlags`  
 [in] Ein Satz von Flags, welche die gleichzeitige Garbage Collection, domänenneutralen Code und das Verhalten des `pwszVersion`-Parameters steuern. Wenn kein Flag festgelegt ist, gilt als Standardwert die Einzeldomäne. Eine Liste der unterstützten Werte finden Sie in der [STARTUP_FLAGS-Enumeration](startup-flags-enumeration.md).  
  
 `rclsid`  
 in Der `CLSID` der Co-Klasse, die entweder die [ICorRuntimeHost](icorruntimehost-interface.md) -oder die [ICLRRuntimeHost](iclrruntimehost-interface.md) -Schnittstelle implementiert. Unterstützte Werte sind "CLSID_CorRuntimeHost" oder "CLSID_CLRRuntimeHost".  
  
 `riid`  
 [in] Die `IID` der angeforderten Schnittstelle. Unterstützte Werte sind "IID_ICorRuntimeHost" oder "IID_ICLRRuntimeHost".  
  
 `ppv`  
 [out] Ein Schnittstellenzeiger auf die Version der Common Language Runtime, die geladen wurde.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. idl  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [CorBindToCurrentRuntime-Funktion](corbindtocurrentruntime-function.md)
- [CorBindToRuntime-Funktion](corbindtoruntime-function.md)
- [CorBindToRuntimeByCfg-Funktion](corbindtoruntimebycfg-function.md)
- [CorBindToRuntimeEx-Funktion](corbindtoruntimeex-function.md)
- [ICorRuntimeHost-Schnittstelle](icorruntimehost-interface.md)
- [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md)

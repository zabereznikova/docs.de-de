---
title: CorBindToRuntime-Funktion
ms.date: 03/30/2017
api_name:
- CorBindToRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntime
helpviewer_keywords:
- CorBindToRuntime function [.NET Framework hosting]
ms.assetid: 799740aa-46ec-4532-95da-6444565b4971
topic_type:
- apiref
ms.openlocfilehash: 52594c36c54c74941371f9950fbc6fb543b86de0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493551"
---
# <a name="corbindtoruntime-function"></a>CorBindToRuntime-Funktion
Ermöglicht es nicht verwalteten Hosts, die Common Language Runtime (CLR) in einen Prozess zu laden.  
  
 Diese Funktion wurde im .NET Framework 4 als veraltet markiert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CorBindToRuntime (  
    [in]  LPCWSTR     pwszVersion,
    [in]  LPCWSTR     pwszBuildFlavor,
    [in]  REFCLSID    rclsid,
    [in]  REFIID      riid,
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pwszVersion`  
 [in] Eine Zeichenfolge, die die Version der zu ladenden CLR beschreibt.  
  
 Eine Versionsnummer im .NET Framework besteht aus vier Teilen, die durch Zeiträume getrennt sind: *Major. Minor. Build. Revision*. Die als `pwszVersion` übergebene Zeichenfolge muss mit dem Buchstaben "v" beginnen, auf den die ersten drei Teile der Versionsnummer folgen (z. B. "v1.0.1529").  
  
 Einige Versionen der CLR werden mit einer Richtlinienanweisung installiert, welche die Kompatibilität mit früheren Versionen der CLR angibt. In der Standardeinstellung wertet das Startmodul `pwszVersion` anhand von Richtlinienanweisungen aus und lädt die neueste Version der Common Language Runtime, die mit der angeforderten Version kompatibel ist. Ein Host kann erzwingen, dass das Startmodul die Richtlinienauswertung überspringt und genau die in `pwszVersion` angegebene Version lädt, indem wie unten beschrieben der Wert `STARTUP_LOADER_SAFEMODE` für den `flags`-Parameter übergeben wird.  
  
 Wenn der Aufrufer NULL für angibt `pwszVersion` , wird die aktuelle Version der Laufzeit geladen. Durch die Übergabe von NULL erhält der Host keine Kontrolle darüber, welche Version der Laufzeit geladen wird. Auch wenn dieser Ansatz in einigen Szenarien angemessen sein kann, wird das Angeben einer bestimmten zu ladenden Version durch den Host dringend empfohlen.  
  
 `pwszBuildFlavor`  
 [in] Eine Zeichenfolge, die angibt, ob der Serverbuild oder der Arbeitsstationsbuild der CLR geladen werden soll. Gültige Werte sind `svr` und `wks`. Der Serverbuild wurde so optimiert, dass mehrere Prozessoren zur Ausführung der Garbage Collection genutzt werden können. Der Arbeitsstationsbuild wurde für die Ausführung von Clientanwendungen auf einem Computer mit einem einzelnen Prozessor optimiert.  
  
 Wenn `pwszBuildFlavor` auf NULL festgelegt ist, wird der Arbeitsstations Build geladen. Bei der Ausführung auf einem Computer mit einem einzelnen Prozessor wird der Arbeitsstations Build immer geladen, auch wenn `pwszBuildFlavor` auf festgelegt ist `svr` . Wenn jedoch `pwszBuildFlavor` auf festgelegt ist `svr` und gleichzeitige Garbage Collection angegeben ist (siehe Beschreibung des `flags` Parameters), wird der Serverbuild geladen.  
  
 `rclsid`  
 in Der `CLSID` der Co-Klasse, die entweder die [ICorRuntimeHost](icorruntimehost-interface.md) -oder die [ICLRRuntimeHost](iclrruntimehost-interface.md) -Schnittstelle implementiert. Unterstützte Werte sind "CLSID_CorRuntimeHost" oder "CLSID_CLRRuntimeHost".  
  
 `riid`  
 [in] Die `IID` der angeforderten Schnittstelle aus `rclsid`. Unterstützte Werte sind "IID_ICorRuntimeHost" oder "IID_ICLRRuntimeHost".  
  
 `ppv`  
 [out] Der zurückgegebene Schnittstellenzeiger auf `riid`.  
  
## <a name="remarks"></a>Bemerkungen  
 Wenn `pwszVersion` eine Laufzeitversion angibt, die nicht vorhanden ist, gibt `CorBindToRuntimeEx` den HRESULT-Wert CLR_E_SHIM_RUNTIMELOAD zurück.  
  
## <a name="execution-context-and-flow-of-windows-identity"></a>Ausführungskontext und Übergabe der Windows-Identität  
 In Version 1 der CLR wird das <xref:System.Security.Principal.WindowsIdentity>-Objekt nicht über asynchrone Punkte wie neue Threads, Threadpools oder Timerrückrufe übergeben. In Version 2.0 der CLR umschließt ein <xref:System.Threading.ExecutionContext>-Objekt einige Informationen zum aktuell ausgeführten Thread und übergibt ihn über einen asynchronen Punkt, aber innerhalb der Anwendungsdomäne. Auf ähnliche Weise wird auch das <xref:System.Security.Principal.WindowsIdentity>-Objekt über einen asynchronen Punkt übergeben. Deshalb wird auch der aktuelle Identitätswechsel auf dem Thread (sofern vorhanden) übergeben.  
  
 Sie können den Fluss auf zwei Weisen ändern:  
  
1. Durch Ändern der <xref:System.Threading.ExecutionContext>-Einstellungen wird die Übergabe für einzelne Threads unterdrückt (siehe die Methoden <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A> und <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A>).  
  
2. Durch Ändern des Prozessstandardmodus in den Kompatibilitätsmodus für Version 1; hier wird das <xref:System.Security.Principal.WindowsIdentity>-Objekt nicht über asynchrone Punkte übergeben, unabhängig von den <xref:System.Threading.ExecutionContext>-Einstellungen des aktuellen Threads. Wie der Standardmodus geändert wird, hängt davon ab, ob Sie zum Laden der CLR eine verwaltete ausführbare Datei oder eine nicht verwaltete Hostschnittstelle verwenden:  
  
    1. Bei verwalteten ausführbaren Dateien müssen Sie das- `enabled` Attribut des- [\<legacyImpersonationPolicy>](../../configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) Elements auf festlegen `true` .  
  
    2. Legen Sie bei nicht verwalteten Hostschnittstellen das `STARTUP_LEGACY_IMPERSONATION`-Flag im `flags`-Parameter fest, wenn Sie die `CorBindToRuntimeEx`-Funktion aufrufen.  
  
     Der Kompatibilitätsmodus für Version 1 gilt für den gesamten Prozess und alle Anwendungsdomänen im Prozess.  
  
## <a name="remarks"></a>Bemerkungen  
 [CorBindToRuntimeEx](corbindtoruntimeex-function.md) und `CorBindToRuntime` führen denselben Vorgang aus, aber mit der- `CorBindToRuntimeEx` Funktion können Sie Flags festlegen, um das Verhalten der CLR anzugeben.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [CorBindToCurrentRuntime-Funktion](corbindtocurrentruntime-function.md)
- [CorBindToRuntimeByCfg-Funktion](corbindtoruntimebycfg-function.md)
- [CorBindToRuntimeEx-Funktion](corbindtoruntimeex-function.md)
- [CorBindToRuntimeHost-Funktion](corbindtoruntimehost-function.md)
- [ICorRuntimeHost-Schnittstelle](icorruntimehost-interface.md)
- [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md)

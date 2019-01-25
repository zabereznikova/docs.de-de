---
title: Veraltete CLR-Hostingfunktionen
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 576b60293ed53448f3829fdcc9f89ad8508599af
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580902"
---
# <a name="deprecated-clr-hosting-functions"></a>Veraltete CLR-Hostingfunktionen
In diesem Abschnitt werden die nicht verwalteten globalen statischen Funktionen beschrieben, die von früheren Versionen der Hosting-API verwendet wurden.  
  
 Mit Ausnahme von Infrastrukturfunktionen (`_Cor*`-Funktionen), die nur von .NET Framework verwendet werden, sind diese Funktionen in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.  
  
## <a name="activation-functions"></a>Aktivierungsfunktionen  
 [ClrCreateManagedInstance-Funktion](../../../../docs/framework/unmanaged-api/hosting/clrcreatemanagedinstance-function.md)  
 Veraltet. Erstellt eine Instanz des angegebenen verwalteten Typs.  
  
 [CoInitializeCor-Funktion](../../../../docs/framework/unmanaged-api/hosting/coinitializecor-function.md)  
 Veraltet. Um die common Language Runtime (CLR) zu initialisieren, verwenden Sie entweder [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) oder [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).  
  
 [CoInitializeEE-Funktion](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)  
 Veraltet. Stellt sicher, dass die CLR-Ausführungs-Engine in einen Prozess geladen wird. Verwenden der [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) Methode stattdessen.  
  
 [CorBindToCurrentRuntime-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 Veraltet. Lädt die Common Language Runtime (CLR) in einen Prozess, indem in einer XML-Datei gespeicherte Versionsinformationen verwendet werden.  
  
 [CorBindToRuntime-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 Veraltet. Ermöglicht es nicht verwalteten Hosts, die CLR in einen Prozess zu laden.  
  
 [CorBindToRuntimeByCfg-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 Veraltet. Lädt die CLR in einen Prozess, indem aus einer XML-Datei gelesene Versionsinformationen verwendet werden.  
  
 [CorBindToRuntimeEx-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 Veraltet. Ermöglicht nicht verwalteten Hosts, die CLR in einen Prozess zu laden, und ermöglicht Ihnen, Flags festzulegen, um das Verhalten der CLR anzugeben.  
  
 [CorBindToRuntimeHost-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 Veraltet. Ermöglicht Hosts, eine angegebene Version der CLR in einen Prozess zu laden.  
  
 [GetCORRequiredVersion-Funktion](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md)  
 Veraltet. Ruft die erforderliche CLR-Versionsnummer ab.  
  
 [GetCORSystemDirectory-Funktion](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md)  
 Veraltet. Gibt das Installationsverzeichnis der CLR zurück, die in den Prozess geladen wird.  
  
 [GetRealProcAddress-Funktion](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md)  
 Veraltet. Ruft die Adresse der angegebenen Funktion ab, die aus der letzten installierten Version der CLR exportiert wird.  
  
 [GetRequestedRuntimeInfo-Funktion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 Veraltet. Ruft Version und Verzeichnisinformationen über die CLR ab, die von einer Anwendung angefordert wurden.  
  
## <a name="clr-version-functions"></a>CLR-Versionsfunktionen  
 Die Funktionen in diesem Abschnitt geben eine CLR-Version zurück; sie aktivieren nicht die CLR.  
  
 [GetCORVersion-Funktion](../../../../docs/framework/unmanaged-api/hosting/getcorversion-function.md)  
 Veraltet. Gibt die Versionsnummer der CLR zurück, die im aktuellen Prozess ausgeführt wird.  
  
 [GetFileVersion-Funktion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)  
 Veraltet. Ruft mithilfe des angegebenen Puffers die Versionsinformationen der CLR für die angegebene Datei ab.  
  
 [GetRequestedRuntimeVersion-Funktion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 Veraltet. Ruft die Versionsnummer der CLR ab, die von der angegebenen Anwendung angefordert wird. Wenn diese Version nicht installiert ist, wird die letzte installierte Version vor der angeforderten Version abgerufen.  
  
 [GetRequestedRuntimeVersionForCLSID-Funktion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversionforclsid-function.md)  
 Veraltet. Ruft die entsprechenden CLR-Versionsinformationen für die Klasse mit der angegebenen CLSID ab.  
  
 [GetVersionFromProcess-Funktion](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 Veraltet. Ruft die Versionsnummer der CLR ab, die dem angegebenen Prozesshandle zugeordnet ist.  
  
 [LockClrVersion-Funktion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)  
 Veraltet. Ermöglicht dem Host, zu bestimmen, welche Version der CLR innerhalb des Prozesses verwendet werden soll, bevor die CLR explizit initialisiert wird.  
  
## <a name="hosting-functions"></a>Hostingfunktionen  
 [CallFunctionShim-Funktion](../../../../docs/framework/unmanaged-api/hosting/callfunctionshim-function.md)  
 Veraltet. Ruft eine Funktion mit dem angegebenen Namen und den angegebenen Parametern in der angegebenen Bibliothek auf.  
  
 [CoEEShutDownCOM-Funktion](../../../../docs/framework/unmanaged-api/hosting/coeeshutdowncom-function.md)  
 Veraltet. Entlädt eine COM-Assembly aus dem Prozess.  
  
 [CorExitProcess-Funktion](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)  
 Veraltet. Beendet den aktuellen nicht verwalteten Prozess.  
  
 [CorLaunchApplication-Funktion](../../../../docs/framework/unmanaged-api/hosting/corlaunchapplication-function.md)  
 Veraltet. Startet die Anwendung im angegebenen Netzwerkpfad, wobei die angegebenen Manifeste und sonstigen Anwendungsdaten verwendet werden.  
  
 [CorMarkThreadInThreadPool-Funktion](../../../../docs/framework/unmanaged-api/hosting/cormarkthreadinthreadpool-function.md)  
 Veraltet. Markiert den aktuell ausgeführten Thread aus dem Threadpool für die Ausführung von verwaltetem Code. Ab .NET Framework Version 2.0 besitzt diese Funktion keine Auswirkungen. Sie ist nicht erforderlich und kann aus dem Code entfernt werden.  
  
 [CoUninitializeCor-Funktion](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)  
 Veraltet. Die CLR kann nicht aus einem Prozess entladen werden.  
  
 [CoUninitializeEE-Funktion](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md)  
 Veraltet.  
  
 [CreateDebuggingInterfaceFromVersion-Funktion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md)  
 Veraltet. Erstellt eine [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) -Objekt auf Grundlage der angegebenen Versionsinformationen.  
  
 [CreateICeeFileGen-Funktion](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md)  
 Veraltet. Erstellt eine [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) Objekt.  
  
 [DestroyICeeFileGen-Funktion](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md)  
 Veraltet. Zerstört ein [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) Objekt.  
  
 [FExecuteInAppDomainCallback-Funktionszeiger](../../../../docs/framework/unmanaged-api/hosting/fexecuteinappdomaincallback-function-pointer.md)  
 Veraltet. Zeigt auf eine Funktion, die die CLR zum Ausführen von verwaltetem Code aufruft.  
  
 [FLockClrVersionCallback-Funktionszeiger](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md)  
 Veraltet. Zeigt auf eine Funktion, die die CLR aufruft, um den Host zu benachrichtigen, dass die Initialisierung gestartet oder abgeschlossen wurde.  
  
 [GetCLRIdentityManager-Funktion](../../../../docs/framework/unmanaged-api/hosting/getclridentitymanager-function.md)  
 Veraltet. Ruft einen Zeiger auf eine Schnittstelle ab, die es der CLR ermöglicht, Identitäten zu verwalten.  
  
 [LoadLibraryShim-Funktion](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md)  
 Veraltet. Lädt die angegebene Version einer .NET Framework-DLL.  
  
 [LoadStringRC-Funktion](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
 Veraltet. Übersetzt einen HRESULT-Wert in eine Fehlermeldung, wobei die Standardkultur des aktuellen Threads verwendet wird.  
  
 [LoadStringRCEx-Funktion](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
 Veraltet. Übersetzt einen HRESULT-Wert in eine entsprechende Fehlermeldung für die angegebene Kultur.  
  
 [LPOVERLAPPED_COMPLETION_ROUTINE-Funktionszeiger](../../../../docs/framework/unmanaged-api/hosting/lpoverlapped-completion-routine-function-pointer.md)  
 Veraltet. Zeigt auf eine Funktion, die den Host benachrichtigt, wenn eine überlappende (d. h. asynchrone) E/A auf einem Gerät abgeschlossen ist.  
  
 [LPTHREAD_START_ROUTINE-Funktionszeiger](../../../../docs/framework/unmanaged-api/hosting/lpthread-start-routine-function-pointer.md)  
 Veraltet. Zeigt auf eine Funktion, die den Host benachrichtigt, dass eine Threadausführung begonnen hat.  
  
 [RunDll32ShimW-Funktion](../../../../docs/framework/unmanaged-api/hosting/rundll32shimw-function.md)  
 Veraltet. Führt den angegebenen Befehl aus.  
  
 [WAITORTIMERCALLBACK-Funktionszeiger](../../../../docs/framework/unmanaged-api/hosting/waitortimercallback-function-pointer.md)  
 Veraltet. Zeigt auf eine Funktion, die den Host benachrichtigt, dass ein Wait-Handle signalisiert wurde oder das Zeitlimit überschritten hat.  
  
## <a name="infrastructure-functions"></a>Infrastrukturfunktionen  
 Die Funktionen in diesem Abschnitt gelten nur für .NET Framework.  
  
 [_CorDllMain-Funktion](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)  
 Initialisiert die CLR, sucht den verwalteten Einstiegspunkt im CLR-Header der DLL-Assembly und startet die Ausführung.  
  
 [_CorExeMain-Funktion](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)  
 Initialisiert die CLR, sucht den verwalteten Einstiegspunkt im CLR-Header der ausführbaren Assembly und startet die Ausführung.  
  
 [_CorExeMain2-Funktion](../../../../docs/framework/unmanaged-api/hosting/corexemain2-function.md)  
 Führt den Einstiegspunkt im angegebenen Speicherabbildcode aus. Diese Funktion wird vom Betriebssystemladeprogramm aufgerufen.  
  
 [_CorImageUnloading-Funktion](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md)  
 Benachrichtigt das Ladeprogramm, wenn die Images des verwalteten Moduls entladen werden.  
  
 [_CorValidateImage-Funktion](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)  
 Überprüft Images des verwalteten Moduls, und benachrichtigt das Betriebssystemladeprogramm, nachdem sie geladen wurden.  
  
## <a name="see-also"></a>Siehe auch
- [Hosten globaler statischer .NET Framework 4-Funktionen](../../../../docs/framework/unmanaged-api/hosting/net-framework-4-hosting-global-static-functions.md)

---
title: Veraltete CLR-Hostingfunktionen
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
ms.openlocfilehash: 9e19502672973f292991b72c7ea9b4fdc17f5707
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673123"
---
# <a name="deprecated-clr-hosting-functions"></a>Veraltete CLR-Hostingfunktionen

In diesem Abschnitt werden die nicht verwalteten globalen statischen Funktionen beschrieben, die von früheren Versionen der Hosting-API verwendet wurden.  
  
 Mit Ausnahme der Infrastrukturfunktionen ( `_Cor*` Funktionen), die nur vom .NET Framework verwendet werden, wurden diese Funktionen in .NET Framework 4 als veraltet markiert.  
  
## <a name="activation-functions"></a>Aktivierungsfunktionen  

 [ClrCreateManagedInstance-Funktion](clrcreatemanagedinstance-function.md)  
 Veraltet. Erstellt eine Instanz des angegebenen verwalteten Typs.  
  
 [CoInitializeCor-Funktion](coinitializecor-function.md)  
 Veraltet. Verwenden Sie zum Initialisieren des Common Language Runtime (CLR) entweder [corbindtoriuntimeex](corbindtoruntimeex-function.md) oder [corbindumcurrentruntime](corbindtocurrentruntime-function.md).  
  
 [CoInitializeEE-Funktion](coinitializeee-function.md)  
 Veraltet. Stellt sicher, dass die CLR-Ausführungs-Engine in einen Prozess geladen wird. Verwenden Sie stattdessen die [ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) -Methode.  
  
 [CorBindToCurrentRuntime-Funktion](corbindtocurrentruntime-function.md)  
 Veraltet. Lädt die Common Language Runtime (CLR) in einen Prozess, indem in einer XML-Datei gespeicherte Versionsinformationen verwendet werden.  
  
 [CorBindToRuntime-Funktion](corbindtoruntime-function.md)  
 Veraltet. Ermöglicht es nicht verwalteten Hosts, die CLR in einen Prozess zu laden.  
  
 [CorBindToRuntimeByCfg-Funktion](corbindtoruntimebycfg-function.md)  
 Veraltet. Lädt die CLR in einen Prozess, indem aus einer XML-Datei gelesene Versionsinformationen verwendet werden.  
  
 [CorBindToRuntimeEx-Funktion](corbindtoruntimeex-function.md)  
 Veraltet. Ermöglicht nicht verwalteten Hosts, die CLR in einen Prozess zu laden, und ermöglicht Ihnen, Flags festzulegen, um das Verhalten der CLR anzugeben.  
  
 [CorBindToRuntimeHost-Funktion](corbindtoruntimehost-function.md)  
 Veraltet. Ermöglicht Hosts, eine angegebene Version der CLR in einen Prozess zu laden.  
  
 [GetCORRequiredVersion-Funktion](getcorrequiredversion-function.md)  
 Veraltet. Ruft die erforderliche CLR-Versionsnummer ab.  
  
 [GetCORSystemDirectory-Funktion](getcorsystemdirectory-function.md)  
 Veraltet. Gibt das Installationsverzeichnis der CLR zurück, die in den Prozess geladen wird.  
  
 [GetRealProcAddress-Funktion](getrealprocaddress-function.md)  
 Veraltet. Ruft die Adresse der angegebenen Funktion ab, die aus der letzten installierten Version der CLR exportiert wird.  
  
 [GetRequestedRuntimeInfo-Funktion](getrequestedruntimeinfo-function.md)  
 Veraltet. Ruft Version und Verzeichnisinformationen über die CLR ab, die von einer Anwendung angefordert wurden.  
  
## <a name="clr-version-functions"></a>CLR-Versionsfunktionen  

 Die Funktionen in diesem Abschnitt geben eine CLR-Version zurück; sie aktivieren nicht die CLR.  
  
 [GetCORVersion-Funktion](getcorversion-function.md)  
 Veraltet. Gibt die Versionsnummer der CLR zurück, die im aktuellen Prozess ausgeführt wird.  
  
 [GetFileVersion-Funktion](getfileversion-function.md)  
 Veraltet. Ruft mithilfe des angegebenen Puffers die Versionsinformationen der CLR für die angegebene Datei ab.  
  
 [GetRequestedRuntimeVersion-Funktion](getrequestedruntimeversion-function.md)  
 Veraltet. Ruft die Versionsnummer der CLR ab, die von der angegebenen Anwendung angefordert wird. Wenn diese Version nicht installiert ist, wird die letzte installierte Version vor der angeforderten Version abgerufen.  
  
 [GetRequestedRuntimeVersionForCLSID-Funktion](getrequestedruntimeversionforclsid-function.md)  
 Veraltet. Ruft die entsprechenden CLR-Versionsinformationen für die Klasse mit der angegebenen CLSID ab.  
  
 [GetVersionFromProcess-Funktion](getversionfromprocess-function.md)  
 Veraltet. Ruft die Versionsnummer der CLR ab, die dem angegebenen Prozesshandle zugeordnet ist.  
  
 [LockClrVersion-Funktion](lockclrversion-function.md)  
 Veraltet. Ermöglicht dem Host, zu bestimmen, welche Version der CLR innerhalb des Prozesses verwendet werden soll, bevor die CLR explizit initialisiert wird.  
  
## <a name="hosting-functions"></a>Hostingfunktionen  

 [CallFunctionShim-Funktion](callfunctionshim-function.md)  
 Veraltet. Ruft eine Funktion mit dem angegebenen Namen und den angegebenen Parametern in der angegebenen Bibliothek auf.  
  
 [CoEEShutDownCOM-Funktion](coeeshutdowncom-function.md)  
 Veraltet. Entlädt eine COM-Assembly aus dem Prozess.  
  
 [CorExitProcess-Funktion](corexitprocess-function.md)  
 Veraltet. Beendet den aktuellen nicht verwalteten Prozess.  
  
 [CorLaunchApplication-Funktion](corlaunchapplication-function.md)  
 Veraltet. Startet die Anwendung im angegebenen Netzwerkpfad, wobei die angegebenen Manifeste und sonstigen Anwendungsdaten verwendet werden.  
  
 [CorMarkThreadInThreadPool-Funktion](cormarkthreadinthreadpool-function.md)  
 Veraltet. Markiert den aktuell ausgeführten Thread aus dem Threadpool für die Ausführung von verwaltetem Code. Ab .NET Framework Version 2.0 besitzt diese Funktion keine Auswirkungen. Sie ist nicht erforderlich und kann aus dem Code entfernt werden.  
  
 [CoUninitializeCor-Funktion](couninitializecor-function.md)  
 Veraltet. Die CLR kann nicht aus einem Prozess entladen werden.  
  
 [CoUninitializeEE-Funktion](couninitializeee-function.md)  
 Veraltet.  
  
 [CreateDebuggingInterfaceFromVersion-Funktion](createdebugginginterfacefromversion-function.md)  
 Veraltet. Erstellt ein [ICorDebug](../debugging/icordebug-interface.md) -Objekt auf Grundlage der angegebenen Versionsinformationen.  
  
 [CreateICeeFileGen-Funktion](createiceefilegen-function.md)  
 Veraltet. Erstellt ein [ICeeFileGen](iceefilegen-class.md) -Objekt.  
  
 [DestroyICeeFileGen-Funktion](destroyiceefilegen-function.md)  
 Veraltet. Zerstört ein [ICeeFileGen](iceefilegen-class.md) -Objekt.  
  
 [FExecuteInAppDomainCallback-Funktionszeiger](fexecuteinappdomaincallback-function-pointer.md)  
 Veraltet. Zeigt auf eine Funktion, die die CLR zum Ausführen von verwaltetem Code aufruft.  
  
 [FLockClrVersionCallback-Funktionszeiger](flockclrversioncallback-function-pointer.md)  
 Veraltet. Zeigt auf eine Funktion, die die CLR aufruft, um den Host zu benachrichtigen, dass die Initialisierung gestartet oder abgeschlossen wurde.  
  
 [GetCLRIdentityManager-Funktion](getclridentitymanager-function.md)  
 Veraltet. Ruft einen Zeiger auf eine Schnittstelle ab, die es der CLR ermöglicht, Identitäten zu verwalten.  
  
 [LoadLibraryShim-Funktion](loadlibraryshim-function.md)  
 Veraltet. Lädt die angegebene Version einer .NET Framework-DLL.  
  
 [LoadStringRC-Funktion](loadstringrc-function.md)  
 Veraltet. Übersetzt einen HRESULT-Wert in eine Fehlermeldung, wobei die Standardkultur des aktuellen Threads verwendet wird.  
  
 [LoadStringRCEx-Funktion](loadstringrcex-function.md)  
 Veraltet. Übersetzt einen HRESULT-Wert in eine entsprechende Fehlermeldung für die angegebene Kultur.  
  
 [LPOVERLAPPED_COMPLETION_ROUTINE-Funktionszeiger](lpoverlapped-completion-routine-function-pointer.md)  
 Veraltet. Zeigt auf eine Funktion, die den Host benachrichtigt, wenn eine überlappende (d. h. asynchrone) E/A auf einem Gerät abgeschlossen ist.  
  
 [LPTHREAD_START_ROUTINE-Funktionszeiger](lpthread-start-routine-function-pointer.md)  
 Veraltet. Zeigt auf eine Funktion, die den Host benachrichtigt, dass eine Threadausführung begonnen hat.  
  
 [RunDll32ShimW-Funktion](rundll32shimw-function.md)  
 Veraltet. Führt den angegebenen Befehl aus.  
  
 [WAITORTIMERCALLBACK-Funktionszeiger](waitortimercallback-function-pointer.md)  
 Veraltet. Zeigt auf eine Funktion, die den Host benachrichtigt, dass ein Wait-Handle signalisiert wurde oder das Zeitlimit überschritten hat.  
  
## <a name="infrastructure-functions"></a>Infrastrukturfunktionen  

 Die Funktionen in diesem Abschnitt gelten nur für .NET Framework.  
  
 [_CorDllMain-Funktion](cordllmain-function.md)  
 Initialisiert die CLR, sucht den verwalteten Einstiegspunkt im CLR-Header der DLL-Assembly und startet die Ausführung.  
  
 [_CorExeMain-Funktion](corexemain-function.md)  
 Initialisiert die CLR, sucht den verwalteten Einstiegspunkt im CLR-Header der ausführbaren Assembly und startet die Ausführung.  
  
 [_CorExeMain2-Funktion](corexemain2-function.md)  
 Führt den Einstiegspunkt im angegebenen Speicherabbildcode aus. Diese Funktion wird vom Betriebssystemladeprogramm aufgerufen.  
  
 [_CorImageUnloading-Funktion](corimageunloading-function.md)  
 Benachrichtigt das Ladeprogramm, wenn die Images des verwalteten Moduls entladen werden.  
  
 [_CorValidateImage-Funktion](corvalidateimage-function.md)  
 Überprüft Images des verwalteten Moduls, und benachrichtigt das Betriebssystemladeprogramm, nachdem sie geladen wurden.  
  
## <a name="see-also"></a>Weitere Informationen

- [Hosten globaler statischer .NET Framework 4-Funktionen](net-framework-4-hosting-global-static-functions.md)

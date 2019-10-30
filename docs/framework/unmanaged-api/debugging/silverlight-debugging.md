---
title: Silverlight-Debugging
ms.date: 03/30/2017
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 5e903e04-17d0-4014-ac9a-a43330ec8b1c
ms.openlocfilehash: b7af03197a43976c47b7ddc30346d622e6b97207
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139137"
---
# <a name="silverlight-debugging"></a>Silverlight-Debugging
In den Themen dieses Abschnitts sind die Umgebung und die Schnittstellen beschrieben, mit denen die Common Language Runtime (CLR) das Debuggen von Silverlight-basierten Anwendungen unterstützt, die unter Windows oder auf der Macintosh-Plattform ausgeführt werden.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [EnumerateCLRs-Funktion](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)  
 Stellt einen Mechanismus für das Auflisten der CLRs in einem Prozess bereit.  
  
 [CloseCLREnumeration-Funktion](../../../../docs/framework/unmanaged-api/debugging/closeclrenumeration-function.md)  
 Schließt alle gültigen CLR-Continue-Startup-Ereignisse in einem Array von Handles, die von der [enumerateclrs-Funktion](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)zurückgegeben werden, und gibt den Arbeitsspeicher für die Array-und Zeichen folgen Pfad Arrays frei.  
  
 [CreateCoreClrDebugTarget-Funktion](../../../../docs/framework/unmanaged-api/debugging/createcoreclrdebugtarget-function.md)  
 Erstellt eine Verbindung mit einem Remoteziel für eine Prozess- und Runtime-Enumeration.  
  
 [CreateCordbObject-Funktion](../../../../docs/framework/unmanaged-api/debugging/createcordbobject-function.md)  
 Erstellt eine Debugschnittstelle, die Funktionen zum Instanziieren einer verwalteten Debugsitzung für einen Remoteprozess bereitstellt.  
  
 [CreateVersionStringFromModule-Funktion](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)  
 Erstellt eine Versionszeichenfolge aus einem CLR-Pfad in einem Zielprozess.  
  
 [CreateDebuggingInterfaceFromVersion-Funktion](../../../../docs/framework/unmanaged-api/debugging/createdebugginginterfacefromversion-function-for-silverlight.md)  
 Akzeptiert eine CLR-Versions Zeichenfolge, die von der Funktion "die Funktion" der Funktion "" der Funktion "" der [Funktion "Funktion](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)" zurückgegeben wird  
  
 [CoreClrDebugProcInfo-Struktur](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md)  
 Entspricht einem Prozess, der auf einem Remotecomputer ausgeführt wird.  
  
 [CoreClrDebugRuntimeInfo-Struktur](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md)  
 Stellt eine CLR-Instanz dar, die in einem Prozess auf einem Remotecomputer geladen ist.  
  
 [GetStartupNotificationEvent-Funktion](../../../../docs/framework/unmanaged-api/debugging/getstartupnotificationevent-function.md)  
 Erstellt oder öffnet ein Ereignishandle, das über jede CLR-Runtime (Common Language Runtime) benachrichtigt wird, die im angegebenen Zielprozess geladen wird.  
  
 [ICoreClrDebugTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)  
 Erstellt eine Verbindung mit einem Remoteziel für eine Prozess- und Runtime-Enumeration.  
  
 [InitDbgTransportManager-Funktion](../../../../docs/framework/unmanaged-api/debugging/initdbgtransportmanager-function.md)  
 Initialisiert den Transport-Manager, um eine Verbindung mit einem Remoteziel für eine Prozess- und Runtime-Enumeration herzustellen.  
  
 [ShutdownDbgTransportManager-Funktion](../../../../docs/framework/unmanaged-api/debugging/shutdowndbgtransportmanager-function.md)  
 Fährt den Transport-Manager für eine Verbindung mit einem Remotecomputer herunter.  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Co-Klassen](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen von globalen statischen Funktionen](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
- [Debuggen von Enumerationen](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)

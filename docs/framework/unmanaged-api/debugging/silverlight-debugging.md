---
title: Silverlight-Debugging
ms.date: 03/30/2017
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 5e903e04-17d0-4014-ac9a-a43330ec8b1c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d20bc002e52c3c6a42b45c0d1c5d559e65dc52c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59113697"
---
# <a name="silverlight-debugging"></a>Silverlight-Debugging
In den Themen dieses Abschnitts sind die Umgebung und die Schnittstellen beschrieben, mit denen die Common Language Runtime (CLR) das Debuggen von Silverlight-basierten Anwendungen unterstützt, die unter Windows oder auf der Macintosh-Plattform ausgeführt werden.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [EnumerateCLRs-Funktion](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)  
 Stellt einen Mechanismus für das Auflisten der CLRs in einem Prozess bereit.  
  
 [CloseCLREnumeration-Funktion](../../../../docs/framework/unmanaged-api/debugging/closeclrenumeration-function.md)  
 Schließt alle gültigen CLR weiterhin-Startup-Ereignisse in ein Array von Handles, die vom der [EnumerateCLRs-Funktion](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md), und den Speicher für den Pfad von Handle- und Zeichenfolgenarrays freigegeben.  
  
 [CreateCoreClrDebugTarget-Funktion](../../../../docs/framework/unmanaged-api/debugging/createcoreclrdebugtarget-function.md)  
 Erstellt eine Verbindung mit einem Remoteziel für eine Prozess- und Runtime-Enumeration.  
  
 [CreateCordbObject-Funktion](../../../../docs/framework/unmanaged-api/debugging/createcordbobject-function.md)  
 Erstellt eine Debugschnittstelle, die Funktionen zum Instanziieren einer verwalteten Debugsitzung für einen Remoteprozess bereitstellt.  
  
 [CreateVersionStringFromModule-Funktion](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)  
 Erstellt eine Versionszeichenfolge aus einem CLR-Pfad in einem Zielprozess.  
  
 [CreateDebuggingInterfaceFromVersion-Funktion](../../../../docs/framework/unmanaged-api/debugging/createdebugginginterfacefromversion-function-for-silverlight.md)  
 Akzeptiert eine CLR-Versionszeichenfolge Merry [CreateVersionStringFromModule-Funktion](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)Funktion, und gibt eine entsprechende Debuggerschnittstelle zurück.  
  
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
- [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen von globalen statischen Funktionen](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
- [Debugenumerationen](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)

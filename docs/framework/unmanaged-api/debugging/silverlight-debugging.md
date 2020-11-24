---
title: Silverlight-Debugging
ms.date: 03/30/2017
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 5e903e04-17d0-4014-ac9a-a43330ec8b1c
ms.openlocfilehash: 49f026b8e1a3dd78a62091e77a5aba0c9a2e09d6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671836"
---
# <a name="silverlight-debugging"></a>Silverlight-Debugging

In den Themen dieses Abschnitts sind die Umgebung und die Schnittstellen beschrieben, mit denen die Common Language Runtime (CLR) das Debuggen von Silverlight-basierten Anwendungen unterstützt, die unter Windows oder auf der Macintosh-Plattform ausgeführt werden.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [EnumerateCLRs-Funktion](enumerateclrs-function.md)  
 Stellt einen Mechanismus für das Auflisten der CLRs in einem Prozess bereit.  
  
 [CloseCLREnumeration-Funktion](closeclrenumeration-function.md)  
 Schließt alle gültigen CLR-Continue-Startup-Ereignisse in einem Array von Handles, die von der [enumerateclrs-Funktion](enumerateclrs-function.md)zurückgegeben werden, und gibt den Arbeitsspeicher für die Array-und Zeichen folgen Pfad Arrays frei.  
  
 [CreateCoreClrDebugTarget-Funktion](createcoreclrdebugtarget-function.md)  
 Erstellt eine Verbindung mit einem Remoteziel für eine Prozess- und Runtime-Enumeration.  
  
 [CreateCordbObject-Funktion](createcordbobject-function.md)  
 Erstellt eine Debugschnittstelle, die Funktionen zum Instanziieren einer verwalteten Debugsitzung für einen Remoteprozess bereitstellt.  
  
 [CreateVersionStringFromModule-Funktion](createversionstringfrommodule-function.md)  
 Erstellt eine Versionszeichenfolge aus einem CLR-Pfad in einem Zielprozess.  
  
 [CreateDebuggingInterfaceFromVersion-Funktion](createdebugginginterfacefromversion-function-for-silverlight.md)  
 Akzeptiert eine CLR-Versions Zeichenfolge, die von der Funktion "die Funktion" der Funktion "" der Funktion "" der [Funktion "Funktion](createversionstringfrommodule-function.md)" zurückgegeben wird  
  
 [CoreClrDebugProcInfo-Struktur](coreclrdebugprocinfo-structure.md)  
 Entspricht einem Prozess, der auf einem Remotecomputer ausgeführt wird.  
  
 [CoreClrDebugRuntimeInfo-Struktur](coreclrdebugruntimeinfo-structure.md)  
 Stellt eine CLR-Instanz dar, die in einem Prozess auf einem Remotecomputer geladen ist.  
  
 [GetStartupNotificationEvent-Funktion](getstartupnotificationevent-function.md)  
 Erstellt oder öffnet ein Ereignishandle, das über jede CLR-Runtime (Common Language Runtime) benachrichtigt wird, die im angegebenen Zielprozess geladen wird.  
  
 [ICoreClrDebugTarget-Schnittstelle](icoreclrdebugtarget-interface.md)  
 Erstellt eine Verbindung mit einem Remoteziel für eine Prozess- und Runtime-Enumeration.  
  
 [InitDbgTransportManager-Funktion](initdbgtransportmanager-function.md)  
 Initialisiert den Transport-Manager, um eine Verbindung mit einem Remoteziel für eine Prozess- und Runtime-Enumeration herzustellen.  
  
 [ShutdownDbgTransportManager-Funktion](shutdowndbgtransportmanager-function.md)  
 Fährt den Transport-Manager für eine Verbindung mit einem Remotecomputer herunter.  
  
## <a name="see-also"></a>Weitere Informationen

- [Debuggen von Co-Klassen](debugging-coclasses.md)
- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen von globalen statischen Funktionen](debugging-global-static-functions.md)
- [Debugenumerationen](debugging-enumerations.md)
- [Debuggen von Strukturen](debugging-structures.md)

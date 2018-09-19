---
title: Hostinganweisungen des Internetinformationsdiensts
ms.date: 03/30/2017
ms.assetid: 959a21c8-9d9d-4757-b255-4e57793ae9d6
ms.openlocfilehash: 303fe47df987901b09cee8cc4292f12bcda2b74d
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46320919"
---
# <a name="internet-information-service-hosting-instructions"></a>Hostinganweisungen des Internetinformationsdiensts
Zum Ausführen der Beispiele, die vom Internetinformationsdienst (IIS) gehostet werden, müssen Sie sicherstellen, dass der IIS ordnungsgemäß installiert ist und ausgeführt wird.  
  
### <a name="to-install-iis-version-75-on-windows-server-2008-r2"></a>So installieren Sie IIS Version 7.5 bei Windows Server 2008 R2  
  
1.  Von **Server-Manager**Option **Rollen.** Klicken Sie unter **Rollenübersicht**, klicken Sie auf **Hinzufügen von Rollen**.  
  
2.  Klicken Sie auf **Weiter** zum Anzeigen der **Serverrollen auswählen** Dialogfeld.  
  
3.  Wählen Sie **Anwendungsserver** aus der **Rollen** aus, und klicken Sie dann auf **Weiter** zweimal, um Sie anzuzeigen die **Rollendienste auswählen** Dialogfeld für die Die Anwendungsserverrolle.  
  
4.  Wählen Sie die **Webserver (IIS)** Kontrollkästchen. Wenn Sie aufgefordert werden, zusätzliche Rollendienste und Features zu installieren, klicken Sie auf **erforderliche Features hinzufügen**. Klicken Sie auf **Weiter** zweimal, um die Anzeige der **Rollendienste auswählen** Dialogfeld für die Rolle Webserver (IIS).  
  
5.  Erweitern Sie **Verwaltungstools**, und erweitern Sie dann **IIS 6-Verwaltungskompatibilität**. Wählen Sie **IIS 6-Skripttools**. Wenn Sie aufgefordert werden, zusätzliche Rollendienste und Features zu installieren, klicken Sie auf **Erforderliche Rollendienste hinzufügen**. Klicken Sie auf **Weiter**.  
  
6.  Wenn die Zusammenfassung der Auswahl korrekt ist, klicken Sie auf **installieren**.  
  
7.  Wenn die Installation abgeschlossen ist, klicken Sie auf **schließen**.  
  
### <a name="to-install-iis-version-75-on-windows-7"></a>So installieren Sie IIS Version 7.5 unter Windows 7  
  
1.  Klicken Sie auf **starten**, und klicken Sie dann auf **Systemsteuerung**.  
  
2.  Öffnen der **Programme** Gruppe.  
  
3.  Klicken Sie unter **Programme und Funktionen**, klicken Sie auf **Windows-Funktionen ein- oder ausschalten**.  
  
4.  Die **User Account Control** Dialogfeld wird angezeigt. Klicken Sie auf **Weiter**.  
  
5.  Die **Windows Features** Dialogfeld wird angezeigt. Erweitern Sie das Element namens **Internet Information Services**.  
  
6.  Erweitern Sie das Element namens **WWW-Dienste**.  
  
7.  Erweitern Sie das Element namens **Application Development Features**.  
  
8.  Stellen Sie sicher, dass die folgenden Elemente ausgewählt sind:  
  
    1.  **NET-Erweiterbarkeit**  
  
    2.  **ASP.NET**  
  
    3.  **ISAPI-Erweiterungen**  
  
    4.  **ISAPI-Filter**  
  
9. Unter dem Element namens **WWW-Dienste**, erweitern Sie **allgemeine Http-Features**.  
  
10. Stellen Sie sicher, dass **statischer Inhalt** ausgewählt ist.  
  
11. Unter dem Element namens **WWW-Dienste**, erweitern Sie **Sicherheit**.  
  
12. Stellen Sie sicher, dass **Windows-Authentifizierung** ausgewählt ist.  
  
13. Unter den **Internet Information Services** Directory, erweitern Sie das Element namens **Webverwaltungstools**, und wählen Sie dann **IIS-Verwaltungskonsole**.  
  
14. Erweitern Sie das Element namens **IIS 6-Verwaltungskompatibilität**, und wählen Sie dann **IIS 6-Skriptingtools**.  
  
15. Unter den **Internet Information Services** Directory, erweitern Sie das Element namens **Microsoft .NET Framework 3.5.1**, und wählen Sie dann **Windows Communication Foundation-Http-Aktivierung**.  
  
16. Klicken Sie auf **OK**.  
  
### <a name="to-install-iis-version-70-on-windows-server-2008"></a>So installieren Sie IIS Version&#160;7.0 unter Windows Server 2008  
  
1.  Von **Server-Manager**Option **Rollen**. Klicken Sie unter **Rollenübersicht**, klicken Sie auf **Hinzufügen von Rollen**.  
  
2.  Klicken Sie auf **Weiter** zum Anzeigen der **Serverrollen auswählen** Dialogfeld.  
  
3.  Wählen Sie **Anwendungsserver** aus der **Rollen** aus, und klicken Sie dann auf **Weiter** zweimal, um Sie anzuzeigen die **Rollendienste auswählen** Dialogfeld für die Die Anwendungsserverrolle.  
  
4.  Wählen Sie **Webserver (IIS)** Kontrollkästchen. Wenn Sie aufgefordert werden, zusätzliche Rollendienste und Features zu installieren, klicken Sie auf **erforderliche Features hinzufügen**. Klicken Sie auf **Weiter** zweimal, um die Anzeige der **Rollendienste auswählen** Dialogfeld für die Rolle Webserver (IIS).  
  
5.  Erweitern Sie **Verwaltungstools**, und erweitern Sie dann **IIS 6-Verwaltungskompatibilität**. Wählen Sie **IIS 6-Skripttools**. Wenn Sie aufgefordert werden, zusätzliche Rollendienste und Features zu installieren, klicken Sie auf **Erforderliche Rollendienste hinzufügen**. Klicken Sie auf **Weiter**.  
  
6.  Wenn die Zusammenfassung der Auswahl korrekt ist, klicken Sie auf **installieren**.  
  
7.  Wenn die Installation abgeschlossen ist, klicken Sie auf **schließen**.  
  
### <a name="to-install-iis-version-70-on-windows-vista"></a>So installieren Sie IIS Version&#160;7.0 unter Windows Vista  
  
1.  Klicken Sie auf Start und anschließend auf Systemsteuerung.  
  
2.  Wählen Sie die **Programme** Gruppe.  
  
3.  Klicken Sie unter **Programme und Funktionen**, klicken Sie auf **Windows-Funktionen ein- oder ausschalten**.  
  
4.  Die **User Account Control** Dialogfeld wird angezeigt. Klicken Sie auf **Weiter**.  
  
5.  Die **Windows Features** Dialogfeld wird angezeigt. Erweitern Sie das Element namens **Internet Information Services**.  
  
6.  Erweitern Sie das Element namens **WWW-Dienste**.  
  
7.  Erweitern Sie das Element namens **Application Development Features**.  
  
8.  Stellen Sie sicher, dass die folgenden Elemente ausgewählt sind:  
  
    1.  **NET-Erweiterbarkeit**  
  
    2.  **ASP.NET**  
  
    3.  **ISAPI-Erweiterungen**  
  
    4.  **ISAPI-Filter**  
  
9. Erweitern Sie das Element namens **Webverwaltungstools**, und wählen Sie dann **IIS-Verwaltungskonsole**.  
  
10. Unter dem Element namens **WWW-Dienste**, erweitern Sie **allgemeine Http-Features**.  
  
11. Stellen Sie sicher, dass **statischer Inhalt** ausgewählt ist.  
  
12. Unter dem Element namens **WWW-Dienste**, erweitern Sie **Sicherheit**.  
  
13. Stellen Sie sicher, dass **Windows-Authentifizierung** ausgewählt ist.  
  
14. Erweitern Sie das Element namens **IIS 6-Verwaltungskompatibilität**, und wählen Sie dann **IIS 6-Skriptingtools**.  
  
15. Erweitern Sie das Element namens **Microsoft .NET Framework 3.0**, und wählen Sie dann **Windows Communication Foundation-Http-Aktivierung**.  
  
16. Klicken Sie auf **OK**.  
  
### <a name="to-install-iis-version-60-on-windows-server-2003"></a>So installieren Sie IIS Version 6.0 unter Windows Server 2003  
  
1.  Von **Serververwaltung**, klicken Sie auf **hinzufügen oder Entfernen einer Rolle**, und klicken Sie dann auf **Weiter**.  
  
2.  Wählen Sie **Anwendungsserver (IIS, ASP.NET)** aus der **Serverrolle** aus, und klicken Sie dann auf **Weiter**.  
  
3.  Wählen Sie **ASP.NET aktivieren** , und klicken Sie dann auf **Weiter**.  
  
4.  Wenn die Zusammenfassung der Auswahl korrekt ist, klicken Sie auf Weiter.  
  
### <a name="to-install-iis-version-51-on-windows-xp-with-service-pack-2-and-service-pack-3-installed"></a>So installieren Sie IIS Version 5.1 unter Windows XP mit installiertem Service Pack 2 und Service Pack 3  
  
1.  Klicken Sie in der Systemsteuerung auf **Software**.  
  
2.  In der **Software** Dialogfeld klicken Sie auf **Windows-Komponenten hinzufügen/entfernen**.  
  
3.  In der **Assistenten für Windows-Komponenten**, wählen die **(Internet Information Services, IIS)** , und klicken Sie dann auf **Weiter**.  
  
4.  Wenn die **benötigten Dateien** Dialogfeld wird angezeigt, fügen Sie den Betriebssystem-Installationsdatenträger, navigieren Sie zum Ordner "i386" und klicken Sie dann auf **OK**.  
  
5.  Wenn die Installation abgeschlossen ist, klicken Sie auf **Fertig stellen**.  
  
6.  Schließen Sie die **Software** (Dialogfeld), und schließen Sie **Systemsteuerung**.  
  
### <a name="to-verify-the-installation-of-iis-and-aspnet"></a>So überprüfen Sie die Installation von IIS und ASP.NET  
  
1.  Speichern Sie die HTML-Datei, die Sie am Ende dieses Themas finden, im Stammverzeichnis \InetPub\wwwroot unter dem Namen Default.aspx.  
  
2.  Öffnen Sie ein Browserfenster.  
  
3.  Typ `http://localhost/Default.aspx` in das Adressfeld ein, und drücken Sie dann die EINGABETASTE.  
  
4.  Es sollte eine Webseite mit dem Text "Hello World" angezeigt werden.  
  
> [!NOTE]
>  Jedes Mal, wenn Sie eine neue Version von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] installieren, müssen Sie aspnet_isapi erneut als Webdiensterweiterung für IIS registrieren. Dazu geben Sie den `aspnet_regiis –I –enable`-Befehl aus.  
  
## <a name="sample-code"></a>Beispielcode  
  
```xml  
<html>  
   <body>  
       <form >  
           <h3> Hello World  
           </h3>  
       </form>  
   </body>  
</html>  
```

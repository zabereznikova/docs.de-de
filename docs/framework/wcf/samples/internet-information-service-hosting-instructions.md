---
title: Hostinganweisungen des Internetinformationsdiensts
ms.date: 03/30/2017
ms.assetid: 959a21c8-9d9d-4757-b255-4e57793ae9d6
ms.openlocfilehash: 151c5ba8dd79e8554e7d79fb5b8182740b0be18e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96237689"
---
# <a name="internet-information-service-hosting-instructions"></a>Hostinganweisungen des Internetinformationsdiensts

Zum Ausführen der Beispiele, die vom Internetinformationsdienst (IIS) gehostet werden, müssen Sie sicherstellen, dass der IIS ordnungsgemäß installiert ist und ausgeführt wird.  
  
### <a name="to-install-iis-version-75-on-windows-server-2008-r2"></a>So installieren Sie IIS Version 7.5 bei Windows Server 2008 R2  
  
1. Wählen Sie unter **Server-Manager** die Option **Rollen aus.** Klicken Sie unter **Rollenübersicht** auf **Rollen hinzufügen**.  
  
2. Klicken Sie auf **weiter** , um das Dialogfeld **Server Rollen auswählen** anzuzeigen.  
  
3. Wählen Sie in der Liste **Rollen** die Option **Anwendungs Server** aus, und klicken Sie dann zweimal auf **weiter** , um das Dialogfeld **Rollen Dienste auswählen** für die Anwendungs Server Rolle anzuzeigen.  
  
4. Aktivieren Sie das Kontrollkästchen **Webserver (IIS)** . Wenn Sie aufgefordert werden, zusätzliche Rollen Dienste und Features zu installieren, klicken Sie auf **erforderliche Features hinzufügen**. Klicken Sie zweimal auf **weiter** , um das Dialogfeld **Rollen Dienste auswählen** für die Rolle Webserver (IIS) anzuzeigen.  
  
5. Erweitern Sie den Knoten **Verwaltung**, und erweitern Sie dann Kompatibilität mit der **IIS 6-Verwaltung**. Wählen Sie **IIS 6-Skript Tools** aus. Wenn Sie aufgefordert werden, zusätzliche Rollen Dienste und Features zu installieren, klicken Sie auf **erforderliche Rollen Dienste hinzufügen**. Klicken Sie auf **Weiter**.  
  
6. Wenn die Zusammenfassung der Auswahl richtig ist, klicken Sie auf **Installieren**.  
  
7. Wenn die Installation abgeschlossen ist, klicken Sie auf **Schließen**.  
  
### <a name="to-install-iis-version-75-on-windows-7"></a>So installieren Sie IIS Version 7.5 unter Windows 7  
  
1. Klicken Sie auf **Start** und dann auf **Systemsteuerung**.  
  
2. Öffnen Sie die Gruppe " **Programme** ".  
  
3. Klicken Sie unter **Programme und Funktionen** **auf Windows-Funktionen ein-oder ausschalten**.  
  
4. Das Dialogfeld **Benutzerkontensteuerung** wird angezeigt. Klicken Sie auf **Weiter**.  
  
5. Das Dialogfeld **Windows-Funktionen** wird angezeigt. Erweitern Sie das Element mit der Bezeichnung **Internetinformationsdienste**.  
  
6. Erweitern Sie das Element mit der Bezeichnung **World Wide Web Services**.  
  
7. Erweitern Sie das Element mit der Bezeichnung **Anwendungs Entwicklungsfunktionen**.  
  
8. Stellen Sie sicher, dass die folgenden Elemente ausgewählt sind:  
  
    1. **.NET-Erweiterbarkeit**  
  
    2. **ASP.NET**  
  
    3. **ISAPI-Erweiterungen**  
  
    4. **ISAPI-Filter**  
  
9. Erweitern Sie unter dem Element mit der Bezeichnung **World Wide Web Services** die Option **Allgemeine HTTP-Funktionen**.  
  
10. Stellen Sie sicher, dass **statischer Inhalt** ausgewählt ist.  
  
11. Erweitern Sie unter dem Element mit der Bezeichnung **World Wide Web Services** den Knoten **Sicherheit**.  
  
12. Stellen Sie sicher, dass **Windows-Authentifizierung** ausgewählt ist.  
  
13. Erweitern Sie unter dem Verzeichnis **Internetinformationsdienste** das Element mit der Bezeichnung **Webverwaltungs Tools**, und wählen Sie dann **IIS-Verwaltungskonsole** aus.  
  
14. Erweitern Sie das Element mit der Bezeichnung **IIS 6-Verwaltungs Kompatibilität**, und wählen Sie dann **IIS 6-Skript Tools** aus.  
  
15. Erweitern Sie unter dem Verzeichnis **Internetinformationsdienste** das Element mit der Bezeichnung **Microsoft .NET Framework 3.5.1**, und wählen Sie dann **Windows Communication Foundation http-Aktivierung** aus.  
  
16. Klicken Sie auf **OK**.  
  
### <a name="to-install-iis-version-70-on-windows-server-2008"></a>So installieren Sie IIS Version&#160;7.0 unter Windows Server 2008  
  
1. Wählen Sie unter **Server-Manager** die Option **Rollen** aus. Klicken Sie unter **Rollenübersicht** auf **Rollen hinzufügen**.  
  
2. Klicken Sie auf **weiter** , um das Dialogfeld **Server Rollen auswählen** anzuzeigen.  
  
3. Wählen Sie in der Liste **Rollen** die Option **Anwendungs Server** aus, und klicken Sie dann zweimal auf **weiter** , um das Dialogfeld **Rollen Dienste auswählen** für die Anwendungs Server Rolle anzuzeigen.  
  
4. Aktivieren Sie das Kontrollkästchen **Webserver (IIS)** . Wenn Sie aufgefordert werden, zusätzliche Rollen Dienste und Features zu installieren, klicken Sie auf **erforderliche Features hinzufügen**. Klicken Sie zweimal auf **weiter** , um das Dialogfeld **Rollen Dienste auswählen** für die Rolle Webserver (IIS) anzuzeigen.  
  
5. Erweitern Sie den Knoten **Verwaltung**, und erweitern Sie dann Kompatibilität mit der **IIS 6-Verwaltung**. Wählen Sie **IIS 6-Skript Tools** aus. Wenn Sie aufgefordert werden, zusätzliche Rollen Dienste und Features zu installieren, klicken Sie auf **erforderliche Rollen Dienste hinzufügen**. Klicken Sie auf **Weiter**.  
  
6. Wenn die Zusammenfassung der Auswahl richtig ist, klicken Sie auf **Installieren**.  
  
7. Wenn die Installation abgeschlossen ist, klicken Sie auf **Schließen**.  
  
### <a name="to-install-iis-version-70-on-windows-vista"></a>So installieren Sie IIS Version&#160;7.0 unter Windows Vista  
  
1. Klicken Sie auf Start und anschließend auf Systemsteuerung.  
  
2. Wählen Sie die Gruppe **Programme** aus.  
  
3. Klicken Sie unter **Programme und Funktionen** **auf Windows-Funktionen ein-oder ausschalten**.  
  
4. Das Dialogfeld **Benutzerkontensteuerung** wird angezeigt. Klicken Sie auf **Weiter**.  
  
5. Das Dialogfeld **Windows-Funktionen** wird angezeigt. Erweitern Sie das Element mit der Bezeichnung **Internetinformationsdienste**.  
  
6. Erweitern Sie das Element mit der Bezeichnung **World Wide Web Services**.  
  
7. Erweitern Sie das Element mit der Bezeichnung **Anwendungs Entwicklungsfunktionen**.  
  
8. Stellen Sie sicher, dass die folgenden Elemente ausgewählt sind:  
  
    1. **.NET-Erweiterbarkeit**  
  
    2. **ASP.NET**  
  
    3. **ISAPI-Erweiterungen**  
  
    4. **ISAPI-Filter**  
  
9. Erweitern Sie das Element mit der Bezeichnung **Webverwaltungs Tools**, und wählen Sie dann **IIS-Verwaltungskonsole** aus.  
  
10. Erweitern Sie unter dem Element mit der Bezeichnung **World Wide Web Services** die Option **Allgemeine HTTP-Funktionen**.  
  
11. Stellen Sie sicher, dass **statischer Inhalt** ausgewählt ist.  
  
12. Erweitern Sie unter dem Element mit der Bezeichnung **World Wide Web Services** den Knoten **Sicherheit**.  
  
13. Stellen Sie sicher, dass **Windows-Authentifizierung** ausgewählt ist.  
  
14. Erweitern Sie das Element mit der Bezeichnung **IIS 6-Verwaltungs Kompatibilität**, und wählen Sie dann **IIS 6-Skript Tools** aus.  
  
15. Erweitern Sie das Element mit der Bezeichnung **Microsoft .NET Framework 3,0**, und wählen Sie dann **Windows Communication Foundation http-Aktivierung** aus.  
  
16. Klicken Sie auf **OK**.  
  
### <a name="to-install-iis-version-60-on-windows-server-2003"></a>So installieren Sie IIS Version 6.0 unter Windows Server 2003  
  
1. Klicken Sie unter **Server verwalten** auf **Rolle hinzufügen oder entfernen**, und klicken Sie dann auf **weiter**.  
  
2. Wählen Sie in der Liste **Server Rolle** die Option **Anwendungsserver (IIS, ASP.net)** aus, und klicken Sie dann auf **weiter**.  
  
3. Aktivieren Sie das Kontrollkästchen **aktivieren ASP.net** , und klicken Sie dann auf **weiter**.  
  
4. Wenn die Zusammenfassung der Auswahl korrekt ist, klicken Sie auf Weiter.  
  
### <a name="to-install-iis-version-51-on-windows-xp-with-service-pack-2-and-service-pack-3-installed"></a>So installieren Sie IIS Version 5.1 unter Windows XP mit installiertem Service Pack 2 und Service Pack 3  
  
1. Klicken Sie in der Systemsteuerung auf **Software**.  
  
2. Klicken Sie im Dialogfeld **Software** auf **Windows-Komponenten hinzufügen/entfernen**.  
  
3. Aktivieren Sie im **Assistenten für Windows-Komponenten** das Kontrollkästchen **Internetinformationsdienste (IIS)** , und klicken Sie dann auf **weiter**.  
  
4. Wenn das Dialogfeld **erforderliche Dateien** angezeigt wird, legen Sie die Installations-CD des Betriebssystems ein, navigieren Sie zum Ordner i386, und klicken Sie dann auf **OK**.  
  
5. Wenn die Installation abgeschlossen ist, klicken Sie auf **Fertig** stellen.  
  
6. Schließen Sie das Dialogfeld Software, und schließen **Sie** dann die **Systemsteuerung**.  
  
### <a name="to-verify-the-installation-of-iis-and-aspnet"></a>So überprüfen Sie die Installation von IIS und ASP.NET  
  
1. Speichern Sie die HTML-Datei, die Sie am Ende dieses Themas finden, im Stammverzeichnis \InetPub\wwwroot unter dem Namen Default.aspx.  
  
2. Öffnen Sie ein Browserfenster.  
  
3. Geben `http://localhost/Default.aspx` Sie in das Feld Adresse ein, und drücken Sie dann die EINGABETASTE.  
  
4. Es sollte eine Webseite mit dem Text "Hello World" angezeigt werden.  
  
> [!NOTE]
> Jedes Mal, wenn Sie eine neue Version der .NET Framework installieren, müssen Sie Aspnet_isapi als Webdienst Erweiterung für IIS erneut registrieren. Dazu geben Sie den `aspnet_regiis –I –enable`-Befehl aus.  
  
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

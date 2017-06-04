---
title: "Hostinganweisungen des Internetinformationsdiensts | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: 959a21c8-9d9d-4757-b255-4e57793ae9d6
caps.latest.revision: 30
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 30
---
# Hostinganweisungen des Internetinformationsdiensts
Zum Ausführen der Beispiele, die vom Internetinformationsdienst \(IIS\) gehostet werden, müssen Sie sicherstellen, dass der IIS ordnungsgemäß installiert ist und ausgeführt wird.  
  
### So installieren Sie IIS Version 7.5 bei Windows Server 2008 R2  
  
1.  Wählen Sie im **Server\-Manager** die Option **Rollen** aus. Klicken Sie unter **Rollenübersicht** auf **Rollen hinzufügen**.  
  
2.  Klicken Sie auf **Weiter**, um das Dialogfeld **Serverrollen auswählen** anzuzeigen.  
  
3.  Wählen Sie **Anwendungsserver** in der Liste **Rollen** aus, und klicken Sie auf **Weiter**, um das Dialogfeld **Rollendienste auswählen** für die Anwendungsserverrolle anzuzeigen.  
  
4.  Aktivieren Sie das Kontrollkästchen **Webserver \(IIS\)**.  Wenn Sie aufgefordert werden, zusätzliche Rollendienste und Features zu installieren, klicken Sie auf **Erforderliche Features hinzufügen**.  Klicken Sie zweimal auf **Weiter**, um das Dialogfeld **Rollendienste auswählen** für die Rolle Webserver \(IIS\) anzuzeigen.  
  
5.  Erweitern Sie das Element **Verwaltungstools** und danach **Kompatibilität mit der IIS 6\-Verwaltung**.  Wählen Sie **IIS 6\-Skriptingtools** aus.  Wenn Sie aufgefordert werden, zusätzliche Rollendienste und Features zu installieren, klicken Sie auf **Erforderliche Rollendienste hinzufügen**.  Klicken Sie auf **Weiter**.  
  
6.  Wenn die Zusammenfassung der Auswahl korrekt ist, klicken Sie auf **Installieren**.  
  
7.  Nach Abschluss der Installation klicken Sie auf **Schließen**.  
  
### So installieren Sie IIS Version 7.5 unter Windows 7  
  
1.  Klicken Sie auf das Menü **Start** und anschließend auf **Systemsteuerung**.  
  
2.  Öffnen Sie die Gruppe **Programme**.  
  
3.  Klicken Sie unter **Programme und Funktionen** auf **Windows\-Funktionen ein\- oder ausschalten**.  
  
4.  Das Dialogfeld **Benutzerkontensteuerung** wird angezeigt.  Klicken Sie auf **Weiter**.  
  
5.  Das Dialogfeld **Windows\-Funktionen** wird angezeigt.  Erweitern Sie das Element namens **Internetinformationsdienste**.  
  
6.  Erweitern Sie das Element namens **World Wide Web\-Dienst**.  
  
7.  Erweitern Sie das Element namens **Anwendungsentwicklungsfeatures**.  
  
8.  Stellen Sie sicher, dass die folgenden Elemente ausgewählt sind:  
  
    1.  **.NET\-Erweiterbarkeit**  
  
    2.  **ASP.NET**  
  
    3.  **ISAPI\-Erweiterungen**  
  
    4.  **ISAPI\-Filter**  
  
9. Erweitern Sie unter dem Element namens **World Wide Web\-Dienste** den Eintrag **Allgemeine HTTP\-Funktionen**.  
  
10. Stellen Sie sicher, dass **Statischer Inhalt** ausgewählt ist.  
  
11. Erweitern Sie unter dem Element namens **World Wide Web\-Dienst** den Eintrag **Sicherheit**.  
  
12. Stellen Sie sicher, dass **Windows\-Authentifizierung** ausgewählt ist.  
  
13. Erweitern Sie unter dem Verzeichnis **Internetinformationsdienste** das Element mit der Bezeichnung **Webverwaltungstools**, und wählen Sie dann **IIS\-Verwaltungskonsole** aus.  
  
14. Erweitern Sie das Element mit der Bezeichnung **IIS 6\-Verwaltungskompatibilität**, und wählen Sie anschließend **IIS 6\-Skriptingtools** aus.  
  
15. Erweitern Sie unter dem Verzeichnis **Internetinformationsdienste** das Element mit der Bezeichnung **Microsoft .NET Framework 3.5.1**, und wählen Sie dann **Windows Communication Foundation\-HTTP\-Aktivierung** aus.  
  
16. Klicken Sie auf **OK**.  
  
### So installieren Sie IIS Version&\#160;7.0 unter Windows Server 2008  
  
1.  Wählen Sie im **Server\-Manager** die Option **Rollen** aus.  Klicken Sie unter **Rollenübersicht** auf **Rollen hinzufügen**.  
  
2.  Klicken Sie auf **Weiter**, um das Dialogfeld **Serverrollen auswählen** anzuzeigen.  
  
3.  Wählen Sie **Anwendungsserver** in der Liste **Rollen** aus, und klicken Sie auf **Weiter**, um das Dialogfeld **Rollendienste auswählen** für die Anwendungsserverrolle anzuzeigen.  
  
4.  Aktivieren Sie das Kontrollkästchen **Webserver \(IIS\)**.  Wenn Sie aufgefordert werden, zusätzliche Rollendienste und Features zu installieren, klicken Sie auf **Erforderliche Features hinzufügen**.  Klicken Sie zweimal auf **Weiter**, um das Dialogfeld **Rollendienste auswählen** für die Rolle Webserver \(IIS\) anzuzeigen.  
  
5.  Erweitern Sie das Element **Verwaltungstools** und danach **Kompatibilität mit der IIS 6\-Verwaltung**.  Wählen Sie **IIS 6\-Skriptingtools** aus.  Wenn Sie aufgefordert werden, zusätzliche Rollendienste und Features zu installieren, klicken Sie auf **Erforderliche Rollendienste hinzufügen**.  Klicken Sie auf **Weiter**.  
  
6.  Wenn die Zusammenfassung der Auswahl korrekt ist, klicken Sie auf **Installieren**.  
  
7.  Nach Abschluss der Installation klicken Sie auf **Schließen**.  
  
### So installieren Sie IIS Version&\#160;7.0 unter Windows Vista  
  
1.  Klicken Sie auf Start und anschließend auf Systemsteuerung.  
  
2.  Wählen Sie die Gruppe **Programme** aus.  
  
3.  Klicken Sie unter **Programme und Funktionen** auf **Windows\-Funktionen ein\- oder ausschalten**.  
  
4.  Das Dialogfeld **Benutzerkontensteuerung** wird angezeigt.  Klicken Sie auf **Weiter**.  
  
5.  Das Dialogfeld **Windows\-Funktionen** wird angezeigt.  Erweitern Sie das Element namens **Internetinformationsdienste**.  
  
6.  Erweitern Sie das Element namens **World Wide Web\-Dienst**.  
  
7.  Erweitern Sie das Element namens **Anwendungsentwicklungsfeatures**.  
  
8.  Stellen Sie sicher, dass die folgenden Elemente ausgewählt sind:  
  
    1.  **.NET\-Erweiterbarkeit**  
  
    2.  **ASP.NET**  
  
    3.  **ISAPI\-Erweiterungen**  
  
    4.  **ISAPI\-Filter**  
  
9. Erweitern Sie das Element namens **Webverwaltungstools**, und wählen Sie dann **IIS\-Verwaltungskonsole** aus.  
  
10. Erweitern Sie unter dem Element namens **World Wide Web\-Dienste** den Eintrag **Allgemeine HTTP\-Funktionen**.  
  
11. Stellen Sie sicher, dass **Statischer Inhalt** ausgewählt ist.  
  
12. Erweitern Sie unter dem Element namens **World Wide Web\-Dienst** den Eintrag **Sicherheit**.  
  
13. Stellen Sie sicher, dass **Windows\-Authentifizierung** ausgewählt ist.  
  
14. Erweitern Sie das Element mit der Bezeichnung **IIS 6\-Verwaltungskompatibilität**, und wählen Sie anschließend **IIS 6\-Skriptingtools** aus.  
  
15. Erweitern Sie das Element namens **Microsoft .NET Framework 3.0**, und wählen Sie dann **Windows Communication Foundation\-HTTP\-Aktivierung** aus.  
  
16. Klicken Sie auf **OK**.  
  
### So installieren Sie IIS Version 6.0 unter Windows Server 2003  
  
1.  Klicken Sie unter **Serververwaltung** auf **Funktion hinzufügen oder entfernen** und dann auf **Weiter**.  
  
2.  Wählen Sie aus der Liste **Serverfunktion** den Eintrag **Anwendungsserver \(IIS, ASP.NET\)** aus, und klicken Sie dann auf **Weiter**.  
  
3.  Aktivieren Sie das Kontrollkästchen **ASP.NET aktivieren**, und klicken Sie dann auf **Weiter**.  
  
4.  Wenn die Zusammenfassung der Auswahl korrekt ist, klicken Sie auf Weiter.  
  
### So installieren Sie IIS Version 5.1 unter Windows XP mit installiertem Service Pack 2 und Service Pack 3  
  
1.  Klicken Sie in der Systemsteuerung auf **Software**.  
  
2.  Klicken Sie im Dialogfeld **Software** auf **Windows\-Komponenten hinzufügen\/entfernen**.  
  
3.  Aktivieren Sie im **Assistenten für Windows\-Komponenten** das Kontrollkästchen **Internetinformationsdienste \(IIS\)**, und klicken Sie dann auf **Weiter**.  
  
4.  Wenn das Dialogfeld **Erforderliche Dateien** angezeigt wird, legen Sie die Installations\-CD für das Betriebssystem ein, wechseln Sie zum Ordner "i386", und klicken Sie anschließend auf **OK**.  
  
5.  Wenn die Installation abgeschlossen ist, klicken Sie auf **Fertig stellen**.  
  
6.  Schließen Sie das Dialogfeld **Software** und anschließend die **Systemsteuerung**.  
  
### So überprüfen Sie die Installation von IIS und ASP.NET  
  
1.  Speichern Sie die HTML\-Datei, die Sie am Ende dieses Themas finden, im Stammverzeichnis \\InetPub\\wwwroot unter dem Namen Default.aspx.  
  
2.  Öffnen Sie ein Browserfenster.  
  
3.  Geben Sie im Adressfeld `http://localhost/Default.aspx` ein, und drücken Sie dann die EINGABETASTE.  
  
4.  Es sollte eine Webseite mit dem Text "Hello World" angezeigt werden.  
  
> [!NOTE]
>  Jedes Mal, wenn Sie eine neue Version von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] installieren, müssen Sie aspnet\_isapi erneut als Webdiensterweiterung für IIS registrieren.  Dazu geben Sie den `aspnet_regiis –I –enable`\-Befehl aus.  
  
## Beispielcode  
  
```  
<html>  
   <body>  
       <form >  
           <h3> Hello World  
           </h3>  
       </form>  
   </body>  
</html>  
```
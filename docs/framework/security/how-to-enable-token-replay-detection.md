---
title: "Gewusst wie: Aktivieren der Erkennung von Tokenwiederholungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5a9f5771-f5f6-4100-8501-406aa20d731a
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# Gewusst wie: Aktivieren der Erkennung von Tokenwiederholungen
## Gilt für  
  
-   Identitäts\-Grundlage Microsoft® Windows® \(WIF\)  
  
-   ASP.NET®\-Web Forms  
  
## Zusammenfassung  
 In dieser Vorgehensweise wird ausführliche Schritt\-für\-Schritt\-Anweisungen zum Aktivieren der Scheinwiederholungserkennung in einer ASP.NET\-Anwendung vor, die WIF verwendet.  Außerdem werden Anweisungen bereit, wie die Anwendung testen, um zu überprüfen, ob Scheinwiederholungserkennung aktiviert ist.  In dieser Vorgehensweise hat nicht ausführliche Anweisungen zum Erstellen eines Sicherheitstokendiensts \(STS\) und verwendet stattdessen die Entwicklungs\-STS, die mit dem Identitäts\- und Zugriffstool stammt.  Die Entwicklungs\-STS führt keine echte Authentifizierung aus und wird nur für Testzwecke vorgesehen.  Sie müssen das Identitäts\- und Zugriffstool installieren, um dieses Gewusst\-wie\-Themen abzuschließen.  Es kann vom folgenden Speicherort heruntergeladen werden: [Identitäts\- und Zugriffs\-Tool](http://go.microsoft.com/fwlink/?LinkID=245849)  
  
## Inhalt  
  
-   Ziele  
  
-   Übersicht  
  
-   Zusammenfassung von Schritten  
  
-   Schritt 1 \- Erstellen einer einfachen ASP.NET Web Forms\-Anwendung und Aktivieren der Wiederholungserkennung  
  
-   Schritt 2 \- testen Sie die Projektmappe  
  
## Ziele  
  
-   Erstellen Sie eine einfache ASP.NET\-Anwendung, die WIF und die Entwicklungs\-STS von der Identität verwendet und greifen Sie auf das Tool zu  
  
-   Aktivieren Sie Scheinwiederholungserkennung und überprüfen Sie, ob sie funktioniert  
  
## Übersicht  
 Ein Wiederholungsangriff tritt auf, wenn ein Client versucht, einen vertrauender Seite mit einem STS\-Token zu authentifizieren, das der Client bereits verwendet hat.  So können diesen Angriff zu verhindern, enthält einen WIF Wiederholungserkennungscachen zuvor verwendete STS\-Token.  Wenn sie aktiviert ist, überprüft Wiederholungserkennung das Token der eingehenden Anforderung und sichergestellt, dass das Token zuvor verwendet wurde.  Wenn das Token bereits verwendet wurde, wird die Anforderung verweigert <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException> und eine Ausnahme wird ausgelöst.  
  
 Die folgenden Schritte zeigen die Konfigurationsänderungen, die erforderlich sind, um Wiederholungserkennung zu aktivieren.  
  
## Zusammenfassung von Schritten  
  
-   Schritt 1 \- Erstellen einer einfachen ASP.NET Web Forms\-Anwendung und Aktivieren der Wiederholungserkennung  
  
-   Schritt 2 \- testen Sie die Projektmappe  
  
## Schritt 1 \- Erstellen einer einfachen ASP.NET Web Forms\-Anwendung und Aktivieren der Wiederholungserkennung  
 In diesem Schritt erstellen Sie eine neue ASP.NET Web Forms\-Anwendung und ändern die Datei *Web.config*, um Wiederholungserkennung zu aktivieren.  
  
#### So fügen Sie eine einfache ASP.NET\-Anwendung erstellen  
  
1.  Starten Sie Visual Studio und klicken Sie auf **Datei**, **Neu** und dann auf **Projekt**.  
  
2.  Im **Neues Projekt** Fenster klicken Sie auf **ASP.NET Web Forms\-Anwendung**.  
  
3.  In **Name** geben Sie `TestApp` ein und drücken Sie **OK**.  
  
4.  Klicken Sie auf das **TestApp** Projekt unter **Projektmappen\-Explorer** mit der rechten Maustaste, und wählen Sie **Identität und Zugriff** aus.  
  
5.  Das **Identität und Zugriff** angezeigt wird.  Die **Anbieter** ausgewähltes **Anwendung mit dem lokalen Entwicklungs\-STS testen** klicken, dann auf **Übernehmen**.  
  
6.  Fügen Sie das folgende **\<tokenReplayDetection\>**\-Element der Konfigurationsdatei *Web.config* direkt hinter den **\<system.identityModel\>** und **\<identityConfiguration\>**\-Elementen hinzu, wie dargestellt:  
  
    ```  
    <system.identityModel>  
        <identityConfiguration>  
            <tokenReplayDetection enabled=”true”/>  
    ```  
  
## Schritt 2 \- testen Sie die Projektmappe  
 In diesem Schritt testen Sie die WIF\-aktivierte ASP.NET\-Anwendung, um zu überprüfen, ob Wiederholungserkennung aktiviert wurde.  
  
#### Um die WIF\-aktivierte ASP.NET\-Anwendung für Wiederholungserkennung testen  
  
1.  Führen Sie die Projektmappe aus, indem Sie die **F5** Taste drücken.  Sie sollten mit der standardmäßigen ASP.NET\-Homepage dargestellt und mit dem Benutzernamen *Terry* automatisch authentifiziert werden, Standardeinstellung Benutzer ist, der über die Entwicklungs\-STS zurückgegeben wird.  
  
2.  Drücken Sie die Schaltfläche **Zurück** des Browsers.  Ihnen sollte eine **Serverfehler in der Anwendung "\/"**\-Seite mit der folgenden Beschreibung angezeigt werden: *ID1062: Wiederholung wurde erkannt für: Token: 'System.IdentityModel.Tokens.SamlSecurityToken'*, gefolgt von einer *AssertionId* und einem *Aussteller*.  
  
     Sie finden diese Fehlerseite, da eine Ausnahme des Typs <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException> ausgelöst wurde, als die Scheinwiederholung erkannt wurde.  Dieser Fehler tritt auf, da Sie versuchen, die ursprüngliche POST\-Anforderung erneut zu senden, als das Token zuerst dargestellt wird.  Die **Zurück** Schaltfläche verursacht dieses Verhalten bei nachfolgenden Anforderungen nicht an den Server.
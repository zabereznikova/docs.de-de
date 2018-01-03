---
title: 'Vorgehensweise: Aktivieren der Erkennung einer Tokenmehrfachverwendung'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a9f5771-f5f6-4100-8501-406aa20d731a
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: a7c72d77b4894376fb6cb8aed2d1c6641a3977da
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enable-token-replay-detection"></a>Vorgehensweise: Aktivieren der Erkennung einer Tokenmehrfachverwendung
## <a name="applies-to"></a>Gilt für  
  
-   Microsoft® Windows® Identity Foundation (WIF)  
  
-   ASP.NET® Web Forms  
  
## <a name="summary"></a>Zusammenfassung  
 In dieser Vorgehensweise werden ausführliche Prozeduren zum Aktivieren der Erkennung einer Tokenmehrfachverwendung in einer ASP.NET-Anwendung, die WIF verwendet, vorgestellt. Es werden auch Anleitungen bereitgestellt, wie die Anwendung danach überprüft werden kann, ob die Erkennung einer Tokenmehrfachverwendung aktiviert ist. Diese Vorgehensweise enthält keine ausführlichen Anweisungen zum Erstellen eines Sicherheitstokendiensts (STS). Stattdessen wird der Entwicklungs-STS verwendet, der aus dem Identitäts- und Zugriffstool stammt. Der Entwicklungs-STS führt keine echte Authentifizierung durch und ist nur für Testzwecke vorgesehen. Sie müssen das Identitäts- und Zugriffs-Tool installieren, um diese Vorgehensweise nachzuvollziehen. Es kann auf der folgenden Seite heruntergeladen werden: [Identity and Access Tool (Identitäts- und Zugriffstool)](http://go.microsoft.com/fwlink/?LinkID=245849)  
  
## <a name="contents"></a>Inhalt  
  
-   Ziele  
  
-   Übersicht  
  
-   Zusammenfassung von Schritten  
  
-   Schritt 1: Erstellen einer einfachen ASP.NET-Web Forms-Anwendung und Aktivieren der Erkennung einer Tokenmehrfachverwendung  
  
-   Schritt 2 – Testen der Projektmappe  
  
## <a name="objectives"></a>Ziele  
  
-   Erstellen einer einfachen ASP.NET-Anwendung, die WIF und den Entwicklungs-STS aus dem Identitäts- und Zugriffs-Tool verwendet  
  
-   Aktivieren Sie die Erkennung einer Tokenmehrfachverwendung, und versichern Sie sich, dass sie funktioniert  
  
## <a name="overview"></a>Übersicht  
 Ein Replay-Angriff tritt auf, wenn ein Client versucht, eine Authentifizierung bei einer vertrauenden Seite mit einem STS-Token vorzunehmen, der vom Client bereits verwendet wurde. WIF enthält ein Cache für die Replay-Erkennung von bereits verwendeten STS-Tokens, um diesem Angriff vorzubeugen. Wenn dieses aktiviert ist, überprüft die Replay-Erkennung den Token der eingehenden Anforderung und ob dieser zuvor bereits verwendet wurde oder nicht. Wenn der Token bereits verwendet wurde, wird die Anforderung abgelehnt und eine <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException>-Ausnahme wird ausgelöst.  
  
 Die folgenden Schritte veranschaulichen die erforderlichen Konfigurationsänderungen zum Aktivieren der Replay-Erkennung.  
  
## <a name="summary-of-steps"></a>Zusammenfassung von Schritten  
  
-   Schritt 1: Erstellen einer einfachen ASP.NET-Web Forms-Anwendung und Aktivieren der Erkennung einer Tokenmehrfachverwendung  
  
-   Schritt 2 – Testen der Projektmappe  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application-and-enable-replay-detection"></a>Schritt 1: Erstellen einer einfachen ASP.NET-Web Forms-Anwendung und Aktivieren der Erkennung einer Tokenmehrfachverwendung  
 In diesem Schritt erstellen Sie eine neue ASP.NET Web Forms-Anwendung und ändern die Datei *Web.config*, um die Replay-Erkennung zu aktivieren.  
  
#### <a name="to-create-a-simple-aspnet-application"></a>So erstellen Sie eine einfache ASP.NET-Anwendung  
  
1.  Starten Sie Visual Studio, und klicken Sie auf **Datei**, **Neu** und anschließend auf **Projekt**.  
  
2.  Klicken Sie im Fenster **Neues Projekt** auf **ASP.NET Web Forms-Anwendung**.  
  
3.  Geben Sie im Feld **Name** die Zeichenfolge `TestApp` ein, und drücken Sie auf **OK**.  
  
4.  Klicken Sie mit der rechten Maustaste unter **Projektmappen-Explorer** auf das Projekt **TestApp**, und wählen Sie anschließend **Identität und Zugriff** aus.  
  
5.  Das Fenster **Identität und Zugriff** wird geöffnet. Klicken Sie unter **Anbieter** auf **Test your application with the Local Development STS** (Anwendung mit dem lokalen Entwicklungs-STS testen), und klicken Sie anschließend auf **Übernehmen**.  
  
6.  Fügen Sie folgendes **\<tokenReplayDetection>**-Element zur Konfigurationsdatei *Web.config* hinzu und direkt danach wie im Folgenden gezeigt die Elemente **\<system.identityModel>** und **\<identityConfiguration>**:  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration>  
            <tokenReplayDetection enabled="true"/>  
    ```  
  
## <a name="step-2--test-your-solution"></a>Schritt 2 – Testen der Projektmappe  
 In diesem Schritt testen Sie die für WIF aktivierte ASP.NET-Anwendung, um zu überprüfen, ob die Replay-Erkennung aktiviert wurde.  
  
#### <a name="to-test-your-wif-enabled-aspnet-application-for-replay-detection"></a>Testen der für WIF aktivierten ASP.NET-Anwendung auf erfolgreiche Replay-Erkennung  
  
1.  Starten Sie die Projektmappe durch Drücken der Taste **F5**. Die Standard-Homepage von ASP.NET wird angezeigt. Sie werden automatisch mit dem Benutzernamen *Terry* authentifiziert. Dies ist der Standardbenutzer, der vom Entwicklungs-STS zurückgegeben wird.  
  
2.  Klicken Sie im Browser auf die Schaltfläche **Zurück**. Ihnen sollte die Seite **Serverfehler in „/“-Anwendung** mit folgender Beschreibung angezeigt werden: *ID1062: Wiedergabe wurde erkannt für: Token: „System.IdentityModel.Tokens.SamlSecurityToken“*, gefolgt von einer *AssertionID* und einem *Zertifikataussteller*.  
  
     Diese Fehlerseite wird Ihnen angezeigt, da eine Ausnahme des Typs <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException> durch eine Tokenmehrfachverwendung ausgelöst wurde. Dieser Fehler tritt auf, weil Sie versuchen, die ursprüngliche POST-Anforderung, bei der der Token zuerst verwendet wurde, erneut zu senden. Die Schaltfläche **Zurück** löst dieses Verhalten bei nachfolgenden Anforderungen an den Server nicht aus.

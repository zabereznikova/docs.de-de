---
title: 'Gewusst wie: Anzeigen des Anmeldestatus mit WIF'
ms.date: 03/30/2017
ms.assetid: 4d1174e4-5397-4962-9a5f-3b1ad7b3fc14
author: BrucePerlerMS
ms.openlocfilehash: 7d3d23dc1f2e081c0a7c53fbdfaef749c9729fd4
ms.sourcegitcommit: daa8788af67ac2d1cecd24f9f3409babb2f978c9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2018
ms.locfileid: "47863051"
---
# <a name="how-to-display-signed-in-status-using-wif"></a>Gewusst wie: Anzeigen des Anmeldestatus mit WIF
## <a name="applies-to"></a>Gilt für  
  
-   Microsoft® Windows® Identity Foundation (WIF) 4.5  
  
-   ASP.NET® Web Forms  
  
## <a name="summary"></a>Zusammenfassung  
 In diesem Thema wird beschrieben, wie der Anmeldestatus in einer WIF-aktivierten ASP.NET-Anwendung angezeigt wird. WIF bietet den Mechanismus, um die Anwendung für die Anspruchsunterstützung kompatibel zu machen sowie die Authentifizierung und Autorisierung für Anwendungsressourcen zu verwalten.  
  
## <a name="contents"></a>Inhalt  
  
-   Übersicht  
  
-   Zusammenfassung von Schritten  
  
-   Schritt 1: Einrichten der Identitäts- und Zugriffserweiterung  
  
-   Schritt 2: Erstellen einer abhängigen Seite der ASP.NET-Anwendung  
  
-   Schritt 3: Aktivieren des lokalen Entwicklungs-STS zur Authentifizierung von Benutzern  
  
-   Schritt 4: Ändern der ASP.NET-Anwendung zum Anzeigen des Anmeldestatus  
  
-   Schritt 5: Testen der Integration zwischen WIF und der ASP.NET-Anwendung  
  
## <a name="overview"></a>Übersicht  
 Dieses Thema veranschaulicht, wie eine einfache Ansprüche unterstützende Anwendung mithilfe von WIF erstellt und wie leicht angezeigt wird, ob ein Benutzer angemeldet ist oder nicht. In den folgenden Schritte wird der lokale Entwicklungs-STS verwendet, der in der Identitäts- und Zugriffserweiterung von Visual Studio enthalten ist. Der lokale Entwicklungs-STS ist für eine Test- und Entwicklungsumgebung vorgesehen, um eine einfache Methode der Integration von Ansprüchen in die Anwendung bereitzustellen. Er sollte nie in einer Produktionsumgebung verwendet werden, da er keine echte Authentifizierung ausführt und Anmeldeinformationen nicht erforderlich sind. Allerdings ist der imperative Code in den folgenden Schritten für eine produktionsbereite Anwendung, die eine echte Authentifizierung verwendet, identisch.  
  
## <a name="summary-of-steps"></a>Zusammenfassung von Schritten  
  
-   Schritt 1: Einrichten der Identitäts- und Zugriffserweiterung  
  
-   Schritt 2: Erstellen einer abhängigen Seite der ASP.NET-Anwendung  
  
-   Schritt 3: Aktivieren des lokalen Entwicklungs-STS zur Authentifizierung von Benutzern  
  
-   Schritt 4: Ändern der ASP.NET-Anwendung zum Anzeigen des Anmeldestatus  
  
-   Schritt 5: Testen der Integration zwischen WIF und der ASP.NET-Anwendung  
  
## <a name="step-1--install-the-identity-and-access-extension"></a>Schritt 1: Einrichten der Identitäts- und Zugriffserweiterung  
 Dieser Schritt beschreibt, wie die Identitäts- und Zugriffserweiterung in Visual Studio 2012 konfiguriert wird. Diese Erweiterung automatisiert die Konfiguration der Anwendung, um mit STS-Endpunkten zu kommunizieren.  
  
#### <a name="to-install-the-identity-and-access-extension"></a>So richten Sie die Identitäts- und Zugriffserweiterung ein  
  
1.  Starten Sie Visual Studio im erweiterten Modus als Administrator.  
  
2.  Klicken Sie in Visual Studio im Menü **Extras** auf **Erweiterungs-Manager**. Das Fenster **Erweiterungs-Manager** wird geöffnet.  
  
3.  Klicken Sie im **Erweiterungs-Manager** im linken Menü auf **Onlineerweiterungen**, und wählen Sie **Visual Studio Gallery** aus.  
  
4.  Suchen Sie in der rechten oberen Ecke des **Erweiterungs-Managers** nach *Identität und Zugriff*.  
  
5.  Das Element **Identität und Zugriff** wird in den Suchergebnissen angezeigt. Klicken Sie darauf, und klicken Sie anschließend auf **Herunterladen**.  
  
6.  Das Dialogfeld **Herunterladen und installieren** wird angezeigt. Wenn Sie den Lizenzbedingungen zustimmen, klicken Sie auf **Installieren**.  
  
7.  Wenn die Installation der Erweiterung **Identität und Zugriff** abgeschlossen ist, starten Sie Visual Studio im Administratormodus erneut.  
  
## <a name="step-2--create-a-relying-party-aspnet-application"></a>Schritt 2: Erstellen einer abhängigen Seite der ASP.NET-Anwendung  
 Dieser Schritt beschreibt, wie eine abhängige Seite der ASP.NET Web Forms-Anwendung erstellt wird, die mit WIF integriert wird.  
  
#### <a name="to-create-a-simple-aspnet-application"></a>So erstellen Sie eine einfache ASP.NET-Anwendung  
  
1.  Starten Sie Visual Studio, und klicken Sie auf **Datei**, **Neu** und anschließend auf **Projekt**.  
  
2.  Klicken Sie im Fenster **Neues Projekt** auf **ASP.NET Web Forms-Anwendung**.  
  
3.  Geben Sie im Feld **Name** die Zeichenfolge `TestApp` ein, und drücken Sie auf **OK**.  
  
## <a name="step-3--enable-local-development-sts-to-authenticate-users"></a>Schritt 3: Aktivieren des lokalen Entwicklungs-STS zur Authentifizierung von Benutzern  
 Dieser Schritt beschreibt die Aktivierung der lokalen Entwicklungs-STS in der Anwendung. Der lokale Entwicklungs-STS wird mithilfe der Identitäts- und Zugriffserweiterung für Visual Studio aktiviert.  
  
#### <a name="to-enable-local-development-sts-in-your-aspnet-application"></a>So aktivieren Sie den lokalen Entwicklungs-STS in der ASP.NET-Anwendung  
  
1.  Klicken Sie in Visual Studio mit der rechten Maustaste unter **Projektmappen-Explorer** auf das Projekt **TestApp**, und wählen Sie **Identität und Zugriff** aus.  
  
2.  Das Fenster **Identität und Zugriff** wird geöffnet. Klicken Sie unter **Anbieter** auf **Test your application with the Local Development STS** (Anwendung mit dem lokalen Entwicklungs-STS testen), und klicken Sie anschließend auf **Übernehmen**.  
  
## <a name="step-4--modify-your-aspnet-application-to-display-sign-in-status"></a>Schritt 4: Ändern der ASP.NET-Anwendung zum Anzeigen des Anmeldestatus  
 Dieser Schritt beschreibt die Änderung der ASP.NET-Anwendung, um dynamisch anzuzeigen, ob der aktuelle Benutzer angemeldet ist. Nachdem der STS-Anbieter konfiguriert wurde, behandelt WIF die eingehenden Ansprüche. Jetzt müssen Sie den Code der Anwendung konfigurieren, um das Ergebnis der Authentifizierung anzuzeigen.  
  
#### <a name="to-display-sign-in-status"></a>So zeigen Sie den Anmeldestatus an  
  
1.  Öffnen Sie in Visual Studio die Datei **Default.aspx** unter dem Projekt **TestApp**.  
  
2.  Ersetzen Sie das vorhandene Markup in der Datei **Default.aspx** durch das folgende Markup:  
  
    ```  
    <%@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="_Default" %>  
  
    <!DOCTYPE html>  
  
    <html>  
    <head runat="server">  
        <title>Logged In Status</title>  
    </head>  
    <body>  
        <asp:label ID="myLabel" runat="server" />  
    </body>  
    </html>  
    ```  
  
3.  Speichern Sie die Datei **Default.aspx**, und öffnen Sie dann die CodeBehind-Datei **Default.aspx.cs**.  
  
    > [!NOTE]
    >  **Default.aspx.cs** ist möglicherweise im Projektmappen-Explorer unter **Default.aspx** ausgeblendet. Wenn **Default.aspx.cs** nicht sichtbar ist, erweitern Sie **Default.aspx**, indem Sie auf das Dreieck daneben klicken.  
  
4.  Ersetzen Sie den vorhandenen Code in **Default.aspx.cs** durch den folgenden Code:  
  
    ```csharp  
    using System;  
    using System.Web.UI;  
    using System.Security.Claims;  
  
    namespace TestApp  
    {  
        protected void Page_Load(object sender, EventArgs e)  
        {  
            ClaimsPrincipal claimsPrincipal = Thread.CurrentPrincipal as ClaimsPrincipal;  
  
            if (claimsPrincipal != null)  
            {  
                myLabel.Text = "You are signed in.";  
            }  
            else  
            {  
                myLabel.Text = "You are not signed in.";  
            }  
        }  
    }  
    ```  
  
5.  Speichern Sie die CodeBehind-Datei **Default.aspx.cs**, und erstellen Sie die Anwendung.  
  
## <a name="step-5--test-the-integration-between-wif-and-your-aspnet-application"></a>Schritt 5: Testen der Integration zwischen WIF und der ASP.NET-Anwendung  
 Dieser Schritt beschreibt, wie Sie die Integration zwischen WIF und der ASP.NET-Anwendung testen können.  
  
#### <a name="to-test-the-integration-between-wif-and-aspnet"></a>So testen Sie die Integration zwischen WIF und ASP.NET  
  
1.  Drücken Sie in Visual Studio die **F5**-TASTE, um die Anwendung zu debuggen. Wenn keine Fehler gefunden werden, wird ein neues Browserfenster geöffnet.  
  
2.  Der Browser leitet möglicherweise die Anforderung automatisch an den STS um und öffnet dann die Seite "Default.aspx". Wenn WIF ordnungsgemäß konfiguriert wurde, wird auf der Website der folgende Text angezeigt: **„Sie sind angemeldet“**.

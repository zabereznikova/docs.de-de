---
title: "Gewusst wie: Erstellen einer Anspr&#252;che unterst&#252;tzenden ASP.NET Web Forms-Anwendung mithilfe von WIF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: efb264dd-f47b-49a9-85ee-9f45d4425765
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# Gewusst wie: Erstellen einer Anspr&#252;che unterst&#252;tzenden ASP.NET Web Forms-Anwendung mithilfe von WIF
## Gilt für  
  
-   Identitäts\-Grundlage Microsoft® Windows® \(WIF\)  
  
-   ASP.NET®\-Web Forms  
  
## Zusammenfassung  
 In dieser Vorgehensweise wird ausführliche Schritt\-für\-Schritt\-Anweisungen zum Erstellen einfacher Ansprüche unterstützende ASP.NET Web Forms\-Anwendung vor.  Außerdem werden Anweisungen bereit, wie die einfache Ansprüche unterstützende ASP.NET Web Forms\-Anwendung für eine erfolgreiche Implementierung der Verbundauthentifizierung testen.  In dieser Vorgehensweise hat nicht ausführliche Anweisungen zum Erstellen eines Sicherheitstokendiensts \(STS\) und wird davon ausgegangen, dass bereits ein STS konfiguriert haben.  
  
## Inhalt  
  
-   Ziele  
  
-   Zusammenfassung von Schritten  
  
-   Schritt 1 \- erstellen Sie eine einfache ASP.NET Web Forms\-Anwendung  
  
-   Schritt 2 \- Konfigurieren einer ASP.NET Web Forms\-Anwendung für anspruchsbasierte Authentifizierung  
  
-   Schritt 3 \- testen Sie die Projektmappe  
  
## Ziele  
  
-   Konfigurieren Sie ASP.NET Web Forms\-Anwendung für anspruchsbasierte Authentifizierung  
  
-   Testen Sie erfolgreiche Ansprüche unterstützende ASP.NET Web Forms\-Anwendung  
  
## Zusammenfassung von Schritten  
  
-   Schritt 1 \- Erstellen einer einfachen ASP.NET Web Forms\-Anwendung  
  
-   Schritt 2 \- Konfigurieren einer ASP.NET Web Forms\-Anwendung für Verbundauthentifizierung  
  
-   Schritt 3 \- testen Sie die Projektmappe  
  
## Schritt 1 \- erstellen Sie eine einfache ASP.NET Web Forms\-Anwendung  
 In diesem Schritt erstellen Sie eine neue ASP.NET Web Forms\-Anwendung.  
  
#### So fügen Sie eine einfache ASP.NET\-Anwendung erstellen  
  
1.  Starten Sie Visual Studio und klicken Sie auf **Datei**, **Neu** und dann auf **Projekt**.  
  
2.  Im **Neues Projekt** Fenster klicken Sie auf **ASP.NET Web Forms\-Anwendung**.  
  
3.  In **Name** geben Sie `TestApp` ein und drücken Sie **OK**.  
  
## Schritt 2 \- Konfigurieren einer ASP.NET Web Forms\-Anwendung für anspruchsbasierte Authentifizierung  
 In diesem Schritt fügen Sie Konfigurationseinträge der Konfigurationsdatei *Web.config* der ASP.NET Web Forms\-Anwendungen hinzu, damit sie Ansprüche unterstützen.  
  
#### So ASP.NET\-Anwendung für anspruchsbasierte Authentifizierung  
  
1.  Fügen Sie die folgenden Konfigurationsabschnittseinträge der Konfigurationsdatei *Web.config* direkt nach dem öffnenden **\<configuration\>**\-Element hinzu:  
  
    ```xml  
    <configSections>  
      <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
      <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    </configSections>  
    ```  
  
2.  Fügen Sie ein **\<location\>**\-Element hinzu, das Zugriff auf den Verbundsmetadaten der Anwendung aktiviert:  
  
    ```xml  
    <location path="FederationMetadata">  
      <system.web>  
        <authorization>  
          <allow users="*" />  
        </authorization>  
      </system.web>  
    </location>  
    ```  
  
3.  Fügen Sie die folgenden Konfigurationseinträge innerhalb der **\<system.web\>**\-Elemente hinzu, um Benutzer zu verweigern, deaktivieren Sie systemeigene Authentifizierung und aktivieren Sie WIF, sodass Authentifizierung zu verwalten.  
  
    ```xml  
    <authorization>  
      <deny users="?" />  
    </authorization>  
    <authentication mode="None" />  
    ```  
  
4.  Fügen Sie ein **\<system.webServer\>**\-Element hinzu, das die Module für Verbundauthentifizierung definiert.  Beachten Sie, dass das *PublicKeyToken\-Attribut* das identisch sein muss, das das *PublicKeyToken\-Attribut* für die **\<configSections\>** Einträge zuvor befindet:  
  
    ```  
    <system.webServer>  
      <modules>  
        <add name="WSFederationAuthenticationModule" type="System.IdentityModel.Services.WSFederationAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
        <add name="SessionAuthenticationModule" type="System.IdentityModel.Services.SessionAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
      </modules>  
    </system.webServer>  
    ```  
  
5.  Fügen Sie die folgenden Windows Identity Foundation verknüpften Konfigurationseinträge hinzu und stellen Sie sicher, dass die URL und Anschlussnummer der ASP.NET\-Anwendung die Werte im **\<audienceUris\>**\-Eintrag, im **realm**\-Attribut des **\<wsFederation\>**\-Elements und im **reply**\-Attribut des **\<wsFederation\>**\-Elements übereinstimmen.  Stellen Sie außerdem, dass der Wert den **Aussteller** Sicherheitstokendienst \(STS\) URL passt.  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration>  
            <audienceUris>  
                <add value="http://localhost:28503/" />  
            </audienceUris>  
            <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
                <trustedIssuers>  
                    <add thumbprint="1234567890ABCDEFGHIJKLMNOPQRSTUVWXYZ1234" name="YourSTSName" />  
                </trustedIssuers>   
            </issuerNameRegistry>  
            <certificateValidation certificateValidationMode="None" />  
        </identityConfiguration>  
    </system.identityModel>  
    <system.identityModel.services>  
        <federationConfiguration>  
            <cookieHandler requireSsl="false" />  
            <wsFederation passiveRedirectEnabled="true" issuer="http://localhost:13922/wsFederationSTS/Issue" realm="http://localhost:28503/" reply="http://localhost:28503/" requireHttps="false" />  
        </federationConfiguration>  
    </system.identityModel.services>  
    ```  
  
6.  Fügen Sie [System.IdentityModel](assetId:///System.IdentityModel?qualifyHint=False&amp;autoUpgrade=True) Verweis auf die Assembly hinzu.  
  
7.  Kompilieren Sie die Projektmappe, um sicherzustellen, dass es Fehler gibt.  
  
## Schritt 3 \- testen Sie die Projektmappe  
 In diesem Schritt testen Sie die ASP.NET Web Forms\-Anwendungen, für die anspruchsbasierte Authentifizierung konfiguriert ist.  Um einen grundlegenden Test auszuführen, fügen Sie Code hinzu der Ansprüche im Token anzeigt, das von dem Sicherheitstokendienst \(STS\) ausgegeben wird.  
  
#### Um die ASP.NET für anspruchsbasierte Authentifizierung testen  
  
1.  Öffnen Sie die Datei **Default.aspx** unter dem Projekt **TestApp** und ersetzen Sie sein vorhandenes Markup durch das folgende Markup:  
  
    ```  
    %@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="_Default" %>  
  
    <!DOCTYPE html>  
  
    <html>  
    <head id="Head1" runat="server">  
        <title></title>  
    </head>  
    <body>  
        <h1><asp:label ID="signedIn" runat="server" /></h1>  
        <asp:label ID="claimType" runat="server" />  
        <asp:label ID="claimValue" runat="server" />  
        <asp:label ID="claimValueType" runat="server" />  
        <asp:label ID="claimSubjectName" runat="server" />  
        <asp:label ID="claimIssuer" runat="server" />  
    </body>  
    </html>  
    ```  
  
2.  Speichern Sie **Default.aspx** und öffnen Sie dann den Code\-Behind\-Datei benanntem **Default.aspx.cs**.  
  
    > [!NOTE]
    >  **Default.aspx.cs** wird unter Explorer **Default.aspx** im Projektmappen\-Explorer ausgeblendet werden.  Wenn **Default.aspx.cs** nicht sichtbar ist, erweitern Sie **Default.aspx**, indem Sie auf das Dreieck daneben klicken.  
  
3.  Ersetzen Sie den vorhandenen Code in der **Page\_Load**\-Methode von **Default.aspx.cs** durch folgenden Code:  
  
    ```csharp  
    using System;  
    using System.IdentityModel;  
    using System.Security.Claims;  
    using System.Threading;  
    using System.Web.UI;  
  
    namespace TestApp  
    {  
        public partial class _Default : System.Web.UI.Page  
        {  
            protected void Page_Load(object sender, EventArgs e)  
            {  
                ClaimsPrincipal claimsPrincipal = Thread.CurrentPrincipal as ClaimsPrincipal;  
  
                if (claimsPrincipal != null)  
                {  
                    signedIn.Text = "You are signed in.";  
  
                    foreach (Claim claim in claimsPrincipal.Claims)  
                    {  
                        claimType.Text = claim.Type;  
                        claimValue.Text = claim.Value;  
                        claimValueType.Text = claim.ValueType;  
                        claimSubjectName.Text = claim.Subject.Name;  
                        claimIssuer.Text = claim.Issuer;  
                    }  
                }  
                else  
                {  
                    signedIn.Text = "You are not signed in.";  
                }  
            }  
        }  
    }  
    ```  
  
4.  Speichern Sie **Default.aspx.cs** und erstellen Sie die Projektmappe.  
  
5.  Führen Sie die Projektmappe aus, indem Sie die **F5** Taste drücken.  
  
6.  Sie sollten mit der Seite dargestellt werden, die die Ansprüche im Token anzeigt, das Ihnen vom Sicherheitstokendienst ausgegeben wurde.
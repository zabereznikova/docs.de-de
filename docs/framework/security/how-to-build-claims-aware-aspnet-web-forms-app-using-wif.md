---
title: 'Gewusst wie: Erstellen einer Ansprüche unterstützenden ASP.NET Web Forms-Anwendung mithilfe von WIF'
ms.date: 03/30/2017
ms.assetid: efb264dd-f47b-49a9-85ee-9f45d4425765
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: e8dc6b1c5073ac55be224eb0d410ad7f87d135d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400093"
---
# <a name="how-to-build-claims-aware-aspnet-web-forms-application-using-wif"></a>Gewusst wie: Erstellen einer Ansprüche unterstützenden ASP.NET Web Forms-Anwendung mithilfe von WIF
## <a name="applies-to"></a>Gilt für  
  
-   Microsoft® Windows® Identity Foundation (WIF)  
  
-   ASP.NET® Web Forms  
  
## <a name="summary"></a>Zusammenfassung  
 In dieser Vorgehensweise werden ausführliche Prozeduren zum Erstellen einer einfachen Ansprüche unterstützenden ASP.NET Web Forms-Anwendung vorgestellt. Sie enthält auch Anweisungen dazu, wie eine einfache ASP.NET Web Forms-Anwendung auf die erfolgreiche Implementierung der Verbundauthentifizierung getestet werden kann. Diese Vorgehensweise enthält keine detaillierten Anweisungen zum Erstellen eines Sicherheitstokendiensts (Security Token Service, STS) und geht davon aus, dass Sie bereits einen STS konfiguriert haben.  
  
## <a name="contents"></a>Inhalt  
  
-   Ziele  
  
-   Zusammenfassung von Schritten  
  
-   Schritt 1: Erstellen einer einfachen ASP.NET Web Forms-Anwendung  
  
-   Schritt 2: Konfigurieren einer ASP.NET Web Forms-Anwendung für die anspruchsbasierte Authentifizierung  
  
-   Schritt 3: Testen Ihrer Projektmappe  
  
## <a name="objectives"></a>Ziele  
  
-   Konfigurieren einer ASP.NET Web Forms-Anwendung für die anspruchsbasierte Authentifizierung  
  
-   Testen einer erfolgreichen Ansprüche unterstützenden ASP.NET Web Forms-Anwendung  
  
## <a name="summary-of-steps"></a>Zusammenfassung von Schritten  
  
-   Schritt 1: Erstellen einer einfachen ASP.NET Web Forms-Anwendung  
  
-   Schritt 2: Konfigurieren einer ASP.NET Web Forms-Anwendung für die Verbundauthentifizierung  
  
-   Schritt 3: Testen Ihrer Projektmappe  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a>Schritt 1: Erstellen einer einfachen ASP.NET Web Forms-Anwendung  
 In diesem Schritt erstellen Sie eine neue ASP.NET Web Forms-Anwendung.  
  
#### <a name="to-create-a-simple-aspnet-application"></a>So erstellen Sie eine einfache ASP.NET-Anwendung  
  
1.  Starten Sie Visual Studio, und klicken Sie auf **Datei**, **Neu** und anschließend auf **Projekt**.  
  
2.  Klicken Sie im Fenster **Neues Projekt** auf **ASP.NET Web Forms-Anwendung**.  
  
3.  Geben Sie im Feld **Name** die Zeichenfolge `TestApp` ein, und drücken Sie auf **OK**.  
  
## <a name="step-2--configure-aspnet-web-forms-application-for-claims-based-authentication"></a>Schritt 2: Konfigurieren einer ASP.NET Web Forms-Anwendung für die anspruchsbasierte Authentifizierung  
 In diesem Schritt fügen Sie Konfigurationseinträge zur Konfigurationsdatei *Web.config* Ihrer ASP.NET Web Forms-Anwendung hinzu, damit diese Ansprüche unterstützt.  
  
#### <a name="to-configure-aspnet-application-for-claims-based-authentication"></a>Konfigurieren einer ASP.NET-Anwendung für die anspruchsbasierte Authentifizierung  
  
1.  Fügen Sie die folgenden Konfigurationseinträge unmittelbar nach dem öffnenden Element **\<configuration>** zur *Web.config*-Konfigurationsdatei hinzu:  
  
    ```xml  
    <configSections>  
      <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
      <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    </configSections>  
    ```  
  
2.  Fügen Sie ein **\<location>**-Element hinzu, das den Zugriff auf die Verbundmetadaten der Anwendung ermöglicht:  
  
    ```xml  
    <location path="FederationMetadata">  
      <system.web>  
        <authorization>  
          <allow users="*" />  
        </authorization>  
      </system.web>  
    </location>  
    ```  
  
3.  Fügen Sie die folgenden Konfigurationseinträge innerhalb des Elements **\<system.web>** hinzu, um Benutzer zu verweigern, die native Authentifizierung zu deaktivieren, und WIF zu ermöglichen, die Authentifizierung zu verwalten.  
  
    ```xml  
    <authorization>  
      <deny users="?" />  
    </authorization>  
    <authentication mode="None" />  
    ```  
  
4.  Fügen Sie das **\<system.webServer>**-Element hinzu, das die Module für Verbundauthentifizierung definiert. Beachten Sie, dass das *PublicKeyToken*-Attribut identisch mit dem *PublicKeyToken*-Attribut für die **\<configSections>**-Einträge sein muss, die zuvor hinzugefügt wurden:  
  
    ```xml  
    <system.webServer>  
      <modules>  
        <add name="WSFederationAuthenticationModule" type="System.IdentityModel.Services.WSFederationAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
        <add name="SessionAuthenticationModule" type="System.IdentityModel.Services.SessionAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
      </modules>  
    </system.webServer>  
    ```  
  
5.  Fügen Sie folgende auf Windows Identity Foundation bezogene Konfigurationseinträge hinzu, und versichern Sie sich, dass die URL und Portnummer Ihrer ASP.NET-Anwendung mit den Werten des **\<audienceUris>**-Eintrags, des **realm**-Attributs des **\<wsFederation>**-Elements und des **reply**-Attributs des **\<wsFederation>**-Elements übereinstimmen. Vergewissern Sie sich zudem, dass der Wert des **Ausstellers** der URL Ihres Sicherheitstokendiensts entspricht.  
  
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
  
6.  Fügen Sie der Assembly <xref:System.IdentityModel> einen Verweis hinzu.  
  
7.  Kompilieren Sie die Projektmappe, um sich zu vergewissern, dass keine Fehler vorliegen.  
  
## <a name="step-3--test-your-solution"></a>Schritt 3: Testen Ihrer Projektmappe  
 In diesem Schritt testen Sie die ASP.NET Web Forms-Anwendung, die für die anspruchsbasierte Authentifizierung konfiguriert wurde. Sie können einen grundlegenden Test ausführen, indem Sie einfachen Code hinzufügen, der die Ansprüche im Token anzeigt, die vom Sicherheitstokendienst (STS) ausgegeben werden.  
  
#### <a name="to-test-your-aspnet-web-form-application-for-claims-based-authentication"></a>Testen Ihrer ASP.NET Web Form-Anwendung für die anspruchsbasierte Authentifizierung  
  
1.  Öffnen Sie die Datei **Default.aspx** im Projekt **TestApp**, und ersetzen Sie das vorhandene Markup durch das folgende Markup:  
  
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
  
2.  Speichern Sie die Datei **Default.aspx**, und öffnen Sie dann die CodeBehind-Datei **Default.aspx.cs**.  
  
    > [!NOTE]
    >  **Default.aspx.cs** ist möglicherweise im Projektmappen-Explorer unter **Default.aspx** ausgeblendet. Wenn **Default.aspx.cs** nicht sichtbar ist, erweitern Sie **Default.aspx**, indem Sie auf das Dreieck daneben klicken.  
  
3.  Ersetzen Sie den vorhandenen Code in der **Page_Load**-Methode von **Default.aspx.cs** durch den folgenden Code:  
  
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
  
4.  Speichern Sie **Default.aspx.cs**, und erstellen Sie die Anwendung.  
  
5.  Starten Sie die Projektmappe durch Drücken der Taste **F5**.  
  
6.  Ihnen sollte die Seite angezeigt werden, die die Ansprüche im Token anzeigt, die Ihnen vom Sicherheitstokendienst ausgegeben wurden.

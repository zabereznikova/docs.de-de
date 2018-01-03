---
title: "Gewusst wie: Erstellen einer Ansprüche unterstützenden ASP.NET MVC-Webanwendung mithilfe von WIF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0efb76bc-9f7b-4afe-be1c-2a57c917010b
caps.latest.revision: "6"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 39364f06cec35b1a5417540dfa29b0cac24fbdb6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-build-claims-aware-aspnet-mvc-web-application-using-wif"></a>Gewusst wie: Erstellen einer Ansprüche unterstützenden ASP.NET MVC-Webanwendung mithilfe von WIF
## <a name="applies-to"></a>Gilt für  
  
-   Microsoft® Windows® Identity Foundation (WIF)  
  
-   ASP.NET® MVC  
  
## <a name="summary"></a>Zusammenfassung  
 In dieser Vorgehensweise werden ausführliche Prozeduren zum Erstellen einer einfachen Ansprüche unterstützenden ASP.NET MVC-Webanwendung vorgestellt. Sie enthält auch Anweisungen dazu, wie eine einfache Ansprüche unterstützende ASP.NET MVC-Webanwendung auf die erfolgreiche Implementierung der anspruchsbasierten Authentifizierung getestet werden kann. Diese Vorgehensweise enthält keine detaillierten Anweisungen zum Erstellen eines Sicherheitstokendiensts (Security Token Service, STS) und geht davon aus, dass Sie bereits einen STS konfiguriert haben.  
  
## <a name="contents"></a>Inhalt  
  
-   Ziele  
  
-   Zusammenfassung von Schritten  
  
-   Schritt 1: Erstellen einer einfachen ASP.NET MVC-Anwendung  
  
-   Schritt 2: Konfigurieren einer ASP.NET MVC-Anwendung für die anspruchsbasierte Authentifizierung  
  
-   Schritt 3: Testen Ihrer Projektmappe  
  
-   Verwandte Elemente  
  
## <a name="objectives"></a>Ziele  
  
-   Konfigurieren einer ASP.NET MVC-Webanwendung für die anspruchsbasierte Authentifizierung  
  
-   Testen einer erfolgreichen Ansprüche unterstützenden ASP.NET MVC-Webanwendung  
  
## <a name="summary-of-steps"></a>Zusammenfassung von Schritten  
  
-   Schritt 1: Erstellen einer einfachen ASP.NET MVC-Anwendung  
  
-   Schritt 2: Konfigurieren einer ASP.NET MVC-Anwendung für die anspruchsbasierte Authentifizierung  
  
-   Schritt 3: Testen Ihrer Projektmappe  
  
## <a name="step-1--create-simple-aspnet-mvc-application"></a>Schritt 1: Erstellen einer einfachen ASP.NET MVC-Anwendung  
 In diesem Schritt erstellen Sie eine neue ASP.NET MVC-Anwendung.  
  
#### <a name="to-create-simple-aspnet-mvc-application"></a>Erstellen einer einfachen ASP.NET MVC-Anwendung  
  
1.  Starten Sie Visual Studio, und klicken Sie auf **Datei**, **Neu**, und klicken Sie dann auf **Projekt**.  
  
2.  Klicken Sie im Fenster **Neues Projekt** auf **ASP.NET MVC 3-Webanwendung**.  
  
3.  Geben Sie im Feld **Name** die Zeichenfolge `TestApp` ein, und klicken Sie auf **OK**.  
  
4.  Wählen Sie im Dialogfeld **Neues ASP.NET MVC 3-Projekt** aus den verfügbaren Vorlagen **Internetanwendung** aus, und versichern Sie sich, dass das **Ansichtsmodul** auf **Razor** festgelegt ist. Klicken Sie dann auf **OK**.  
  
5.  Wenn das neue Projekt sich öffnet, klicken Sie mit der rechten Maustaste auf das **TestApp**-Projekt im **Projektmappen-Explorer**, und klicken Sie dann auf die Option **Eigenschaften**.  
  
6.  Klicken Sie auf der Seite „Eigenschaften“ des Projekts links auf die Registerkarte **Web**, und versichern Sie sich, dass die Option **Lokalen IIS-Webserver verwenden** ausgewählt ist.  
  
## <a name="step-2--configure-aspnet-mvc-application-for-claims-based-authentication"></a>Schritt 2: Konfigurieren einer ASP.NET MVC-Anwendung für die anspruchsbasierte Authentifizierung  
 In diesem Schritt fügen Sie Konfigurationseinträge zur Konfigurationsdatei *Web.config* Ihrer ASP.NET MVC-Webanwendung hinzu, damit diese Ansprüche unterstützt.  
  
#### <a name="to-configure-aspnet-mvc-application-for-claims-based-authentication"></a>Konfigurieren einer ASP.NET MVC-Anwendung für die anspruchsbasierte Authentifizierung  
  
1.  Fügen Sie der Konfigurationsdatei *Web.config* folgende Definitionen für den Konfigurationsabschnitt hinzu. Dadurch werden Konfigurationsabschnitte definiert, die für Windows Identity Foundation erforderlich sind. Fügen Sie die Definitionen direkt nach dem öffnenden Element **\<configuration>** hinzu:  
  
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
  
3.  Fügen Sie die folgenden Konfigurationseinträge innerhalb des Elements **\<system.web>** hinzu, um Benutzer zu verweigern, die native Authentifizierung zu deaktivieren und WIF zu ermöglichen, die Authentifizierung zu verwalten.  
  
    ```xml  
    <authorization>  
        <deny users="?" />  
    </authorization>  
    <authentication mode="None" />  
    ```  
  
4.  Fügen Sie folgende auf Windows Identity Foundation bezogene Konfigurationseinträge hinzu, und versichern Sie sich, dass die URL und Portnummer Ihrer ASP.NET-Anwendungen mit den Werten des **\<audienceUris>**-Eintrags, des **realm**-Attributs des **\<wsFederation>**-Elements und des **reply**-Attributs des **\<wsFederation>**-Elements übereinstimmen. Vergewissern Sie sich zudem, dass der Wert des **Ausstellers** der URL Ihres Sicherheitstokendiensts entspricht.  
  
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
  
5.  Fügen Sie der Assembly <xref:System.IdentityModel> einen Verweis hinzu.  
  
6.  Kompilieren Sie die Projektmappe, um sich zu vergewissern, ob Fehler vorliegen.  
  
## <a name="step-3--test-your-solution"></a>Schritt 3: Testen Ihrer Projektmappe  
 In diesem Schritt testen Sie die ASP.NET MVC-Webanwendung, die für die anspruchsbasierte Authentifizierung konfiguriert wurde. Sie können einen grundlegenden Test ausführen, indem Sie einfachen Code hinzufügen, der die Ansprüche im Token anzeigt, die vom Sicherheitstokendienst (STS) ausgegeben werden.  
  
#### <a name="to-test-your-aspnet-mvc-application-for-claims-based-authentication"></a>Testen Ihrer ASP.NET MVC-Anwendung für die anspruchsbasierte Authentifizierung  
  
1.  Erweitern Sie im **Projektmappen-Explorer** den Ordner **Controller**, und öffnen Sie die Datei *HomeController.cs* im Editor. Fügen Sie der **Index**-Methode folgenden Code hinzu:  
  
    ```csharp  
    public ActionResult Index()  
    {  
        ViewBag.ClaimsIdentity = Thread.CurrentPrincipal.Identity;  
  
        return View();  
    }  
    ```  
  
2.  Erweitern Sie im **Projektmappen-Explorer** zunächst **Ansichten** und dann die Ordner **Home**. Öffnen Sie dann die Datei *Index.cshtml* im Editor. Löschen Sie deren Inhalte, und fügen Sie das folgende Markup hinzu:  
  
    ```html  
    @{  
        ViewBag.Title = "Home Page";  
    }  
  
    <h2>Welcome: @ViewBag.ClaimsIdentity.Name</h2>  
    <h3>Values from Identity</h3>  
    <table>  
        <tr>  
            <th>  
                IsAuthenticated   
            </th>  
            <td>  
                @ViewBag.ClaimsIdentity.IsAuthenticated   
            </td>  
        </tr>  
        <tr>  
            <th>  
                Name   
            </th>          
            <td>  
                @ViewBag.ClaimsIdentity.Name  
            </td>          
        </tr>  
    </table>  
    <h3>Claims from ClaimsIdentity</h3>  
    <table>  
        <tr>  
            <th>  
                Claim Type  
            </th>  
            <th>  
                Claim Value  
            </th>  
            <th>  
                Value Type  
            </th>  
            <th>  
                Subject Name  
            </th>          
            <th>  
                Issuer Name  
            </th>          
        </tr>  
            @foreach (System.Security.Claims.Claim claim in ViewBag.ClaimsIdentity.Claims ) {  
        <tr>  
            <td>  
                @claim.Type  
            </td>  
            <td>  
                @claim.Value  
            </td>  
            <td>  
                @claim.ValueType  
            </td>  
            <td>  
                @claim.Subject.Name  
            </td>  
            <td>  
                @claim.Issuer  
            </td>  
        </tr>  
    }  
    </table>  
    ```  
  
3.  Starten Sie die Projektmappe durch Drücken der Taste **F5**.  
  
4.  Ihnen sollte die Seite angezeigt werden, die die Ansprüche im Token anzeigen, die Ihnen vom Sicherheitstokendienst ausgegeben wurden.  
  
## <a name="related-items"></a>Verwandte Elemente  
  
-   [Gewusst wie: Erstellen einer Ansprüche unterstützenden ASP.NET Web Forms-Anwendung mithilfe von WIF](../../../docs/framework/security/how-to-build-claims-aware-aspnet-web-forms-app-using-wif.md)

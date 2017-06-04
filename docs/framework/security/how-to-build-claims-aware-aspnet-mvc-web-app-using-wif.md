---
title: "Gewusst wie: Erstellen einer Anspr&#252;che unterst&#252;tzenden ASP.NET MVC-Webanwendung mithilfe von WIF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0efb76bc-9f7b-4afe-be1c-2a57c917010b
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 6
---
# Gewusst wie: Erstellen einer Anspr&#252;che unterst&#252;tzenden ASP.NET MVC-Webanwendung mithilfe von WIF
## Gilt für  
  
-   Identitäts\-Grundlage Microsoft® Windows® \(WIF\)  
  
-   ASP.NET® MVC  
  
## Zusammenfassung  
 In dieser Vorgehensweise wird ausführliche Schritt\-für\-Schritt\-Anweisungen zum Erstellen einfacher Ansprüche unterstützende ASP.NET\-MVC\-Webanwendung vor.  Sie stellt auch Anweisungen, wie die einfache Ansprüche unterstützende ASP.NET\-MVC\-Webanwendung für eine erfolgreiche Implementierung der anspruchsbasierten Authentifizierung testet.  In dieser Vorgehensweise hat nicht ausführliche Anweisungen zum Erstellen eines Sicherheitstokendiensts \(STS\) und wird davon ausgegangen, dass bereits ein STS konfiguriert haben.  
  
## Inhalt  
  
-   Ziele  
  
-   Zusammenfassung von Schritten  
  
-   Schritt 1 \- erstellen Sie einfache ASP.NET\-MVC\-Anwendung  
  
-   Schritt 2 \- konfigurieren Sie ASP.NET MVC\-Anwendung für anspruchsbasierte Authentifizierung  
  
-   Schritt 3 \- testen Sie die Projektmappe  
  
-   Verwandte Themen  
  
## Ziele  
  
-   Konfigurieren von ASP.NET MVC\-Webanwendung für anspruchsbasierte Authentifizierung  
  
-   Testen Sie erfolgreiche Ansprüche unterstützende ASP.NET\-MVC\-Webanwendung  
  
## Zusammenfassung von Schritten  
  
-   Schritt 1 \- erstellen Sie einfache ASP.NET\-MVC\-Anwendung  
  
-   Schritt 2 \- konfigurieren Sie ASP.NET MVC\-Anwendung für anspruchsbasierte Authentifizierung  
  
-   Schritt 3 \- testen Sie die Projektmappe  
  
## Schritt 1 \- erstellen Sie einfache ASP.NET\-MVC\-Anwendung  
 In diesem Schritt erstellen Sie eine neue ASP.NET\-MVC\-Anwendung.  
  
#### So einfache ASP.NET\-MVC\-Anwendung erstellen  
  
1.  Starten Sie Visual Studio und klicken Sie auf **Datei**, **Neu** und dann auf **Projekt**.  
  
2.  Im **Neues Projekt** Fenster klicken Sie auf **ASP.NET MVC 3\-Webanwendung**.  
  
3.  In **Name** geben Sie `TestApp` ein und drücken Sie **OK**.  
  
4.  Im Dialogfeld wählen Sie **Neues ASP.NET MVC 3\-Projekt** **Internetanwendung** der verfügbaren Vorlagen, aus sicherstellen, dass **Ansichtsmodul** zu **Razor** festgelegt und anschließend auf **OK** klickt wird.  
  
5.  Wenn das neue Projekt geöffnet wird, klicken Sie auf das **TestApp** Projekt in **Projektmappen\-Explorer** mit der rechten Maustaste und wählen Sie die Option aus. **Eigenschaften**  
  
6.  Klicken Sie auf der Eigenschaftenseite des Projekts klicken Sie auf der Registerkarte **Web** links und stellen Sie sicher, dass die Option **Lokalen IIS\-Webserver verwenden**.  
  
## Schritt 2 \- konfigurieren Sie ASP.NET MVC\-Anwendung für anspruchsbasierte Authentifizierung  
 In diesem Schritt fügen Sie Konfigurationseinträge der Konfigurationsdatei *Web.config* der ASP.NET MVC\-Webanwendung, sie aufmerksam zu machen hinzu.  
  
#### So ASP.NET\-MVC\-Anwendung für anspruchsbasierte Authentifizierung  
  
1.  Fügen Sie die folgenden Konfigurationsabschnittsdefinitionen der Konfigurationsdatei *Web.config* hinzu.  Diese definieren die Konfigurationsabschnitte, die von Windows Identity Foundation erforderlich sind.  Fügen Sie die Definitionen unmittelbar nach dem öffnenden **\<configuration\>**\-Element hinzu:  
  
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
  
4.  Fügen Sie die folgenden Windows Identity Foundation verknüpften Konfigurationseinträge hinzu und stellen Sie sicher, dass die URL und Anschlussnummer der ASP.NET\-Anwendung die Werte im **\<audienceUris\>**\-Eintrag, im **realm**\-Attribut des **\<wsFederation\>**\-Elements und im **reply**\-Attribut des **\<wsFederation\>**\-Elements übereinstimmen.  Stellen Sie außerdem, dass der Wert den **Aussteller** Sicherheitstokendienst \(STS\) URL passt.  
  
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
  
5.  Fügen Sie [System.IdentityModel](assetId:///System.IdentityModel?qualifyHint=False&amp;autoUpgrade=True) Verweis auf die Assembly hinzu.  
  
6.  Kompilieren Sie die Projektmappe, um sicherzustellen, dass es Fehler gibt.  
  
## Schritt 3 \- testen Sie die Projektmappe  
 In diesem Schritt testen Sie die ASP.NET MVC\-Webanwendung, für die anspruchsbasierte Authentifizierung konfiguriert ist.  Um grundlegenden Test auszuführen fügen Sie einfachen Code hinzu der Ansprüche im Token anzeigt, das von dem Sicherheitstokendienst \(STS\) ausgegeben wird.  
  
#### Um die ASP.NET\-MVC\-Anwendung für anspruchsbasierte Authentifizierung testen  
  
1.  In **Projektmappen\-Explorer** erweitern Sie den Ordner **Controller** und öffnen *die HomeController.cs\-Datei* im Editor.  Fügen Sie den folgenden Code der **Index**\-Methode hinzu:  
  
    ```csharp  
    public ActionResult Index()  
    {  
        ViewBag.ClaimsIdentity = Thread.CurrentPrincipal.Identity;  
  
        return View();  
    }  
  
    ```  
  
2.  In **Projektmappen\-Explorer** erweitern Sie **Ansichten** und dann Ordner **Startseite** und offene *Index.cshtml\-Datei* im Editor.  Löschen Sie den Inhalt und fügen Sie das folgende Markup hinzu:  
  
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
  
3.  Führen Sie die Projektmappe aus, indem Sie die **F5** Taste drücken.  
  
4.  Sie sollten mit der Seite dargestellt werden, die die Ansprüche im Token anzeigt, das Ihnen vom Sicherheitstokendienst ausgegeben wurde.  
  
## Verwandte Themen  
  
-   [Gewusst wie: Erstellen einer Ansprüche unterstützenden ASP.NET Web Forms\-Anwendung mithilfe von WIF](../../../docs/framework/security/how-to-build-claims-aware-aspnet-web-forms-app-using-wif.md)
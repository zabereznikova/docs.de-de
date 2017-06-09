---
title: "Gewusst wie: Transformieren eingehender Anspr&#252;che | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2831d514-d9d8-4200-9192-954bb6da1126
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# Gewusst wie: Transformieren eingehender Anspr&#252;che
## Gilt für  
  
-   Identitäts\-Grundlage Microsoft® Windows® \(WIF\)  
  
-   ASP.NET®\-Web Forms  
  
## Zusammenfassung  
 In dieser Vorgehensweise wird ausführliche schrittweise Prozeduren zum Erstellen einer einfachen Ansprüche unterstützende ASP.NET Web Forms\-Anwendung und Transformieren von eingehenden Ansprüchen vor.  Außerdem werden Anweisungen bereit, wie die Anwendung testen, um zu überprüfen, ob Transformation Ansprüche dargestellt werden, wenn die Anwendung ausgeführt wird.  
  
## Inhalt  
  
-   Ziele  
  
-   Übersicht  
  
-   Zusammenfassung von Schritten  
  
-   Schritt 1 \- erstellen Sie eine einfache ASP.NET Web Forms\-Anwendung  
  
-   Schritt 2 \- Werkzeug\-Anspruchstransformation mithilfe eines benutzerdefinierten ClaimsAuthenticationManager  
  
-   Schritt 3 \- testen Sie die Projektmappe  
  
## Ziele  
  
-   Konfigurieren Sie eine ASP.NET Web Forms\-Anwendung für anspruchsbasierte Authentifizierung  
  
-   Transformieren Sie eingehende Ansprüche, indem Sie einen Administratorrollenanspruch hinzufügen  
  
-   Testen Sie die ASP.NET Web Forms\-Anwendungen, festzustellen, ob sie ordnungsgemäß funktioniert  
  
## Übersicht  
 WIF macht eine Klasse verfügbar <xref:System.Security.Claims.ClaimsAuthenticationManager> genannt wird, die es Benutzern ermöglicht, Ansprüche zu ändern, bevor er einer Anwendung des vertrauender Seite \(RP\) dargestellt werden.  <xref:System.Security.Claims.ClaimsAuthenticationManager> ist für Trennung einzelner Bereiche zwischen Authentifizierung und dem zugrunde liegenden Anwendungscode hilfreich.  Das folgende Beispiel zeigt, wie eine Rolle den Ansprüchen in eingehenden <xref:System.Security.Claims.ClaimsPrincipal> hinzufügt, das möglicherweise von RP benötigt wird.  
  
## Zusammenfassung von Schritten  
  
-   Schritt 1 \- erstellen Sie eine einfache ASP.NET Web Forms\-Anwendung  
  
-   Schritt 2 \- Werkzeug\-Anspruchstransformation mithilfe eines benutzerdefinierten ClaimsAuthenticationManager  
  
-   Schritt 3 \- testen Sie die Projektmappe  
  
## Schritt 1 \- erstellen Sie eine einfache ASP.NET Web Forms\-Anwendung  
 In diesem Schritt erstellen Sie eine neue ASP.NET Web Forms\-Anwendung.  
  
#### So fügen Sie eine einfache ASP.NET\-Anwendung erstellen  
  
1.  Anfangsvisual studio im erweiterten Modus als Administrator.  
  
2.  In Visual Studio auf **Datei** **Neu**, klicken Sie auf und dann auf **Projekt**.  
  
3.  Im **Neues Projekt** Fenster klicken Sie auf **ASP.NET Web Forms\-Anwendung**.  
  
4.  In **Name** geben Sie `TestApp` ein und drücken Sie **OK**.  
  
5.  Klicken Sie auf das **TestApp** Projekt unter **Projektmappen\-Explorer** mit der rechten Maustaste, und wählen Sie **Identität und Zugriff** aus.  
  
6.  Das **Identität und Zugriff** angezeigt wird.  Die **Anbieter** ausgewähltes **Anwendung mit dem lokalen Entwicklungs\-STS testen** klicken, dann auf **Übernehmen**.  
  
7.  In der Datei *Default.aspx* ersetzen Sie das vorhandene Markup durch das folgende, speichern Sie die Datei:  
  
    ```  
    <%@ Page Title="Home Page" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true"  
        CodeBehind="Default.aspx.cs" Inherits="TestApp._Default" %>  
  
    <asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">  
          <h3>Your Claims</h3>  
        <p>  
            <asp:GridView ID="ClaimsGridView" runat="server" CellPadding="3">  
                <AlternatingRowStyle BackColor="White" />  
                <HeaderStyle BackColor="#7AC0DA" ForeColor="White" />  
            </asp:GridView>  
        </p>  
    </asp:Content>  
  
    ```  
  
8.  Öffnen Sie die Code\-Behind\-Datei, die *Default.aspx.cs ".* Ersetzen Sie den vorhandenen Code durch Folgendes, speichern Sie die Datei:  
  
    ```csharp  
    using System;  
    using System.Web.UI;  
    using System.Security.Claims;  
  
    namespace TestApp  
    {  
        public partial class _Default : Page  
        {  
            protected void Page_Load(object sender, EventArgs e)  
            {  
                ClaimsPrincipal claimsPrincipal = Page.User as ClaimsPrincipal;  
                this.ClaimsGridView.DataSource = claimsPrincipal.Claims;  
                this.ClaimsGridView.DataBind();  
            }  
        }  
    }  
    ```  
  
## Schritt 2 \- Werkzeug\-Anspruchstransformation mithilfe eines benutzerdefinierten ClaimsAuthenticationManager  
 In diesem Schritt überschreiben Sie Standardfunktionalität in der <xref:System.Security.Claims.ClaimsAuthenticationManager>\-Klasse, um eine Administratorrolle dem eingehenden Principal hinzuzufügen.  
  
#### So Anspruchstransformation mithilfe eines benutzerdefinierten ClaimsAuthenticationManager implementieren  
  
1.  Klicken Sie in Visual Studio die Projektmappe an, klicken Sie mit der rechten Maustaste auf **Hinzufügen** und dann auf **Neues Projekt**.  
  
2.  Im Fenster **Neues Projekt hinzufügen** führen ausgewähltes **Klassenbibliothek** von den **Visual C\#** Vorlagen auf, geben `ClaimsTransformation` ein und drücken dann **OK**.  Das neue Projekt wird im Projektmappenordner erstellt.  
  
3.  Klicken Sie auf **Verweise** unter dem **ClaimsTransformation** Projekt, und klicken Sie dann auf **Verweis hinzufügen**.  
  
4.  Im Fenster **Verweis\-Manager** ausgewähltes **System.IdentityModel** klicken und dann auf **OK**.  
  
5.  Geöffnetes **Class1.cs** oder wenn es nicht vorhanden ist, auf **ClaimsTransformation** mit der rechten Maustaste klicken, auf **Hinzufügen** klicken, dann auf, **Klasse…** auf  
  
6.  Fügen Sie unter Verwendung der \- Direktive der Codedatei hinzu:  
  
    ```csharp  
    using System.Security.Claims;  
    using System.Security.Principal;  
    ```  
  
7.  Fügen Sie die folgende Klasse und die \- Methode in der Codedatei hinzu.  
  
    > [!WARNING]
    >  Der folgende Code dient nur der Veranschaulichung; Überprüfen Sie, ob Sie die gewünschten Berechtigungen im Produktionscode überprüfen.  
  
    ```csharp  
    public class ClaimsTransformationModule : ClaimsAuthenticationManager  
    {  
        public override ClaimsPrincipal Authenticate(string resourceName, ClaimsPrincipal incomingPrincipal)  
        {  
            if (incomingPrincipal != null && incomingPrincipal.Identity.IsAuthenticated == true)  
            {  
               ((ClaimsIdentity)incomingPrincipal.Identity).AddClaim(new Claim(ClaimTypes.Role, "Admin"));  
            }  
  
            return incomingPrincipal;  
        }  
    }  
    ```  
  
8.  Speichern Sie die Datei und erstellen Sie das **ClaimsTransformation** Projekt.  
  
9. Im Projekt **TestApp** ASP.NET Verweisen klicken Sie auf, und klicken Sie dann auf **Verweis hinzufügen**.  
  
10. Im Fenster auf **Verweis\-Manager** ausgewähltes **Projektmappe** vom linken Menü, wählen Sie **ClaimsTransformation** von gefüllten Optionen und dann auf **OK**.  
  
11. In der Stammdatei **Web.config** navigieren Sie zu **\<system.identityModel\>** den Eintrag.  Innerhalb der **\<identityConfiguration\>**\-Elemente fügen Sie die folgende Zeile hinzu und speichern Sie die Datei:  
  
    ```  
    <claimsAuthenticationManager type="ClaimsTransformation.ClaimsTransformationModule, ClaimsTransformation" />  
    ```  
  
## Schritt 3 \- testen Sie die Projektmappe  
 In diesem Schritt testen Sie die ASP.NET Web Forms\-Anwendung und überprüfen, ob Ansprüche dargestellt werden, wenn ein Benutzer im mit Formularauthentifizierung signiert.  
  
#### Um die ASP.NET Web Forms\-Anwendung für Ansprüche mit Formularauthentifizierung testen  
  
1.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  Sie sollten mit *Default.aspx* dargestellt werden.  
  
2.  Klicken Sie auf der Seite *Default.aspx* sollten Sie eine Tabelle unter der Überschrift **Your Claims** finden, die **Issuer**, **OriginalIssuer**, **Typ**, **Wert** und **ValueType** Anspruchsinformationen über das Konto enthält.  Die letzte Zeile sollte wie folgt dargestellt werden:  
  
    ||||||  
    |-|-|-|-|-|  
    |LOKALE BEHÖRDE|LOKALE BEHÖRDE|http:\/\/schemas.microsoft.com\/ws\/2008\/06\/identity\/claims\/role|Admin|http:\/\/www.w3.org\/2001\/XMLSchema\#string|
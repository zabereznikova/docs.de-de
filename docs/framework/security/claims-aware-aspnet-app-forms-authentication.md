---
title: "Gewusst wie: Erstellen einer Anspr&#252;che unterst&#252;tzenden ASP.NET-Anwendung mit formularbasierter Authentifizierung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 98a3e029-1a9b-4e0c-b5d0-29d3f23f5b15
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 6
---
# Gewusst wie: Erstellen einer Anspr&#252;che unterst&#252;tzenden ASP.NET-Anwendung mit formularbasierter Authentifizierung
## Gilt für  
  
-   Identitäts\-Grundlage Microsoft® Windows® \(WIF\)  
  
-   ASP.NET®\-Web Forms  
  
## Zusammenfassung  
 In dieser Vorgehensweise wird ausführliche schrittweise Prozeduren zum Erstellen einer einfachen Ansprüche unterstützende ASP.NET Web Forms\-Anwendung vor, die Formularauthentifizierung verwendet.  Außerdem werden Anweisungen bereit, wie die Anwendung testen, um zu überprüfen, ob Ansprüche dargestellt werden, wenn ein Benutzer im mit Formularauthentifizierung signiert.  
  
## Inhalt  
  
-   Ziele  
  
-   Übersicht  
  
-   Zusammenfassung von Schritten  
  
-   Schritt 1 \- erstellen Sie eine einfache ASP.NET Web Forms\-Anwendung  
  
-   Schritt 2 \- Konfigurieren der ASP.NET Web Forms\-Anwendung für Ansprüche mit Formularauthentifizierung  
  
-   Schritt 3 \- testen Sie die Projektmappe  
  
## Ziele  
  
-   Konfigurieren Sie eine ASP.NET Web Forms\-Anwendung für Ansprüche mit Formularauthentifizierung  
  
-   Testen Sie die ASP.NET Web Forms\-Anwendungen, festzustellen, ob sie ordnungsgemäß funktioniert  
  
## Übersicht  
 In .NET 4.5 sind WIF und die anspruchsbasierte Autorisierung als ganzzahliger Teil des Frameworks eingefügt.  Zuvor wenn Sie Ansprüche von einem ASP.NET\-Benutzer soll, wurden verlangt, WIF zu installieren und dann Schnittstellen zu den Prinzipalobjekten wie `Thread.CurrentPrincipal` oder `HttpContext.Current.User` umwandeln.  Nun werden Ansprüche automatisch durch diese Principalobjekte präsentiert.  
  
 Formularauthentifizierung wurde von Aufnahme WIF in .NET 4.5 profitieren, da alle Benutzer, die in Formularen authentifiziert werden automatisch, die Ansprüche verfügen, die mit ihnen zugeordnet werden.  Sie können mithilfe dieser Ansprüche unmittelbar in einer ASP.NET\-Anwendung beginnen, die Formularauthentifizierung verwendet, da dieses dieser Vorgehensweise werden.  
  
## Zusammenfassung von Schritten  
  
-   Schritt 1 \- erstellen Sie eine einfache ASP.NET Web Forms\-Anwendung  
  
-   Schritt 2 \- Konfigurieren der ASP.NET Web Forms\-Anwendung für Ansprüche mit Formularauthentifizierung  
  
-   Schritt 3 \- testen Sie die Projektmappe  
  
## Schritt 1 \- erstellen Sie eine einfache ASP.NET Web Forms\-Anwendung  
 In diesem Schritt erstellen Sie eine neue ASP.NET Web Forms\-Anwendung.  
  
#### So fügen Sie eine einfache ASP.NET\-Anwendung erstellen  
  
1.  Starten Sie Visual Studio und klicken Sie auf **Datei**, **Neu** und dann auf **Projekt**.  
  
2.  Im **Neues Projekt** Fenster klicken Sie auf **ASP.NET Web Forms\-Anwendung**.  
  
3.  In **Name** geben Sie `TestApp` ein und drücken Sie **OK**.  
  
## Schritt 2 \- Konfigurieren der ASP.NET Web Forms\-Anwendung für Ansprüche mit Formularauthentifizierung  
 In diesem Schritt fügen Sie einen Konfigurationseintrag der Konfigurationsdatei *Web.config* hinzu und ändern die Datei *Default.aspx*, um Anspruchsinformationen für ein Konto anzuzeigen.  
  
#### So ASP.NET\-Anwendung für Ansprüche mit Formularauthentifizierung konfigurieren  
  
1.  In der Datei *Default.aspx* ersetzen Sie das vorhandene Markup durch Folgendes:  
  
    ```  
    <%@ Page Title="Home Page" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true" CodeBehind="Default.aspx.cs" Inherits="TestApp._Default" %>  
  
    <asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">  
        <p>  
            This page displays the claims associated with a Forms authenticated user.          
        </p>  
        <h3>Your Claims</h3>  
        <p>  
            <asp:GridView ID="ClaimsGridView" runat="server" CellPadding="3">  
                <AlternatingRowStyle BackColor="White" />  
                <HeaderStyle BackColor="#7AC0DA" ForeColor="White" />  
            </asp:GridView>  
        </p>  
    </asp:Content>  
  
    ```  
  
     In diesem Schritt wird ein GridView\-Steuerelement der Seite *Default.aspx hinzu,*, die den Ansprüchen aufgefüllt wird, die von der Formularauthentifizierung abgerufen werden.  
  
2.  Speichern Sie die Datei *Default.aspx*, und öffnen Sie dann die Datei mit dem Namen *Default.aspx.cs*.  Ersetzen Sie den vorhandenen Code durch Folgendes:  
  
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
  
                if (claimsPrincipal != null)  
                {  
                    this.ClaimsGridView.DataSource = claimsPrincipal.Claims;  
                    this.ClaimsGridView.DataBind();  
                }  
            }  
        }  
    }  
    ```  
  
     Der obige Code zeigt Ansprüche über einen authentifizierten Benutzer, einschließlich der Benutzer an, die von Formularauthentifizierung identifiziert werden.  
  
## Schritt 3 \- testen Sie die Projektmappe  
 In diesem Schritt testen Sie die ASP.NET Web Forms\-Anwendung und überprüfen, ob Ansprüche dargestellt werden, wenn ein Benutzer im mit Formularauthentifizierung signiert.  
  
#### Um die ASP.NET Web Forms\-Anwendung für Ansprüche mit Formularauthentifizierung testen  
  
1.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  Ihnen sollte *Default.aspx* angezeigt werden, das über die Links **Registrieren** und **Anmelden** rechts oben auf der Seite verfügt.  Klicken Sie auf **Registrieren**.  
  
2.  Klicken Sie auf der Seite **Registrieren** erstellen Sie ein Benutzerkonto, und klicken Sie dann auf **Registrieren**.  Das Konto wird unter Verwendung der Formularauthentifizierung erstellt, und Sie werden automatisch in signiert.  
  
3.  Nachdem Sie sich zur Homepage umgeleitet haben, sollten Sie eine Tabelle unter der Überschrift **Your Claims** finden, die **Issuer**, **OriginalIssuer**, **Typ**, **Wert** und **ValueType** Anspruchsinformationen über das Konto enthält.
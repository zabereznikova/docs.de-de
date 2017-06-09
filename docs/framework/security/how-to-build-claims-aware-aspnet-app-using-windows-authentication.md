---
title: "Gewusst wie: Erstellen einer Anspr&#252;che unterst&#252;tzenden ASP.NET-Anwendung mit Windows-Authentifizierung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 11c53d9d-d34a-44b4-8b5e-22e3eaeaee93
caps.latest.revision: 5
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# Gewusst wie: Erstellen einer Anspr&#252;che unterst&#252;tzenden ASP.NET-Anwendung mit Windows-Authentifizierung
## Gilt für  
  
-   Identitäts\-Grundlage Microsoft® Windows® \(WIF\)  
  
-   ASP.NET®\-Web Forms  
  
## Zusammenfassung  
 In dieser Vorgehensweise wird ausführliche schrittweise Prozeduren zum Erstellen einer einfachen Ansprüche unterstützende ASP.NET Web Forms\-Anwendung vor, die Windows\-Authentifizierung verwendet.  Außerdem werden Anweisungen bereit, wie die Anwendung testen, um zu überprüfen, ob Ansprüche dargestellt werden, wenn ein Benutzer in mithilfe der Windows\-Authentifizierung signiert.  
  
## Inhalt  
  
-   Ziele  
  
-   Übersicht  
  
-   Zusammenfassung von Schritten  
  
-   Schritt 1 \- erstellen Sie eine einfache ASP.NET Web Forms\-Anwendung  
  
-   Schritt 2 \- konfigurieren Sie ASP.NET Web Forms\-Anwendung für Ansprüche mithilfe der Windows\-Authentifizierung  
  
-   Schritt 3 \- testen Sie die Projektmappe  
  
## Ziele  
  
-   Konfigurieren Sie eine ASP.NET Web Forms\-Anwendung für Ansprüche mithilfe der Windows\-Authentifizierung  
  
-   Testen Sie die ASP.NET Web Forms\-Anwendungen, festzustellen, ob sie ordnungsgemäß funktioniert  
  
## Übersicht  
 In .NET 4.5 sind WIF und die anspruchsbasierte Autorisierung als ganzzahliger Teil des Frameworks eingefügt.  Zuvor wenn Sie Ansprüche von einem ASP.NET\-Benutzer soll, wurden verlangt, WIF zu installieren und dann Schnittstellen zu den Prinzipalobjekten wie `Thread.CurrentPrincipal` oder `HttpContext.Current.User` umwandeln.  Nun werden Ansprüche automatisch durch diese Principalobjekte präsentiert.  
  
 Windows\-Authentifizierung wurde von Aufnahme WIF in .NET 4.5 profitieren, da alle Benutzer, die von Windows\-Anmeldeinformationen authentifiziert werden automatisch, die Ansprüche verfügen, die mit ihnen zugeordnet werden.  Sie können mithilfe dieser Ansprüche unmittelbar in einer ASP.NET\-Anwendung beginnen, die Windows\-Authentifizierung verwendet, da dieses dieser Vorgehensweise werden.  
  
## Zusammenfassung von Schritten  
  
-   Schritt 1 \- erstellen Sie eine einfache ASP.NET Web Forms\-Anwendung  
  
-   Schritt 2 \- konfigurieren Sie ASP.NET Web Forms\-Anwendung für Ansprüche mithilfe der Windows\-Authentifizierung  
  
-   Schritt 3 \- testen Sie die Projektmappe  
  
## Schritt 1 \- erstellen Sie eine einfache ASP.NET Web Forms\-Anwendung  
 In diesem Schritt erstellen Sie eine neue ASP.NET Web Forms\-Anwendung.  
  
#### So fügen Sie eine einfache ASP.NET\-Anwendung erstellen  
  
1.  Starten Sie Visual Studio, klicken Sie auf **Datei**, **Neu** und dann auf **Projekt**.  
  
2.  Im **Neues Projekt** Fenster klicken Sie auf **ASP.NET Web Forms\-Anwendung**.  
  
3.  In **Name** geben Sie `TestApp` ein und drücken Sie **OK**.  
  
4.  Nachdem das **TestApp** Projekt erstellt wurde, klicken Sie in **Projektmappen\-Explorer**.  Die Eigenschaften des Projekts werden im **Eigenschaften** Bereich unter **Projektmappen\-Explorer**.  Legen Sie die **Windows\-Authentifizierung**\-Eigenschaft auf **Aktiviert** fest.  
  
    > [!WARNING]
    >  Die Windows\-Authentifizierung wird standardmäßig in neuen ASP.NET\-Anwendungen deaktiviert ist, müssen Sie sie manuell aktivieren.  
  
## Schritt 2 \- konfigurieren Sie ASP.NET Web Forms\-Anwendung für Ansprüche mithilfe der Windows\-Authentifizierung  
 In diesem Schritt fügen Sie einen Konfigurationseintrag der Konfigurationsdatei *Web.config* hinzu und ändern die Datei *Default.aspx*, um Anspruchsinformationen für ein Konto anzuzeigen.  
  
#### So ASP.NET\-Anwendung für Ansprüche mithilfe der Windows\-Authentifizierung konfigurieren  
  
1.  In der Datei *Default.aspx* des Projekts **TestApp** ersetzen Sie das vorhandene Markup durch Folgendes:  
  
    ```  
    <%@ Page Title="Home Page" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true"  
        CodeBehind="Default.aspx.cs" Inherits="TestApp._Default" %>  
  
    <asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">  
        <p>  
            This page displays the claims associated with a Windows authenticated user.          
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
  
     In diesem Schritt wird ein GridView\-Steuerelement der Seite *Default.aspx hinzu,*, die den Ansprüchen aufgefüllt wird, die von der Windows\-Authentifizierung abgerufen werden.  
  
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
                this.ClaimsGridView.DataSource = claimsPrincipal.Claims;  
                this.ClaimsGridView.DataBind();  
            }  
        }  
    }  
    ```  
  
     Der obige Code zeigt Ansprüche über einen authentifizierten Benutzer an.  
  
3.  Um den Authentifizierungstyp der Anwendung zu ändern, ändern Sie den **\<authentication\>**\-Block im **\<system.web\>**\-Abschnitt der Stammdatei *Web.config* des Projekts damit sie nur folgenden Konfigurationseintrag enthält:  
  
    ```  
    <authentication mode="Windows" />  
    ```  
  
4.  Ändern Sie abschließend den **\<authorization\>**\-Block im **\<system.web\>**\-Abschnitt dieser *Web.config*\-Datei, um die Authentifizierung zu erzwingen:  
  
    ```  
    <authorization>  
        <deny users="?" />  
    </authorization>  
    ```  
  
## Schritt 3 \- testen Sie die Projektmappe  
 In diesem Schritt testen Sie die ASP.NET Web Forms\-Anwendung und überprüfen, ob Ansprüche dargestellt werden, wenn ein Benutzer im mit Windows\-Authentifizierung signiert.  
  
#### Um die ASP.NET Web Forms\-Anwendung für Ansprüche mithilfe der Windows\-Authentifizierung testen  
  
1.  Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  Sie sollten mit *Default.aspx* dargestellt werden, und der Windows\-Kontoname \(einschließlich Domänenname\) sollte als authentifizierter Benutzer oben rechts auf der Seite bereits angezeigt werden.  Der Inhalt der Seite sollte eine Tabelle enthalten, die mit den Ansprüchen gefüllt wird, die aus dem Windows\-Konto abgerufen werden.
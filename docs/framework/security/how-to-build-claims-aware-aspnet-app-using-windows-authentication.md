---
title: "Gewusst wie: Erstellen einer Ansprüche unterstützenden ASP.NET-Anwendung mit Windows-Authentifizierung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 11c53d9d-d34a-44b4-8b5e-22e3eaeaee93
caps.latest.revision: 5
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 676a03678cbdf6fe08e628806df2a1853fb71718
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="how-to-build-claims-aware-aspnet-application-using-windows-authentication"></a>Gewusst wie: Erstellen einer Ansprüche unterstützenden ASP.NET-Anwendung mit Windows-Authentifizierung
## <a name="applies-to"></a>Gilt für  
  
-   Microsoft® Windows® Identity Foundation (WIF)  
  
-   ASP.NET® Web Forms  
  
## <a name="summary"></a>Zusammenfassung  
 In dieser Vorgehensweise werden ausführliche Prozeduren zum Erstellen einer einfachen Ansprüche unterstützenden ASP.NET Web Forms-Anwendung, die Windows-Authentifizierung verwendet, vorgestellt. Sie enthält auch Anweisungen zum Testen der Anwendung, mit denen überprüft werden kann, ob Ansprüche dargestellt werden, wenn sich ein Benutzer mit der Windows-Authentifizierung anmeldet.  
  
## <a name="contents"></a>Inhalt  
  
-   Ziele  
  
-   Übersicht  
  
-   Zusammenfassung von Schritten  
  
-   Schritt 1: Erstellen einer einfachen ASP.NET Web Forms-Anwendung  
  
-   Schritt 2: Konfigurieren der ASP.NET Web Forms-Anwendung für Ansprüche bei Verwendung der Windows-Authentifizierung  
  
-   Schritt 3: Testen Ihrer Projektmappe  
  
## <a name="objectives"></a>Ziele  
  
-   Konfigurieren einer ASP.NET Web Forms-Anwendung für Ansprüche bei Verwendung der Windows-Authentifizierung  
  
-   Testen Sie die ASP.NET Web Forms-Anwendung, um festzustellen, ob sie ordnungsgemäß funktioniert.  
  
## <a name="overview"></a>Übersicht  
 In .NET 4.5 wurden WIF und seine anspruchsbasierte Autorisierung als wesentlicher Bestandteil in das Framework integriert. Wenn Sie zuvor die Ansprüche eines ASP.NET-Benutzers abrufen wollten, war es erforderlich, WIF zu installieren und anschließend Schnittstellen in Principal-Objekte wie `Thread.CurrentPrincipal` oder `HttpContext.Current.User` umzuwandeln. Nun werden Ansprüche automatisch von diesen Principal-Objekten verarbeitet.  
  
 Die Windows-Authentifizierung profitiert von der Integration von WIF in .NET 4.5, da allen Benutzern, die über Windows-Anmeldeinformationen authentifiziert wurden, automatisch Ansprüche zugeordnet sind. Sie können diese Ansprüche sofort in einer ASP.NET-Anwendung verwenden, die die Windows-Authentifizierung verwendet. Dies wird in dieser Vorgehensweise veranschaulicht.  
  
## <a name="summary-of-steps"></a>Zusammenfassung von Schritten  
  
-   Schritt 1: Erstellen einer einfachen ASP.NET Web Forms-Anwendung  
  
-   Schritt 2: Konfigurieren der ASP.NET Web Forms-Anwendung für Ansprüche bei Verwendung der Windows-Authentifizierung  
  
-   Schritt 3: Testen Ihrer Projektmappe  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a>Schritt 1: Erstellen einer einfachen ASP.NET Web Forms-Anwendung  
 In diesem Schritt erstellen Sie eine neue ASP.NET Web Forms-Anwendung.  
  
#### <a name="to-create-a-simple-aspnet-application"></a>So erstellen Sie eine einfache ASP.NET-Anwendung  
  
1.  Starten Sie Visual Studio, klicken Sie auf **Datei**, **Neu**, und klicken Sie dann auf **Projekt**.  
  
2.  Klicken Sie im Fenster **Neues Projekt** auf **ASP.NET Web Forms-Anwendung**.  
  
3.  Geben Sie im Feld **Name** die Zeichenfolge `TestApp` ein, und klicken Sie auf **OK**.  
  
4.  Klicken Sie im **Projektmappen-Explorer** auf das Projekt **TestApp**, nachdem Sie dieses erstellt haben. Die Eigenschaften des Projekts werden im Bereich **Eigenschaften** unter dem **Projektmappen-Explorer** angezeigt. Legen Sie die Eigenschaft **Windows-Authentifizierung** auf **Aktiviert** fest.  
  
    > [!WARNING]
    >  Die Windows-Authentifizierung ist standardmäßig für neue ASP.NET-Anwendungen deaktiviert, sodass Sie sie manuell aktivieren müssen.  
  
## <a name="step-2--configure-aspnet-web-forms-application-for-claims-using-windows-authentication"></a>Schritt 2: Konfigurieren der ASP.NET Web Forms-Anwendung für Ansprüche bei Verwendung der Windows-Authentifizierung  
 In diesem Schritt fügen Sie einen Konfigurationseintrag zur Konfigurationsdatei *Web.config* hinzu und ändern die Datei *Default.aspx*, damit diese die Informationen zu den Ansprüchen eines Kontos anzeigt.  
  
#### <a name="to-configure-aspnet-application-for-claims-using-windows-authentication"></a>Konfigurieren einer ASP.NET-Anwendung für Ansprüche bei Verwendung der Windows-Authentifizierung  
  
1.  Ersetzen Sie in der Datei *Default.aspx* des Projekts **TestApp** das vorhandene Markup durch das folgende Markup:  
  
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
  
     In diesem Schritt wird eine „GridView“-Steuerung zu Ihrer Seite *Default.aspx* hinzugefügt, die mit den Ansprüchen aufgefüllt wird, die von der Windows-Authentifizierung abgerufen wurden.  
  
2.  Speichern Sie die Datei *Default.aspx*, und öffnen Sie dann die CodeBehind-Datei *Default.aspx.cs*. Ersetzen Sie den vorhandenen Code durch folgenden Code:  
  
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
  
     Der obige Code zeigt die Ansprüche eines authentifizierten Benutzers an.  
  
3.  Modifizieren Sie zum Ändern des Authentifizierungstyps einer Anwendung den Block **\<authentication>** im Abschnitt **\<system.web>** der Stammdatei des Projekts (*Web.config*), sodass diese nur den folgenden Konfigurationseintrag enthält:  
  
    ```xml  
    <authentication mode="Windows" />  
    ```  
  
4.  Ändern Sie abschließend den Block **\<authorization>** im Abschnitt **\<system.web>** derselben *Web.config*-Datei, um die Authentifizierung zu erzwingen:  
  
    ```xml  
    <authorization>  
        <deny users="?" />  
    </authorization>  
    ```  
  
## <a name="step-3--test-your-solution"></a>Schritt 3: Testen Ihrer Projektmappe  
 In diesem Schritt testen Sie Ihre ASP.NET Web Forms-Anwendung und überprüfen, ob Ansprüche dargestellt werden, wenn sich ein Benutzer mit der Windows-Authentifizierung anmeldet.  
  
#### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-windows-authentication"></a>Testen der ASP.NET Web Forms-Anwendung für Ansprüche bei Verwendung der Windows-Authentifizierung  
  
1.  Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen. Ihnen sollte *Default.aspx* angezeigt werden, und Ihr Windows-Kontoname (einschließlich des Domänennamens) sollte bereits als der authentifizierte Benutzer oben rechts auf der Seite angezeigt werden. Die Seite sollte eine Tabelle enthalten, die mit den Ansprüchen gefüllt ist, die von Ihrem Windows-Konto abgerufen wurden.


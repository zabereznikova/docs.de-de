---
title: 'Gewusst wie: Erstellen einer Ansprüche unterstützenden ASP.NET-Anwendung mit formularbasierter Authentifizierung'
ms.date: 03/30/2017
ms.assetid: 98a3e029-1a9b-4e0c-b5d0-29d3f23f5b15
author: BrucePerlerMS
ms.openlocfilehash: 8dab5cfbcf14707699e6672017f5f80db232f01d
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/29/2018
ms.locfileid: "47454933"
---
# <a name="how-to-build-claims-aware-aspnet-application-using-forms-based-authentication"></a>Gewusst wie: Erstellen einer Ansprüche unterstützenden ASP.NET-Anwendung mit formularbasierter Authentifizierung
## <a name="applies-to"></a>Gilt für  
  
-   Microsoft® Windows® Identity Foundation (WIF)  
  
-   ASP.NET® Web Forms  
  
## <a name="summary"></a>Zusammenfassung  
 In dieser Vorgehensweise werden ausführliche Prozeduren zum Erstellen einer einfachen Ansprüche unterstützenden ASP.NET Web Forms-Anwendung, die Formularauthentifizierung verwendet, vorgestellt. Sie enthält auch Anweisungen zum Testen der Anwendung, mit denen überprüft werden kann, ob Ansprüche dargestellt werden, wenn sich ein Benutzer mit der Formularauthentifizierung anmeldet.  
  
## <a name="contents"></a>Inhalt  
  
-   Ziele  
  
-   Übersicht  
  
-   Zusammenfassung von Schritten  
  
-   Schritt 1: Erstellen einer einfachen ASP.NET Web Forms-Anwendung  
  
-   Schritt 2: Konfigurieren der ASP.NET Web Forms-Anwendung für Ansprüche bei Verwendung der Formularauthentifizierung  
  
-   Schritt 3: Testen Ihrer Projektmappe  
  
## <a name="objectives"></a>Ziele  
  
-   Konfigurieren einer ASP.NET Web Forms-Anwendung für Ansprüche bei Verwendung der Formularauthentifizierung  
  
-   Testen Sie die ASP.NET Web Forms-Anwendung, um festzustellen, ob sie ordnungsgemäß funktioniert.  
  
## <a name="overview"></a>Übersicht  
 In .NET 4.5 wurden WIF und seine anspruchsbasierte Autorisierung als wesentlicher Bestandteil in das Framework integriert. Wenn Sie zuvor die Ansprüche eines ASP.NET-Benutzers abrufen wollten, war es erforderlich, WIF zu installieren und anschließend Schnittstellen in Principal-Objekte wie `Thread.CurrentPrincipal` oder `HttpContext.Current.User` umzuwandeln. Nun werden Ansprüche automatisch von diesen Principal-Objekten verarbeitet.  
  
 Die Formularauthentifizierung profitiert von der Integration von WIF in .NET 4.5, da allen Benutzern, die über Formularauthentifizierung authentifiziert wurden, automatisch Ansprüche zugeordnet sind. Sie können diese Ansprüche sofort in einer ASP.NET-Anwendung verwenden, die die Formularauthentifizierung verwendet. Dies wird in dieser Vorgehensweise veranschaulicht.  
  
## <a name="summary-of-steps"></a>Zusammenfassung von Schritten  
  
-   Schritt 1: Erstellen einer einfachen ASP.NET Web Forms-Anwendung  
  
-   Schritt 2: Konfigurieren der ASP.NET Web Forms-Anwendung für Ansprüche bei Verwendung der Formularauthentifizierung  
  
-   Schritt 3: Testen Ihrer Projektmappe  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a>Schritt 1: Erstellen einer einfachen ASP.NET Web Forms-Anwendung  
 In diesem Schritt erstellen Sie eine neue ASP.NET Web Forms-Anwendung.  
  
#### <a name="to-create-a-simple-aspnet-application"></a>So erstellen Sie eine einfache ASP.NET-Anwendung  
  
1.  Starten Sie Visual Studio, und klicken Sie auf **Datei**, **Neu** und anschließend auf **Projekt**.  
  
2.  Klicken Sie im Fenster **Neues Projekt** auf **ASP.NET Web Forms-Anwendung**.  
  
3.  Geben Sie im Feld **Name** die Zeichenfolge `TestApp` ein, und drücken Sie auf **OK**.  
  
## <a name="step-2--configure-aspnet-web-forms-application-for-claims-using-forms-authentication"></a>Schritt 2: Konfigurieren der ASP.NET Web Forms-Anwendung für Ansprüche bei Verwendung der Formularauthentifizierung  
 In diesem Schritt fügen Sie einen Konfigurationseintrag zur Konfigurationsdatei *Web.config* hinzu und bearbeiten die Datei *Default.aspx*, damit diese die Informationen zu den Ansprüchen eines Kontos anzeigt.  
  
#### <a name="to-configure-aspnet-application-for-claims-using-forms-authentication"></a>Konfigurieren einer ASP.NET-Anwendung für Ansprüche bei Verwendung der Formularauthentifizierung  
  
1.  Ersetzten Sie das vorhandene Markup in der Datei *Default.aspx* durch das folgende Markup:  
  
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
  
     In diesem Schritt wird eine „GridView“-Steuerung zu Ihrer Seite *Default.aspx* hinzugefügt, die mit den Ansprüchen aufgefüllt wird, die von der Formularauthentifizierung abgerufen wurden.  
  
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
  
                if (claimsPrincipal != null)  
                {  
                    this.ClaimsGridView.DataSource = claimsPrincipal.Claims;  
                    this.ClaimsGridView.DataBind();  
                }  
            }  
        }  
    }  
    ```  
  
     Der obige Code zeigt die Ansprüche bezüglich eines authentifizierten Benutzers, einschließlich Benutzer, die durch die Formularauthentifizierung identifiziert werden.  
  
## <a name="step-3--test-your-solution"></a>Schritt 3: Testen Ihrer Projektmappe  
 In diesem Schritt testen Sie Ihre ASP.NET Web Forms-Anwendung und überprüfen, ob Ansprüche dargestellt werden, wenn sich ein Benutzer mit der Formularauthentifizierung anmeldet.  
  
#### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-forms-authentication"></a>Testen der ASP.NET Web Forms-Anwendung für Ansprüche bei Verwendung der Formularauthentifizierung  
  
1.  Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen. *Default.aspx* sollte mit den Links **Registrieren** und **Anmelden** rechts oben auf der Seite angezeigt werden. Klicken Sie auf **Registrieren**.  
  
2.  Erstellen Sie auf der Seite **Registrieren** ein Benutzerkonto, und klicken Sie dann auf **Registrieren**. Ihr Konto wird unter Verwendung der Formularauthentifizierung erstellt, und Sie werden automatisch angemeldet.  
  
3.  Nachdem Sie zur Startseite umgeleitet werden, sollte unter der Überschrift **Ihre Ansprüche** eine Tabelle angezeigt werden, die die Anspruchsinformationen **Aussteller**, **Originalaussteller**, **Typ**, **Welt** und **Werttyp** Ihres Kontos enthält.

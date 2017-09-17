---
title: "Gewusst wie: Transformieren eingehender Ansprüche"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2831d514-d9d8-4200-9192-954bb6da1126
caps.latest.revision: 4
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: bcf0e640e6b6b45ddb87070c7d6df2fa6dadc834
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="how-to-transform-incoming-claims"></a>Gewusst wie: Transformieren eingehender Ansprüche
## <a name="applies-to"></a>Gilt für  
  
-   Microsoft® Windows® Identity Foundation (WIF)  
  
-   ASP.NET® Web Forms  
  
## <a name="summary"></a>Zusammenfassung  
 In dieser Vorgehensweise werden ausführliche Prozeduren zum Erstellen einer einfachen Ansprüche unterstützenden ASP.NET Web Forms-Anwendung und zum Transformieren eingehender Ansprüche vorgestellt. Sie enthält auch Anweisungen zum Testen der Anwendung, mit denen überprüft werden kann, ob transformierte Ansprüche dargestellt werden, wenn die Anwendung ausgeführt wird.  
  
## <a name="contents"></a>Inhalt  
  
-   Ziele  
  
-   Übersicht  
  
-   Zusammenfassung von Schritten  
  
-   Schritt 1: Erstellen einer einfachen ASP.NET Web Forms-Anwendung  
  
-   Schritt 2: Implementieren der Anspruchstransformation mithilfe eines benutzerdefinierten „ClaimsAuthenticationManager“  
  
-   Schritt 3: Testen Ihrer Projektmappe  
  
## <a name="objectives"></a>Ziele  
  
-   Konfigurieren Sie eine ASP.NET Web Forms-Anwendung für die anspruchsbasierte Authentifizierung.  
  
-   Transformieren Sie eingehende Ansprüche durch Hinzufügen eines Administratorrollenanspruchs.  
  
-   Testen Sie die ASP.NET Web Forms-Anwendung, um festzustellen, ob sie ordnungsgemäß funktioniert.  
  
## <a name="overview"></a>Übersicht  
 WIF macht eine Klasse mit dem Namen <xref:System.Security.Claims.ClaimsAuthenticationManager> verfügbar, mit der Benutzer Ansprüche ändern können, bevor sie in einer Anwendung der vertrauenden Seite (Relying Party, RP) dargestellt werden. <xref:System.Security.Claims.ClaimsAuthenticationManager> eignet sich für die Trennung von Bereichen zwischen Authentifizierung und zugrunde liegendem Anwendungscode. Das unten aufgeführte Beispiel zeigt, wie eine Rolle den Ansprüchen im eingehenden <xref:System.Security.Claims.ClaimsPrincipal> hinzugefügt wird, die möglicherweise für die vertrauende Seite erforderlich ist.  
  
## <a name="summary-of-steps"></a>Zusammenfassung von Schritten  
  
-   Schritt 1: Erstellen einer einfachen ASP.NET Web Forms-Anwendung  
  
-   Schritt 2: Implementieren der Anspruchstransformation mithilfe eines benutzerdefinierten „ClaimsAuthenticationManager“  
  
-   Schritt 3: Testen Ihrer Projektmappe  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a>Schritt 1: Erstellen einer einfachen ASP.NET Web Forms-Anwendung  
 In diesem Schritt erstellen Sie eine neue ASP.NET Web Forms-Anwendung.  
  
#### <a name="to-create-a-simple-aspnet-application"></a>So erstellen Sie eine einfache ASP.NET-Anwendung  
  
1.  Starten Sie Visual Studio im erweiterten Modus als Administrator.  
  
2.  Klicken Sie in Visual Studio auf **Datei**, **Neu** und anschließend auf **Projekt**.  
  
3.  Klicken Sie im Fenster **Neues Projekt** auf **ASP.NET Web Forms-Anwendung**.  
  
4.  Geben Sie im Feld **Name** die Zeichenfolge `TestApp` ein, und klicken Sie auf **OK**.  
  
5.  Klicken Sie mit der rechten Maustaste unter **Projektmappen-Explorer** auf das Projekt **TestApp**, und wählen Sie anschließend **Identität und Zugriff** aus.  
  
6.  Das Fenster **Identität und Zugriff** wird geöffnet. Klicken Sie unter **Anbieter** auf **Test your application with the Local Development STS** (Anwendung mit dem lokalen Entwicklungs-STS testen), und klicken Sie anschließend auf **Übernehmen**.  
  
7.  Ersetzen Sie in der Datei *Default.aspx* das vorhandene Markup durch das folgende Markup, und speichern Sie die Datei anschließend:  
  
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
  
8.  Öffnen Sie die CodeBehind-Datei mit dem Namen *Default.aspx.cs*. Ersetzen Sie den vorhandenen Code durch folgenden Code, und speichern Sie die Datei anschließend:  
  
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
  
## <a name="step-2--implement-claims-transformation-using-a-custom-claimsauthenticationmanager"></a>Schritt 2: Implementieren der Anspruchstransformation mithilfe eines benutzerdefinierten „ClaimsAuthenticationManager“  
 In diesem Schritt überschreiben Sie die Standardfunktionen in der <xref:System.Security.Claims.ClaimsAuthenticationManager>-Klasse, um dem eingehenden Prinzipal eine Administratorrolle hinzuzufügen.  
  
#### <a name="to-implement-claims-transformation-using-a-custom-claimsauthenticationmanager"></a>Implementieren der Anspruchstransformation mithilfe eines benutzerdefinierten „ClaimsAuthenticationManager“  
  
1.  Klicken Sie mit der rechten Maustaste in Visual Studio auf die Projektmappe, und klicken Sie dann auf **Hinzufügen** und **Neues Projekt**.  
  
2.  Wählen Sie im Fenster **Neues Projekt hinzufügen** aus der Vorlagenliste **Visual C#** die Option **Klassenbibliothek** aus. Geben Sie `ClaimsTransformation` ein, und klicken Sie anschließend auf **OK**. Das neue Projekt wird im Projektmappenordner erstellt.  
  
3.  Klicken Sie mit der rechten Maustaste unter dem Projekt **ClaimsTransformation** auf **Verweise**, und klicken Sie dann auf **Verweis hinzufügen**.  
  
4.  Wählen Sie im Fenster **Verweis-Manager** die Option **System.IdentityModel** aus, und klicken Sie anschließend auf **OK**.  
  
5.  Öffnen Sie, sofern vorhanden, **Class1.cs**. Andernfalls klicken Sie mit der rechten Maustaste auf **ClaimsTransformation**, und klicken Sie anschließend auf **Hinzufügen** und **Class...** (Klasse...).  
  
6.  Fügen Sie der Codedatei die folgenden using-Anweisungen hinzu:  
  
    ```csharp  
    using System.Security.Claims;  
    using System.Security.Principal;  
    ```  
  
7.  Fügen Sie in der Codedatei die folgende Klasse und Methode hinzu.  
  
    > [!WARNING]
    >  Der folgende Code dient nur der Veranschaulichung. Überprüfen Sie Ihre beabsichtigten Berechtigungen im Produktionscode.  
  
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
  
8.  Speichern Sie die Datei, und erstellen Sie das Projekt **ClaimsTransformation**.  
  
9. Klicken Sie mit der rechten Maustaste in Ihrem ASP.NET-Projekt **TestApp** auf „Verweise“, und klicken Sie anschließend auf **Verweis hinzufügen**.  
  
10. Wählen Sie im Fenster **Verweis-Manager** im linken Menü die Option **Projektmappe** aus. Wählen Sie aus den aufgefüllten Optionen die Option **ClaimsTransformation** aus, und klicken Sie anschließend auf **OK**.  
  
11. Gehen Sie in der Stammdatei **Web.config** zum Eintrag **\<system.identityModel>**. Fügen Sie den Elementen **\<identityConfiguration>** die folgende Zeile hinzu, und speichern Sie die Datei:  
  
    ```xml  
    <claimsAuthenticationManager type="ClaimsTransformation.ClaimsTransformationModule, ClaimsTransformation" />  
    ```  
  
## <a name="step-3--test-your-solution"></a>Schritt 3: Testen Ihrer Projektmappe  
 In diesem Schritt testen Sie Ihre ASP.NET Web Forms-Anwendung und überprüfen, ob Ansprüche dargestellt werden, wenn sich ein Benutzer mit der Formularauthentifizierung anmeldet.  
  
#### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-forms-authentication"></a>Testen der ASP.NET Web Forms-Anwendung für Ansprüche bei Verwendung der Formularauthentifizierung  
  
1.  Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen. Es sollte *Default.aspx* dargestellt werden.  
  
2.  Auf der Seite *Default.aspx* sollte unter der Überschrift **Your Claims** (Ihre Ansprüche) eine Tabelle angezeigt werden, die die Anspruchsinformationen **Issuer** (Aussteller), **OriginalIssuer** (Originalaussteller), **Type** (Typ), **Value** (Wert) und **ValueType** (Werttyp) Ihres Kontos enthält. Die letzte Zeile sollte folgendermaßen dargestellt werden:  
  
    ||||||  
    |-|-|-|-|-|  
    |LOKALE AUTORITÄT|LOKALE AUTORITÄT|http://schemas.microsoft.com/ws/2008/06/identity/claims/role|Admin|http://www.w3.org/2001/XMLSchema#string|


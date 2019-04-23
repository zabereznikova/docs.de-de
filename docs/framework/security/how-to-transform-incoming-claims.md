---
title: 'Vorgehensweise: Transformieren eingehender Ansprüche'
ms.date: 03/30/2017
ms.assetid: 2831d514-d9d8-4200-9192-954bb6da1126
author: BrucePerlerMS
ms.openlocfilehash: f836356125f1462f302b7e9f45a841c869c9a690
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "59977885"
---
# <a name="how-to-transform-incoming-claims"></a><span data-ttu-id="407f9-102">Vorgehensweise: Transformieren eingehender Ansprüche</span><span class="sxs-lookup"><span data-stu-id="407f9-102">How To: Transform Incoming Claims</span></span>
## <a name="applies-to"></a><span data-ttu-id="407f9-103">Gilt für</span><span class="sxs-lookup"><span data-stu-id="407f9-103">Applies To</span></span>  
  
-   <span data-ttu-id="407f9-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="407f9-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="407f9-105">ASP.NET® Web Forms</span><span class="sxs-lookup"><span data-stu-id="407f9-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="407f9-106">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="407f9-106">Summary</span></span>  
 <span data-ttu-id="407f9-107">In dieser Vorgehensweise werden ausführliche Prozeduren zum Erstellen einer einfachen Ansprüche unterstützenden ASP.NET Web Forms-Anwendung und zum Transformieren eingehender Ansprüche vorgestellt.</span><span class="sxs-lookup"><span data-stu-id="407f9-107">This How-To provides detailed step-by-step procedures for creating a simple claims-aware ASP.NET Web Forms application and transforming incoming claims.</span></span> <span data-ttu-id="407f9-108">Sie enthält auch Anweisungen zum Testen der Anwendung, mit denen überprüft werden kann, ob transformierte Ansprüche dargestellt werden, wenn die Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="407f9-108">It also provides instructions for how to test the application to verify that transformed claims are presented when the application is run.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="407f9-109">Inhalt</span><span class="sxs-lookup"><span data-stu-id="407f9-109">Contents</span></span>  
  
-   <span data-ttu-id="407f9-110">Ziele</span><span class="sxs-lookup"><span data-stu-id="407f9-110">Objectives</span></span>  
  
-   <span data-ttu-id="407f9-111">Übersicht</span><span class="sxs-lookup"><span data-stu-id="407f9-111">Overview</span></span>  
  
-   <span data-ttu-id="407f9-112">Zusammenfassung von Schritten</span><span class="sxs-lookup"><span data-stu-id="407f9-112">Summary of Steps</span></span>  
  
-   <span data-ttu-id="407f9-113">Schritt 1: Erstellen einer einfachen ASP.NET Web Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="407f9-113">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="407f9-114">Schritt 2: Implementieren der Anspruchstransformation mithilfe eines benutzerdefinierten „ClaimsAuthenticationManager“</span><span class="sxs-lookup"><span data-stu-id="407f9-114">Step 2 – Implement Claims Transformation Using a Custom ClaimsAuthenticationManager</span></span>  
  
-   <span data-ttu-id="407f9-115">Schritt 3: Testen Ihrer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="407f9-115">Step 3 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="407f9-116">Ziele</span><span class="sxs-lookup"><span data-stu-id="407f9-116">Objectives</span></span>  
  
-   <span data-ttu-id="407f9-117">Konfigurieren Sie eine ASP.NET Web Forms-Anwendung für die anspruchsbasierte Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="407f9-117">Configure an ASP.NET Web Forms application for claims-based authentication</span></span>  
  
-   <span data-ttu-id="407f9-118">Transformieren Sie eingehende Ansprüche durch Hinzufügen eines Administratorrollenanspruchs.</span><span class="sxs-lookup"><span data-stu-id="407f9-118">Transform incoming claims by adding an Administrator role claim</span></span>  
  
-   <span data-ttu-id="407f9-119">Testen Sie die ASP.NET Web Forms-Anwendung, um festzustellen, ob sie ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="407f9-119">Test the ASP.NET Web Forms application to see if it is working properly</span></span>  
  
## <a name="overview"></a><span data-ttu-id="407f9-120">Übersicht</span><span class="sxs-lookup"><span data-stu-id="407f9-120">Overview</span></span>  
 <span data-ttu-id="407f9-121">WIF macht eine Klasse mit dem Namen <xref:System.Security.Claims.ClaimsAuthenticationManager> verfügbar, mit der Benutzer Ansprüche ändern können, bevor sie in einer Anwendung der vertrauenden Seite (Relying Party, RP) dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="407f9-121">WIF exposes a class named <xref:System.Security.Claims.ClaimsAuthenticationManager> that enables users to modify claims before they are presented to a relying party (RP) application.</span></span> <span data-ttu-id="407f9-122"><xref:System.Security.Claims.ClaimsAuthenticationManager> eignet sich für die Trennung von Bereichen zwischen Authentifizierung und zugrunde liegendem Anwendungscode.</span><span class="sxs-lookup"><span data-stu-id="407f9-122">The <xref:System.Security.Claims.ClaimsAuthenticationManager> is useful for separation of concerns between authentication and the underlying application code.</span></span> <span data-ttu-id="407f9-123">Das unten aufgeführte Beispiel zeigt, wie eine Rolle den Ansprüchen im eingehenden <xref:System.Security.Claims.ClaimsPrincipal> hinzugefügt wird, die möglicherweise für die vertrauende Seite erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="407f9-123">The example below demonstrates how to add a role to the claims in the incoming <xref:System.Security.Claims.ClaimsPrincipal> that may be required by the RP.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="407f9-124">Zusammenfassung von Schritten</span><span class="sxs-lookup"><span data-stu-id="407f9-124">Summary of Steps</span></span>  
  
-   <span data-ttu-id="407f9-125">Schritt 1: Erstellen einer einfachen ASP.NET Web Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="407f9-125">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="407f9-126">Schritt 2: Implementieren der Anspruchstransformation mithilfe eines benutzerdefinierten „ClaimsAuthenticationManager“</span><span class="sxs-lookup"><span data-stu-id="407f9-126">Step 2 – Implement Claims Transformation Using a Custom ClaimsAuthenticationManager</span></span>  
  
-   <span data-ttu-id="407f9-127">Schritt 3: Testen Ihrer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="407f9-127">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a><span data-ttu-id="407f9-128">Schritt 1: Erstellen einer einfachen ASP.NET Web Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="407f9-128">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
 <span data-ttu-id="407f9-129">In diesem Schritt erstellen Sie eine neue ASP.NET Web Forms-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="407f9-129">In this step, you will create a new ASP.NET Web Forms application.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="407f9-130">So erstellen Sie eine einfache ASP.NET-Anwendung</span><span class="sxs-lookup"><span data-stu-id="407f9-130">To create a simple ASP.NET application</span></span>  
  
1. <span data-ttu-id="407f9-131">Starten Sie Visual Studio im erweiterten Modus als Administrator.</span><span class="sxs-lookup"><span data-stu-id="407f9-131">Start Visual Studio in elevated mode as administrator.</span></span>  
  
2. <span data-ttu-id="407f9-132">Klicken Sie in Visual Studio auf **Datei**, **Neu** und anschließend auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="407f9-132">In Visual Studio, click **File**, click **New**, and then click **Project**.</span></span>  
  
3. <span data-ttu-id="407f9-133">Klicken Sie im Fenster **Neues Projekt** auf **ASP.NET Web Forms-Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="407f9-133">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
4. <span data-ttu-id="407f9-134">Geben Sie im Feld **Name** die Zeichenfolge `TestApp` ein, und drücken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="407f9-134">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
5. <span data-ttu-id="407f9-135">Klicken Sie mit der rechten Maustaste unter **Projektmappen-Explorer** auf das Projekt **TestApp**, und wählen Sie anschließend **Identität und Zugriff** aus.</span><span class="sxs-lookup"><span data-stu-id="407f9-135">Right-click the **TestApp** project under **Solution Explorer**, then select **Identity and Access**.</span></span>  
  
6. <span data-ttu-id="407f9-136">Das Fenster **Identität und Zugriff** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="407f9-136">The **Identity and Access** window appears.</span></span> <span data-ttu-id="407f9-137">Klicken Sie unter **Anbieter** auf **Test your application with the Local Development STS** (Anwendung mit dem lokalen Entwicklungs-STS testen), und klicken Sie anschließend auf **Übernehmen**.</span><span class="sxs-lookup"><span data-stu-id="407f9-137">Under **Providers**, select **Test your application with the Local Development STS**, then click **Apply**.</span></span>  
  
7. <span data-ttu-id="407f9-138">Ersetzen Sie in der Datei *Default.aspx* das vorhandene Markup durch das folgende Markup, und speichern Sie die Datei anschließend:</span><span class="sxs-lookup"><span data-stu-id="407f9-138">In the *Default.aspx* file, replace the existing markup with the following, then save the file:</span></span>  
  
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
  
8. <span data-ttu-id="407f9-139">Öffnen Sie die CodeBehind-Datei mit dem Namen *Default.aspx.cs*.</span><span class="sxs-lookup"><span data-stu-id="407f9-139">Open the code-behind file named *Default.aspx.cs*.</span></span> <span data-ttu-id="407f9-140">Ersetzen Sie den vorhandenen Code durch folgenden Code, und speichern Sie die Datei anschließend:</span><span class="sxs-lookup"><span data-stu-id="407f9-140">Replace the existing code with the following, then save the file:</span></span>  
  
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
  
## <a name="step-2--implement-claims-transformation-using-a-custom-claimsauthenticationmanager"></a><span data-ttu-id="407f9-141">Schritt 2: Implementieren der Anspruchstransformation mithilfe eines benutzerdefinierten „ClaimsAuthenticationManager“</span><span class="sxs-lookup"><span data-stu-id="407f9-141">Step 2 – Implement Claims Transformation Using a Custom ClaimsAuthenticationManager</span></span>  
 <span data-ttu-id="407f9-142">In diesem Schritt überschreiben Sie die Standardfunktionen in der <xref:System.Security.Claims.ClaimsAuthenticationManager>-Klasse, um dem eingehenden Prinzipal eine Administratorrolle hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="407f9-142">In this step you will override default functionality in the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to add an Administrator role to the incoming Principal.</span></span>  
  
#### <a name="to-implement-claims-transformation-using-a-custom-claimsauthenticationmanager"></a><span data-ttu-id="407f9-143">Implementieren der Anspruchstransformation mithilfe eines benutzerdefinierten „ClaimsAuthenticationManager“</span><span class="sxs-lookup"><span data-stu-id="407f9-143">To implement claims transformation using a custom ClaimsAuthenticationManager</span></span>  
  
1. <span data-ttu-id="407f9-144">Klicken Sie mit der rechten Maustaste in Visual Studio auf die Projektmappe, und klicken Sie dann auf **Hinzufügen** und **Neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="407f9-144">In Visual Studio, right-click the on the solution, click **Add**, and then click **New Project**.</span></span>  
  
2. <span data-ttu-id="407f9-145">Wählen Sie im Fenster **Neues Projekt hinzufügen** aus der Vorlagenliste **Visual C#** die Option **Klassenbibliothek** aus. Geben Sie `ClaimsTransformation` ein, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="407f9-145">In the **Add New Project** window, select **Class Library** from the **Visual C#** templates list, enter `ClaimsTransformation`, and then press **OK**.</span></span> <span data-ttu-id="407f9-146">Das neue Projekt wird im Projektmappenordner erstellt.</span><span class="sxs-lookup"><span data-stu-id="407f9-146">The new project will be created in your solution folder.</span></span>  
  
3. <span data-ttu-id="407f9-147">Klicken Sie mit der rechten Maustaste unter dem Projekt **ClaimsTransformation** auf **Verweise**, und klicken Sie dann auf **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="407f9-147">Right-click on **References** under the **ClaimsTransformation** project, and then click **Add Reference**.</span></span>  
  
4. <span data-ttu-id="407f9-148">Wählen Sie im Fenster **Verweis-Manager** die Option **System.IdentityModel** aus, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="407f9-148">In the **Reference Manager** window, select **System.IdentityModel**, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="407f9-149">Öffnen Sie, sofern vorhanden, **Class1.cs**. Andernfalls klicken Sie mit der rechten Maustaste auf **ClaimsTransformation**, und klicken Sie anschließend auf **Hinzufügen** und **Class...** (Klasse...).</span><span class="sxs-lookup"><span data-stu-id="407f9-149">Open **Class1.cs**, or if it doesn’t exist, right-click **ClaimsTransformation**, click **Add**, then click **Class…**</span></span>  
  
6. <span data-ttu-id="407f9-150">Fügen Sie der Codedatei die folgenden using-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="407f9-150">Add the following using directives to the code file:</span></span>  
  
    ```csharp  
    using System.Security.Claims;  
    using System.Security.Principal;  
    ```  
  
7. <span data-ttu-id="407f9-151">Fügen Sie in der Codedatei die folgende Klasse und Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="407f9-151">Add the following class and method in the code file.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="407f9-152">Der folgende Code dient nur der Veranschaulichung. Überprüfen Sie Ihre beabsichtigten Berechtigungen im Produktionscode.</span><span class="sxs-lookup"><span data-stu-id="407f9-152">The following code is for demonstration purposes only; make sure that you verify your intended permissions in production code.</span></span>  
  
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
  
8. <span data-ttu-id="407f9-153">Speichern Sie die Datei, und erstellen Sie das Projekt **ClaimsTransformation**.</span><span class="sxs-lookup"><span data-stu-id="407f9-153">Save the file and build the **ClaimsTransformation** project.</span></span>  
  
9. <span data-ttu-id="407f9-154">Klicken Sie mit der rechten Maustaste in Ihrem ASP.NET-Projekt **TestApp** auf „Verweise“, und klicken Sie anschließend auf **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="407f9-154">In your **TestApp** ASP.NET project, right-click on References, and then click **Add Reference**.</span></span>  
  
10. <span data-ttu-id="407f9-155">Wählen Sie im Fenster **Verweis-Manager** im linken Menü die Option **Projektmappe** aus. Wählen Sie aus den aufgefüllten Optionen die Option **ClaimsTransformation** aus, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="407f9-155">In the **Reference Manager** window, select **Solution** from the left menu, select **ClaimsTransformation** from the populated options, and then click **OK**.</span></span>  
  
11. <span data-ttu-id="407f9-156">Gehen Sie in der Stammdatei **Web.config** zum Eintrag **\<system.identityModel>**.</span><span class="sxs-lookup"><span data-stu-id="407f9-156">In the root **Web.config** file, navigate to the **\<system.identityModel>** entry.</span></span> <span data-ttu-id="407f9-157">Fügen Sie den Elementen **\<identityConfiguration>** die folgende Zeile hinzu, und speichern Sie die Datei:</span><span class="sxs-lookup"><span data-stu-id="407f9-157">Within the **\<identityConfiguration>** elements, add the following line and save the file:</span></span>  
  
    ```xml  
    <claimsAuthenticationManager type="ClaimsTransformation.ClaimsTransformationModule, ClaimsTransformation" />  
    ```  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="407f9-158">Schritt 3: Testen Ihrer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="407f9-158">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="407f9-159">In diesem Schritt testen Sie Ihre ASP.NET Web Forms-Anwendung und überprüfen, ob Ansprüche dargestellt werden, wenn sich ein Benutzer mit der Formularauthentifizierung anmeldet.</span><span class="sxs-lookup"><span data-stu-id="407f9-159">In this step you will test your ASP.NET Web Forms application, and verify that claims are presented when a user signs in with Forms authentication.</span></span>  
  
#### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-forms-authentication"></a><span data-ttu-id="407f9-160">Testen der ASP.NET Web Forms-Anwendung für Ansprüche bei Verwendung der Formularauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="407f9-160">To test your ASP.NET Web Forms application for claims using Forms authentication</span></span>  
  
1. <span data-ttu-id="407f9-161">Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="407f9-161">Press **F5** to build and run the application.</span></span> <span data-ttu-id="407f9-162">Es sollte *Default.aspx* dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="407f9-162">You should be presented with *Default.aspx*.</span></span>  
  
2. <span data-ttu-id="407f9-163">Auf der Seite *Default.aspx* sollte unter der Überschrift **Your Claims** (Ihre Ansprüche) eine Tabelle angezeigt werden, die die Anspruchsinformationen **Issuer** (Aussteller), **OriginalIssuer** (Originalaussteller), **Type** (Typ), **Value** (Wert) und **ValueType** (Werttyp) Ihres Kontos enthält.</span><span class="sxs-lookup"><span data-stu-id="407f9-163">On the *Default.aspx* page, you should see a table beneath the **Your Claims** heading that includes the **Issuer**, **OriginalIssuer**, **Type**, **Value**, and **ValueType** claims information about your account.</span></span> <span data-ttu-id="407f9-164">Die letzte Zeile sollte folgendermaßen dargestellt werden:</span><span class="sxs-lookup"><span data-stu-id="407f9-164">The last row should be presented in the following way:</span></span>  
  
    ||||||  
    |-|-|-|-|-|  
    |<span data-ttu-id="407f9-165">LOKALE AUTORITÄT</span><span class="sxs-lookup"><span data-stu-id="407f9-165">LOCAL AUTHORITY</span></span>|<span data-ttu-id="407f9-166">LOKALE AUTORITÄT</span><span class="sxs-lookup"><span data-stu-id="407f9-166">LOCAL AUTHORITY</span></span>|`http://schemas.microsoft.com/ws/2008/06/identity/claims/role`|<span data-ttu-id="407f9-167">Admin</span><span class="sxs-lookup"><span data-stu-id="407f9-167">Admin</span></span>|<https://www.w3.org/2001/XMLSchema#string>|

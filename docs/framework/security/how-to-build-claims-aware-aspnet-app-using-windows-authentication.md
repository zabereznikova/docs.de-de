---
title: 'Vorgehensweise: Erstellen einer Ansprüche unterstützenden ASP.NET-Anwendung mit Windows-Authentifizierung'
ms.date: 03/30/2017
ms.assetid: 11c53d9d-d34a-44b4-8b5e-22e3eaeaee93
author: BrucePerlerMS
ms.openlocfilehash: 48b1b4715e9e2613757a981ba692d84ad06a1ec6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59767967"
---
# <a name="how-to-build-claims-aware-aspnet-application-using-windows-authentication"></a><span data-ttu-id="84b8e-102">Vorgehensweise: Erstellen einer Ansprüche unterstützenden ASP.NET-Anwendung mit Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="84b8e-102">How To: Build Claims-Aware ASP.NET Application Using Windows Authentication</span></span>
## <a name="applies-to"></a><span data-ttu-id="84b8e-103">Gilt für</span><span class="sxs-lookup"><span data-stu-id="84b8e-103">Applies To</span></span>  
  
-   <span data-ttu-id="84b8e-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="84b8e-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="84b8e-105">ASP.NET® Web Forms</span><span class="sxs-lookup"><span data-stu-id="84b8e-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="84b8e-106">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="84b8e-106">Summary</span></span>  
 <span data-ttu-id="84b8e-107">In dieser Vorgehensweise werden ausführliche Prozeduren zum Erstellen einer einfachen Ansprüche unterstützenden ASP.NET Web Forms-Anwendung, die Windows-Authentifizierung verwendet, vorgestellt.</span><span class="sxs-lookup"><span data-stu-id="84b8e-107">This How-To provides detailed step-by-step procedures for creating a simple claims-aware ASP.NET Web Forms application that uses Windows authentication.</span></span> <span data-ttu-id="84b8e-108">Sie enthält auch Anweisungen zum Testen der Anwendung, mit denen überprüft werden kann, ob Ansprüche dargestellt werden, wenn sich ein Benutzer mit der Windows-Authentifizierung anmeldet.</span><span class="sxs-lookup"><span data-stu-id="84b8e-108">It also provides instructions for how to test the application to verify that claims are presented when a user signs in using Windows authentication.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="84b8e-109">Inhalt</span><span class="sxs-lookup"><span data-stu-id="84b8e-109">Contents</span></span>  
  
-   <span data-ttu-id="84b8e-110">Ziele</span><span class="sxs-lookup"><span data-stu-id="84b8e-110">Objectives</span></span>  
  
-   <span data-ttu-id="84b8e-111">Übersicht</span><span class="sxs-lookup"><span data-stu-id="84b8e-111">Overview</span></span>  
  
-   <span data-ttu-id="84b8e-112">Zusammenfassung von Schritten</span><span class="sxs-lookup"><span data-stu-id="84b8e-112">Summary of Steps</span></span>  
  
-   <span data-ttu-id="84b8e-113">Schritt 1: Erstellen einer einfachen ASP.NET Web Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="84b8e-113">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="84b8e-114">Schritt 2: Konfigurieren der ASP.NET Web Forms-Anwendung für Ansprüche bei Verwendung der Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="84b8e-114">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Windows Authentication</span></span>  
  
-   <span data-ttu-id="84b8e-115">Schritt 3: Testen Ihrer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="84b8e-115">Step 3 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="84b8e-116">Ziele</span><span class="sxs-lookup"><span data-stu-id="84b8e-116">Objectives</span></span>  
  
-   <span data-ttu-id="84b8e-117">Konfigurieren einer ASP.NET Web Forms-Anwendung für Ansprüche bei Verwendung der Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="84b8e-117">Configure an ASP.NET Web Forms application for claims using Windows authentication</span></span>  
  
-   <span data-ttu-id="84b8e-118">Testen Sie die ASP.NET Web Forms-Anwendung, um festzustellen, ob sie ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="84b8e-118">Test the ASP.NET Web Forms application to see if it is working properly</span></span>  
  
## <a name="overview"></a><span data-ttu-id="84b8e-119">Übersicht</span><span class="sxs-lookup"><span data-stu-id="84b8e-119">Overview</span></span>  
 <span data-ttu-id="84b8e-120">In .NET 4.5 wurden WIF und seine anspruchsbasierte Autorisierung als wesentlicher Bestandteil in das Framework integriert.</span><span class="sxs-lookup"><span data-stu-id="84b8e-120">In .NET 4.5, WIF and its claims-based authorization have been included as an integral part of the Framework.</span></span> <span data-ttu-id="84b8e-121">Wenn Sie zuvor die Ansprüche eines ASP.NET-Benutzers abrufen wollten, war es erforderlich, WIF zu installieren und anschließend Schnittstellen in Principal-Objekte wie `Thread.CurrentPrincipal` oder `HttpContext.Current.User` umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="84b8e-121">Previously, if you wanted claims from an ASP.NET user, you were required to install WIF, and then cast interfaces to Principal objects such as `Thread.CurrentPrincipal` or `HttpContext.Current.User`.</span></span> <span data-ttu-id="84b8e-122">Nun werden Ansprüche automatisch von diesen Principal-Objekten verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="84b8e-122">Now, claims are served automatically by these Principal objects.</span></span>  
  
 <span data-ttu-id="84b8e-123">Die Windows-Authentifizierung profitiert von der Integration von WIF in .NET 4.5, da allen Benutzern, die über Windows-Anmeldeinformationen authentifiziert wurden, automatisch Ansprüche zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="84b8e-123">Windows authentication has benefited from WIF’s inclusion in .NET 4.5 because all users authenticated by Windows credentials automatically have claims associated with them.</span></span> <span data-ttu-id="84b8e-124">Sie können diese Ansprüche sofort in einer ASP.NET-Anwendung verwenden, die die Windows-Authentifizierung verwendet. Dies wird in dieser Vorgehensweise veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="84b8e-124">You can begin using these claims immediately in an ASP.NET application that uses Windows authentication, as this How-To demonstrates.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="84b8e-125">Zusammenfassung von Schritten</span><span class="sxs-lookup"><span data-stu-id="84b8e-125">Summary of Steps</span></span>  
  
-   <span data-ttu-id="84b8e-126">Schritt 1: Erstellen einer einfachen ASP.NET Web Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="84b8e-126">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="84b8e-127">Schritt 2: Konfigurieren der ASP.NET Web Forms-Anwendung für Ansprüche bei Verwendung der Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="84b8e-127">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Windows Authentication</span></span>  
  
-   <span data-ttu-id="84b8e-128">Schritt 3: Testen Ihrer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="84b8e-128">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a><span data-ttu-id="84b8e-129">Schritt 1: Erstellen einer einfachen ASP.NET Web Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="84b8e-129">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
 <span data-ttu-id="84b8e-130">In diesem Schritt erstellen Sie eine neue ASP.NET Web Forms-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="84b8e-130">In this step, you will create a new ASP.NET Web Forms application.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="84b8e-131">So erstellen Sie eine einfache ASP.NET-Anwendung</span><span class="sxs-lookup"><span data-stu-id="84b8e-131">To create a simple ASP.NET application</span></span>  
  
1. <span data-ttu-id="84b8e-132">Starten Sie Visual Studio, klicken Sie auf **Datei**, **Neu**, und klicken Sie dann auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="84b8e-132">Start Visual Studio, then click **File**, **New**, and then **Project**.</span></span>  
  
2. <span data-ttu-id="84b8e-133">Klicken Sie im Fenster **Neues Projekt** auf **ASP.NET Web Forms-Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="84b8e-133">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3. <span data-ttu-id="84b8e-134">Geben Sie im Feld **Name** die Zeichenfolge `TestApp` ein, und drücken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="84b8e-134">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
4. <span data-ttu-id="84b8e-135">Klicken Sie im **Projektmappen-Explorer** auf das Projekt **TestApp**, nachdem Sie dieses erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="84b8e-135">After the **TestApp** project has been created, click on it in **Solution Explorer**.</span></span> <span data-ttu-id="84b8e-136">Die Eigenschaften des Projekts werden im Bereich **Eigenschaften** unter dem **Projektmappen-Explorer** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="84b8e-136">The project’s properties will appear in the **Properties** pane below **Solution Explorer**.</span></span> <span data-ttu-id="84b8e-137">Legen Sie die Eigenschaft **Windows-Authentifizierung** auf **Aktiviert** fest.</span><span class="sxs-lookup"><span data-stu-id="84b8e-137">Set the **Windows Authentication** property to **Enabled**.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="84b8e-138">Die Windows-Authentifizierung ist standardmäßig für neue ASP.NET-Anwendungen deaktiviert, sodass Sie sie manuell aktivieren müssen.</span><span class="sxs-lookup"><span data-stu-id="84b8e-138">Windows authentication is disabled by default in new ASP.NET applications, so you must manually enable it.</span></span>  
  
## <a name="step-2--configure-aspnet-web-forms-application-for-claims-using-windows-authentication"></a><span data-ttu-id="84b8e-139">Schritt 2: Konfigurieren der ASP.NET Web Forms-Anwendung für Ansprüche bei Verwendung der Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="84b8e-139">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Windows Authentication</span></span>  
 <span data-ttu-id="84b8e-140">In diesem Schritt fügen Sie einen Konfigurationseintrag zur Konfigurationsdatei *Web.config* hinzu und ändern die Datei *Default.aspx*, damit diese die Informationen zu den Ansprüchen eines Kontos anzeigt.</span><span class="sxs-lookup"><span data-stu-id="84b8e-140">In this step you will add a configuration entry to the *Web.config* configuration file and modify the *Default.aspx* file to display claims information for an account.</span></span>  
  
#### <a name="to-configure-aspnet-application-for-claims-using-windows-authentication"></a><span data-ttu-id="84b8e-141">Konfigurieren einer ASP.NET-Anwendung für Ansprüche bei Verwendung der Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="84b8e-141">To configure ASP.NET application for claims using Windows authentication</span></span>  
  
1. <span data-ttu-id="84b8e-142">Ersetzen Sie in der Datei *Default.aspx* des Projekts **TestApp** das vorhandene Markup durch das folgende Markup:</span><span class="sxs-lookup"><span data-stu-id="84b8e-142">In the **TestApp** project’s *Default.aspx* file, replace the existing markup with the following:</span></span>  
  
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
  
     <span data-ttu-id="84b8e-143">In diesem Schritt wird eine „GridView“-Steuerung zu Ihrer Seite *Default.aspx* hinzugefügt, die mit den Ansprüchen aufgefüllt wird, die von der Windows-Authentifizierung abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="84b8e-143">This step adds a GridView control to your *Default.aspx* page that will be populated with the claims retrieved from Windows authentication.</span></span>  
  
2. <span data-ttu-id="84b8e-144">Speichern Sie die Datei *Default.aspx*, und öffnen Sie dann die CodeBehind-Datei *Default.aspx.cs*.</span><span class="sxs-lookup"><span data-stu-id="84b8e-144">Save the *Default.aspx* file, then open its code-behind file named *Default.aspx.cs*.</span></span> <span data-ttu-id="84b8e-145">Ersetzen Sie den vorhandenen Code durch folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="84b8e-145">Replace the existing code with the following:</span></span>  
  
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
  
     <span data-ttu-id="84b8e-146">Der obige Code zeigt die Ansprüche eines authentifizierten Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="84b8e-146">The above code will display claims about an authenticated user.</span></span>  
  
3. <span data-ttu-id="84b8e-147">Modifizieren Sie zum Ändern des Authentifizierungstyps einer Anwendung den Block **\<authentication>** im Abschnitt **\<system.web>** der Stammdatei des Projekts (*Web.config*), sodass diese nur den folgenden Konfigurationseintrag enthält:</span><span class="sxs-lookup"><span data-stu-id="84b8e-147">To change the application’s authentication type, modify the **\<authentication>** block in the **\<system.web>** section of the project’s root *Web.config* file so that it only includes the following configuration entry:</span></span>  
  
    ```xml  
    <authentication mode="Windows" />  
    ```  
  
4. <span data-ttu-id="84b8e-148">Ändern Sie abschließend den Block **\<authorization>** im Abschnitt **\<system.web>** derselben *Web.config*-Datei, um die Authentifizierung zu erzwingen:</span><span class="sxs-lookup"><span data-stu-id="84b8e-148">Finally, modify the **\<authorization>** block in the **\<system.web>** section of the same *Web.config* file to force authentication:</span></span>  
  
    ```xml  
    <authorization>  
        <deny users="?" />  
    </authorization>  
    ```  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="84b8e-149">Schritt 3: Testen Ihrer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="84b8e-149">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="84b8e-150">In diesem Schritt testen Sie Ihre ASP.NET Web Forms-Anwendung und überprüfen, ob Ansprüche dargestellt werden, wenn sich ein Benutzer mit der Windows-Authentifizierung anmeldet.</span><span class="sxs-lookup"><span data-stu-id="84b8e-150">In this step you will test your ASP.NET Web Forms application, and verify that claims are presented when a user signs in with Windows authentication.</span></span>  
  
#### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-windows-authentication"></a><span data-ttu-id="84b8e-151">Testen der ASP.NET Web Forms-Anwendung für Ansprüche bei Verwendung der Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="84b8e-151">To test your ASP.NET Web Forms application for claims using Windows authentication</span></span>  
  
1. <span data-ttu-id="84b8e-152">Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="84b8e-152">Press **F5** to build and run the application.</span></span> <span data-ttu-id="84b8e-153">Ihnen sollte *Default.aspx* angezeigt werden, und Ihr Windows-Kontoname (einschließlich des Domänennamens) sollte bereits als der authentifizierte Benutzer oben rechts auf der Seite angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="84b8e-153">You should be presented with *Default.aspx*, and your Windows account name (including domain name) should already appear as the authenticated user in the top right of the page.</span></span> <span data-ttu-id="84b8e-154">Die Seite sollte eine Tabelle enthalten, die mit den Ansprüchen gefüllt ist, die von Ihrem Windows-Konto abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="84b8e-154">The page’s content should include a table filled with claims retrieved from your Windows account.</span></span>

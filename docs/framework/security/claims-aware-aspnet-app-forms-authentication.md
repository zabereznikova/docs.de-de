---
title: 'Gewusst wie: Erstellen einer Ansprüche unterstützenden ASP.NET-Anwendung mit formularbasierter Authentifizierung'
ms.date: 03/30/2017
ms.assetid: 98a3e029-1a9b-4e0c-b5d0-29d3f23f5b15
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 851a856d291da78265e9eac73e9e06028e24ef2e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33408618"
---
# <a name="how-to-build-claims-aware-aspnet-application-using-forms-based-authentication"></a><span data-ttu-id="a3549-102">Gewusst wie: Erstellen einer Ansprüche unterstützenden ASP.NET-Anwendung mit formularbasierter Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="a3549-102">How To: Build Claims-Aware ASP.NET Application Using Forms-Based Authentication</span></span>
## <a name="applies-to"></a><span data-ttu-id="a3549-103">Gilt für</span><span class="sxs-lookup"><span data-stu-id="a3549-103">Applies To</span></span>  
  
-   <span data-ttu-id="a3549-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="a3549-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="a3549-105">ASP.NET® Web Forms</span><span class="sxs-lookup"><span data-stu-id="a3549-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="a3549-106">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="a3549-106">Summary</span></span>  
 <span data-ttu-id="a3549-107">In dieser Vorgehensweise werden ausführliche Prozeduren zum Erstellen einer einfachen Ansprüche unterstützenden ASP.NET Web Forms-Anwendung, die Formularauthentifizierung verwendet, vorgestellt.</span><span class="sxs-lookup"><span data-stu-id="a3549-107">This How-To provides detailed step-by-step procedures for creating a simple claims-aware ASP.NET Web Forms application that uses Forms authentication.</span></span> <span data-ttu-id="a3549-108">Sie enthält auch Anweisungen zum Testen der Anwendung, mit denen überprüft werden kann, ob Ansprüche dargestellt werden, wenn sich ein Benutzer mit der Formularauthentifizierung anmeldet.</span><span class="sxs-lookup"><span data-stu-id="a3549-108">It also provides instructions for how to test the application to verify that claims are presented when a user signs in with Forms authentication.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="a3549-109">Inhalt</span><span class="sxs-lookup"><span data-stu-id="a3549-109">Contents</span></span>  
  
-   <span data-ttu-id="a3549-110">Ziele</span><span class="sxs-lookup"><span data-stu-id="a3549-110">Objectives</span></span>  
  
-   <span data-ttu-id="a3549-111">Übersicht</span><span class="sxs-lookup"><span data-stu-id="a3549-111">Overview</span></span>  
  
-   <span data-ttu-id="a3549-112">Zusammenfassung von Schritten</span><span class="sxs-lookup"><span data-stu-id="a3549-112">Summary of Steps</span></span>  
  
-   <span data-ttu-id="a3549-113">Schritt 1: Erstellen einer einfachen ASP.NET Web Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="a3549-113">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="a3549-114">Schritt 2: Konfigurieren der ASP.NET Web Forms-Anwendung für Ansprüche bei Verwendung der Formularauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="a3549-114">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Forms Authentication</span></span>  
  
-   <span data-ttu-id="a3549-115">Schritt 3: Testen Ihrer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="a3549-115">Step 3 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="a3549-116">Ziele</span><span class="sxs-lookup"><span data-stu-id="a3549-116">Objectives</span></span>  
  
-   <span data-ttu-id="a3549-117">Konfigurieren einer ASP.NET Web Forms-Anwendung für Ansprüche bei Verwendung der Formularauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="a3549-117">Configure an ASP.NET Web Forms application for claims using Forms authentication</span></span>  
  
-   <span data-ttu-id="a3549-118">Testen Sie die ASP.NET Web Forms-Anwendung, um festzustellen, ob sie ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="a3549-118">Test the ASP.NET Web Forms application to see if it is working properly</span></span>  
  
## <a name="overview"></a><span data-ttu-id="a3549-119">Übersicht</span><span class="sxs-lookup"><span data-stu-id="a3549-119">Overview</span></span>  
 <span data-ttu-id="a3549-120">In .NET 4.5 wurden WIF und seine anspruchsbasierte Autorisierung als wesentlicher Bestandteil in das Framework integriert.</span><span class="sxs-lookup"><span data-stu-id="a3549-120">In .NET 4.5, WIF and its claims-based authorization have been included as an integral part of the Framework.</span></span> <span data-ttu-id="a3549-121">Wenn Sie zuvor die Ansprüche eines ASP.NET-Benutzers abrufen wollten, war es erforderlich, WIF zu installieren und anschließend Schnittstellen in Principal-Objekte wie `Thread.CurrentPrincipal` oder `HttpContext.Current.User` umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="a3549-121">Previously, if you wanted claims from an ASP.NET user, you were required to install WIF, and then cast interfaces to Principal objects such as `Thread.CurrentPrincipal` or `HttpContext.Current.User`.</span></span> <span data-ttu-id="a3549-122">Nun werden Ansprüche automatisch von diesen Principal-Objekten verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="a3549-122">Now, claims are served automatically by these Principal objects.</span></span>  
  
 <span data-ttu-id="a3549-123">Die Formularauthentifizierung profitiert von der Integration von WIF in .NET 4.5, da allen Benutzern, die über Formularauthentifizierung authentifiziert wurden, automatisch Ansprüche zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="a3549-123">Forms authentication has benefited from WIF’s inclusion in .NET 4.5 because all users authenticated by Forms automatically have claims associated with them.</span></span> <span data-ttu-id="a3549-124">Sie können diese Ansprüche sofort in einer ASP.NET-Anwendung verwenden, die die Formularauthentifizierung verwendet. Dies wird in dieser Vorgehensweise veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a3549-124">You can begin using these claims immediately in an ASP.NET application that uses Forms authentication, as this How-To demonstrates.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="a3549-125">Zusammenfassung von Schritten</span><span class="sxs-lookup"><span data-stu-id="a3549-125">Summary of Steps</span></span>  
  
-   <span data-ttu-id="a3549-126">Schritt 1: Erstellen einer einfachen ASP.NET Web Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="a3549-126">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
-   <span data-ttu-id="a3549-127">Schritt 2: Konfigurieren der ASP.NET Web Forms-Anwendung für Ansprüche bei Verwendung der Formularauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="a3549-127">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Forms Authentication</span></span>  
  
-   <span data-ttu-id="a3549-128">Schritt 3: Testen Ihrer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="a3549-128">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a><span data-ttu-id="a3549-129">Schritt 1: Erstellen einer einfachen ASP.NET Web Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="a3549-129">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
 <span data-ttu-id="a3549-130">In diesem Schritt erstellen Sie eine neue ASP.NET Web Forms-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a3549-130">In this step, you will create a new ASP.NET Web Forms application.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="a3549-131">So erstellen Sie eine einfache ASP.NET-Anwendung</span><span class="sxs-lookup"><span data-stu-id="a3549-131">To create a simple ASP.NET application</span></span>  
  
1.  <span data-ttu-id="a3549-132">Starten Sie Visual Studio, und klicken Sie auf **Datei**, **Neu** und anschließend auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="a3549-132">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2.  <span data-ttu-id="a3549-133">Klicken Sie im Fenster **Neues Projekt** auf **ASP.NET Web Forms-Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="a3549-133">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3.  <span data-ttu-id="a3549-134">Geben Sie im Feld **Name** die Zeichenfolge `TestApp` ein, und drücken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a3549-134">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
## <a name="step-2--configure-aspnet-web-forms-application-for-claims-using-forms-authentication"></a><span data-ttu-id="a3549-135">Schritt 2: Konfigurieren der ASP.NET Web Forms-Anwendung für Ansprüche bei Verwendung der Formularauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="a3549-135">Step 2 – Configure ASP.NET Web Forms Application for Claims Using Forms Authentication</span></span>  
 <span data-ttu-id="a3549-136">In diesem Schritt fügen Sie einen Konfigurationseintrag zur Konfigurationsdatei *Web.config* hinzu und bearbeiten die Datei *Default.aspx*, damit diese die Informationen zu den Ansprüchen eines Kontos anzeigt.</span><span class="sxs-lookup"><span data-stu-id="a3549-136">In this step you will add a configuration entry to the *Web.config* configuration file and edit the *Default.aspx* file to display claims information for an account.</span></span>  
  
#### <a name="to-configure-aspnet-application-for-claims-using-forms-authentication"></a><span data-ttu-id="a3549-137">Konfigurieren einer ASP.NET-Anwendung für Ansprüche bei Verwendung der Formularauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="a3549-137">To configure ASP.NET application for claims using Forms authentication</span></span>  
  
1.  <span data-ttu-id="a3549-138">Ersetzten Sie das vorhandene Markup in der Datei *Default.aspx* durch das folgende Markup:</span><span class="sxs-lookup"><span data-stu-id="a3549-138">In the *Default.aspx* file, replace the existing markup with the following:</span></span>  
  
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
  
     <span data-ttu-id="a3549-139">In diesem Schritt wird eine „GridView“-Steuerung zu Ihrer Seite *Default.aspx* hinzugefügt, die mit den Ansprüchen aufgefüllt wird, die von der Formularauthentifizierung abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="a3549-139">This step adds a GridView control to your *Default.aspx* page that will be populated with the claims retrieved from Forms authentication.</span></span>  
  
2.  <span data-ttu-id="a3549-140">Speichern Sie die Datei *Default.aspx*, und öffnen Sie dann die CodeBehind-Datei *Default.aspx.cs*.</span><span class="sxs-lookup"><span data-stu-id="a3549-140">Save the *Default.aspx* file, then open its code-behind file named *Default.aspx.cs*.</span></span> <span data-ttu-id="a3549-141">Ersetzen Sie den vorhandenen Code durch folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="a3549-141">Replace the existing code with the following:</span></span>  
  
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
  
     <span data-ttu-id="a3549-142">Der obige Code zeigt die Ansprüche bezüglich eines authentifizierten Benutzers, einschließlich Benutzer, die durch die Formularauthentifizierung identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="a3549-142">The above code will display claims about an authenticated user, including users identified by Forms authentication.</span></span>  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="a3549-143">Schritt 3: Testen Ihrer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="a3549-143">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="a3549-144">In diesem Schritt testen Sie Ihre ASP.NET Web Forms-Anwendung und überprüfen, ob Ansprüche dargestellt werden, wenn sich ein Benutzer mit der Formularauthentifizierung anmeldet.</span><span class="sxs-lookup"><span data-stu-id="a3549-144">In this step you will test your ASP.NET Web Forms application, and verify that claims are presented when a user signs in with Forms authentication.</span></span>  
  
#### <a name="to-test-your-aspnet-web-forms-application-for-claims-using-forms-authentication"></a><span data-ttu-id="a3549-145">Testen der ASP.NET Web Forms-Anwendung für Ansprüche bei Verwendung der Formularauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="a3549-145">To test your ASP.NET Web Forms application for claims using Forms authentication</span></span>  
  
1.  <span data-ttu-id="a3549-146">Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a3549-146">Press **F5** to build and run the application.</span></span> <span data-ttu-id="a3549-147">*Default.aspx* sollte mit den Links **Registrieren** und **Anmelden** rechts oben auf der Seite angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a3549-147">You should be presented with *Default.aspx*, which has **Register** and **Log in** links in the top right of the page.</span></span> <span data-ttu-id="a3549-148">Klicken Sie auf **Registrieren**.</span><span class="sxs-lookup"><span data-stu-id="a3549-148">Click **Register**.</span></span>  
  
2.  <span data-ttu-id="a3549-149">Erstellen Sie auf der Seite **Registrieren** ein Benutzerkonto, und klicken Sie dann auf **Registrieren**.</span><span class="sxs-lookup"><span data-stu-id="a3549-149">On the **Register** page, create a user account, and then click **Register**.</span></span> <span data-ttu-id="a3549-150">Ihr Konto wird unter Verwendung der Formularauthentifizierung erstellt, und Sie werden automatisch angemeldet.</span><span class="sxs-lookup"><span data-stu-id="a3549-150">Your account will be created using Forms authentication, and you will be automatically signed in.</span></span>  
  
3.  <span data-ttu-id="a3549-151">Nachdem Sie zur Startseite umgeleitet werden, sollte unter der Überschrift **Ihre Ansprüche** eine Tabelle angezeigt werden, die die Anspruchsinformationen **Aussteller**, **Originalaussteller**, **Typ**, **Welt** und **Werttyp** Ihres Kontos enthält.</span><span class="sxs-lookup"><span data-stu-id="a3549-151">After you have been redirected to the home page, you should see a table beneath the **Your Claims** heading that includes the **Issuer**, **OriginalIssuer**, **Type**, **Value**, and **ValueType** claims information about your account.</span></span>

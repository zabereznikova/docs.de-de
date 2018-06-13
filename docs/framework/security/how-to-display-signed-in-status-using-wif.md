---
title: 'Gewusst wie: Anzeigen des Anmeldestatus mit WIF'
ms.date: 03/30/2017
ms.assetid: 4d1174e4-5397-4962-9a5f-3b1ad7b3fc14
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 53ef5e8b3fae976bacff3be9a50c323a22aef0e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33398917"
---
# <a name="how-to-display-signed-in-status-using-wif"></a><span data-ttu-id="91a07-102">Gewusst wie: Anzeigen des Anmeldestatus mit WIF</span><span class="sxs-lookup"><span data-stu-id="91a07-102">How To: Display Signed In Status Using WIF</span></span>
## <a name="applies-to"></a><span data-ttu-id="91a07-103">Gilt für</span><span class="sxs-lookup"><span data-stu-id="91a07-103">Applies To</span></span>  
  
-   <span data-ttu-id="91a07-104">Microsoft® Windows® Identity Foundation (WIF) 4.5</span><span class="sxs-lookup"><span data-stu-id="91a07-104">Microsoft® Windows® Identity Foundation (WIF) 4.5</span></span>  
  
-   <span data-ttu-id="91a07-105">ASP.NET® Web Forms</span><span class="sxs-lookup"><span data-stu-id="91a07-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="91a07-106">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="91a07-106">Summary</span></span>  
 <span data-ttu-id="91a07-107">In diesem Thema wird beschrieben, wie der Anmeldestatus in einer WIF-aktivierten ASP.NET-Anwendung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="91a07-107">This topic describes how to display the sign in status in a WIF-enabled ASP.NET application.</span></span> <span data-ttu-id="91a07-108">WIF bietet den Mechanismus, um die Anwendung für die Anspruchsunterstützung kompatibel zu machen sowie die Authentifizierung und Autorisierung für Anwendungsressourcen zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="91a07-108">WIF provides the mechanism for making your application claims-aware, and managing authentication and authorization for application resources.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="91a07-109">Inhalt</span><span class="sxs-lookup"><span data-stu-id="91a07-109">Contents</span></span>  
  
-   <span data-ttu-id="91a07-110">Übersicht</span><span class="sxs-lookup"><span data-stu-id="91a07-110">Overview</span></span>  
  
-   <span data-ttu-id="91a07-111">Zusammenfassung von Schritten</span><span class="sxs-lookup"><span data-stu-id="91a07-111">Summary of Steps</span></span>  
  
-   <span data-ttu-id="91a07-112">Schritt 1: Einrichten der Identitäts- und Zugriffserweiterung</span><span class="sxs-lookup"><span data-stu-id="91a07-112">Step 1 – Install the Identity and Access Extension</span></span>  
  
-   <span data-ttu-id="91a07-113">Schritt 2: Erstellen einer abhängigen Seite der ASP.NET-Anwendung</span><span class="sxs-lookup"><span data-stu-id="91a07-113">Step 2 – Create a Relying Party ASP.NET Application</span></span>  
  
-   <span data-ttu-id="91a07-114">Schritt 3: Aktivieren des lokalen Entwicklungs-STS zur Authentifizierung von Benutzern</span><span class="sxs-lookup"><span data-stu-id="91a07-114">Step 3 – Enable Local Development STS to Authenticate Users</span></span>  
  
-   <span data-ttu-id="91a07-115">Schritt 4: Ändern der ASP.NET-Anwendung zum Anzeigen des Anmeldestatus</span><span class="sxs-lookup"><span data-stu-id="91a07-115">Step 4 – Modify Your ASP.NET Application to Display Sign In Status</span></span>  
  
-   <span data-ttu-id="91a07-116">Schritt 5: Testen der Integration zwischen WIF und der ASP.NET-Anwendung</span><span class="sxs-lookup"><span data-stu-id="91a07-116">Step 5 – Test the Integration Between WIF and Your ASP.NET Application</span></span>  
  
## <a name="overview"></a><span data-ttu-id="91a07-117">Übersicht</span><span class="sxs-lookup"><span data-stu-id="91a07-117">Overview</span></span>  
 <span data-ttu-id="91a07-118">Dieses Thema veranschaulicht, wie eine einfache Ansprüche unterstützende Anwendung mithilfe von WIF erstellt und wie leicht angezeigt wird, ob ein Benutzer angemeldet ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="91a07-118">This topic demonstrates how to create a simple claims-aware application using WIF and how to easily display whether a user is signed in or not.</span></span> <span data-ttu-id="91a07-119">In den folgenden Schritte wird der lokale Entwicklungs-STS verwendet, der in der Identitäts- und Zugriffserweiterung von Visual Studio enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="91a07-119">The following steps use the Local Development STS that is included with the Identity and Access Visual Studio Extension.</span></span> <span data-ttu-id="91a07-120">Der lokale Entwicklungs-STS ist für eine Test- und Entwicklungsumgebung vorgesehen, um eine einfache Methode der Integration von Ansprüchen in die Anwendung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="91a07-120">The Local Development STS is intended for a testing and development environment to provide a simple method of integrating claims into your application.</span></span> <span data-ttu-id="91a07-121">Er sollte nie in einer Produktionsumgebung verwendet werden, da er keine echte Authentifizierung ausführt und Anmeldeinformationen nicht erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="91a07-121">It should never be used in a production environment, as it does not perform real authentication and credentials are not required.</span></span> <span data-ttu-id="91a07-122">Allerdings ist der imperative Code in den folgenden Schritten für eine produktionsbereite Anwendung, die eine echte Authentifizierung verwendet, identisch.</span><span class="sxs-lookup"><span data-stu-id="91a07-122">However, the imperative code in the following steps is the same for a production-ready application using real authentication.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="91a07-123">Zusammenfassung von Schritten</span><span class="sxs-lookup"><span data-stu-id="91a07-123">Summary of Steps</span></span>  
  
-   <span data-ttu-id="91a07-124">Schritt 1: Einrichten der Identitäts- und Zugriffserweiterung</span><span class="sxs-lookup"><span data-stu-id="91a07-124">Step 1 – Install the Identity and Access Extension</span></span>  
  
-   <span data-ttu-id="91a07-125">Schritt 2: Erstellen einer abhängigen Seite der ASP.NET-Anwendung</span><span class="sxs-lookup"><span data-stu-id="91a07-125">Step 2 – Create a Relying Party ASP.NET Application</span></span>  
  
-   <span data-ttu-id="91a07-126">Schritt 3: Aktivieren des lokalen Entwicklungs-STS zur Authentifizierung von Benutzern</span><span class="sxs-lookup"><span data-stu-id="91a07-126">Step 3 – Enable Local Development STS to Authenticate Users</span></span>  
  
-   <span data-ttu-id="91a07-127">Schritt 4: Ändern der ASP.NET-Anwendung zum Anzeigen des Anmeldestatus</span><span class="sxs-lookup"><span data-stu-id="91a07-127">Step 4 – Modify Your ASP.NET Application to Display Sign In Status</span></span>  
  
-   <span data-ttu-id="91a07-128">Schritt 5: Testen der Integration zwischen WIF und der ASP.NET-Anwendung</span><span class="sxs-lookup"><span data-stu-id="91a07-128">Step 5 – Test the Integration Between WIF and Your ASP.NET Application</span></span>  
  
## <a name="step-1--install-the-identity-and-access-extension"></a><span data-ttu-id="91a07-129">Schritt 1: Einrichten der Identitäts- und Zugriffserweiterung</span><span class="sxs-lookup"><span data-stu-id="91a07-129">Step 1 – Install the Identity and Access Extension</span></span>  
 <span data-ttu-id="91a07-130">Dieser Schritt beschreibt, wie die Identitäts- und Zugriffserweiterung in Visual Studio 2012 konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="91a07-130">This step describes how to configure the Identity and Access extension to Visual Studio 2012.</span></span> <span data-ttu-id="91a07-131">Diese Erweiterung automatisiert die Konfiguration der Anwendung, um mit STS-Endpunkten zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="91a07-131">This extension automates the process of configuring your application to communicate with STS endpoints.</span></span>  
  
#### <a name="to-install-the-identity-and-access-extension"></a><span data-ttu-id="91a07-132">So richten Sie die Identitäts- und Zugriffserweiterung ein</span><span class="sxs-lookup"><span data-stu-id="91a07-132">To install the Identity and Access extension</span></span>  
  
1.  <span data-ttu-id="91a07-133">Starten Sie Visual Studio im erweiterten Modus als Administrator.</span><span class="sxs-lookup"><span data-stu-id="91a07-133">Start Visual Studio in elevated mode as administrator.</span></span>  
  
2.  <span data-ttu-id="91a07-134">Klicken Sie in Visual Studio im Menü **Extras** auf **Erweiterungs-Manager**.</span><span class="sxs-lookup"><span data-stu-id="91a07-134">In Visual Studio, click **Tools** and click **Extension Manager**.</span></span> <span data-ttu-id="91a07-135">Das Fenster **Erweiterungs-Manager** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="91a07-135">The **Extension Manager** window appears.</span></span>  
  
3.  <span data-ttu-id="91a07-136">Klicken Sie im **Erweiterungs-Manager** im linken Menü auf **Onlineerweiterungen**, und wählen Sie **Visual Studio Gallery** aus.</span><span class="sxs-lookup"><span data-stu-id="91a07-136">In **Extension Manager**, click **Online Extensions** from the left menu, then select **Visual Studio Gallery**.</span></span>  
  
4.  <span data-ttu-id="91a07-137">Suchen Sie in der rechten oberen Ecke des **Erweiterungs-Managers** nach *Identität und Zugriff*.</span><span class="sxs-lookup"><span data-stu-id="91a07-137">In the top right corner of **Extension Manager**, search for *Identity and Access*.</span></span>  
  
5.  <span data-ttu-id="91a07-138">Das Element **Identität und Zugriff** wird in den Suchergebnissen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="91a07-138">The **Identity and Access** item will appear in the search results.</span></span> <span data-ttu-id="91a07-139">Klicken Sie darauf, und klicken Sie anschließend auf **Herunterladen**.</span><span class="sxs-lookup"><span data-stu-id="91a07-139">Click it, and then click **Download**.</span></span>  
  
6.  <span data-ttu-id="91a07-140">Das Dialogfeld **Herunterladen und installieren** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="91a07-140">The **Download and Install** dialog appears.</span></span> <span data-ttu-id="91a07-141">Wenn Sie den Lizenzbedingungen zustimmen, klicken Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="91a07-141">If you agree with the license terms, click **Install**.</span></span>  
  
7.  <span data-ttu-id="91a07-142">Wenn die Installation der Erweiterung **Identität und Zugriff** abgeschlossen ist, starten Sie Visual Studio im Administratormodus erneut.</span><span class="sxs-lookup"><span data-stu-id="91a07-142">When the **Identity and Access** extension has finished installing, restart Visual Studio in administrator mode.</span></span>  
  
## <a name="step-2--create-a-relying-party-aspnet-application"></a><span data-ttu-id="91a07-143">Schritt 2: Erstellen einer abhängigen Seite der ASP.NET-Anwendung</span><span class="sxs-lookup"><span data-stu-id="91a07-143">Step 2 – Create a Relying Party ASP.NET Application</span></span>  
 <span data-ttu-id="91a07-144">Dieser Schritt beschreibt, wie eine abhängige Seite der ASP.NET Web Forms-Anwendung erstellt wird, die mit WIF integriert wird.</span><span class="sxs-lookup"><span data-stu-id="91a07-144">This step describes how to create a relying party ASP.NET Web Forms application that will integrate with WIF.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="91a07-145">So erstellen Sie eine einfache ASP.NET-Anwendung</span><span class="sxs-lookup"><span data-stu-id="91a07-145">To create a simple ASP.NET application</span></span>  
  
1.  <span data-ttu-id="91a07-146">Starten Sie Visual Studio, und klicken Sie auf **Datei**, **Neu** und anschließend auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="91a07-146">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2.  <span data-ttu-id="91a07-147">Klicken Sie im Fenster **Neues Projekt** auf **ASP.NET Web Forms-Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="91a07-147">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3.  <span data-ttu-id="91a07-148">Geben Sie im Feld **Name** die Zeichenfolge `TestApp` ein, und drücken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="91a07-148">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
## <a name="step-3--enable-local-development-sts-to-authenticate-users"></a><span data-ttu-id="91a07-149">Schritt 3: Aktivieren des lokalen Entwicklungs-STS zur Authentifizierung von Benutzern</span><span class="sxs-lookup"><span data-stu-id="91a07-149">Step 3 – Enable Local Development STS to Authenticate Users</span></span>  
 <span data-ttu-id="91a07-150">Dieser Schritt beschreibt die Aktivierung der lokalen Entwicklungs-STS in der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="91a07-150">This step describes how to enable Local Development STS in your application.</span></span> <span data-ttu-id="91a07-151">Der lokale Entwicklungs-STS wird mithilfe der Identitäts- und Zugriffserweiterung für Visual Studio aktiviert.</span><span class="sxs-lookup"><span data-stu-id="91a07-151">Local Development STS is enabled by using the Identity and Access extension for Visual Studio.</span></span>  
  
#### <a name="to-enable-local-development-sts-in-your-aspnet-application"></a><span data-ttu-id="91a07-152">So aktivieren Sie den lokalen Entwicklungs-STS in der ASP.NET-Anwendung</span><span class="sxs-lookup"><span data-stu-id="91a07-152">To enable Local Development STS in your ASP.NET application</span></span>  
  
1.  <span data-ttu-id="91a07-153">Klicken Sie in Visual Studio mit der rechten Maustaste unter **Projektmappen-Explorer** auf das Projekt **TestApp**, und wählen Sie **Identität und Zugriff** aus.</span><span class="sxs-lookup"><span data-stu-id="91a07-153">In Visual Studio, right-click the **TestApp** project under **Solution Explorer**, then select **Identity and Access**.</span></span>  
  
2.  <span data-ttu-id="91a07-154">Das Fenster **Identität und Zugriff** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="91a07-154">The **Identity and Access** window appears.</span></span> <span data-ttu-id="91a07-155">Klicken Sie unter **Anbieter** auf **Test your application with the Local Development STS** (Anwendung mit dem lokalen Entwicklungs-STS testen), und klicken Sie anschließend auf **Übernehmen**.</span><span class="sxs-lookup"><span data-stu-id="91a07-155">Under **Providers**, select **Test your application with the Local Development STS**, then click **Apply**.</span></span>  
  
## <a name="step-4--modify-your-aspnet-application-to-display-sign-in-status"></a><span data-ttu-id="91a07-156">Schritt 4: Ändern der ASP.NET-Anwendung zum Anzeigen des Anmeldestatus</span><span class="sxs-lookup"><span data-stu-id="91a07-156">Step 4 – Modify Your ASP.NET Application to Display Sign In Status</span></span>  
 <span data-ttu-id="91a07-157">Dieser Schritt beschreibt die Änderung der ASP.NET-Anwendung, um dynamisch anzuzeigen, ob der aktuelle Benutzer angemeldet ist.</span><span class="sxs-lookup"><span data-stu-id="91a07-157">This step describes how to modify your ASP.NET application to dynamically display whether the current user is signed in.</span></span> <span data-ttu-id="91a07-158">Nachdem der STS-Anbieter konfiguriert wurde, behandelt WIF die eingehenden Ansprüche.</span><span class="sxs-lookup"><span data-stu-id="91a07-158">Once your STS provider has been configured, WIF handles the incoming claims.</span></span> <span data-ttu-id="91a07-159">Jetzt müssen Sie den Code der Anwendung konfigurieren, um das Ergebnis der Authentifizierung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="91a07-159">Now you need to configure your application’s code to display the result of the authentication.</span></span>  
  
#### <a name="to-display-sign-in-status"></a><span data-ttu-id="91a07-160">So zeigen Sie den Anmeldestatus an</span><span class="sxs-lookup"><span data-stu-id="91a07-160">To display sign in status</span></span>  
  
1.  <span data-ttu-id="91a07-161">Öffnen Sie in Visual Studio die Datei **Default.aspx** unter dem Projekt **TestApp**.</span><span class="sxs-lookup"><span data-stu-id="91a07-161">In Visual Studio, open the **Default.aspx** file under the **TestApp** project.</span></span>  
  
2.  <span data-ttu-id="91a07-162">Ersetzen Sie das vorhandene Markup in der Datei **Default.aspx** durch das folgende Markup:</span><span class="sxs-lookup"><span data-stu-id="91a07-162">Replace the existing markup in the **Default.aspx** file with the following markup:</span></span>  
  
    ```  
    <%@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="_Default" %>  
  
    <!DOCTYPE html>  
  
    <html>  
    <head runat="server">  
        <title>Logged In Status</title>  
    </head>  
    <body>  
        <asp:label ID="myLabel" runat="server" />  
    </body>  
    </html>  
    ```  
  
3.  <span data-ttu-id="91a07-163">Speichern Sie die Datei **Default.aspx**, und öffnen Sie dann die CodeBehind-Datei **Default.aspx.cs**.</span><span class="sxs-lookup"><span data-stu-id="91a07-163">Save **Default.aspx**, and then open its code behind file named **Default.aspx.cs**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="91a07-164">**Default.aspx.cs** ist möglicherweise im Projektmappen-Explorer unter **Default.aspx** ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="91a07-164">**Default.aspx.cs** may be hidden beneath **Default.aspx** in Solution Explorer.</span></span> <span data-ttu-id="91a07-165">Wenn **Default.aspx.cs** nicht sichtbar ist, erweitern Sie **Default.aspx**, indem Sie auf das Dreieck daneben klicken.</span><span class="sxs-lookup"><span data-stu-id="91a07-165">If **Default.aspx.cs** is not visible, expand **Default.aspx** by clicking on the triangle next to it.</span></span>  
  
4.  <span data-ttu-id="91a07-166">Ersetzen Sie den vorhandenen Code in **Default.aspx.cs** durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="91a07-166">Replace the existing code in **Default.aspx.cs** with the following code:</span></span>  
  
    ```csharp  
    using System;  
    using System.Web.UI;  
    using System.Security.Claims;  
  
    namespace TestApp  
    {  
        protected void Page_Load(object sender, EventArgs e)  
        {  
            ClaimsPrincipal claimsPrincipal = Thread.CurrentPrincipal as ClaimsPrincipal;  
  
            if (claimsPrincipal != null)  
            {  
                myLabel.Text = "You are signed in.";  
            }  
            else  
            {  
                myLabel.Text = "You are not signed in.";  
            }  
        }  
    }  
    ```  
  
5.  <span data-ttu-id="91a07-167">Speichern Sie die CodeBehind-Datei **Default.aspx.cs**, und erstellen Sie die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="91a07-167">Save **Default.aspx.cs**, and build the application.</span></span>  
  
## <a name="step-5--test-the-integration-between-wif-and-your-aspnet-application"></a><span data-ttu-id="91a07-168">Schritt 5: Testen der Integration zwischen WIF und der ASP.NET-Anwendung</span><span class="sxs-lookup"><span data-stu-id="91a07-168">Step 5 – Test the Integration Between WIF and Your ASP.NET Application</span></span>  
 <span data-ttu-id="91a07-169">Dieser Schritt beschreibt, wie Sie die Integration zwischen WIF und der ASP.NET-Anwendung testen können.</span><span class="sxs-lookup"><span data-stu-id="91a07-169">This step describes how you can test the integration between WIF and your ASP.NET application.</span></span>  
  
#### <a name="to-test-the-integration-between-wif-and-aspnet"></a><span data-ttu-id="91a07-170">So testen Sie die Integration zwischen WIF und ASP.NET</span><span class="sxs-lookup"><span data-stu-id="91a07-170">To test the integration between WIF and ASP.NET</span></span>  
  
1.  <span data-ttu-id="91a07-171">Drücken Sie in Visual Studio die **F5**-TASTE, um die Anwendung zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="91a07-171">In Visual Studio, press **F5** to start debugging your application.</span></span> <span data-ttu-id="91a07-172">Wenn keine Fehler gefunden werden, wird ein neues Browserfenster geöffnet.</span><span class="sxs-lookup"><span data-stu-id="91a07-172">If no errors are found, a new browser window will open.</span></span>  
  
2.  <span data-ttu-id="91a07-173">Der Browser leitet möglicherweise die Anforderung automatisch an den STS um und öffnet dann die Seite "Default.aspx".</span><span class="sxs-lookup"><span data-stu-id="91a07-173">You may notice that the browser silently redirects your request to the STS, and then opens the Default.aspx page.</span></span> <span data-ttu-id="91a07-174">Wenn WIF ordnungsgemäß konfiguriert wurde, wird auf der Website der folgende Text angezeigt: **„Sie sind angemeldet“**.</span><span class="sxs-lookup"><span data-stu-id="91a07-174">If WIF is properly configured, you should see the site display the following text: **"You are signed in"**.</span></span>

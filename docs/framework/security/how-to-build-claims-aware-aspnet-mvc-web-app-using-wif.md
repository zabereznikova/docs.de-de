---
title: 'Gewusst wie: Erstellen einer Ansprüche unterstützenden ASP.NET MVC-Webanwendung mithilfe von WIF'
ms.date: 03/30/2017
ms.assetid: 0efb76bc-9f7b-4afe-be1c-2a57c917010b
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 146724f31e1d09f09f94d102366539dc79ddfe02
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33399148"
---
# <a name="how-to-build-claims-aware-aspnet-mvc-web-application-using-wif"></a><span data-ttu-id="4f19e-102">Gewusst wie: Erstellen einer Ansprüche unterstützenden ASP.NET MVC-Webanwendung mithilfe von WIF</span><span class="sxs-lookup"><span data-stu-id="4f19e-102">How To: Build Claims-Aware ASP.NET MVC Web Application Using WIF</span></span>
## <a name="applies-to"></a><span data-ttu-id="4f19e-103">Gilt für</span><span class="sxs-lookup"><span data-stu-id="4f19e-103">Applies To</span></span>  
  
-   <span data-ttu-id="4f19e-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="4f19e-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="4f19e-105">ASP.NET® MVC</span><span class="sxs-lookup"><span data-stu-id="4f19e-105">ASP.NET® MVC</span></span>  
  
## <a name="summary"></a><span data-ttu-id="4f19e-106">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="4f19e-106">Summary</span></span>  
 <span data-ttu-id="4f19e-107">In dieser Vorgehensweise werden ausführliche Prozeduren zum Erstellen einer einfachen Ansprüche unterstützenden ASP.NET MVC-Webanwendung vorgestellt.</span><span class="sxs-lookup"><span data-stu-id="4f19e-107">This How-To provides detailed step-by-step procedures for creating simple claims-aware ASP.NET MVC web application.</span></span> <span data-ttu-id="4f19e-108">Sie enthält auch Anweisungen dazu, wie eine einfache Ansprüche unterstützende ASP.NET MVC-Webanwendung auf die erfolgreiche Implementierung der anspruchsbasierten Authentifizierung getestet werden kann.</span><span class="sxs-lookup"><span data-stu-id="4f19e-108">It also provides instructions how to test the simple claims-aware ASP.NET MVC web application for successful implementation of claims-based authentication.</span></span> <span data-ttu-id="4f19e-109">Diese Vorgehensweise enthält keine detaillierten Anweisungen zum Erstellen eines Sicherheitstokendiensts (Security Token Service, STS) und geht davon aus, dass Sie bereits einen STS konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="4f19e-109">This How-To does not have detailed instructions for creating a Security Token Service (STS), and assumes you have already configured an STS.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="4f19e-110">Inhalt</span><span class="sxs-lookup"><span data-stu-id="4f19e-110">Contents</span></span>  
  
-   <span data-ttu-id="4f19e-111">Ziele</span><span class="sxs-lookup"><span data-stu-id="4f19e-111">Objectives</span></span>  
  
-   <span data-ttu-id="4f19e-112">Zusammenfassung von Schritten</span><span class="sxs-lookup"><span data-stu-id="4f19e-112">Summary of Steps</span></span>  
  
-   <span data-ttu-id="4f19e-113">Schritt 1: Erstellen einer einfachen ASP.NET MVC-Anwendung</span><span class="sxs-lookup"><span data-stu-id="4f19e-113">Step 1 – Create Simple ASP.NET MVC Application</span></span>  
  
-   <span data-ttu-id="4f19e-114">Schritt 2: Konfigurieren einer ASP.NET MVC-Anwendung für die anspruchsbasierte Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="4f19e-114">Step 2 – Configure ASP.NET MVC Application for Claims-Based Authentication</span></span>  
  
-   <span data-ttu-id="4f19e-115">Schritt 3: Testen Ihrer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="4f19e-115">Step 3 – Test Your Solution</span></span>  
  
-   <span data-ttu-id="4f19e-116">Verwandte Elemente</span><span class="sxs-lookup"><span data-stu-id="4f19e-116">Related Items</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="4f19e-117">Ziele</span><span class="sxs-lookup"><span data-stu-id="4f19e-117">Objectives</span></span>  
  
-   <span data-ttu-id="4f19e-118">Konfigurieren einer ASP.NET MVC-Webanwendung für die anspruchsbasierte Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="4f19e-118">Configure ASP.NET MVC web application for claims-based authentication</span></span>  
  
-   <span data-ttu-id="4f19e-119">Testen einer erfolgreichen Ansprüche unterstützenden ASP.NET MVC-Webanwendung</span><span class="sxs-lookup"><span data-stu-id="4f19e-119">Test successful claims-aware ASP.NET MVC web application</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="4f19e-120">Zusammenfassung von Schritten</span><span class="sxs-lookup"><span data-stu-id="4f19e-120">Summary of Steps</span></span>  
  
-   <span data-ttu-id="4f19e-121">Schritt 1: Erstellen einer einfachen ASP.NET MVC-Anwendung</span><span class="sxs-lookup"><span data-stu-id="4f19e-121">Step 1 – Create Simple ASP.NET MVC Application</span></span>  
  
-   <span data-ttu-id="4f19e-122">Schritt 2: Konfigurieren einer ASP.NET MVC-Anwendung für die anspruchsbasierte Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="4f19e-122">Step 2 – Configure ASP.NET MVC Application for Claims-Based Authentication</span></span>  
  
-   <span data-ttu-id="4f19e-123">Schritt 3: Testen Ihrer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="4f19e-123">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-simple-aspnet-mvc-application"></a><span data-ttu-id="4f19e-124">Schritt 1: Erstellen einer einfachen ASP.NET MVC-Anwendung</span><span class="sxs-lookup"><span data-stu-id="4f19e-124">Step 1 – Create Simple ASP.NET MVC Application</span></span>  
 <span data-ttu-id="4f19e-125">In diesem Schritt erstellen Sie eine neue ASP.NET MVC-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="4f19e-125">In this step, you will create a new ASP.NET MVC application.</span></span>  
  
#### <a name="to-create-simple-aspnet-mvc-application"></a><span data-ttu-id="4f19e-126">Erstellen einer einfachen ASP.NET MVC-Anwendung</span><span class="sxs-lookup"><span data-stu-id="4f19e-126">To create simple ASP.NET MVC application</span></span>  
  
1.  <span data-ttu-id="4f19e-127">Starten Sie Visual Studio, und klicken Sie auf **Datei**, **Neu**, und klicken Sie dann auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="4f19e-127">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2.  <span data-ttu-id="4f19e-128">Klicken Sie im Fenster **Neues Projekt** auf **ASP.NET MVC 3-Webanwendung**.</span><span class="sxs-lookup"><span data-stu-id="4f19e-128">In the **New Project** window, click **ASP.NET MVC 3 Web Application**.</span></span>  
  
3.  <span data-ttu-id="4f19e-129">Geben Sie im Feld **Name** die Zeichenfolge `TestApp` ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f19e-129">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
4.  <span data-ttu-id="4f19e-130">Wählen Sie im Dialogfeld **Neues ASP.NET MVC 3-Projekt** aus den verfügbaren Vorlagen **Internetanwendung** aus, und versichern Sie sich, dass das **Ansichtsmodul** auf **Razor** festgelegt ist. Klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f19e-130">In the **New ASP.NET MVC 3 Project** dialog, select **Internet Application** from the available templates, ensure **View Engine** is set to **Razor**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="4f19e-131">Wenn das neue Projekt sich öffnet, klicken Sie mit der rechten Maustaste auf das **TestApp**-Projekt im **Projektmappen-Explorer**, und klicken Sie dann auf die Option **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="4f19e-131">When the new project opens, right-click the **TestApp** project in **Solution Explorer** and select the **Properties** option.</span></span>  
  
6.  <span data-ttu-id="4f19e-132">Klicken Sie auf der Seite „Eigenschaften“ des Projekts links auf die Registerkarte **Web**, und versichern Sie sich, dass die Option **Lokalen IIS-Webserver verwenden** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="4f19e-132">On the project’s properties page, click on the **Web** tab on the left and ensure that the **Use Local IIS Web Server** option is selected.</span></span>  
  
## <a name="step-2--configure-aspnet-mvc-application-for-claims-based-authentication"></a><span data-ttu-id="4f19e-133">Schritt 2: Konfigurieren einer ASP.NET MVC-Anwendung für die anspruchsbasierte Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="4f19e-133">Step 2 – Configure ASP.NET MVC Application for Claims-Based Authentication</span></span>  
 <span data-ttu-id="4f19e-134">In diesem Schritt fügen Sie Konfigurationseinträge zur Konfigurationsdatei *Web.config* Ihrer ASP.NET MVC-Webanwendung hinzu, damit diese Ansprüche unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4f19e-134">In this step you will add configuration entries to the *Web.config* configuration file of your ASP.NET MVC web application to make it claims-aware.</span></span>  
  
#### <a name="to-configure-aspnet-mvc-application-for-claims-based-authentication"></a><span data-ttu-id="4f19e-135">Konfigurieren einer ASP.NET MVC-Anwendung für die anspruchsbasierte Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="4f19e-135">To configure ASP.NET MVC application for claims-based authentication</span></span>  
  
1.  <span data-ttu-id="4f19e-136">Fügen Sie der Konfigurationsdatei *Web.config* folgende Definitionen für den Konfigurationsabschnitt hinzu.</span><span class="sxs-lookup"><span data-stu-id="4f19e-136">Add the following configuration section definitions to the *Web.config* configuration file.</span></span> <span data-ttu-id="4f19e-137">Dadurch werden Konfigurationsabschnitte definiert, die für Windows Identity Foundation erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="4f19e-137">These define configuration sections required by Windows Identity Foundation.</span></span> <span data-ttu-id="4f19e-138">Fügen Sie die Definitionen direkt nach dem öffnenden Element **\<configuration>** hinzu:</span><span class="sxs-lookup"><span data-stu-id="4f19e-138">Add the definitions immediately after the **\<configuration>** opening element:</span></span>  
  
    ```xml  
    <configSections>  
        <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
        <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    </configSections>  
    ```  
  
2.  <span data-ttu-id="4f19e-139">Fügen Sie ein **\<location>**-Element hinzu, das den Zugriff auf die Verbundmetadaten der Anwendung ermöglicht:</span><span class="sxs-lookup"><span data-stu-id="4f19e-139">Add a **\<location>** element that enables access to the application’s federation metadata:</span></span>  
  
    ```xml  
    <location path="FederationMetadata">  
        <system.web>  
            <authorization>  
                <allow users="*" />  
            </authorization>  
        </system.web>  
    </location>  
    ```  
  
3.  <span data-ttu-id="4f19e-140">Fügen Sie die folgenden Konfigurationseinträge innerhalb des Elements **\<system.web>** hinzu, um Benutzer zu verweigern, die native Authentifizierung zu deaktivieren und WIF zu ermöglichen, die Authentifizierung zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="4f19e-140">Add the following configuration entries within the **\<system.web>** elements to deny users, disable native authentication, and enable WIF to manage authentication.</span></span>  
  
    ```xml  
    <authorization>  
        <deny users="?" />  
    </authorization>  
    <authentication mode="None" />  
    ```  
  
4.  <span data-ttu-id="4f19e-141">Fügen Sie folgende auf Windows Identity Foundation bezogene Konfigurationseinträge hinzu, und versichern Sie sich, dass die URL und Portnummer Ihrer ASP.NET-Anwendungen mit den Werten des **\<audienceUris>**-Eintrags, des **realm**-Attributs des **\<wsFederation>**-Elements und des **reply**-Attributs des **\<wsFederation>**-Elements übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="4f19e-141">Add the following Windows Identity Foundation related configuration entries and ensure that your ASP.NET application’s URL and port number match the values in the **\<audienceUris>** entry, **realm** attribute of the **\<wsFederation>** element, and the **reply** attribute of the **\<wsFederation>** element.</span></span> <span data-ttu-id="4f19e-142">Vergewissern Sie sich zudem, dass der Wert des **Ausstellers** der URL Ihres Sicherheitstokendiensts entspricht.</span><span class="sxs-lookup"><span data-stu-id="4f19e-142">Also ensure that the **issuer** value fits your Security Token Service (STS) URL.</span></span>  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration>  
            <audienceUris>  
                <add value="http://localhost:28503/" />  
            </audienceUris>  
            <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
                <trustedIssuers>  
                    <add thumbprint="1234567890ABCDEFGHIJKLMNOPQRSTUVWXYZ1234" name="YourSTSName" />  
                </trustedIssuers>   
            </issuerNameRegistry>  
            <certificateValidation certificateValidationMode="None" />  
        </identityConfiguration>  
    </system.identityModel>  
    <system.identityModel.services>  
        <federationConfiguration>  
            <cookieHandler requireSsl="false" />  
            <wsFederation passiveRedirectEnabled="true" issuer="http://localhost:13922/wsFederationSTS/Issue" realm="http://localhost:28503/" reply="http://localhost:28503/" requireHttps="false" />  
        </federationConfiguration>  
    </system.identityModel.services>  
    ```  
  
5.  <span data-ttu-id="4f19e-143">Fügen Sie der Assembly <xref:System.IdentityModel> einen Verweis hinzu.</span><span class="sxs-lookup"><span data-stu-id="4f19e-143">Add reference to the <xref:System.IdentityModel> assembly.</span></span>  
  
6.  <span data-ttu-id="4f19e-144">Kompilieren Sie die Projektmappe, um sich zu vergewissern, ob Fehler vorliegen.</span><span class="sxs-lookup"><span data-stu-id="4f19e-144">Compile the solution to make sure there are errors.</span></span>  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="4f19e-145">Schritt 3: Testen Ihrer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="4f19e-145">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="4f19e-146">In diesem Schritt testen Sie die ASP.NET MVC-Webanwendung, die für die anspruchsbasierte Authentifizierung konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="4f19e-146">In this step you will test your ASP.NET MVC web application configured for claims-based authentication.</span></span> <span data-ttu-id="4f19e-147">Sie können einen grundlegenden Test ausführen, indem Sie einfachen Code hinzufügen, der die Ansprüche im Token anzeigt, die vom Sicherheitstokendienst (STS) ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4f19e-147">To perform basic test you will add simple code that displays claims in the token issued by the Security Token Service (STS).</span></span>  
  
#### <a name="to-test-your-aspnet-mvc-application-for-claims-based-authentication"></a><span data-ttu-id="4f19e-148">Testen Ihrer ASP.NET MVC-Anwendung für die anspruchsbasierte Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="4f19e-148">To test your ASP.NET MVC application for claims-based authentication</span></span>  
  
1.  <span data-ttu-id="4f19e-149">Erweitern Sie im **Projektmappen-Explorer** den Ordner **Controller**, und öffnen Sie die Datei *HomeController.cs* im Editor.</span><span class="sxs-lookup"><span data-stu-id="4f19e-149">In the **Solution Explorer**, expand the **Controllers** folder and open *HomeController.cs* file in the editor.</span></span> <span data-ttu-id="4f19e-150">Fügen Sie der **Index**-Methode folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="4f19e-150">Add the following code to the **Index** method:</span></span>  
  
    ```csharp  
    public ActionResult Index()  
    {  
        ViewBag.ClaimsIdentity = Thread.CurrentPrincipal.Identity;  
  
        return View();  
    }  
    ```  
  
2.  <span data-ttu-id="4f19e-151">Erweitern Sie im **Projektmappen-Explorer** zunächst **Ansichten** und dann die Ordner **Home**. Öffnen Sie dann die Datei *Index.cshtml* im Editor.</span><span class="sxs-lookup"><span data-stu-id="4f19e-151">In the **Solution Explorer** expand **Views** and then **Home** folders and open *Index.cshtml* file in the editor.</span></span> <span data-ttu-id="4f19e-152">Löschen Sie deren Inhalte, und fügen Sie das folgende Markup hinzu:</span><span class="sxs-lookup"><span data-stu-id="4f19e-152">Delete its contents and add the following markup:</span></span>  
  
    ```html  
    @{  
        ViewBag.Title = "Home Page";  
    }  
  
    <h2>Welcome: @ViewBag.ClaimsIdentity.Name</h2>  
    <h3>Values from Identity</h3>  
    <table>  
        <tr>  
            <th>  
                IsAuthenticated   
            </th>  
            <td>  
                @ViewBag.ClaimsIdentity.IsAuthenticated   
            </td>  
        </tr>  
        <tr>  
            <th>  
                Name   
            </th>          
            <td>  
                @ViewBag.ClaimsIdentity.Name  
            </td>          
        </tr>  
    </table>  
    <h3>Claims from ClaimsIdentity</h3>  
    <table>  
        <tr>  
            <th>  
                Claim Type  
            </th>  
            <th>  
                Claim Value  
            </th>  
            <th>  
                Value Type  
            </th>  
            <th>  
                Subject Name  
            </th>          
            <th>  
                Issuer Name  
            </th>          
        </tr>  
            @foreach (System.Security.Claims.Claim claim in ViewBag.ClaimsIdentity.Claims ) {  
        <tr>  
            <td>  
                @claim.Type  
            </td>  
            <td>  
                @claim.Value  
            </td>  
            <td>  
                @claim.ValueType  
            </td>  
            <td>  
                @claim.Subject.Name  
            </td>  
            <td>  
                @claim.Issuer  
            </td>  
        </tr>  
    }  
    </table>  
    ```  
  
3.  <span data-ttu-id="4f19e-153">Starten Sie die Projektmappe durch Drücken der Taste **F5**.</span><span class="sxs-lookup"><span data-stu-id="4f19e-153">Run the solution by pressing the **F5** key.</span></span>  
  
4.  <span data-ttu-id="4f19e-154">Ihnen sollte die Seite angezeigt werden, die die Ansprüche im Token anzeigen, die Ihnen vom Sicherheitstokendienst ausgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="4f19e-154">You should be presented with the page that displays the claims in the token that was issued to you by Security Token Service.</span></span>  
  
## <a name="related-items"></a><span data-ttu-id="4f19e-155">Verwandte Elemente</span><span class="sxs-lookup"><span data-stu-id="4f19e-155">Related Items</span></span>  
  
-   [<span data-ttu-id="4f19e-156">Gewusst wie: Erstellen einer Ansprüche unterstützenden ASP.NET Web Forms-Anwendung mithilfe von WIF</span><span class="sxs-lookup"><span data-stu-id="4f19e-156">How To: Build Claims-Aware ASP.NET Web Forms Application Using WIF</span></span>](../../../docs/framework/security/how-to-build-claims-aware-aspnet-web-forms-app-using-wif.md)

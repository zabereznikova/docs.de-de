---
title: 'Vorgehensweise: Erstellen einer Ansprüche unterstützenden ASP.NET Web Forms-Anwendung mithilfe von WIF'
ms.date: 03/30/2017
ms.assetid: efb264dd-f47b-49a9-85ee-9f45d4425765
author: BrucePerlerMS
ms.openlocfilehash: 74f15c3ac6e5192ce3565579d515198d3b7e39f5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940529"
---
# <a name="how-to-build-claims-aware-aspnet-web-forms-application-using-wif"></a><span data-ttu-id="45bc3-102">Vorgehensweise: Erstellen einer Ansprüche unterstützenden ASP.NET Web Forms-Anwendung mithilfe von WIF</span><span class="sxs-lookup"><span data-stu-id="45bc3-102">How To: Build Claims-Aware ASP.NET Web Forms Application Using WIF</span></span>
## <a name="applies-to"></a><span data-ttu-id="45bc3-103">Gilt für</span><span class="sxs-lookup"><span data-stu-id="45bc3-103">Applies To</span></span>  
  
- <span data-ttu-id="45bc3-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="45bc3-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
- <span data-ttu-id="45bc3-105">ASP.NET® Web Forms</span><span class="sxs-lookup"><span data-stu-id="45bc3-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="45bc3-106">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="45bc3-106">Summary</span></span>  
 <span data-ttu-id="45bc3-107">In dieser Vorgehensweise werden ausführliche Prozeduren zum Erstellen einer einfachen Ansprüche unterstützenden ASP.NET Web Forms-Anwendung vorgestellt.</span><span class="sxs-lookup"><span data-stu-id="45bc3-107">This How-To provides detailed step-by-step procedures for creating simple claims-aware ASP.NET Web Forms application.</span></span> <span data-ttu-id="45bc3-108">Sie enthält auch Anweisungen dazu, wie eine einfache ASP.NET Web Forms-Anwendung auf die erfolgreiche Implementierung der Verbundauthentifizierung getestet werden kann.</span><span class="sxs-lookup"><span data-stu-id="45bc3-108">It also provides instructions for how to test the simple claims-aware ASP.NET Web Forms application for successful implementation of federated authentication.</span></span> <span data-ttu-id="45bc3-109">Diese Vorgehensweise enthält keine detaillierten Anweisungen zum Erstellen eines Sicherheitstokendiensts (Security Token Service, STS) und geht davon aus, dass Sie bereits einen STS konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="45bc3-109">This How-To does not have detailed instructions for creating a Security Token Service (STS), and assumes you have already configured an STS.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="45bc3-110">Inhalt</span><span class="sxs-lookup"><span data-stu-id="45bc3-110">Contents</span></span>  
  
- <span data-ttu-id="45bc3-111">Ziele</span><span class="sxs-lookup"><span data-stu-id="45bc3-111">Objectives</span></span>  
  
- <span data-ttu-id="45bc3-112">Zusammenfassung von Schritten</span><span class="sxs-lookup"><span data-stu-id="45bc3-112">Summary of Steps</span></span>  
  
- <span data-ttu-id="45bc3-113">Schritt 1: Erstellen einer einfachen ASP.NET Web Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="45bc3-113">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
  
- <span data-ttu-id="45bc3-114">Schritt 2: Konfigurieren einer ASP.NET Web Forms-Anwendung für die anspruchsbasierte Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="45bc3-114">Step 2 – Configure ASP.NET Web Forms Application for Claims-Based Authentication</span></span>  
  
- <span data-ttu-id="45bc3-115">Schritt 3: Testen Ihrer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="45bc3-115">Step 3 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="45bc3-116">Ziele</span><span class="sxs-lookup"><span data-stu-id="45bc3-116">Objectives</span></span>  
  
- <span data-ttu-id="45bc3-117">Konfigurieren einer ASP.NET Web Forms-Anwendung für die anspruchsbasierte Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="45bc3-117">Configure ASP.NET Web Forms application for claims-based authentication</span></span>  
  
- <span data-ttu-id="45bc3-118">Testen einer erfolgreichen Ansprüche unterstützenden ASP.NET Web Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="45bc3-118">Test successful claims-aware ASP.NET Web Forms application</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="45bc3-119">Zusammenfassung von Schritten</span><span class="sxs-lookup"><span data-stu-id="45bc3-119">Summary of Steps</span></span>  
  
- <span data-ttu-id="45bc3-120">Schritt 1: Erstellen einer einfachen ASP.NET Web Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="45bc3-120">Step 1 – Create Simple ASP.NET Web Forms Application</span></span>  
  
- <span data-ttu-id="45bc3-121">Schritt 2: Konfigurieren einer ASP.NET Web Forms-Anwendung für die Verbundauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="45bc3-121">Step 2 – Configure ASP.NET Web Forms Application for Federated Authentication</span></span>  
  
- <span data-ttu-id="45bc3-122">Schritt 3: Testen Ihrer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="45bc3-122">Step 3 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application"></a><span data-ttu-id="45bc3-123">Schritt 1: Erstellen einer einfachen ASP.NET Web Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="45bc3-123">Step 1 – Create a Simple ASP.NET Web Forms Application</span></span>  
 <span data-ttu-id="45bc3-124">In diesem Schritt erstellen Sie eine neue ASP.NET Web Forms-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="45bc3-124">In this step, you will create a new ASP.NET Web Forms application.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="45bc3-125">So erstellen Sie eine einfache ASP.NET-Anwendung</span><span class="sxs-lookup"><span data-stu-id="45bc3-125">To create a simple ASP.NET application</span></span>  
  
1. <span data-ttu-id="45bc3-126">Starten Sie Visual Studio, und klicken Sie auf **Datei**, **Neu** und anschließend auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="45bc3-126">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2. <span data-ttu-id="45bc3-127">Klicken Sie im Fenster **Neues Projekt** auf **ASP.NET Web Forms-Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="45bc3-127">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3. <span data-ttu-id="45bc3-128">Geben Sie im Feld **Name** die Zeichenfolge `TestApp` ein, und drücken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="45bc3-128">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
## <a name="step-2--configure-aspnet-web-forms-application-for-claims-based-authentication"></a><span data-ttu-id="45bc3-129">Schritt 2: Konfigurieren einer ASP.NET Web Forms-Anwendung für die anspruchsbasierte Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="45bc3-129">Step 2 – Configure ASP.NET Web Forms Application for Claims-Based Authentication</span></span>  
 <span data-ttu-id="45bc3-130">In diesem Schritt fügen Sie Konfigurationseinträge zur Konfigurationsdatei *Web.config* Ihrer ASP.NET Web Forms-Anwendung hinzu, damit diese Ansprüche unterstützt.</span><span class="sxs-lookup"><span data-stu-id="45bc3-130">In this step you will add configuration entries to the *Web.config* configuration file of your ASP.NET Web Forms application to make it claims-aware.</span></span>  
  
#### <a name="to-configure-aspnet-application-for-claims-based-authentication"></a><span data-ttu-id="45bc3-131">Konfigurieren einer ASP.NET-Anwendung für die anspruchsbasierte Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="45bc3-131">To configure ASP.NET application for claims-based authentication</span></span>  
  
1. <span data-ttu-id="45bc3-132">Fügen Sie die folgenden Konfigurationseinträge unmittelbar nach dem öffnenden Element **\<configuration>** zur *Web.config*-Konfigurationsdatei hinzu:</span><span class="sxs-lookup"><span data-stu-id="45bc3-132">Add the following configuration section entries to the *Web.config* configuration file immediately after the **\<configuration>** opening element:</span></span>  
  
    ```xml  
    <configSections>  
      <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
      <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    </configSections>  
    ```  
  
2. <span data-ttu-id="45bc3-133">Fügen Sie ein **\<location>**-Element hinzu, das den Zugriff auf die Verbundmetadaten der Anwendung ermöglicht:</span><span class="sxs-lookup"><span data-stu-id="45bc3-133">Add a **\<location>** element that enables access to the application’s federation metadata:</span></span>  
  
    ```xml  
    <location path="FederationMetadata">  
      <system.web>  
        <authorization>  
          <allow users="*" />  
        </authorization>  
      </system.web>  
    </location>  
    ```  
  
3. <span data-ttu-id="45bc3-134">Fügen Sie die folgenden Konfigurationseinträge innerhalb des Elements **\<system.web>** hinzu, um Benutzer zu verweigern, die native Authentifizierung zu deaktivieren, und WIF zu ermöglichen, die Authentifizierung zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="45bc3-134">Add the following configuration entries within the **\<system.web>** elements to deny users, disable native authentication, and enable WIF to manage authentication.</span></span>  
  
    ```xml  
    <authorization>  
      <deny users="?" />  
    </authorization>  
    <authentication mode="None" />  
    ```  
  
4. <span data-ttu-id="45bc3-135">Fügen Sie das **\<system.webServer>**-Element hinzu, das die Module für Verbundauthentifizierung definiert.</span><span class="sxs-lookup"><span data-stu-id="45bc3-135">Add a **\<system.webServer>** element that defines the modules for federated authentication.</span></span> <span data-ttu-id="45bc3-136">Beachten Sie, dass das *PublicKeyToken*-Attribut identisch mit dem *PublicKeyToken*-Attribut für die **\<configSections>**-Einträge sein muss, die zuvor hinzugefügt wurden:</span><span class="sxs-lookup"><span data-stu-id="45bc3-136">Note that the *PublicKeyToken* attribute must be the same as the *PublicKeyToken* attribute for the **\<configSections>** entries added earlier:</span></span>  
  
    ```xml  
    <system.webServer>  
      <modules>  
        <add name="WSFederationAuthenticationModule" type="System.IdentityModel.Services.WSFederationAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
        <add name="SessionAuthenticationModule" type="System.IdentityModel.Services.SessionAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
      </modules>  
    </system.webServer>  
    ```  
  
5. <span data-ttu-id="45bc3-137">Fügen Sie folgende auf Windows Identity Foundation bezogene Konfigurationseinträge hinzu, und versichern Sie sich, dass die URL und Portnummer Ihrer ASP.NET-Anwendung mit den Werten des **\<audienceUris>**-Eintrags, des **realm**-Attributs des **\<wsFederation>**-Elements und des **reply**-Attributs des **\<wsFederation>**-Elements übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="45bc3-137">Add the following Windows Identity Foundation related configuration entries and ensure that your ASP.NET application’s URL and port number match the values in the **\<audienceUris>** entry, **realm** attribute of the **\<wsFederation>** element, and the **reply** attribute of the **\<wsFederation>** element.</span></span> <span data-ttu-id="45bc3-138">Vergewissern Sie sich zudem, dass der Wert des **Ausstellers** der URL Ihres Sicherheitstokendiensts entspricht.</span><span class="sxs-lookup"><span data-stu-id="45bc3-138">Also ensure that the **issuer** value fits your Security Token Service (STS) URL.</span></span>  
  
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
            <cookieHandler requireSsl="true" />  
            <wsFederation passiveRedirectEnabled="true" issuer="http://localhost:13922/wsFederationSTS/Issue" realm="http://localhost:28503/" reply="http://localhost:28503/" requireHttps="true" />  
        </federationConfiguration>  
    </system.identityModel.services>  
    ```  
  
6. <span data-ttu-id="45bc3-139">Fügen Sie der Assembly <xref:System.IdentityModel> einen Verweis hinzu.</span><span class="sxs-lookup"><span data-stu-id="45bc3-139">Add reference to the <xref:System.IdentityModel> assembly.</span></span>  
  
7. <span data-ttu-id="45bc3-140">Kompilieren Sie die Projektmappe, um sich zu vergewissern, dass keine Fehler vorliegen.</span><span class="sxs-lookup"><span data-stu-id="45bc3-140">Compile the solution to make sure there are no errors.</span></span>  
  
## <a name="step-3--test-your-solution"></a><span data-ttu-id="45bc3-141">Schritt 3: Testen Ihrer Projektmappe</span><span class="sxs-lookup"><span data-stu-id="45bc3-141">Step 3 – Test Your Solution</span></span>  
 <span data-ttu-id="45bc3-142">In diesem Schritt testen Sie die ASP.NET Web Forms-Anwendung, die für die anspruchsbasierte Authentifizierung konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="45bc3-142">In this step you will test your ASP.NET Web Forms application configured for claims-based authentication.</span></span> <span data-ttu-id="45bc3-143">Sie können einen grundlegenden Test ausführen, indem Sie einfachen Code hinzufügen, der die Ansprüche im Token anzeigt, die vom Sicherheitstokendienst (STS) ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="45bc3-143">To perform a basic test, you will add code that displays claims in the token issued by the Security Token Service (STS).</span></span>  
  
#### <a name="to-test-your-aspnet-web-form-application-for-claims-based-authentication"></a><span data-ttu-id="45bc3-144">Testen Ihrer ASP.NET Web Form-Anwendung für die anspruchsbasierte Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="45bc3-144">To test your ASP.NET Web Form application for claims-based authentication</span></span>  
  
1. <span data-ttu-id="45bc3-145">Öffnen Sie die Datei **Default.aspx** im Projekt **TestApp**, und ersetzen Sie das vorhandene Markup durch das folgende Markup:</span><span class="sxs-lookup"><span data-stu-id="45bc3-145">Open the **Default.aspx** file under the **TestApp** project and replace its existing markup with the following markup:</span></span>  
  
    ```  
    %@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="_Default" %>  
  
    <!DOCTYPE html>  
  
    <html>  
    <head id="Head1" runat="server">  
        <title></title>  
    </head>  
    <body>  
        <h1><asp:label ID="signedIn" runat="server" /></h1>  
        <asp:label ID="claimType" runat="server" />  
        <asp:label ID="claimValue" runat="server" />  
        <asp:label ID="claimValueType" runat="server" />  
        <asp:label ID="claimSubjectName" runat="server" />  
        <asp:label ID="claimIssuer" runat="server" />  
    </body>  
    </html>  
    ```  
  
2. <span data-ttu-id="45bc3-146">Speichern Sie die Datei **Default.aspx**, und öffnen Sie dann die CodeBehind-Datei **Default.aspx.cs**.</span><span class="sxs-lookup"><span data-stu-id="45bc3-146">Save **Default.aspx**, and then open its code behind file named **Default.aspx.cs**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="45bc3-147">**Default.aspx.cs** ist möglicherweise im Projektmappen-Explorer unter **Default.aspx** ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="45bc3-147">**Default.aspx.cs** may be hidden beneath **Default.aspx** in Solution Explorer.</span></span> <span data-ttu-id="45bc3-148">Wenn **Default.aspx.cs** nicht sichtbar ist, erweitern Sie **Default.aspx**, indem Sie auf das Dreieck daneben klicken.</span><span class="sxs-lookup"><span data-stu-id="45bc3-148">If **Default.aspx.cs** is not visible, expand **Default.aspx** by clicking on the triangle next to it.</span></span>  
  
3. <span data-ttu-id="45bc3-149">Ersetzen Sie den vorhandenen Code in der **Page_Load**-Methode von **Default.aspx.cs** durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="45bc3-149">Replace the existing code in the **Page_Load** method of **Default.aspx.cs** with the following code:</span></span>  
  
    ```csharp  
    using System;  
    using System.IdentityModel;  
    using System.Security.Claims;  
    using System.Threading;  
    using System.Web.UI;  
  
    namespace TestApp  
    {  
        public partial class _Default : System.Web.UI.Page  
        {  
            protected void Page_Load(object sender, EventArgs e)  
            {  
                ClaimsPrincipal claimsPrincipal = Thread.CurrentPrincipal as ClaimsPrincipal;  
  
                if (claimsPrincipal != null)  
                {  
                    signedIn.Text = "You are signed in.";  
  
                    foreach (Claim claim in claimsPrincipal.Claims)  
                    {  
                        claimType.Text = claim.Type;  
                        claimValue.Text = claim.Value;  
                        claimValueType.Text = claim.ValueType;  
                        claimSubjectName.Text = claim.Subject.Name;  
                        claimIssuer.Text = claim.Issuer;  
                    }  
                }  
                else  
                {  
                    signedIn.Text = "You are not signed in.";  
                }  
            }  
        }  
    }  
    ```  
  
4. <span data-ttu-id="45bc3-150">Speichern Sie **Default.aspx.cs**, und erstellen Sie die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="45bc3-150">Save **Default.aspx.cs**, and build the solution.</span></span>  
  
5. <span data-ttu-id="45bc3-151">Starten Sie die Projektmappe durch Drücken der Taste **F5**.</span><span class="sxs-lookup"><span data-stu-id="45bc3-151">Run the solution by pressing the **F5** key.</span></span>  
  
6. <span data-ttu-id="45bc3-152">Ihnen sollte die Seite angezeigt werden, die die Ansprüche im Token anzeigt, die Ihnen vom Sicherheitstokendienst ausgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="45bc3-152">You should be presented with the page that displays the claims in the token that was issued to you by the Security Token Service.</span></span>

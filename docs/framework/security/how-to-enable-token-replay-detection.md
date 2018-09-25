---
title: 'Vorgehensweise: Aktivieren der Erkennung einer Tokenmehrfachverwendung'
ms.date: 03/30/2017
ms.assetid: 5a9f5771-f5f6-4100-8501-406aa20d731a
author: BrucePerlerMS
ms.openlocfilehash: 373177924a0a2e03bd43237510c918694cd5a340
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47075345"
---
# <a name="how-to-enable-token-replay-detection"></a><span data-ttu-id="d1f72-102">Vorgehensweise: Aktivieren der Erkennung einer Tokenmehrfachverwendung</span><span class="sxs-lookup"><span data-stu-id="d1f72-102">How To: Enable Token Replay Detection</span></span>
## <a name="applies-to"></a><span data-ttu-id="d1f72-103">Gilt für</span><span class="sxs-lookup"><span data-stu-id="d1f72-103">Applies To</span></span>  
  
-   <span data-ttu-id="d1f72-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="d1f72-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="d1f72-105">ASP.NET® Web Forms</span><span class="sxs-lookup"><span data-stu-id="d1f72-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="d1f72-106">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="d1f72-106">Summary</span></span>  
 <span data-ttu-id="d1f72-107">In dieser Vorgehensweise werden ausführliche Prozeduren zum Aktivieren der Erkennung einer Tokenmehrfachverwendung in einer ASP.NET-Anwendung, die WIF verwendet, vorgestellt.</span><span class="sxs-lookup"><span data-stu-id="d1f72-107">This How-To provides detailed step-by-step procedures for enabling token replay detection in an ASP.NET application that uses WIF.</span></span> <span data-ttu-id="d1f72-108">Es werden auch Anleitungen bereitgestellt, wie die Anwendung danach überprüft werden kann, ob die Erkennung einer Tokenmehrfachverwendung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d1f72-108">It also provides instructions for how to test the application to verify that token replay detection is enabled.</span></span> <span data-ttu-id="d1f72-109">Diese Vorgehensweise enthält keine ausführlichen Anweisungen zum Erstellen eines Sicherheitstokendiensts (STS). Stattdessen wird der Entwicklungs-STS verwendet, der aus dem Identitäts- und Zugriffstool stammt.</span><span class="sxs-lookup"><span data-stu-id="d1f72-109">This How-To does not have detailed instructions for creating a Security Token Service (STS), and instead uses the Development STS that comes with the Identity and Access tool.</span></span> <span data-ttu-id="d1f72-110">Der Entwicklungs-STS führt keine echte Authentifizierung durch und ist nur für Testzwecke vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="d1f72-110">The Development STS does not perform real authentication and is intended for testing purposes only.</span></span> <span data-ttu-id="d1f72-111">Sie müssen das Identitäts- und Zugriffs-Tool installieren, um diese Vorgehensweise nachzuvollziehen.</span><span class="sxs-lookup"><span data-stu-id="d1f72-111">You will need to install the Identity and Access tool to complete this How-To.</span></span> <span data-ttu-id="d1f72-112">Es kann auf der folgenden Seite heruntergeladen werden: [Identity and Access Tool (Identitäts- und Zugriffstool)](https://go.microsoft.com/fwlink/?LinkID=245849)</span><span class="sxs-lookup"><span data-stu-id="d1f72-112">It can be downloaded from the following location: [Identity and Access Tool](https://go.microsoft.com/fwlink/?LinkID=245849)</span></span>  
  
## <a name="contents"></a><span data-ttu-id="d1f72-113">Inhalt</span><span class="sxs-lookup"><span data-stu-id="d1f72-113">Contents</span></span>  
  
-   <span data-ttu-id="d1f72-114">Ziele</span><span class="sxs-lookup"><span data-stu-id="d1f72-114">Objectives</span></span>  
  
-   <span data-ttu-id="d1f72-115">Übersicht</span><span class="sxs-lookup"><span data-stu-id="d1f72-115">Overview</span></span>  
  
-   <span data-ttu-id="d1f72-116">Zusammenfassung von Schritten</span><span class="sxs-lookup"><span data-stu-id="d1f72-116">Summary of Steps</span></span>  
  
-   <span data-ttu-id="d1f72-117">Schritt 1: Erstellen einer einfachen ASP.NET-Web Forms-Anwendung und Aktivieren der Erkennung einer Tokenmehrfachverwendung</span><span class="sxs-lookup"><span data-stu-id="d1f72-117">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Replay Detection</span></span>  
  
-   <span data-ttu-id="d1f72-118">Schritt 2 – Testen der Projektmappe</span><span class="sxs-lookup"><span data-stu-id="d1f72-118">Step 2 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="d1f72-119">Ziele</span><span class="sxs-lookup"><span data-stu-id="d1f72-119">Objectives</span></span>  
  
-   <span data-ttu-id="d1f72-120">Erstellen einer einfachen ASP.NET-Anwendung, die WIF und den Entwicklungs-STS aus dem Identitäts- und Zugriffs-Tool verwendet</span><span class="sxs-lookup"><span data-stu-id="d1f72-120">Create a simple ASP.NET application that uses WIF and the Development STS from the Identity and Access Tool</span></span>  
  
-   <span data-ttu-id="d1f72-121">Aktivieren Sie die Erkennung einer Tokenmehrfachverwendung, und versichern Sie sich, dass sie funktioniert</span><span class="sxs-lookup"><span data-stu-id="d1f72-121">Enable token replay detection and verify that it is working</span></span>  
  
## <a name="overview"></a><span data-ttu-id="d1f72-122">Übersicht</span><span class="sxs-lookup"><span data-stu-id="d1f72-122">Overview</span></span>  
 <span data-ttu-id="d1f72-123">Ein Replay-Angriff tritt auf, wenn ein Client versucht, eine Authentifizierung bei einer vertrauenden Seite mit einem STS-Token vorzunehmen, der vom Client bereits verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="d1f72-123">A replay attack occurs when a client attempts to authenticate to a relying party with an STS token that the client has already used.</span></span> <span data-ttu-id="d1f72-124">WIF enthält ein Cache für die Replay-Erkennung von bereits verwendeten STS-Tokens, um diesem Angriff vorzubeugen.</span><span class="sxs-lookup"><span data-stu-id="d1f72-124">To help prevent this attack, WIF contains a replay detection cache of previously used STS tokens.</span></span> <span data-ttu-id="d1f72-125">Wenn dieses aktiviert ist, überprüft die Replay-Erkennung den Token der eingehenden Anforderung und ob dieser zuvor bereits verwendet wurde oder nicht.</span><span class="sxs-lookup"><span data-stu-id="d1f72-125">When enabled, replay detection checks the token of the incoming request and verifies whether or not the token has been previously used.</span></span> <span data-ttu-id="d1f72-126">Wenn der Token bereits verwendet wurde, wird die Anforderung abgelehnt und eine <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException>-Ausnahme wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="d1f72-126">If the token has been used already, the request is refused and a <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException> exception is thrown.</span></span>  
  
 <span data-ttu-id="d1f72-127">Die folgenden Schritte veranschaulichen die erforderlichen Konfigurationsänderungen zum Aktivieren der Replay-Erkennung.</span><span class="sxs-lookup"><span data-stu-id="d1f72-127">The following steps demonstrate the configuration changes required to enable replay detection.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="d1f72-128">Zusammenfassung von Schritten</span><span class="sxs-lookup"><span data-stu-id="d1f72-128">Summary of Steps</span></span>  
  
-   <span data-ttu-id="d1f72-129">Schritt 1: Erstellen einer einfachen ASP.NET-Web Forms-Anwendung und Aktivieren der Erkennung einer Tokenmehrfachverwendung</span><span class="sxs-lookup"><span data-stu-id="d1f72-129">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Replay Detection</span></span>  
  
-   <span data-ttu-id="d1f72-130">Schritt 2 – Testen der Projektmappe</span><span class="sxs-lookup"><span data-stu-id="d1f72-130">Step 2 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application-and-enable-replay-detection"></a><span data-ttu-id="d1f72-131">Schritt 1: Erstellen einer einfachen ASP.NET-Web Forms-Anwendung und Aktivieren der Erkennung einer Tokenmehrfachverwendung</span><span class="sxs-lookup"><span data-stu-id="d1f72-131">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Replay Detection</span></span>  
 <span data-ttu-id="d1f72-132">In diesem Schritt erstellen Sie eine neue ASP.NET Web Forms-Anwendung und ändern die Datei *Web.config*, um die Replay-Erkennung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d1f72-132">In this step, you will create a new ASP.NET Web Forms application and modify the *Web.config* file to enable replay detection.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="d1f72-133">So erstellen Sie eine einfache ASP.NET-Anwendung</span><span class="sxs-lookup"><span data-stu-id="d1f72-133">To create a simple ASP.NET application</span></span>  
  
1.  <span data-ttu-id="d1f72-134">Starten Sie Visual Studio, und klicken Sie auf **Datei**, **Neu** und anschließend auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="d1f72-134">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2.  <span data-ttu-id="d1f72-135">Klicken Sie im Fenster **Neues Projekt** auf **ASP.NET Web Forms-Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="d1f72-135">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3.  <span data-ttu-id="d1f72-136">Geben Sie im Feld **Name** die Zeichenfolge `TestApp` ein, und drücken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d1f72-136">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
4.  <span data-ttu-id="d1f72-137">Klicken Sie mit der rechten Maustaste unter **Projektmappen-Explorer** auf das Projekt **TestApp**, und wählen Sie anschließend **Identität und Zugriff** aus.</span><span class="sxs-lookup"><span data-stu-id="d1f72-137">Right-click the **TestApp** project under **Solution Explorer**, then select **Identity and Access**.</span></span>  
  
5.  <span data-ttu-id="d1f72-138">Das Fenster **Identität und Zugriff** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="d1f72-138">The **Identity and Access** window appears.</span></span> <span data-ttu-id="d1f72-139">Klicken Sie unter **Anbieter** auf **Test your application with the Local Development STS** (Anwendung mit dem lokalen Entwicklungs-STS testen), und klicken Sie anschließend auf **Übernehmen**.</span><span class="sxs-lookup"><span data-stu-id="d1f72-139">Under **Providers**, select **Test your application with the Local Development STS**, then click **Apply**.</span></span>  
  
6.  <span data-ttu-id="d1f72-140">Fügen Sie folgendes **\<tokenReplayDetection>**-Element zur Konfigurationsdatei *Web.config* hinzu und direkt danach wie im Folgenden gezeigt die Elemente **\<system.identityModel>** und **\<identityConfiguration>**:</span><span class="sxs-lookup"><span data-stu-id="d1f72-140">Add the following **\<tokenReplayDetection>** element to the *Web.config* configuration file immediately following the **\<system.identityModel>** and **\<identityConfiguration>** elements, like shown:</span></span>  
  
    ```xml  
    <system.identityModel>  
        <identityConfiguration>  
            <tokenReplayDetection enabled="true"/>  
    ```  
  
## <a name="step-2--test-your-solution"></a><span data-ttu-id="d1f72-141">Schritt 2 – Testen der Projektmappe</span><span class="sxs-lookup"><span data-stu-id="d1f72-141">Step 2 – Test Your Solution</span></span>  
 <span data-ttu-id="d1f72-142">In diesem Schritt testen Sie die für WIF aktivierte ASP.NET-Anwendung, um zu überprüfen, ob die Replay-Erkennung aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="d1f72-142">In this step, you will test your WIF-enabled ASP.NET application to verify that replay detection has been enabled.</span></span>  
  
#### <a name="to-test-your-wif-enabled-aspnet-application-for-replay-detection"></a><span data-ttu-id="d1f72-143">Testen der für WIF aktivierten ASP.NET-Anwendung auf erfolgreiche Replay-Erkennung</span><span class="sxs-lookup"><span data-stu-id="d1f72-143">To test your WIF-enabled ASP.NET application for replay detection</span></span>  
  
1.  <span data-ttu-id="d1f72-144">Starten Sie die Projektmappe durch Drücken der Taste **F5**.</span><span class="sxs-lookup"><span data-stu-id="d1f72-144">Run the solution by pressing the **F5** key.</span></span> <span data-ttu-id="d1f72-145">Die Standard-Homepage von ASP.NET wird angezeigt. Sie werden automatisch mit dem Benutzernamen *Terry* authentifiziert. Dies ist der Standardbenutzer, der vom Entwicklungs-STS zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d1f72-145">You should be presented with the default ASP.NET Home Page and automatically authenticated with the username *Terry*, which is the default user that is returned by the Development STS.</span></span>  
  
2.  <span data-ttu-id="d1f72-146">Klicken Sie im Browser auf die Schaltfläche **Zurück**.</span><span class="sxs-lookup"><span data-stu-id="d1f72-146">Press the browser’s **Back** button.</span></span> <span data-ttu-id="d1f72-147">Ihnen sollte die Seite **Serverfehler in „/“-Anwendung** mit folgender Beschreibung angezeigt werden: *ID1062: Wiedergabe wurde erkannt für: Token: „System.IdentityModel.Tokens.SamlSecurityToken“*, gefolgt von einer *AssertionID* und einem *Zertifikataussteller*.</span><span class="sxs-lookup"><span data-stu-id="d1f72-147">You should be presented with a **Server Error in ‘/’ Application** page with the following description: *ID1062: Replay has been detected for: Token: 'System.IdentityModel.Tokens.SamlSecurityToken'*, followed by an *AssertionId* and an *Issuer*.</span></span>  
  
     <span data-ttu-id="d1f72-148">Diese Fehlerseite wird Ihnen angezeigt, da eine Ausnahme des Typs <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException> durch eine Tokenmehrfachverwendung ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="d1f72-148">You are seeing this error page because an exception of type <xref:System.IdentityModel.Tokens.SecurityTokenReplayDetectedException> was thrown when the token replay was detected.</span></span> <span data-ttu-id="d1f72-149">Dieser Fehler tritt auf, weil Sie versuchen, die ursprüngliche POST-Anforderung, bei der der Token zuerst verwendet wurde, erneut zu senden.</span><span class="sxs-lookup"><span data-stu-id="d1f72-149">This error occurs because you are attempting to re-send the initial POST request when the token was first presented.</span></span> <span data-ttu-id="d1f72-150">Die Schaltfläche **Zurück** löst dieses Verhalten bei nachfolgenden Anforderungen an den Server nicht aus.</span><span class="sxs-lookup"><span data-stu-id="d1f72-150">The **Back** button will not cause this behavior on subsequent requests to the server.</span></span>

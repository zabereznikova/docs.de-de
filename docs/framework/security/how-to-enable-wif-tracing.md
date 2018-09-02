---
title: 'Gewusst wie: Aktivieren der WIF-Ablaufverfolgung'
ms.date: 03/30/2017
ms.assetid: 271b6889-3454-46ff-96ab-9feb15e742ee
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 17650e06cb505dd778a9c0980c2a32fda8099cb4
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43407572"
---
# <a name="how-to-enable-wif-tracing"></a><span data-ttu-id="46c50-102">Gewusst wie: Aktivieren der WIF-Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="46c50-102">How To: Enable WIF Tracing</span></span>
## <a name="applies-to"></a><span data-ttu-id="46c50-103">Gilt für</span><span class="sxs-lookup"><span data-stu-id="46c50-103">Applies To</span></span>  
  
-   <span data-ttu-id="46c50-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="46c50-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="46c50-105">ASP.NET® Web Forms</span><span class="sxs-lookup"><span data-stu-id="46c50-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="46c50-106">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="46c50-106">Summary</span></span>  
 <span data-ttu-id="46c50-107">In dieser Vorgehensweise werden ausführliche schrittweise Prozeduren zum Aktivieren von WIF-Ablaufverfolgung in einer ASP.NET-Anwendung vorgestellt.</span><span class="sxs-lookup"><span data-stu-id="46c50-107">This How-To provides detailed step-by-step procedures for enabling WIF tracing in an ASP.NET application.</span></span> <span data-ttu-id="46c50-108">Außerdem werden Anweisungen für den Test der Anwendung gegeben, mit dem geprüft wird, ob der Ablaufverfolgungslistener und das Protokoll ordnungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="46c50-108">It also provides instructions testing the application to verify that the trace listener and log are working correctly.</span></span> <span data-ttu-id="46c50-109">Diese Vorgehensweise enthält keine ausführlichen Anweisungen zum Erstellen eines Sicherheitstokendiensts (STS). Stattdessen wird der Entwicklungs-STS verwendet, der aus dem Identitäts- und Zugriffstool stammt.</span><span class="sxs-lookup"><span data-stu-id="46c50-109">This How-To does not have detailed instructions for creating a Security Token Service (STS), and instead uses the Development STS that comes with the Identity and Access tool.</span></span> <span data-ttu-id="46c50-110">Der Entwicklungs-STS führt keine echte Authentifizierung durch und ist nur für Testzwecke vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="46c50-110">The Development STS does not perform real authentication and is intended for testing purposes only.</span></span> <span data-ttu-id="46c50-111">Sie müssen das Identitäts- und Zugriffs-Tool installieren, um diese Vorgehensweise nachzuvollziehen.</span><span class="sxs-lookup"><span data-stu-id="46c50-111">You will need to install the Identity and Access tool to complete this How-To.</span></span> <span data-ttu-id="46c50-112">Es kann auf der folgenden Seite heruntergeladen werden: [Identity and Access Tool (Identitäts- und Zugriffstool)](https://go.microsoft.com/fwlink/?LinkID=245849)</span><span class="sxs-lookup"><span data-stu-id="46c50-112">It can be downloaded from the following location: [Identity and Access Tool](https://go.microsoft.com/fwlink/?LinkID=245849)</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="46c50-113">Wenn die WIF-Ablaufverfolgung für passive Anwendungen, also Anwendungen, die das WS-Verbundprotokoll verwenden, aktiviert wird, kann die Anwendung DoS-Angriffen (DoS, Denial of Services) ausgesetzt sein oder Informationen könnten für nicht vertrauenswürdige Seiten mit böswilligen Absichten verfügbar werden.</span><span class="sxs-lookup"><span data-stu-id="46c50-113">Enabling WIF tracing for passive applications, that is, applications that use the WS-Federation protocol, can potentially expose the application to denial of service (DoS) attacks or to information disclosure to a malicious party.</span></span> <span data-ttu-id="46c50-114">Dazu gehören auch passive vertrauende Seiten und passive STS.</span><span class="sxs-lookup"><span data-stu-id="46c50-114">This includes both passive RPs and passive STSes.</span></span> <span data-ttu-id="46c50-115">Aus diesem Grund wird empfohlen, keine WIF-Ablaufverfolgung für passive vertrauende Seiten oder STS in einer Produktionsumgebung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="46c50-115">For this reason, we recommend that you not enable WIF tracing for passive RPs or STSes in a production environment.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="46c50-116">Inhalt</span><span class="sxs-lookup"><span data-stu-id="46c50-116">Contents</span></span>  
  
-   <span data-ttu-id="46c50-117">Ziele</span><span class="sxs-lookup"><span data-stu-id="46c50-117">Objectives</span></span>  
  
-   <span data-ttu-id="46c50-118">Übersicht</span><span class="sxs-lookup"><span data-stu-id="46c50-118">Overview</span></span>  
  
-   <span data-ttu-id="46c50-119">Zusammenfassung von Schritten</span><span class="sxs-lookup"><span data-stu-id="46c50-119">Summary of Steps</span></span>  
  
-   <span data-ttu-id="46c50-120">Schritt 1 – Erstellen einer einfachen ASP.NET-Web Forms-Anwendung und Aktivieren der Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="46c50-120">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Tracing</span></span>  
  
-   <span data-ttu-id="46c50-121">Schritt 2 – Testen der Projektmappe</span><span class="sxs-lookup"><span data-stu-id="46c50-121">Step 2 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="46c50-122">Ziele</span><span class="sxs-lookup"><span data-stu-id="46c50-122">Objectives</span></span>  
  
-   <span data-ttu-id="46c50-123">Erstellen einer einfachen ASP.NET-Anwendung, die WIF und den Entwicklungs-STS aus dem Identitäts- und Zugriffs-Tool verwendet</span><span class="sxs-lookup"><span data-stu-id="46c50-123">Create a simple ASP.NET application that uses WIF and the Development STS from the Identity and Access Tool</span></span>  
  
-   <span data-ttu-id="46c50-124">Aktivieren der Ablaufverfolgung und Überprüfen der Funktion</span><span class="sxs-lookup"><span data-stu-id="46c50-124">Enable tracing and verify that it is working</span></span>  
  
## <a name="overview"></a><span data-ttu-id="46c50-125">Übersicht</span><span class="sxs-lookup"><span data-stu-id="46c50-125">Overview</span></span>  
 <span data-ttu-id="46c50-126">Mit Ablaufverfolgung können Sie viele Arten von Problemen mit WIF, einschließlich Token, Cookies, Ansprüche, Protokollmeldungen usw. debuggen und Fehler daran beheben.</span><span class="sxs-lookup"><span data-stu-id="46c50-126">Tracing enables you to debug and troubleshoot many types of issues with WIF, including tokens, cookies, claims, protocol messages, and more.</span></span> <span data-ttu-id="46c50-127">WIF-Ablaufverfolgung ähnelt der WCF-Ablaufverfolgung; Sie können beispielsweise den Ausführlichkeitsgrad von Ablaufverfolgungen auswählen, um Meldungen von kritischen Meldungen bis hin zu allen Meldungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="46c50-127">WIF tracing is similar to WCF tracing; for example, you can choose the verbosity of traces to display everything from critical messages to all messages.</span></span> <span data-ttu-id="46c50-128">WIF-Ablaufverfolgungen können in **XML**-Dateien oder in **SVCLOG**-Dateien generiert werden, die mit dem Service Trace Viewer-Tool angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="46c50-128">WIF traces can be generated in **.xml** files or in **.svclog** files that are viewable by using the Service Trace Viewer Tool.</span></span> <span data-ttu-id="46c50-129">Dieses Tool befindet sich im Verzeichnis **bin** im Windows SDK-Installationspfad auf dem Computer, beispielsweise: **C:\Programme\Microsoft SDKs\Windows\v7.1\Bin\SvcTraceViewer.exe**.</span><span class="sxs-lookup"><span data-stu-id="46c50-129">This tool is located in the **bin** directory of the Windows SDK install path on your computer, for example: **C:\Program Files\Microsoft SDKs\Windows\v7.1\Bin\SvcTraceViewer.exe**.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="46c50-130">Zusammenfassung von Schritten</span><span class="sxs-lookup"><span data-stu-id="46c50-130">Summary of Steps</span></span>  
  
-   <span data-ttu-id="46c50-131">Schritt 1 – Erstellen einer einfachen ASP.NET-Web Forms-Anwendung und Aktivieren der Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="46c50-131">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Tracing</span></span>  
  
-   <span data-ttu-id="46c50-132">Schritt 2 – Testen der Projektmappe</span><span class="sxs-lookup"><span data-stu-id="46c50-132">Step 2 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application-and-enable-tracing"></a><span data-ttu-id="46c50-133">Schritt 1 – Erstellen einer einfachen ASP.NET-Web Forms-Anwendung und Aktivieren der Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="46c50-133">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Tracing</span></span>  
 <span data-ttu-id="46c50-134">In diesem Schritt erstellen Sie eine neue ASP.NET Web Forms-Anwendung und ändern die Datei *Web.config*, um die Ablaufverfolgung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="46c50-134">In this step, you will create a new ASP.NET Web Forms application and modify the *Web.config* file to enable tracing.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="46c50-135">So erstellen Sie eine einfache ASP.NET-Anwendung</span><span class="sxs-lookup"><span data-stu-id="46c50-135">To create a simple ASP.NET application</span></span>  
  
1.  <span data-ttu-id="46c50-136">Starten Sie Visual Studio, und klicken Sie auf **Datei**, **Neu** und anschließend auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="46c50-136">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2.  <span data-ttu-id="46c50-137">Klicken Sie im Fenster **Neues Projekt** auf **ASP.NET Web Forms-Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="46c50-137">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3.  <span data-ttu-id="46c50-138">Geben Sie im Feld **Name** die Zeichenfolge `TestApp` ein, und drücken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="46c50-138">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
4.  <span data-ttu-id="46c50-139">Klicken Sie mit der rechten Maustaste unter **Projektmappen-Explorer** auf das Projekt **TestApp**, und wählen Sie anschließend **Identität und Zugriff** aus.</span><span class="sxs-lookup"><span data-stu-id="46c50-139">Right-click the **TestApp** project under **Solution Explorer**, then select **Identity and Access**.</span></span>  
  
5.  <span data-ttu-id="46c50-140">Das Fenster **Identität und Zugriff** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="46c50-140">The **Identity and Access** window appears.</span></span> <span data-ttu-id="46c50-141">Klicken Sie unter **Anbieter** auf **Test your application with the Local Development STS** (Anwendung mit dem lokalen Entwicklungs-STS testen), und klicken Sie anschließend auf **Übernehmen**.</span><span class="sxs-lookup"><span data-stu-id="46c50-141">Under **Providers**, select **Test your application with the Local Development STS**, then click **Apply**.</span></span>  
  
6.  <span data-ttu-id="46c50-142">Erstellen Sie wie hier dargestellt im Stamm des Laufwerks **C:** einen neuen Ordner mit dem Namen **logs**: **C:\logs**.</span><span class="sxs-lookup"><span data-stu-id="46c50-142">Create a new folder in named **logs** in the root of the **C:** drive, like shown: **C:\logs**</span></span>  
  
7.  <span data-ttu-id="46c50-143">Fügen Sie der Konfigurationsdatei *Web.config* direkt nach dem schließenden **\</configSections>**-Element das folgende **\<system.diagnostics>**-Element wie dargestellt hinzu:</span><span class="sxs-lookup"><span data-stu-id="46c50-143">Add the following **\<system.diagnostics>** element to the *Web.config* configuration file immediately following the closing **\</configSections>** element, like shown:</span></span>  
  
    ```xml  
    <configuration>  
        <configSections>  
        …  
        </configSections>  
        <system.diagnostics>  
            <sources>  
                <source name="System.IdentityModel" switchValue="Verbose">  
                    <listeners>  
                        <add name="xml" type="System.Diagnostics.XmlWriterTraceListener" initializeData="C:\logs\WIF.xml" />  
                    </listeners>  
                </source>  
            </sources>  
            <trace autoflush="true" />  
        </system.diagnostics>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="46c50-144">Der Verzeichnisspeicherort, der im Attribut **initializeData** angegeben wird, muss vorhanden sein, bevor die Protokollierung beginnen kann.</span><span class="sxs-lookup"><span data-stu-id="46c50-144">The directory location specified in the **initializeData** attribute must exist before logging can begin.</span></span> <span data-ttu-id="46c50-145">Wenn der Speicherort nicht vorhanden ist, werden keine Protokolle erstellt.</span><span class="sxs-lookup"><span data-stu-id="46c50-145">If the location does not exist, no logs will be created.</span></span>  
  
     <span data-ttu-id="46c50-146">Mit den oben erwähnten Konfigurationseinstellungen werden die **ausführliche** Ablaufverfolgung für WIF aktiviert und das resultierende Protokoll in der Datei **C:\logs\WIF.xml** gespeichert.</span><span class="sxs-lookup"><span data-stu-id="46c50-146">The configuration settings above will enable **Verbose** tracing for WIF and save the resulting log to the **C:logsWIF.xml** file.</span></span>  
  
## <a name="step-2--test-your-solution"></a><span data-ttu-id="46c50-147">Schritt 2 – Testen der Projektmappe</span><span class="sxs-lookup"><span data-stu-id="46c50-147">Step 2 – Test Your Solution</span></span>  
 <span data-ttu-id="46c50-148">In diesem Schritt testen Sie die für WIF aktivierte ASP.NET-Anwendung, um zu überprüfen, ob Protokolle aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="46c50-148">In this step, you will test your WIF-enabled ASP.NET application to verify that logs are being recorded.</span></span>  
  
#### <a name="to-test-your-wif-enabled-aspnet-application-for-successful-tracing"></a><span data-ttu-id="46c50-149">So testen Sie die für WIF aktivierte ASP.NET-Anwendung auf erfolgreiche Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="46c50-149">To test your WIF-enabled ASP.NET application for successful tracing</span></span>  
  
1.  <span data-ttu-id="46c50-150">Starten Sie die Projektmappe durch Drücken der Taste **F5**.</span><span class="sxs-lookup"><span data-stu-id="46c50-150">Run the solution by pressing the **F5** key.</span></span> <span data-ttu-id="46c50-151">Die Standard-Homepage von ASP.NET wird angezeigt. Sie werden automatisch mit dem Benutzernamen *Terry* authentifiziert. Dies ist der Standardbenutzer, der vom Entwicklungs-STS zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="46c50-151">You should be presented with the default ASP.NET Home Page and automatically authenticated with the username *Terry*, which is the default user that is returned by the Development STS.</span></span>  
  
2.  <span data-ttu-id="46c50-152">Schließen Sie das Browserfenster, und navigieren Sie dann zum Ordner **C:\logs**.</span><span class="sxs-lookup"><span data-stu-id="46c50-152">Close the browser window and then navigate to the **C:\logs** folder.</span></span> <span data-ttu-id="46c50-153">Öffnen Sie die Datei **C:\logs\WIF.xml** in einem Text-Editor.</span><span class="sxs-lookup"><span data-stu-id="46c50-153">Open the **C:\logs\WIF.xml** file using a text editor.</span></span>  
  
3.  <span data-ttu-id="46c50-154">Überprüfen Sie, ob die Datei **WIF.xml** Einträge enthält, die mit **\<E2ETraceEvent>** beginnen.</span><span class="sxs-lookup"><span data-stu-id="46c50-154">Inspect the **WIF.xml** file and verify that it contains entries starting with **\<E2ETraceEvent>**.</span></span> <span data-ttu-id="46c50-155">Diese Ablaufverfolgungen enthalten **\<TraceRecord>**-Elemente mit Beschreibungen für die aufgezeichnete Aktivität, z. B. **Sicherheitstoken wird überprüft**.</span><span class="sxs-lookup"><span data-stu-id="46c50-155">These traces will contain **\<TraceRecord>** elements with descriptions for the traced activity, such as **Validating SecurityToken**.</span></span>

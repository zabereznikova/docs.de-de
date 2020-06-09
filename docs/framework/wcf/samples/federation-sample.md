---
title: Verbundbeispiel
ms.date: 03/30/2017
ms.assetid: 7e9da0ca-e925-4644-aa96-8bfaf649d4bb
ms.openlocfilehash: 00cb9a13a01687fb41f1d5c09f277d582f706e3b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594685"
---
# <a name="federation-sample"></a><span data-ttu-id="3583d-102">Verbundbeispiel</span><span class="sxs-lookup"><span data-stu-id="3583d-102">Federation Sample</span></span>
<span data-ttu-id="3583d-103">Dieses Beispiel veranschaulicht die Verbundsicherheit.</span><span class="sxs-lookup"><span data-stu-id="3583d-103">This sample demonstrates federated security.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="3583d-104">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="3583d-104">Sample Details</span></span>  
 <span data-ttu-id="3583d-105">Windows Communication Foundation (WCF) bietet Unterstützung für die Bereitstellung von Verbund Sicherheitsarchitekturen über `wsFederationHttpBinding` .</span><span class="sxs-lookup"><span data-stu-id="3583d-105">Windows Communication Foundation (WCF) provides support for deploying federated security architectures through the `wsFederationHttpBinding`.</span></span> <span data-ttu-id="3583d-106">Die `wsFederationHttpBinding` bietet eine sichere, zuverlässige und interoperable Bindung, die die Verwendung von HTTP als den zugrunde liegenden Transportmechanismus für die Anforderungs-Antwort-Kommunikation umfasst, während Text und XML als Übertragungsformate für die Codierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3583d-106">The `wsFederationHttpBinding` provides a secure, reliable, and interoperable binding that involves the use of HTTP as the underlying transport mechanism for request/reply communication, and Text/XML as the wire format for encoding.</span></span> <span data-ttu-id="3583d-107">Weitere Informationen zum Verbund in WCF finden Sie unter [Federation](../feature-details/federation.md).</span><span class="sxs-lookup"><span data-stu-id="3583d-107">For more information about Federation in WCF, see [Federation](../feature-details/federation.md).</span></span>  
  
 <span data-ttu-id="3583d-108">Das Szenario besteht aus 4 Einheiten:</span><span class="sxs-lookup"><span data-stu-id="3583d-108">The scenario is made up of 4 pieces:</span></span>  
  
- <span data-ttu-id="3583d-109">BookStore-Dienst</span><span class="sxs-lookup"><span data-stu-id="3583d-109">BookStore service</span></span>  
  
- <span data-ttu-id="3583d-110">BookStore STS</span><span class="sxs-lookup"><span data-stu-id="3583d-110">BookStore STS</span></span>  
  
- <span data-ttu-id="3583d-111">HomeRealm STS</span><span class="sxs-lookup"><span data-stu-id="3583d-111">HomeRealm STS</span></span>  
  
- <span data-ttu-id="3583d-112">BookStore-Client</span><span class="sxs-lookup"><span data-stu-id="3583d-112">BookStore Client</span></span>  
  
 <span data-ttu-id="3583d-113">Der BookStore-Dienst unterstützt zwei Vorgänge: `BrowseBooks` und `BuyBook`.</span><span class="sxs-lookup"><span data-stu-id="3583d-113">The BookStore service supports two operations, `BrowseBooks` and `BuyBook`.</span></span> <span data-ttu-id="3583d-114">Es lässt anonymen Zugriff auf den `BrowseBooks`-Vorgang zu, aber erfordert authentifizierten Zugriff, um auf den `BuyBooks`-Vorgang zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="3583d-114">It allows anonymous access to the `BrowseBooks` operation, but requires authenticated access to access the `BuyBooks` operation.</span></span> <span data-ttu-id="3583d-115">Die Authentifizierung hat das Format eines Tokens, das von BookStore STS ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3583d-115">The authentication takes the form of a token issued by the BookStore STS.</span></span> <span data-ttu-id="3583d-116">Die Konfigurationsdatei zum BookStore-Dienst verweist Clients mit `wsFederationHttpBinding` auf BookStore STS.</span><span class="sxs-lookup"><span data-stu-id="3583d-116">The configuration file for the BookStore Service points clients to the BookStore STS using the `wsFederationHttpBinding`.</span></span>  
  
```xml  
<wsFederationHttpBinding>  
<!-- This is the Service binding for the BuyBooks endpoint. It redirects clients to the BookStore STS -->  
    <binding name='BuyBookBinding'>  
        <security mode="Message">  
            <message>  
                <issuerMetadata  
  address='http://localhost/FederationSample/BookStoreSTS/STS.svc/mex' >  
                    <identity>  
                        <dns value ='BookStoreSTS.com'/>  
                    </identity>  
                </issuerMetadata>  
            </message>  
        </security>  
    </binding>  
</wsFederationHttpBinding>  
```  
  
 <span data-ttu-id="3583d-117">BookStore STS erfordert dann, dass Clients mit einem von HomeRealm STS ausgegebenen Token authentifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="3583d-117">The BookStore STS then requires that clients authenticate using a token issued by the HomeRealm STS.</span></span> <span data-ttu-id="3583d-118">Die Konfigurationsdatei für BookStore STS verweist dann Clients mit `wsFederationHttpBinding` auf HomeRealm STS.</span><span class="sxs-lookup"><span data-stu-id="3583d-118">Again, the configuration file for the BookStore STS points clients to the HomeRealm STS using the `wsFederationHttpBinding`.</span></span>  
  
```xml  
<wsFederationHttpBinding>  
 <!-- This is the binding for the clients requesting tokens from this STS. It redirects clients to the HomeRealm STS -->  
    <binding name='BookStoreSTSBinding'>  
        <security mode='Message'>  
            <message>  
                <issuerMetadata  
 address='http://localhost/FederationSample/HomeRealmSTS/STS.svc/mex' >  
                    <identity>  
                        <dns value ='HomeRealmSTS.com' />  
                    </identity>  
                </issuerMetadata>  
            </message>  
        </security>  
    </binding>  
</wsFederationHttpBinding>  
```  
  
 <span data-ttu-id="3583d-119">Die Sequenz von Ereignissen beim Zugriff auf den `BuyBook`-Vorgang lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="3583d-119">The sequence of events when accessing the `BuyBook` operation is as follows:</span></span>  
  
1. <span data-ttu-id="3583d-120">Der Client wird mit Windows-Anmeldeinformationen bei HomeRealm STS authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="3583d-120">The client authenticates to the HomeRealm STS using Windows credentials.</span></span>  
  
2. <span data-ttu-id="3583d-121">HomeRealm STS gibt ein Token aus, das verwendet werden kann, um bei BookStore STS authentifiziert zu werden.</span><span class="sxs-lookup"><span data-stu-id="3583d-121">The HomeRealm STS issues a token that can be used to authenticate to the BookStore STS.</span></span>  
  
3. <span data-ttu-id="3583d-122">Der Client wird bei BookStore STS mit einem von HomeRealm STS ausgegebenen Token authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="3583d-122">The client authenticates to the BookStore STS using the token issued by the HomeRealm STS.</span></span>  
  
4. <span data-ttu-id="3583d-123">BookStore STS gibt ein Token aus, das verwendet werden kann, um beim BookStore-Dienst authentifiziert zu werden.</span><span class="sxs-lookup"><span data-stu-id="3583d-123">The BookStore STS issues a token that can be used to authenticate to the BookStore Service.</span></span>  
  
5. <span data-ttu-id="3583d-124">Der Client wird beim BookStore-Dienst mit einem von BookStore STS ausgegebenen Token authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="3583d-124">The client authenticates to the BookStore service using the token issued by the BookStore STS.</span></span>  
  
6. <span data-ttu-id="3583d-125">Der Client greift auf den `BuyBook`-Vorgang zu.</span><span class="sxs-lookup"><span data-stu-id="3583d-125">The client accesses the `BuyBook` operation.</span></span>  
  
 <span data-ttu-id="3583d-126">In den folgenden Anweisungen finden Sie Informationen zum Einrichten und Ausführen dieses Beispiels.</span><span class="sxs-lookup"><span data-stu-id="3583d-126">See the following instructions about how to set up and run this sample.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3583d-127">Sie müssen über Schreibberechtigungen für das Verzeichnis " **wwwroot** " verfügen, um dieses Beispiel ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="3583d-127">You must have Write permissions to the **wwwroot** directory to run this sample.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3583d-128">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="3583d-128">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="3583d-129">Öffnen Sie das SDK-Befehlsfenster.</span><span class="sxs-lookup"><span data-stu-id="3583d-129">Open the SDK command window.</span></span> <span data-ttu-id="3583d-130">Führen Sie im Beispielpfad die Datei "Setup.bat" aus.</span><span class="sxs-lookup"><span data-stu-id="3583d-130">In the sample path, run Setup.bat.</span></span> <span data-ttu-id="3583d-131">Dadurch werden die erforderlichen virtuellen Verzeichnisse für das Beispiel erstellt und die erforderlichen Zertifikate mit entsprechenden Berechtigungen installiert.</span><span class="sxs-lookup"><span data-stu-id="3583d-131">This creates the virtual directories required for the sample and installs the required certificates with appropriate permissions.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="3583d-132">Die Batchdatei "Setup.bat" ist dafür ausgelegt, von einer Windows SDK-Eingabeaufforderung ausgeführt zu werden.</span><span class="sxs-lookup"><span data-stu-id="3583d-132">The Setup.bat batch file is designed to be run from a Windows SDK Command Prompt.</span></span> <span data-ttu-id="3583d-133">Die MSSDK-Umgebungsvariable muss auf das Verzeichnis zeigen, in dem das SDK installiert ist.</span><span class="sxs-lookup"><span data-stu-id="3583d-133">It requires that the MSSDK environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="3583d-134">Diese Umgebungsvariable wird automatisch innerhalb einer Windows SDK-Eingabeaufforderung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3583d-134">This environment variable is automatically set within a Windows SDK Command Prompt.</span></span> <span data-ttu-id="3583d-135">Unter Windows Vista müssen Sie sicherstellen, dass die IIS 6,0-Verwaltungs Kompatibilität installiert ist, da für die Einrichtung IIS-Administrator Skripts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3583d-135">On Windows Vista, you must ensure that IIS 6.0 Management Compatibility is installed because the set up uses IIS administrator scripts.</span></span> <span data-ttu-id="3583d-136">Das Ausführen des Setup Skripts unter Windows Vista erfordert Administratorrechte.</span><span class="sxs-lookup"><span data-stu-id="3583d-136">Running the set-up script on Windows Vista requires administrator privileges.</span></span>  
  
2. <span data-ttu-id="3583d-137">Öffnen Sie in Visual Studio die Datei FederationSample. sln, und wählen Sie im Menü **Erstellen** die Option Projekt Mappe **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="3583d-137">Open FederationSample.sln in Visual Studio and select **Build Solution** from the **Build** menu.</span></span> <span data-ttu-id="3583d-138">Dadurch werden die allgemeinen Projektdateien, der Bookstore-Dienst, Bookstore-STS und HomeRealm STS erstellt und in IIS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="3583d-138">This builds the common project files, Bookstore service, Bookstore STS, HomeRealm STS, and deploys them in IIS.</span></span> <span data-ttu-id="3583d-139">Auf diese Weise wird auch die Buchhandlungsclientanwendung erstellt, und die ausführbare Datei "BookStoreClient.exe" wird im Ordner "FederationSample\BookStoreClient\bin\Debug" gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3583d-139">This also builds the Bookstore client application and places the executable BookStoreClient.exe in the FederationSample\BookStoreClient\bin\Debug folder.</span></span>  
  
3. <span data-ttu-id="3583d-140">Doppelklicken Sie auf "BookStoreClient.exe".</span><span class="sxs-lookup"><span data-stu-id="3583d-140">Double-click BookStoreClient.exe.</span></span> <span data-ttu-id="3583d-141">Das Fenster "BookStoreClient" wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3583d-141">The BookStoreClient window is displayed.</span></span>  
  
4. <span data-ttu-id="3583d-142">Sie können die Bücher in der Buchhandlung durchsuchen, indem Sie auf **Bücher durchsuchen**klicken.</span><span class="sxs-lookup"><span data-stu-id="3583d-142">You can browse the books available in the bookstore by clicking **Browse Books**.</span></span>  
  
5. <span data-ttu-id="3583d-143">Wenn Sie ein bestimmtes Buch kaufen möchten, wählen Sie das Buch in der Liste aus, und klicken Sie auf **Buch kaufen**.</span><span class="sxs-lookup"><span data-stu-id="3583d-143">To purchase a particular book, select the book in the list and click **Buy Book**.</span></span> <span data-ttu-id="3583d-144">Die Anwendung startet und wird mit der Windows-Authentifizierung beim HomeRealm-Sicherheitstokendienst authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="3583d-144">The application starts up and authenticates using Windows authentication with the HomeRealm Security Token Service.</span></span>  
  
     <span data-ttu-id="3583d-145">Das Beispiel ist so konfiguriert, dass Benutzern der Kauf von Büchern ermöglicht wird, die $15 oder weniger kosten.</span><span class="sxs-lookup"><span data-stu-id="3583d-145">The sample is configured to allow users to purchase books that cost $15 or less.</span></span> <span data-ttu-id="3583d-146">Wenn versucht wird, Bücher zu kaufen, die mehr als $15 kosten, erhält der Client vom BookStore-Dienst eine Nachricht vom Typ Zugriff verweigert.</span><span class="sxs-lookup"><span data-stu-id="3583d-146">Attempting to buy books that cost more than $15 results in the client getting an Access Denied message from the Book Store Service.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="3583d-147">Im Beispiel wird der Kreditrahmen des Benutzers nach einem Kauf nicht aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="3583d-147">The sample does not update the user’s credit limit after a purchase.</span></span> <span data-ttu-id="3583d-148">Sie können immer wieder Bücher innerhalb des Kreditrahmens (fest) des Benutzers kaufen.</span><span class="sxs-lookup"><span data-stu-id="3583d-148">You can repeatedly purchase books within the user’s (fixed) credit limit.</span></span>  
  
#### <a name="to-clean-up"></a><span data-ttu-id="3583d-149">So führen Sie eine Bereinigung durch</span><span class="sxs-lookup"><span data-stu-id="3583d-149">To clean up</span></span>  
  
1. <span data-ttu-id="3583d-150">Führen Sie die Datei Cleanup.bat aus.</span><span class="sxs-lookup"><span data-stu-id="3583d-150">Run Cleanup.bat.</span></span> <span data-ttu-id="3583d-151">Dadurch werden die virtuellen Verzeichnisse, die beim Setup erstellt wurden, gelöscht, und auch die beim Setup installierten Zertifikate werden entfernt.</span><span class="sxs-lookup"><span data-stu-id="3583d-151">This deletes the virtual directories that were created during set up and also removes the certificates installed during setup.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3583d-152">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="3583d-152">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3583d-153">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="3583d-153">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="3583d-154">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3583d-154">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3583d-155">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="3583d-155">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\Federation`  

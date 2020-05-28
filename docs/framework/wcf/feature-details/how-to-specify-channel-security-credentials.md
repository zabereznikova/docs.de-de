---
title: 'Vorgehensweise: Angeben von Anmeldeinformationen für Kanalsicherheit'
ms.date: 03/30/2017
ms.assetid: f8e03f47-9c4f-4dd5-8f85-429e6d876119
ms.openlocfilehash: 72fdcd18fba2eabe8255f73acd240e12e57d56ea
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144707"
---
# <a name="how-to-specify-channel-security-credentials"></a><span data-ttu-id="ef53d-102">Vorgehensweise: Angeben von Anmeldeinformationen für Kanalsicherheit</span><span class="sxs-lookup"><span data-stu-id="ef53d-102">How to: Specify Channel Security Credentials</span></span>
<span data-ttu-id="ef53d-103">Der Windows Communication Foundation (WCF)-Dienstmoniker ermöglicht com-Anwendungen das Aufrufen von WCF-Diensten.</span><span class="sxs-lookup"><span data-stu-id="ef53d-103">The Windows Communication Foundation (WCF) Service Moniker allows COM applications to call WCF services.</span></span> <span data-ttu-id="ef53d-104">Die meisten WCF-Dienste erfordern, dass der Client Anmelde Informationen für die Authentifizierung und Autorisierung angibt.</span><span class="sxs-lookup"><span data-stu-id="ef53d-104">Most WCF services require the client to specify credentials for authentication and authorization.</span></span> <span data-ttu-id="ef53d-105">Wenn Sie einen WCF-Dienst von einem WCF-Client aufrufen, können Sie diese Anmelde Informationen in verwaltetem Code oder in einer Anwendungs Konfigurationsdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="ef53d-105">When calling a WCF service from a WCF client, you can specify these credentials in managed code or in an application configuration file.</span></span> <span data-ttu-id="ef53d-106">Wenn Sie einen WCF-Dienst aus einer COM-Anwendung aufrufen, können Sie die- <xref:System.ServiceModel.ComIntegration.IChannelCredentials> Schnittstelle verwenden, um Anmelde Informationen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ef53d-106">When calling a WCF service from a COM application, you can use the <xref:System.ServiceModel.ComIntegration.IChannelCredentials> interface to specify credentials.</span></span> <span data-ttu-id="ef53d-107">In diesem Thema werden verschiedene Möglichkeiten zur Angabe von Anmeldeinformationen mithilfe der <xref:System.ServiceModel.ComIntegration.IChannelCredentials>-Schnittstelle erläutert.</span><span class="sxs-lookup"><span data-stu-id="ef53d-107">This topic will illustrate various ways to specify credentials using the <xref:System.ServiceModel.ComIntegration.IChannelCredentials> interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ef53d-108"><xref:System.ServiceModel.ComIntegration.IChannelCredentials> ist eine IDispatch-basierte Schnittstelle, und Sie erhalten keine IntelliSense-Funktionen in der Visual Studio-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="ef53d-108"><xref:System.ServiceModel.ComIntegration.IChannelCredentials> is an IDispatch-based interface and you will not get IntelliSense functionality in the Visual Studio environment.</span></span>  
  
 <span data-ttu-id="ef53d-109">In diesem Artikel wird der im [Nachrichten Sicherheits Beispiel](../../../../docs/framework/wcf/samples/message-security-sample.md)definierte WCF-Dienst verwendet.</span><span class="sxs-lookup"><span data-stu-id="ef53d-109">This article will use the WCF service defined in the [Message Security Sample](../../../../docs/framework/wcf/samples/message-security-sample.md).</span></span>  
  
### <a name="to-specify-a-client-certificate"></a><span data-ttu-id="ef53d-110">So geben Sie ein Clientzertifikat an:</span><span class="sxs-lookup"><span data-stu-id="ef53d-110">To specify a client certificate</span></span>  
  
1. <span data-ttu-id="ef53d-111">Führen Sie die Datei Setup.bat im Nachrichtensicherheitsverzeichnis aus, um die erforderlichen Testzertifikate zu erstellen und zu installieren.</span><span class="sxs-lookup"><span data-stu-id="ef53d-111">Run the Setup.bat file in the Message Security directory to create and install the required test certificates.</span></span>  
  
2. <span data-ttu-id="ef53d-112">Öffnen Sie das Nachrichtensicherheitsprojekt.</span><span class="sxs-lookup"><span data-stu-id="ef53d-112">Open the Message Security project.</span></span>  
  
3. <span data-ttu-id="ef53d-113">Fügen Sie `[ServiceBehavior(Namespace="http://Microsoft.ServiceModel.Samples")]` der `ICalculator` Schnittstellen Definition hinzu.</span><span class="sxs-lookup"><span data-stu-id="ef53d-113">Add `[ServiceBehavior(Namespace="http://Microsoft.ServiceModel.Samples")]` to the `ICalculator` interface definition.</span></span>  
  
4. <span data-ttu-id="ef53d-114">Fügen Sie dem `bindingNamespace="http://Microsoft.ServiceModel.Samples"` Endpunkt-Tag in der app. config-Datei für den Dienst hinzu.</span><span class="sxs-lookup"><span data-stu-id="ef53d-114">Add `bindingNamespace="http://Microsoft.ServiceModel.Samples"` to the endpoint tag in the App.config for the service.</span></span>  
  
5. <span data-ttu-id="ef53d-115">Erstellen Sie das Nachrichtensicherheitsbeispiel, und führen Sie Service.exe aus.</span><span class="sxs-lookup"><span data-stu-id="ef53d-115">Build the Message Security Sample and run Service.exe.</span></span> <span data-ttu-id="ef53d-116">Verwenden Sie Internet Explorer, und navigieren Sie zum URI des dienstangs ( `http://localhost:8000/ServiceModelSamples/Service` ), um sicherzustellen, dass der Dienst funktioniert.</span><span class="sxs-lookup"><span data-stu-id="ef53d-116">Use Internet Explorer and browse to the service's URI (`http://localhost:8000/ServiceModelSamples/Service`) to ensure that the service is working.</span></span>  
  
6. <span data-ttu-id="ef53d-117">Öffnen Sie Visual Basic 6.0, und erstellen Sie eine neue Standard-EXE-Datei.</span><span class="sxs-lookup"><span data-stu-id="ef53d-117">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="ef53d-118">Fügen Sie dem Formular eine Schaltfläche hinzu, und doppelklicken Sie darauf, um dem Click-Handler den folgenden Code hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ef53d-118">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
    ```vb  
        monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
        monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
        monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
        monString = monString + ", binding=BasicHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
        Set monikerProxy = GetObject(monString)  
  
        'Set the Service Certificate.  
     monikerProxy.ChannelCredentials.SetServiceCertificateAuthentication "CurrentUser", "NoCheck", "PeerOrChainTrust"  
    monikerProxy.ChannelCredentials.SetDefaultServiceCertificateFromStore "CurrentUser", "TrustedPeople", "FindBySubjectName", "localhost"  
  
        'Set the Client Certificate.  
        monikerProxy.ChannelCredentials.SetClientCertificateFromStoreByName "CN=client.com", "CurrentUser", "My"  
        MsgBox monikerProxy.Add(3, 4)  
    ```  
  
7. <span data-ttu-id="ef53d-119">Führen Sie die Visual Basic-Anwendung aus, und überprüfen Sie die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="ef53d-119">Run the Visual Basic application and verify the results.</span></span>  
  
     <span data-ttu-id="ef53d-120">Die Visual Basic-Anwendung zeigt ein Meldungsfeld mit dem Ergebnis des Aufrufs von Add(3, 4) an.</span><span class="sxs-lookup"><span data-stu-id="ef53d-120">The Visual Basic application will display a message box with the result from calling Add(3, 4).</span></span> <span data-ttu-id="ef53d-121"><xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromFile%28System.String%2CSystem.String%2CSystem.String%29> oder <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStoreByName%28System.String%2CSystem.String%2CSystem.String%29> können anstelle von <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStore%28System.String%2CSystem.String%2CSystem.String%2CSystem.Object%29> verwendet werden, um das Clientzertifikat festzulegen:</span><span class="sxs-lookup"><span data-stu-id="ef53d-121"><xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromFile%28System.String%2CSystem.String%2CSystem.String%29> or <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStoreByName%28System.String%2CSystem.String%2CSystem.String%29> can also be used in place of <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStore%28System.String%2CSystem.String%2CSystem.String%2CSystem.Object%29> to set the Client Certificate:</span></span>  
  
    ```vb  
    monikerProxy.ChannelCredentials.SetClientCertificateFromFile "C:\MyClientCert.pfx", "password", "DefaultKeySet"  
    ```  
  
> [!NOTE]
> <span data-ttu-id="ef53d-122">Damit dieser Aufruf funktioniert, muss das Clientzertifikat auf dem Computer, auf dem der Client ausgeführt wird, als vertrauenswürdig eingestuft sein.</span><span class="sxs-lookup"><span data-stu-id="ef53d-122">For this call to work, the client certificate needs to be trusted on the machine the client is running on.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ef53d-123">Ist der Moniker nicht ordnungsgemäß formatiert oder der Dienst nicht verfügbar, wird nach dem `GetObject`-Aufruf ein Syntaxfehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ef53d-123">If the moniker is malformed or if the service is unavailable, the call to `GetObject` will return an error saying "Invalid Syntax."</span></span> <span data-ttu-id="ef53d-124">Vergewissern Sie sich bei Auftreten dieses Fehlers, dass der verwendete Moniker korrekt und der Dienst verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ef53d-124">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
### <a name="to-specify-user-name-and-password"></a><span data-ttu-id="ef53d-125">So geben Sie einen Benutzernamen und ein Kennwort an:</span><span class="sxs-lookup"><span data-stu-id="ef53d-125">To specify user name and password</span></span>  
  
1. <span data-ttu-id="ef53d-126">Ändern Sie die Datei Service App.config, um `wsHttpBinding` zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ef53d-126">Modify the Service App.config file to use the `wsHttpBinding`.</span></span> <span data-ttu-id="ef53d-127">Dies ist für die Validierung von Benutzername und Kennwort erforderlich:</span><span class="sxs-lookup"><span data-stu-id="ef53d-127">This is required for user name and password validation:</span></span>  

2. <span data-ttu-id="ef53d-128">Legen Sie `clientCredentialType` auf UserName fest:</span><span class="sxs-lookup"><span data-stu-id="ef53d-128">Set the `clientCredentialType` to UserName:</span></span>  

3. <span data-ttu-id="ef53d-129">Öffnen Sie Visual Basic 6.0, und erstellen Sie eine neue Standard-EXE-Datei.</span><span class="sxs-lookup"><span data-stu-id="ef53d-129">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="ef53d-130">Fügen Sie dem Formular eine Schaltfläche hinzu, und doppelklicken Sie darauf, um dem Click-Handler den folgenden Code hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ef53d-130">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
    ```vb
    monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
    monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set monikerProxy = GetObject(monString)  
  
    monikerProxy.ChannelCredentials.SetServiceCertificateAuthentication "CurrentUser", "NoCheck", "PeerOrChainTrust"  
    monikerProxy.ChannelCredentials.SetUserNameCredential "username", "password"  
  
    MsgBox monikerProxy.Add(3, 4)  
    ```  
  
4. <span data-ttu-id="ef53d-131">Führen Sie die Visual Basic-Anwendung aus, und überprüfen Sie die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="ef53d-131">Run the Visual Basic application and verify the results.</span></span> <span data-ttu-id="ef53d-132">Die Visual Basic-Anwendung zeigt ein Meldungsfeld mit dem Ergebnis des Aufrufs von Add(3, 4) an.</span><span class="sxs-lookup"><span data-stu-id="ef53d-132">The Visual Basic application will display a message box with the result from calling Add(3, 4).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="ef53d-133">Die im Dienstmoniker in diesem Beispiel angegebene Bindung wurde in WSHttpBinding_ICalculator geändert.</span><span class="sxs-lookup"><span data-stu-id="ef53d-133">The binding specified in the service moniker in this sample has been changed to WSHttpBinding_ICalculator.</span></span> <span data-ttu-id="ef53d-134">Zudem müssen beim Aufruf von <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetUserNameCredential%28System.String%2CSystem.String%29> ein gültiger Benutzername und ein Kennwort angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ef53d-134">Also note that you must supply a valid user name and password in the call to <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetUserNameCredential%28System.String%2CSystem.String%29>.</span></span>  
  
### <a name="to-specify-windows-credentials"></a><span data-ttu-id="ef53d-135">So geben Sie Windows-Anmeldeinformationen an:</span><span class="sxs-lookup"><span data-stu-id="ef53d-135">To specify Windows Credentials</span></span>  
  
1. <span data-ttu-id="ef53d-136">Legen Sie `clientCredentialType` in der Datei Service App.config auf Windows fest:</span><span class="sxs-lookup"><span data-stu-id="ef53d-136">Set `clientCredentialType` to Windows in the Service App.config file:</span></span>  

2. <span data-ttu-id="ef53d-137">Öffnen Sie Visual Basic 6.0, und erstellen Sie eine neue Standard-EXE-Datei.</span><span class="sxs-lookup"><span data-stu-id="ef53d-137">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="ef53d-138">Fügen Sie dem Formular eine Schaltfläche hinzu, und doppelklicken Sie darauf, um dem Click-Handler den folgenden Code hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ef53d-138">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
    ```vb
    monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
    monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", upnidentity=domain\userID"  
  
    Set monikerProxy = GetObject(monString)  
     monikerProxy.ChannelCredentials.SetWindowsCredential "domain", "userID", "password", 1, True  
  
    MsgBox monikerProxy.Add(3, 4)  
    ```  
  
3. <span data-ttu-id="ef53d-139">Führen Sie die Visual Basic-Anwendung aus, und überprüfen Sie die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="ef53d-139">Run the Visual Basic application and verify the results.</span></span> <span data-ttu-id="ef53d-140">Die Visual Basic-Anwendung zeigt ein Meldungsfeld mit dem Ergebnis des Aufrufs von Add(3, 4) an.</span><span class="sxs-lookup"><span data-stu-id="ef53d-140">The Visual Basic application will display a message box with the result from calling Add(3, 4).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="ef53d-141">"Domäne", "Benutzer-ID" und "Kennwort" müssen durch gültige Werte ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="ef53d-141">You must replace "domain", "userID", and "password" with valid values.</span></span>  
  
### <a name="to-specify-an-issue-token"></a><span data-ttu-id="ef53d-142">So geben Sie ein Problemtoken an:</span><span class="sxs-lookup"><span data-stu-id="ef53d-142">To specify an issue token</span></span>  
  
1. <span data-ttu-id="ef53d-143">Problemtoken werden nur für Anwendungen, die verbundene Sicherheit verwenden, eingesetzt.</span><span class="sxs-lookup"><span data-stu-id="ef53d-143">Issue tokens are used only for applications using federated security.</span></span> <span data-ttu-id="ef53d-144">Weitere Informationen zur Verbund Sicherheit finden Sie unter Verbund [-und ausgestellte Token](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md) und Verbund [Beispiel](../../../../docs/framework/wcf/samples/federation-sample.md).</span><span class="sxs-lookup"><span data-stu-id="ef53d-144">For more information about federated security, see [Federation and Issued Tokens](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md) and [Federation Sample](../../../../docs/framework/wcf/samples/federation-sample.md).</span></span>  
  
     <span data-ttu-id="ef53d-145">Im folgenden Visual Basic-Codebeispiel wird veranschaulicht, wie die <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>-Methode aufgerufen wird:</span><span class="sxs-lookup"><span data-stu-id="ef53d-145">The following Visual Basic code example illustrates how to call the <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29> method:</span></span>  
  
    ```vb
        monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
        monString = monString + ", address=http://localhost:8000/SomeService/Service"  
        monString = monString + ", contract=ICalculator, contractNamespace=http://SomeService.Samples"  
        monString = monString + ", binding=WSHttpBinding_ISomeContract, bindingNamespace=http://SomeService.Samples"  
  
        Set monikerProxy = GetObject(monString)  
    monikerProxy.SetIssuedToken("http://somemachine/sts", "bindingType", "binding")  
    ```  
  
     <span data-ttu-id="ef53d-146">Weiter Informationen zu den Parametern für diese Methode finden Sie unter <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>.</span><span class="sxs-lookup"><span data-stu-id="ef53d-146">For more information about the parameters for this method, see <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef53d-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef53d-147">See also</span></span>

- [<span data-ttu-id="ef53d-148">Verbund</span><span class="sxs-lookup"><span data-stu-id="ef53d-148">Federation</span></span>](../../../../docs/framework/wcf/feature-details/federation.md)
- [<span data-ttu-id="ef53d-149">Vorgehensweise: Konfigurieren von Anmeldeinformationen auf einem Verbunddienst</span><span class="sxs-lookup"><span data-stu-id="ef53d-149">How to: Configure Credentials on a Federation Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="ef53d-150">Vorgehensweise: Erstellen eines Verbundclients</span><span class="sxs-lookup"><span data-stu-id="ef53d-150">How to: Create a Federated Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="ef53d-151">Nachrichtensicherheit</span><span class="sxs-lookup"><span data-stu-id="ef53d-151">Message Security</span></span>](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)
- [<span data-ttu-id="ef53d-152">Bindungen und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="ef53d-152">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)

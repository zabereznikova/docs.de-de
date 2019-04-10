---
title: WS 2007 Federation-HTTP-Bindung
ms.date: 03/30/2017
ms.assetid: 91c1b477-a96e-4bf5-9330-5e9312113371
ms.openlocfilehash: 550a88552658864e3eedb70463e676ad6f9a2511
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59324941"
---
# <a name="ws-2007-federation-http-binding"></a><span data-ttu-id="570c4-102">WS 2007 Federation-HTTP-Bindung</span><span class="sxs-lookup"><span data-stu-id="570c4-102">WS 2007 Federation HTTP Binding</span></span>
<span data-ttu-id="570c4-103">In diesem Beispiel wird die Verwendung von <xref:System.ServiceModel.WS2007FederationHttpBinding> veranschaulicht. Dabei handelt es sich um eine Standardbindung, mit der Sie verbundene Szenarien erstellen können, die die Version 1.3 der WS-Trust-Spezifikation unterstützen.</span><span class="sxs-lookup"><span data-stu-id="570c4-103">This sample demonstrates the use of <xref:System.ServiceModel.WS2007FederationHttpBinding>, a standard binding that you can use to build federated scenarios that support version 1.3 of the WS-Trust specification.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="570c4-104">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="570c4-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="570c4-105">Das Beispiel besteht aus einem konsolenbasierten Clientprogramm (Client.exe), einem konsolenbasierten Sicherheitstokendienstprogramm (Securitytokenservice.exe) und einem konsolenbasierten Dienstprogramm (Service.exe).</span><span class="sxs-lookup"><span data-stu-id="570c4-105">The sample consists of a console-based client program (Client.exe), a console-based security token service program (Securitytokenservice.exe), and a console-based service program (Service.exe).</span></span> <span data-ttu-id="570c4-106">Der Dienst implementiert einen Vertrag, der ein Anforderung-/Antwort-Kommunikationsmuster definiert.</span><span class="sxs-lookup"><span data-stu-id="570c4-106">The service implements a contract that defines a request/reply communication pattern.</span></span> <span data-ttu-id="570c4-107">Der Vertrag wird durch die `ICalculator`-Schnittstelle definiert, die mathematische Operationen (`Add`, `Subtract`, `Multiply` und `Divide`) verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="570c4-107">The contract is defined by the `ICalculator` interface, which exposes math operations (`Add`, `Subtract`, `Multiply`, and `Divide`).</span></span> <span data-ttu-id="570c4-108">Der Client empfängt ein Sicherheitstoken vom Sicherheitstokendienst (STS) und stellt beim Dienst synchrone Anforderungen an eine bestimmte mathematische Operation.</span><span class="sxs-lookup"><span data-stu-id="570c4-108">The client obtains a security token from the Security Token Service (STS) and makes synchronous requests to the service for a given math operation.</span></span> <span data-ttu-id="570c4-109">Der Dienst antwortet dann mit dem Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="570c4-109">The service then replies with the result.</span></span> <span data-ttu-id="570c4-110">Die Clientaktivität ist im Konsolenfenster sichtbar.</span><span class="sxs-lookup"><span data-stu-id="570c4-110">Client activity is visible in the console window.</span></span>  
  
 <span data-ttu-id="570c4-111">Im Beispiel wird der `ICalculator`-Vertrag mit dem `ws2007FederationHttpBinding`-Element verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="570c4-111">The sample makes the `ICalculator` contract available using the `ws2007FederationHttpBinding` element.</span></span> <span data-ttu-id="570c4-112">Das folgende Codebeispiel zeigt die Konfiguration dieser Bindung auf dem Client.</span><span class="sxs-lookup"><span data-stu-id="570c4-112">The configuration of this binding on the client is shown in the following code.</span></span>  
  
```xml  
<bindings>  
  <ws2007FederationHttpBinding>  
    <binding name="ServiceFed" >  
      <security mode ="Message">  
        <message issuedKeyType ="SymmetricKey"  
                 issuedTokenType ="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1" >  
          <!-- Endpoint address and binding for Security Token Service -->  
          <issuer address ="http://localhost:8000/sts/windows"   
                  binding ="ws2007HttpBinding" />                
        </message>  
      </security>  
    </binding>  
  </ws2007FederationHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="570c4-113">Auf der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md), `security` Wert gibt an, welcher Sicherheitsmodus verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="570c4-113">On the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md), the `security` value specifies which security mode should be used.</span></span> <span data-ttu-id="570c4-114">In diesem Beispiel wird `message` Sicherheit verwendet wird, wird daher die [ \<Nachricht >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) angegeben ist, in der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="570c4-114">In this sample, `message` security is used, which is why the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) is specified inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md).</span></span> <span data-ttu-id="570c4-115">Die [ \<Aussteller >](../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md) Element innerhalb der [ \<Nachricht >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) gibt die Adresse und Bindung für den STS an, die ein Sicherheitstoken an den Client ausgibt, damit der Client kann authentifizieren Sie sich bei der `ICalculator` Service.</span><span class="sxs-lookup"><span data-stu-id="570c4-115">The [\<issuer>](../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md) element inside the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) specifies the address and binding for the STS that issues a security token to the client so that the client can authenticate to the `ICalculator` service.</span></span>  
  
 <span data-ttu-id="570c4-116">Das folgende Codebeispiel zeigt die Konfiguration dieser Bindung auf dem Dienst.</span><span class="sxs-lookup"><span data-stu-id="570c4-116">The configuration of this binding on the service is shown in the following code.</span></span>  
  
```xml  
<bindings>  
  <ws2007FederationHttpBinding>  
    <binding name="ServiceFed" >  
      <security mode ="Message">  
        <message issuedKeyType ="SymmetricKey"  
                 issuedTokenType ="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1" >  
          <!-- Metadata address for Security Token Service -->  
          <issuerMetadata address ="http://localhost:8000/sts/mex" >  
            <identity>  
              <certificateReference storeLocation ="CurrentUser"   
                                    storeName="TrustedPeople"   
                                    x509FindType ="FindBySubjectDistinguishedName"   
                                    findValue ="CN=STS" />  
            </identity>  
          </issuerMetadata>  
        </message>  
      </security>  
    </binding>  
  </ws2007FederationHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="570c4-117">Auf der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md), `security` Wert gibt an, welcher Sicherheitsmodus verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="570c4-117">On the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md), the `security` value specifies which security mode should be used.</span></span> <span data-ttu-id="570c4-118">In diesem Beispiel wird `message` Sicherheit verwendet wird, wird daher die [ \<Nachricht >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) angegeben ist, in der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="570c4-118">In this sample, `message` security is used, which is why the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) is specified inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md).</span></span> <span data-ttu-id="570c4-119">Die [ \<"issuermetadata" >](../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md) Element `ws2007FederationHttpBinding` innerhalb der [ \<Nachricht >](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) gibt die Adresse und Identität für einen Endpunkt, der zum Abrufen von verwendet werden kann die Metadaten für den STS.</span><span class="sxs-lookup"><span data-stu-id="570c4-119">The [\<issuerMetadata>](../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md) element of `ws2007FederationHttpBinding` inside the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) specifies the address and identity for an endpoint that can be used to retrieve metadata for the STS.</span></span>  
  
 <span data-ttu-id="570c4-120">Das Verhalten für den Dienst wird im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="570c4-120">The behavior for the service is shown in the following code.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name ="ServiceBehaviour" >  
      <serviceDebug includeExceptionDetailInFaults ="true"/>  
      <serviceMetadata httpGetEnabled ="true"/>  
      <serviceCredentials>  
        <issuedTokenAuthentication>  
          <knownCertificates>  
            <add storeLocation ="LocalMachine"  
                 storeName="TrustedPeople"  
                 x509FindType="FindBySubjectDistinguishedName"  
                 findValue="CN=STS" />  
          </knownCertificates>  
        </issuedTokenAuthentication>  
        <serviceCertificate storeLocation ="LocalMachine"  
                            storeName ="My"  
                            x509FindType ="FindBySubjectDistinguishedName"  
                            findValue ="CN=localhost"/>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="570c4-121">Die [ \<IssuedTokenAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)> kann der Dienst Einschränkungen für die Token Geben sie die Clients bei der Authentifizierung ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="570c4-121">The [\<issuedTokenAuthentication>](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)> allows the service to specify constraints on the tokens it allows clients to present during authentication.</span></span> <span data-ttu-id="570c4-122">In dieser Konfiguration wird angegeben, dass von einem Zertifikat mit dem Ausstellernamen CN=STS signierte Token vom Dienst akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="570c4-122">This configuration specifies that tokens signed by a certificate whose subject name is CN=STS are accepted by the service.</span></span>  
  
 <span data-ttu-id="570c4-123">STS macht einen einzelnen Endpunkt durch die Standard-<xref:System.ServiceModel.WS2007HttpBinding> verfügbar.</span><span class="sxs-lookup"><span data-stu-id="570c4-123">STS makes a single endpoint available using the standard <xref:System.ServiceModel.WS2007HttpBinding>.</span></span> <span data-ttu-id="570c4-124">Der Dienst antwortet auf Token-Anforderungen von Clients.</span><span class="sxs-lookup"><span data-stu-id="570c4-124">The service responds to requests from clients for tokens.</span></span> <span data-ttu-id="570c4-125">Wenn der Client mit einem Windows-Konto authentifiziert ist, gibt der Dienst ein Token aus, das den Benutzernamen des Clients als einen Anspruch enthält.</span><span class="sxs-lookup"><span data-stu-id="570c4-125">If the client is authenticated using a Windows account, the service issues a token that contains the client's user name as a claim.</span></span> <span data-ttu-id="570c4-126">Beim Erstellen des Tokens signiert STS das Token mit dem privaten Schlüssel, der dem CN=STS-Zertifikat zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="570c4-126">As part of creating the token, STS signs the token using the private key associated with the CN=STS certificate.</span></span> <span data-ttu-id="570c4-127">Außerdem wird ein symmetrischer Schlüssel erstellt und mit dem öffentlichen Schlüssel verschlüsselt, der dem CN=localhost-Zertifikat zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="570c4-127">In addition, it creates a symmetric key and encrypts it using the public key associated with the CN=localhost certificate.</span></span> <span data-ttu-id="570c4-128">Beim Zurückgeben des Tokens an den Client gibt STS auch den symmetrischen Schlüssel zurück.</span><span class="sxs-lookup"><span data-stu-id="570c4-128">In returning the token to the client, STS also returns the symmetric key.</span></span> <span data-ttu-id="570c4-129">Der Client zeigt dem `ICalculator`-Dienst das ausgegebene Token und beweist, dass der symmetrische Schlüssel bekannt ist, indem die Nachricht mit diesem Schlüssel signiert wird.</span><span class="sxs-lookup"><span data-stu-id="570c4-129">The client presents the issued token to the `ICalculator` service and proves that it knows the symmetric key by signing the message with that key.</span></span>  
  
 <span data-ttu-id="570c4-130">Wenn Sie das Beispiel ausführen, wird die Anforderung des Sicherheitstokens im STS-Konsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="570c4-130">When you run the sample, the request for the security token is shown in the STS console window.</span></span> <span data-ttu-id="570c4-131">Die Anforderungen und Antworten des Vorgangs werden im Client- und Dienstkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="570c4-131">The operation's requests and responses are displayed in the client and service console windows.</span></span> <span data-ttu-id="570c4-132">Drücken Sie die EINGABETASTE in einem der Konsolenfenster, um die Anwendung zu schließen.</span><span class="sxs-lookup"><span data-stu-id="570c4-132">Press ENTER in any of the console windows to shut down the application.</span></span>  

```
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714
Press <ENTER> to terminate client.
```

 <span data-ttu-id="570c4-133">Mit der in diesem Beispiel enthaltenen Datei "Setup.bat" können Sie den Server und STS mit den relevanten Zertifikaten zum Ausführen einer selbst gehosteten Anwendung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="570c4-133">The Setup.bat file included with this sample allows you to configure the server and STS with the relevant certificates to run a self-hosted application.</span></span> <span data-ttu-id="570c4-134">Die Batchdatei erstellt zwei Zertifikate im Zertifikatspeicher LocalMachine/TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="570c4-134">The batch file creates two certificates in the LocalMachine/TrustedPeople certificate store.</span></span> <span data-ttu-id="570c4-135">Der Antragstellername des ersten Zertifikats lautet CN=STS. Dieses Zertifikat wird vom STS zum Signieren des Sicherheitstokens verwendet, das an den Client herausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="570c4-135">The first certificate has a subject name of CN=STS and is used by STS to sign the security tokens that it issues to the client.</span></span> <span data-ttu-id="570c4-136">Der Antragstellername des zweiten Zertifikats lautet CN=localhost. Dieses Zertifikat wird vom STS verwendet, um einen Schlüssel so zu verschlüsseln, dass er vom Dienst entschlüsselt werden kann.</span><span class="sxs-lookup"><span data-stu-id="570c4-136">The second certificate has a subject name of CN=localhost and is used by STS to encrypt a key in a way that the service can decrypt.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="570c4-137">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="570c4-137">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="570c4-138">Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="570c4-138">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="570c4-139">Öffnen Sie eine Developer-Eingabeaufforderung für Visual Studio mit Administratorrechten, und führen Sie die Datei "Setup.bat", um die erforderlichen Zertifikate zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="570c4-139">Open a Developer Command Prompt for Visual Studio with administrator privileges and run the Setup.bat file to create the required certificates.</span></span>  
  
 <span data-ttu-id="570c4-140">Diese Batchdatei verwendet Certmgr.exe und Makecert.exe, die mit dem Windows SDK verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="570c4-140">This batch file uses Certmgr.exe and Makecert.exe, which are distributed with the Windows SDK.</span></span> <span data-ttu-id="570c4-141">Sie müssen Setup.bat an einer Visual Studio-Eingabeaufforderung ausführen, sodass das Skript diese Tools finden kann.</span><span class="sxs-lookup"><span data-stu-id="570c4-141">However, you must run Setup.bat from within a Visual Studio  command prompt to enable the script to find these tools.</span></span>  
  
1. <span data-ttu-id="570c4-142">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="570c4-142">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="570c4-143">Folgen Sie den Anweisungen, um das Beispiel in einer Konfiguration für die einzelnen-Computer oder computerübergreifend auszuführen, [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="570c4-143">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span> <span data-ttu-id="570c4-144">Bei Verwendung von [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)], führen Sie Service.exe, Client.exe und SecurityTokenService.exe mit erweiterten Berechtigungen (mit der rechten Maustaste in der Dateien, und klicken Sie dann auf **als Administrator ausführen**).</span><span class="sxs-lookup"><span data-stu-id="570c4-144">If you are using [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)], you must run Service.exe, Client.exe, and SecurityTokenService.exe with elevated privileges (right-click the files and then click **Run as administrator**).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="570c4-145">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="570c4-145">The samples may already be installed on your computer.</span></span> <span data-ttu-id="570c4-146">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="570c4-146">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="570c4-147">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="570c4-147">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="570c4-148">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="570c4-148">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\WS2007FederationHttp`  

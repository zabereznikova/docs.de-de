---
title: Dienstidentitätsbeispiel
ms.date: 03/30/2017
ms.assetid: 79fa8c1c-85bb-4b67-bc67-bfaf721303f8
ms.openlocfilehash: eb2dd3c6392164905cf755075856608ec5fcaf30
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837791"
---
# <a name="service-identity-sample"></a><span data-ttu-id="bb360-102">Dienstidentitätsbeispiel</span><span class="sxs-lookup"><span data-stu-id="bb360-102">Service Identity Sample</span></span>
<span data-ttu-id="bb360-103">Dieses Dienstidentitätsbeispiel veranschaulicht das Festlegen der Identität eines Diensts.</span><span class="sxs-lookup"><span data-stu-id="bb360-103">This service identity sample demonstrates how to set the identity for a service.</span></span> <span data-ttu-id="bb360-104">Während der Entwurfszeit kann ein Client die Identität mithilfe der Metadaten des Diensts abrufen und zur Laufzeit die Identität des Diensts authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="bb360-104">At design time, a client can retrieve the identity using the service's metadata and then at runtime the client can authenticate the service's identity.</span></span> <span data-ttu-id="bb360-105">Das Konzept der Dienstidentität besteht darin, dass ein Client einen Dienst authentifizieren kann, bevor er einen seiner Vorgänge aufruft. Auf diese Weise wird der Client vor nicht authentifizierten Aufrufen geschützt.</span><span class="sxs-lookup"><span data-stu-id="bb360-105">The concept of service identity is to allow a client to authenticate a service before calling any of its operations, thereby protecting the client from unauthenticated calls.</span></span> <span data-ttu-id="bb360-106">Bei einer sicheren Verbindung authentifiziert der Dienst auch die Anmeldeinformationen eines Clients, bevor er diesem Zugriff gewährt. Diese Funktion steht jedoch nicht im Mittelpunkt dieses Beispiels.</span><span class="sxs-lookup"><span data-stu-id="bb360-106">On a secure connection the service also authenticates a client's credentials before allowing it access, but this is not the focus of this sample.</span></span> <span data-ttu-id="bb360-107">Sehen Sie sich die Beispiele in [Client](../../../../docs/framework/wcf/samples/client.md) an, die die Server Authentifizierung anzeigen.</span><span class="sxs-lookup"><span data-stu-id="bb360-107">See the samples in [Client](../../../../docs/framework/wcf/samples/client.md) that show server authentication.</span></span>

> [!NOTE]
> <span data-ttu-id="bb360-108">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="bb360-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

 <span data-ttu-id="bb360-109">In diesem Beispiel werden die folgenden Funktionen veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="bb360-109">This sample illustrates the following features:</span></span>

- <span data-ttu-id="bb360-110">Wie die verschiedenen Identitätstypen auf unterschiedlichen Endpunkten zu einem Dienst festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="bb360-110">How to set the different types of identity on different endpoints for a service.</span></span> <span data-ttu-id="bb360-111">Jeder Identitätstyp hat andere Funktionen.</span><span class="sxs-lookup"><span data-stu-id="bb360-111">Each type of identity has different capabilities.</span></span> <span data-ttu-id="bb360-112">Der zu verwendende Identitätstyp ist vom Typ der Sicherheitsanmeldeinformationen abhängig, die bei der Bindung des Endpunkts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bb360-112">The type of identity to use is dependent on the type of security credentials used on the endpoint's binding.</span></span>

- <span data-ttu-id="bb360-113">Die Identität kann entweder deklarativ in der Konfiguration oder imperativ im Code festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="bb360-113">Identity can either be set declaratively in configuration or imperatively in code.</span></span> <span data-ttu-id="bb360-114">In der Regel sollten Sie sowohl für den Client als auch für den Dienst die Konfiguration verwenden, um die Identität festzulegen.</span><span class="sxs-lookup"><span data-stu-id="bb360-114">Typically for both the client and the service you should use configuration to set the identity.</span></span>

- <span data-ttu-id="bb360-115">Gewusst wie: Festlegen einer benutzerdefinierten Identität für den Client</span><span class="sxs-lookup"><span data-stu-id="bb360-115">How to set a custom identity on the client.</span></span> <span data-ttu-id="bb360-116">Eine benutzerdefinierte Identität ist normalerweise eine Anpassung eines vorhandenen Identitätstyps, mit dem ein Client andere in den Dienstanmeldeinformationen enthaltene Anspruchsinformationen überprüfen kann. Auf diese Weise können Autorisierungsentscheidungen getroffen werden, bevor der Dienst aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="bb360-116">A custom identity is typically a customization of an existing type of identity that enables the client to examine other claim information provided in the service's credentials to make authorization decisions before calling the service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bb360-117">Dieses Beispiel überprüft die Identität eines Zertifikats mit der Bezeichnung "identity.com" und den RSA-Schlüssel in diesem Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="bb360-117">This sample checks the identity of a specific certificate called identity.com and the RSA key contained within this certificate.</span></span> <span data-ttu-id="bb360-118">Wenn Sie die Identitätstypen "Zertifikat" und "RSA" in der Konfiguration des Clients verwenden, können diese Werte problemlos durch das Überprüfen des WSDL für den Dienst abgerufen werden, auf dem diese Werte serialisiert sind.</span><span class="sxs-lookup"><span data-stu-id="bb360-118">When using the Certificate and RSA identity types in configuration on the client, an easy way to get these values is to inspect the WSDL for the service where these values are serialized.</span></span>

 <span data-ttu-id="bb360-119">Der folgende Beispielcode zeigt, wie Sie mit "WSHttpBinding" die Identität eines Dienstendpunkts mit dem DNS (Domain Name Server) eines Zertifikats konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="bb360-119">The following sample code shows how to configure the identity of a service endpoint with the Domain Name Server (DNS) of a certificate using a WSHttpBinding.</span></span>

```csharp
//Create a service endpoint and set its identity to the certificate's DNS
WSHttpBinding wsAnonbinding = new WSHttpBinding (SecurityMode.Message);
// Client are Anonymous to the service
wsAnonbinding.Security.Message.ClientCredentialType = MessageCredentialType.None;
WServiceEndpoint ep = serviceHost.AddServiceEndpoint(typeof(ICalculator),wsAnonbinding, String.Empty);
EndpointAddress epa = new EndpointAddress(dnsrelativeAddress,EndpointIdentity.CreateDnsIdentity("identity.com"));
ep.Address = epa;
```

 <span data-ttu-id="bb360-120">Die Identität kann auch in der Konfiguration der Datei "App.config" angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bb360-120">The identity can also be specified in configuration in the App.config file.</span></span> <span data-ttu-id="bb360-121">Im folgenden Beispiel wird gezeigt, wie die UPN-Identität (User Principal Name) für einen Dienstendpunkt festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="bb360-121">The following example shows how to set the UPN (User Principal Name) identity for a service endpoint.</span></span>

```xml
<endpoint address="upnidentity"
        behaviorConfiguration=""
        binding="wsHttpBinding"
        bindingConfiguration="WSHttpBinding_Windows"
        name="WSHttpBinding_ICalculator_Windows"
        contract="Microsoft.ServiceModel.Samples.ICalculator">
  <!-- Set the UPN identity for this endpoint -->
  <identity>
      <userPrincipalName value="host\myservice.com" />
  </identity >
</endpoint>
```

 <span data-ttu-id="bb360-122">Eine benutzerdefinierte Identität kann durch Ableiten von den <xref:System.ServiceModel.EndpointIdentity>- und <xref:System.ServiceModel.Security.IdentityVerifier>-Klassen auf dem Client eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="bb360-122">A custom identity can be set on the client by deriving from the <xref:System.ServiceModel.EndpointIdentity> and the <xref:System.ServiceModel.Security.IdentityVerifier> classes.</span></span> <span data-ttu-id="bb360-123">Im Prinzip kann die <xref:System.ServiceModel.Security.IdentityVerifier>-Klasse als Cliententsprechung der `AuthorizationManager`-Klasse des Diensts betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="bb360-123">Conceptually the <xref:System.ServiceModel.Security.IdentityVerifier> class can be considered to be the client equivalent of the service's `AuthorizationManager` class.</span></span> <span data-ttu-id="bb360-124">Im folgenden Codebeispiel wird eine Implementierung von `OrgEndpointIdentity` veranschaulicht. Hier wird der Name einer Organisation gespeichert, der mit dem Antragstellernamen des Serverzertifikats verglichen wird.</span><span class="sxs-lookup"><span data-stu-id="bb360-124">The following code example shows an implementation of `OrgEndpointIdentity`, which stores an organization name to match in the subject name of the server's certificate.</span></span> <span data-ttu-id="bb360-125">Die Autorisierungsprüfung des Organisationsnamens findet in der `CheckAccess`-Methode der `CustomIdentityVerifier`-Klasse statt.</span><span class="sxs-lookup"><span data-stu-id="bb360-125">The authorization check for the organization name occurs in the `CheckAccess` method on the `CustomIdentityVerifier` class.</span></span>

```csharp
// This custom EndpointIdentity stores an organization name
public class OrgEndpointIdentity : EndpointIdentity
{
    private string orgClaim;
    public OrgEndpointIdentity(string orgName)
    {
        orgClaim = orgName;
    }
    public string OrganizationClaim
    {
        get { return orgClaim; }
        set { orgClaim = value; }
    }
}

//This custom IdentityVerifier uses the supplied OrgEndpointIdentity to
//check that X.509 certificate's distinguished name claim contains
//the organization name e.g. the string value "O=Contoso"
class CustomIdentityVerifier : IdentityVerifier
{
    public override bool CheckAccess(EndpointIdentity identity, AuthorizationContext authContext)
    {
        bool returnvalue = false;
        foreach (ClaimSet claimset in authContext.ClaimSets)
        {
            foreach (Claim claim in claimset)
            {
                if (claim.ClaimType == "http://schemas.microsoft.com/ws/2005/05/identity/claims/x500distinguishedname")
                {
                    X500DistinguishedName name = (X500DistinguishedName)claim.Resource;
                    if (name.Name.Contains(((OrgEndpointIdentity)identity).OrganizationClaim))
                    {
                        Console.WriteLine("Claim Type: {0}",claim.ClaimType);
                        Console.WriteLine("Right: {0}", claim.Right);
                        Console.WriteLine("Resource: {0}",claim.Resource);
                        Console.WriteLine();
                        returnvalue = true;
                    }
                }
            }
        }
        return returnvalue;
    }
}
```

 <span data-ttu-id="bb360-126">In diesem Beispiel wird ein Zertifikat namens "identity.com" verwendet, das sich im sprachspezifischen Identitätsprojektmappenordner befindet.</span><span class="sxs-lookup"><span data-stu-id="bb360-126">This sample uses a certificate called identity.com which is in the language-specific Identity solution folder.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="bb360-127">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="bb360-127">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="bb360-128">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="bb360-128">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="bb360-129">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="bb360-129">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="bb360-130">Um das Beispiel in einer Konfiguration mit einem Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="bb360-130">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="bb360-131">So führen Sie das Beispiel auf demselben Computer aus</span><span class="sxs-lookup"><span data-stu-id="bb360-131">To run the sample on the same computer</span></span>

1. <span data-ttu-id="bb360-132">Importieren Sie unter [!INCLUDE[wxp](../../../../includes/wxp-md.md)] oder Windows Vista die Identity. pfx-Zertifikat Datei im Identitäts Lösungs Ordner mithilfe des MMC-Snap-in-Tools in den Zertifikat Speicher LocalMachine/My (Personal).</span><span class="sxs-lookup"><span data-stu-id="bb360-132">On [!INCLUDE[wxp](../../../../includes/wxp-md.md)] or Windows Vista, import the Identity.pfx certificate file in the Identity solution folder into the LocalMachine/My (Personal) certificate store using the MMC snap-in tool.</span></span> <span data-ttu-id="bb360-133">Diese Datei ist durch ein Kennwort geschützt.</span><span class="sxs-lookup"><span data-stu-id="bb360-133">This file is password protected.</span></span> <span data-ttu-id="bb360-134">Während des Imports werden Sie um ein Kennwort gebeten.</span><span class="sxs-lookup"><span data-stu-id="bb360-134">During the import you are asked for a password.</span></span> <span data-ttu-id="bb360-135">Geben Sie `xyz` in das Feld Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="bb360-135">Type `xyz` into the password box.</span></span> <span data-ttu-id="bb360-136">Weitere Informationen finden Sie im Thema Gewusst [wie: Anzeigen von Zertifikaten mit dem MMC-Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md) .</span><span class="sxs-lookup"><span data-stu-id="bb360-136">For more information, see the [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md) topic.</span></span> <span data-ttu-id="bb360-137">Führen Sie anschließend die Datei "Setup. bat" in einer Developer-Eingabeaufforderung für Visual Studio mit Administratorrechten aus, die dieses Zertifikat zur Verwendung auf dem Client in den Speicher "CurrentUser/Trusted People" kopiert.</span><span class="sxs-lookup"><span data-stu-id="bb360-137">Once this is done, run Setup.bat in a Developer Command Prompt for Visual Studio with administrator privileges, which copies this certificate to the CurrentUser/Trusted People store for use on the client.</span></span>

2. <span data-ttu-id="bb360-138">Führen Sie auf [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]die Datei "Setup. bat" aus dem Beispiel Installationsordner innerhalb einer Visual Studio 2012-Eingabeaufforderung mit Administratorrechten aus.</span><span class="sxs-lookup"><span data-stu-id="bb360-138">On [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], run Setup.bat from the sample install folder inside a Visual Studio 2012 command prompt with administrator privileges.</span></span> <span data-ttu-id="bb360-139">Hiermit werden alle Zertifikate installiert, die zum Ausführen des Beispiels erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="bb360-139">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bb360-140">Die Batchdatei "Setup. bat" ist so konzipiert, dass Sie über eine Visual Studio 2012-Eingabeaufforderung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bb360-140">The Setup.bat batch file is designed to be run from a Visual Studio 2012 Command Prompt.</span></span> <span data-ttu-id="bb360-141">Die in der Visual Studio 2012-Eingabeaufforderung festgelegte PATH-Umgebungsvariable verweist auf das Verzeichnis, das ausführbare Dateien enthält, die für das Skript "Setup. bat" erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="bb360-141">The PATH environment variable set within the Visual Studio 2012 Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span> <span data-ttu-id="bb360-142">Wenn Sie mit dem Beispiel fertig sind, müssen Sie die Datei Cleanup.bat ausführen, um die Zertifikate zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="bb360-142">Ensure that you remove the certificates by running Cleanup.bat when you have finished with the sample.</span></span> <span data-ttu-id="bb360-143">In anderen Sicherheitsbeispielen werden die gleichen Zertifikate verwendet.</span><span class="sxs-lookup"><span data-stu-id="bb360-143">Other security samples use the same certificates.</span></span>  
  
3. <span data-ttu-id="bb360-144">Starten Sie "Service.exe" aus dem Verzeichnis "\service\bin".</span><span class="sxs-lookup"><span data-stu-id="bb360-144">Launch Service.exe from the \service\bin directory.</span></span> <span data-ttu-id="bb360-145">Stellen Sie sicher, dass der Dienst darauf hinweist, dass er bereit ist, und zeigt eine Eingabeaufforderung an, um \<Eingabe > zum Beenden des Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="bb360-145">Ensure that the service indicates that it is ready and displays a prompt to Press \<Enter> to terminate the service.</span></span>  
  
4. <span data-ttu-id="bb360-146">Starten Sie "Client.exe" aus dem Verzeichnis "\client\bin" oder durch das Drücken der Taste F5 in Visual Studio zum Erstellen und Ausführen.</span><span class="sxs-lookup"><span data-stu-id="bb360-146">Launch Client.exe from \client\bin directory or by pressing F5 in Visual Studio to build and run.</span></span> <span data-ttu-id="bb360-147">In der Clientkonsolenanwendung wird Clientaktivität angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bb360-147">Client activity is displayed on the client console application.</span></span>  
  
5. <span data-ttu-id="bb360-148">Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="bb360-148">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="bb360-149">So führen Sie das Beispiel computerübergreifend aus</span><span class="sxs-lookup"><span data-stu-id="bb360-149">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="bb360-150">Bevor Sie die Clientseite des Beispiels erstellen, müssen Sie den Wert der Dienstendpunktadresse in der Datei Client.cs in der `CallServiceCustomClientIdentity`-Methode ändern.</span><span class="sxs-lookup"><span data-stu-id="bb360-150">Before building the client part of the sample, be sure to change the value for the service's endpoint address in the Client.cs file in the `CallServiceCustomClientIdentity` method.</span></span> <span data-ttu-id="bb360-151">Erstellen Sie anschließend das Beispiel.</span><span class="sxs-lookup"><span data-stu-id="bb360-151">Then build the sample.</span></span>  
  
2. <span data-ttu-id="bb360-152">Erstellen Sie auf dem Dienstcomputer ein Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="bb360-152">Create a directory on the service computer.</span></span>  
  
3. <span data-ttu-id="bb360-153">Kopieren Sie die Dienstprogrammdateien aus service\bin in das Verzeichnis auf dem Dienstcomputer.</span><span class="sxs-lookup"><span data-stu-id="bb360-153">Copy the service program files from service\bin to the directory on the service computer.</span></span> <span data-ttu-id="bb360-154">Kopieren Sie außerdem die Dateien Setup.bat und Cleanup.bat auf den Dienstcomputer.</span><span class="sxs-lookup"><span data-stu-id="bb360-154">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
4. <span data-ttu-id="bb360-155">Erstellen Sie auf dem Clientcomputer ein Verzeichnis für die Clientbinärdateien.</span><span class="sxs-lookup"><span data-stu-id="bb360-155">Create a directory on the client computer for the client binaries.</span></span>  
  
5. <span data-ttu-id="bb360-156">Kopieren Sie die Clientprogrammdateien in das Clientverzeichnis auf dem Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="bb360-156">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="bb360-157">Kopieren Sie die Dateien Setup.bat, Cleanup.bat und ImportServiceCert.bat ebenfalls auf den Client.</span><span class="sxs-lookup"><span data-stu-id="bb360-157">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
6. <span data-ttu-id="bb360-158">Führen Sie für den Dienst `setup.bat service` in einem Developer-Eingabeaufforderung für Visual Studio aus, das mit Administratorrechten geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="bb360-158">On the service, run `setup.bat service` in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="bb360-159">Beim Ausführen von `setup.bat` mit dem `service`-Argument wird ein Dienst Zertifikat mit dem voll qualifizierten Domänen Namen des Computers erstellt und in die Datei Service. CER exportiert.</span><span class="sxs-lookup"><span data-stu-id="bb360-159">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
7. <span data-ttu-id="bb360-160">Kopieren Sie die Datei Service.cer aus dem Dienstverzeichnis in das Clientverzeichnis auf dem Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="bb360-160">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
8. <span data-ttu-id="bb360-161">Ändern Sie in der Datei Client.exe.config auf dem Clientcomputer den Wert für die Adresse des Endpunkts, sodass er mit der neuen Adresse Ihres Diensts übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="bb360-161">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="bb360-162">Es gibt mehrere Instanzen, die geändert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="bb360-162">There are multiple instances that must be changed.</span></span>  
  
9. <span data-ttu-id="bb360-163">Führen Sie auf dem Client ImportServiceCert. bat in einem Developer-Eingabeaufforderung für Visual Studio aus, das mit Administratorrechten geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="bb360-163">On the client, run ImportServiceCert.bat in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="bb360-164">Dadurch wird das Dienstzertifikat aus der Datei Service.cer in den Speicher CurrentUser – TrustedPeople importiert.</span><span class="sxs-lookup"><span data-stu-id="bb360-164">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
10. <span data-ttu-id="bb360-165">Starten Sie auf dem Dienstcomputer Service.exe an einer Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="bb360-165">On the service computer, launch the Service.exe from the command prompt.</span></span>  
  
11. <span data-ttu-id="bb360-166">Starten Sie auf dem Clientcomputer Client.exe an einer Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="bb360-166">On the client computer, launch Client.exe from a command prompt.</span></span> <span data-ttu-id="bb360-167">Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="bb360-167">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="bb360-168">So stellen Sie den Zustand vor Ausführung des Beispiels wieder her</span><span class="sxs-lookup"><span data-stu-id="bb360-168">To clean up after the sample</span></span>  
  
- <span data-ttu-id="bb360-169">Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie das Beispiel fertig ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="bb360-169">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="bb360-170">Wenn dieses Beispiel computerübergreifend ausgeführt wird, entfernt dieses Skript keine Dienstzertifikate auf einem Client.</span><span class="sxs-lookup"><span data-stu-id="bb360-170">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="bb360-171">Wenn Sie Windows Communication Foundation (WCF)-Beispiele ausgeführt haben, die Zertifikate Computer übergreifend verwenden, müssen Sie sicherstellen, dass Sie die Dienst Zertifikate löschen, die im Speicher CurrentUser-treudpeople installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="bb360-171">If you have run Windows Communication Foundation (WCF) samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="bb360-172">Verwenden Sie dazu den folgenden Befehl: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Beispiel: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="bb360-172">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>

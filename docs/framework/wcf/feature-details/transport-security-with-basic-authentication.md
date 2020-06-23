---
title: Transportsicherheit mit Standardauthentifizierung
description: Lesen Sie dieses WCF-Szenario, in dem die Standard Authentifizierung für einen WCF-Dienst und-Client dargestellt wird. Der Dienst benötigt ein gültiges Zertifikat, dem der Client vertraut.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b54f491d-196b-4279-876c-76b83ec0442c
ms.openlocfilehash: f15a19feaed631a76948efd24ee225acf789cb2d
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244854"
---
# <a name="transport-security-with-basic-authentication"></a><span data-ttu-id="6a83b-104">Transportsicherheit mit Standardauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="6a83b-104">Transport Security with Basic Authentication</span></span>
<span data-ttu-id="6a83b-105">Die folgende Abbildung zeigt einen Windows Communication Foundation (WCF)-Dienst und-Client.</span><span class="sxs-lookup"><span data-stu-id="6a83b-105">The following illustration shows a Windows Communication Foundation (WCF) service and client.</span></span> <span data-ttu-id="6a83b-106">Der Server benötigt ein gültiges X.509-Zertifikat, das für Secure Sockets Layer (SSL) verwendet werden kann, und die Clients müssen das Zertifikat des Servers als vertrauenswürdig ansehen.</span><span class="sxs-lookup"><span data-stu-id="6a83b-106">The server needs a valid X.509 certificate that can be used for Secure Sockets Layer (SSL), and the clients must trust the server’s certificate.</span></span> <span data-ttu-id="6a83b-107">Außerdem verfügt der Webdienst bereits über eine SSL-Implementierung, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="6a83b-107">Further, the Web service already has an SSL implementation that can be used.</span></span> <span data-ttu-id="6a83b-108">Weitere Informationen zum Aktivieren der Standard Authentifizierung für Internetinformationsdienste (IIS) finden Sie unter <https://docs.microsoft.com/iis/configuration/system.webserver/security/authentication/basicauthentication> .</span><span class="sxs-lookup"><span data-stu-id="6a83b-108">For more information about enabling basic authentication on Internet Information Services (IIS), see <https://docs.microsoft.com/iis/configuration/system.webserver/security/authentication/basicauthentication>.</span></span>  
  
 ![Screenshot, der die Transportsicherheit mit Standard Authentifizierung anzeigt.](./media/transport-security-with-basic-authentication/transport-security-basic-authentication.gif)  
  
|<span data-ttu-id="6a83b-110">Merkmal</span><span class="sxs-lookup"><span data-stu-id="6a83b-110">Characteristic</span></span>|<span data-ttu-id="6a83b-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6a83b-111">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="6a83b-112">Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="6a83b-112">Security Mode</span></span>|<span data-ttu-id="6a83b-113">Transport</span><span class="sxs-lookup"><span data-stu-id="6a83b-113">Transport</span></span>|  
|<span data-ttu-id="6a83b-114">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="6a83b-114">Interoperability</span></span>|<span data-ttu-id="6a83b-115">Mit vorhandenen Webdienstclients und Diensten</span><span class="sxs-lookup"><span data-stu-id="6a83b-115">With existing Web service clients and services</span></span>|  
|<span data-ttu-id="6a83b-116">Authentifizierung (Server)</span><span class="sxs-lookup"><span data-stu-id="6a83b-116">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="6a83b-117">Authentifizierung (Client)</span><span class="sxs-lookup"><span data-stu-id="6a83b-117">Authentication (Client)</span></span>|<span data-ttu-id="6a83b-118">Ja (mithilfe von HTTPS)</span><span class="sxs-lookup"><span data-stu-id="6a83b-118">Yes (using HTTPS)</span></span><br /><br /> <span data-ttu-id="6a83b-119">Ja (mithilfe von Benutzername/Kennwort)</span><span class="sxs-lookup"><span data-stu-id="6a83b-119">Yes (through User name/Password)</span></span>|  
|<span data-ttu-id="6a83b-120">Integrität</span><span class="sxs-lookup"><span data-stu-id="6a83b-120">Integrity</span></span>|<span data-ttu-id="6a83b-121">Ja</span><span class="sxs-lookup"><span data-stu-id="6a83b-121">Yes</span></span>|  
|<span data-ttu-id="6a83b-122">Vertraulichkeit</span><span class="sxs-lookup"><span data-stu-id="6a83b-122">Confidentiality</span></span>|<span data-ttu-id="6a83b-123">Ja</span><span class="sxs-lookup"><span data-stu-id="6a83b-123">Yes</span></span>|  
|<span data-ttu-id="6a83b-124">Transport</span><span class="sxs-lookup"><span data-stu-id="6a83b-124">Transport</span></span>|<span data-ttu-id="6a83b-125">HTTPS</span><span class="sxs-lookup"><span data-stu-id="6a83b-125">HTTPS</span></span>|  
|<span data-ttu-id="6a83b-126">Bindung</span><span class="sxs-lookup"><span data-stu-id="6a83b-126">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="6a83b-127">Dienst</span><span class="sxs-lookup"><span data-stu-id="6a83b-127">Service</span></span>  
 <span data-ttu-id="6a83b-128">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6a83b-128">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="6a83b-129">Führen Sie eines der folgenden Verfahren aus:</span><span class="sxs-lookup"><span data-stu-id="6a83b-129">Do one of the following:</span></span>  
  
- <span data-ttu-id="6a83b-130">Erstellen Sie einen separaten Dienst, indem Sie den Code ohne Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="6a83b-130">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="6a83b-131">Erstellen Sie mit der angegebenen Konfiguration einen Dienst, aber definieren Sie keine Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="6a83b-131">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="6a83b-132">Code</span><span class="sxs-lookup"><span data-stu-id="6a83b-132">Code</span></span>  
 <span data-ttu-id="6a83b-133">Der folgende Code zeigt, wie Sie einen Dienstendpunkt erstellen, der zur Sicherstellung der Übertragungssicherheit einen Benutzernamen und ein Kennwort für die Windows-Domäne verwendet.</span><span class="sxs-lookup"><span data-stu-id="6a83b-133">The following code shows how to create a service endpoint that uses a Windows domain user name and password for transfer security.</span></span> <span data-ttu-id="6a83b-134">Beachten Sie, dass der Dienst ein X.509-Zertifikat erfordert, um den Client zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="6a83b-134">Note that the service requires an X.509 certificate to authenticate to the client.</span></span> <span data-ttu-id="6a83b-135">Weitere Informationen finden Sie unter [Arbeiten mit Zertifikaten](working-with-certificates.md) und Gewusst [wie: Konfigurieren eines Ports mit einem SSL-Zertifikat](how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="6a83b-135">For more information, see [Working with Certificates](working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>  
  
 [!code-csharp[C_SecurityScenarios#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#1)]
 [!code-vb[C_SecurityScenarios#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#1)]  
  
## <a name="configuration"></a><span data-ttu-id="6a83b-136">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="6a83b-136">Configuration</span></span>  
 <span data-ttu-id="6a83b-137">Der folgende Code konfiguriert einen Dienst, um die Standardauthentifizierung mit der Sicherheit auf Transportebene zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="6a83b-137">The following configures a service to use basic authentication with transport-level security:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
    <system.serviceModel>  
        <bindings>  
            <wsHttpBinding>  
                <binding name="UsernameWithTransport">  
                    <security mode="Transport">  
                        <transport clientCredentialType="Basic" />  
                    </security>  
                </binding>  
            </wsHttpBinding>  
        </bindings>  
        <services>  
            <service name="BasicAuthentication.Calculator">  
                <endpoint address="https://localhost/Calculator"  
                          binding="wsHttpBinding"
                          bindingConfiguration="UsernameWithTransport"  
                          name="BasicEndpoint"
                          contract="BasicAuthentication.ICalculator" />  
            </service>  
        </services>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="6a83b-138">Client</span><span class="sxs-lookup"><span data-stu-id="6a83b-138">Client</span></span>  
  
### <a name="code"></a><span data-ttu-id="6a83b-139">Code</span><span class="sxs-lookup"><span data-stu-id="6a83b-139">Code</span></span>  
 <span data-ttu-id="6a83b-140">Der folgende Code zeigt den Clientcode, der den Benutzernamen und das Kennwort enthält.</span><span class="sxs-lookup"><span data-stu-id="6a83b-140">The following code shows the client code that includes the user name and password.</span></span> <span data-ttu-id="6a83b-141">Beachten Sie, dass der Benutzer einen gültigen Windows-Benutzernamen und ein Kennwort angeben muss.</span><span class="sxs-lookup"><span data-stu-id="6a83b-141">Note that the user must provide a valid Windows user name and password.</span></span> <span data-ttu-id="6a83b-142">Der Code zum Zurückgeben des Benutzernamens und des Kennworts ist hier nicht gezeigt.</span><span class="sxs-lookup"><span data-stu-id="6a83b-142">The code to return the user name and password is not shown here.</span></span> <span data-ttu-id="6a83b-143">Verwenden Sie ein Dialogfeld oder ein anderes Oberflächenelement, um die Informationen vom Benutzer abzufragen.</span><span class="sxs-lookup"><span data-stu-id="6a83b-143">Use a dialog box or other interface to query the user for the information.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6a83b-144">Sie können den Benutzernamen und das Kennwort nur mithilfe von Code festlegen.</span><span class="sxs-lookup"><span data-stu-id="6a83b-144">User name and password can only be set using code.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#2)]
 [!code-vb[C_SecurityScenarios#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="6a83b-145">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="6a83b-145">Configuration</span></span>  
 <span data-ttu-id="6a83b-146">Der folgende Code zeigt die Clientkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="6a83b-146">The following code shows the client configuration.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6a83b-147">Sie können die Konfiguration nicht verwenden, um den Benutzernamen und das Kennwort festzulegen.</span><span class="sxs-lookup"><span data-stu-id="6a83b-147">You cannot use configuration to set the user name and password.</span></span> <span data-ttu-id="6a83b-148">Die hier gezeigte Konfiguration muss mithilfe von Code erweitert werden, um den Benutzernamen und das Kennwort festzulegen.</span><span class="sxs-lookup"><span data-stu-id="6a83b-148">The configuration shown here must be augmented using code to set the user name and password.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Transport">  
            <transport clientCredentialType="Basic" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="https://machineName/Calculator"
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6a83b-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6a83b-149">See also</span></span>

- <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>
- [<span data-ttu-id="6a83b-150">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="6a83b-150">Working with Certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="6a83b-151">Vorgehensweise: Konfigurieren eines Anschlusses mit einem SSL-Zertifikat</span><span class="sxs-lookup"><span data-stu-id="6a83b-151">How to: Configure a Port with an SSL Certificate</span></span>](how-to-configure-a-port-with-an-ssl-certificate.md)
- [<span data-ttu-id="6a83b-152">Sicherheitsübersicht</span><span class="sxs-lookup"><span data-stu-id="6a83b-152">Security Overview</span></span>](security-overview.md)
- [\<clientCredentials>](../../configure-apps/file-schema/wcf/clientcredentials.md)
- <span data-ttu-id="6a83b-153">[Sicherheitsmodell für Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="6a83b-153">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>

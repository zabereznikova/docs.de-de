---
title: WS-Transport mit Nachrichtenanmeldeinformationen
ms.date: 03/30/2017
ms.assetid: 0d092f3a-b309-439b-920b-66d8f46a0e3c
ms.openlocfilehash: cc452ade4ef7d0d2d197f058d74ca0c3d0e0230d
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423078"
---
# <a name="ws-transport-with-message-credential"></a>WS-Transport mit Nachrichtenanmeldeinformationen
In diesem Beispiel wird die Verwendung der SSL-Transportsicherheit in Verbindung mit Clientanmeldeinformationen veranschaulicht, die in der Nachricht übertragen werden. In diesem Beispiel wird die `wsHttpBinding`-Bindung verwendet.  
  
 Standardmäßig bietet die `wsHttpBinding`-Bindung HTTP-Kommunikation. Wenn die Bindung für Transportsicherheit konfiguriert ist, unterstützt sie HTTPS-Kommunikation. HTTPS stellt Vertraulichkeit und Integritätsschutz für die über die Verbindung übertragenen Nachrichten bereit. Die Authentifizierungsmechanismen, die zum Authentifizieren des Clients beim Dienst verwendet werden können, sind jedoch auf die Mechanismen beschränkt, die der HTTPS-Transport unterstützt. Windows Communication Foundation (WCF) bietet einen `TransportWithMessageCredential` Sicherheitsmodus, der diese Einschränkung überwinden soll. Wenn dieser Sicherheitsmodus konfiguriert ist, werden mithilfe der Transportsicherheit Vertraulichkeit und Integrität für die übertragenen Nachrichten bereitgestellt und die Dienstauthentifizierung durchgeführt. Die Client Authentifizierung wird jedoch ausgeführt, indem die Client Anmelde Informationen direkt in der Nachricht angegeben werden. Dies ermöglicht es Ihnen, jeden beliebigen Anmelde Informationstyp zu verwenden, der vom Nachrichten Sicherheitsmodus für die Client Authentifizierung unterstützt wird, und gleichzeitig die Leistungsvorteile des Transport Sicherheitsmodus zu behalten.  
  
 In diesem Beispiel wird der `UserName`-Anmeldeinformationstyp verwendet, um den Client beim Dienst zu authentifizieren.  
  
 Dieses Beispiel basiert auf den ersten [Schritten, mit](../../../../docs/framework/wcf/samples/getting-started-sample.md) denen ein Rechner Dienst implementiert wird. Die `wsHttpBinding`-Bindung wird in den Anwendungskonfigurationsdateien für den Client und den Dienst angegeben und konfiguriert.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Der Programmcode im Beispiel ist fast identisch mit dem des Dienst " [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) ". Es gibt einen zusätzlichen vom Dienstvertrag bereitgestellten Vorgang: `GetCallerIdentity`. Dieser Vorgang gibt den Namen der Identität des Aufrufers an den Aufrufer zurück.  

```csharp
public string GetCallerIdentity()  
{  
    // Use ServiceSecurityContext.WindowsIdentity to get the name of the caller.  
    return ServiceSecurityContext.Current.WindowsIdentity.Name;  
}  
```

 Sie müssen ein Zertifikat erstellen und es mithilfe des Assistenten für Webserverzertifikate zuweisen, bevor Sie das Beispiel erstellen und ausführen. Durch die Endpunktdefinition und Bindungsdefinition in den Einstellungen der Konfigurationsdatei wird der `TransportWithMessageCredential`-Sicherheitsmodus aktiviert, wie in der folgenden Beispielkonfiguration für den Client dargestellt.  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint name=""  
              address="https://localhost/servicemodelsamples/service.svc"   
              binding="wsHttpBinding"   
              bindingConfiguration="Binding1"   
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!--   
        This configuration defines the security mode as TransportWithMessageCredential.  
        and the clientCredentialType as UserName.  
        -->  
      <binding name="Binding1">  
        <security mode ="TransportWithMessageCredential">  
          <message clientCredentialType="UserName" />  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 Für die angegebene Adresse wird das https://-Schema verwendet. Die Bindungskonfiguration legt den Sicherheitsmodus auf `TransportWithMessageCredential` fest. Der gleiche Sicherheitsmodus muss in der Datei "Web.config" für den Dienst angegeben werden.  
  
 Da es sich bei dem in diesem Beispiel verwendeten Zertifikat um ein Test Zertifikat handelt, das mit Makecert. exe erstellt wurde, wird eine Sicherheitswarnung angezeigt, wenn Sie versuchen, auf eine https:-Adresse (z. b. `https://localhost/servicemodelsamples/service.svc`) über Ihren Browser zuzugreifen. Damit der WCF-Client mit einem vorhandenen Test Zertifikat arbeiten kann, wurde dem Client zusätzlicher Code hinzugefügt, um die Sicherheitswarnung zu unterdrücken. Dieser Code und die begleitende Klasse sind bei der Verwendung von Produktionszertifikaten nicht erforderlich.  

```csharp
// WARNING: This code is only needed for test certificates such as those created by makecert. It is   
// not recommended for production code.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
```console  
Username authentication required.  
Provide a valid machine or domain account. [domain\\user]  
   Enter username:   
YourDomainName\YourAccountName  
   Enter password:   
********  
YourDomainName\YourAccountName  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Stellen Sie sicher, dass Sie die [Installationsanweisungen für das Internetinformationsdienste (IIS)-Server Zertifikat](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md)durchgeführt haben.  
  
3. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
4. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  

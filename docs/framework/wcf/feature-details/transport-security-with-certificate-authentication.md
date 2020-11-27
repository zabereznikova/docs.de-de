---
title: Transportsicherheit mit Zertifikatauthentifizierung
description: Erfahren Sie, wie WFC bei Verwendung der Transportsicherheit Zertifikate für die Server-und Client Authentifizierung verwendet.
ms.date: 03/30/2017
dev_langs:
- csharp
ms.assetid: 3d726b71-4d8b-4581-a3bb-02b9af51d11b
ms.openlocfilehash: d3f2a10bb6b355e82f94b8cc793c93ce4634c7d2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251827"
---
# <a name="transport-security-with-certificate-authentication"></a>Transportsicherheit mit Zertifikatauthentifizierung

In diesem Artikel wird die Verwendung von X. 509-Zertifikaten für die Server-und Client Authentifizierung bei der Transportsicherheit erläutert. Weitere Informationen zu X.509-Zertifikaten finden Sie unter [X.509 Public Key Certificates (X.509-Zertifikate mit öffentlichem Schlüssel)](/windows/desktop/SecCertEnroll/about-x-509-public-key-certificates). Zertifikate müssen von einer Zertifizierungsstelle ausgestellt werden, bei der es sich oft um einen Drittanbieter von Zertifikaten handelt. In einer Windows Server-Domäne können Sie Active Directory-Zertifikatdienste verwenden, um Zertifikate für Clientcomputer in der Domäne auszustellen. In diesem Szenario wird der Dienst unter Internetinformationsdienste (IIS) konfiguriert mit Secure Sockets Layer (SSL) gehostet. Der Dienst ist mit einem SSL-Zertifikat (X.509) konfiguriert, um Clients das Überprüfen der Identität des Servers zu ermöglichen. Der Client ist ebenfalls mit einem X.509-Zertifikat konfiguriert, das es dem Dienst ermöglicht, die Identität des Clients zu überprüfen. Das Zertifikat des Servers muss für den Client vertrauenswürdig sein und das Zertifikat des Clients für den Server. Die tatsächliche Funktionsweise, in der der Dienst und der Client die Identität der anderen überprüfen, würde den Rahmen dieses Artikels sprengen. Weitere Informationen finden Sie unter [digitale Signatur](https://en.wikipedia.org/wiki/Digital_signature) auf Wikipedia.
  
 In diesem Szenario wird das im folgenden Diagramm dargestellte Anforderungs-/Antwortnachrichtenmuster implementiert.  
  
 ![Sichere Übertragung mit Zertifikaten](media/8f7b8968-899f-4538-a9e8-0eaa872a291c.gif "8f 7b8968-899f-4538-a9e8-0eaa872a291c")  
  
 Weitere Informationen zum Verwenden eines Zertifikats mit einem Dienst finden Sie unter [Arbeiten mit Zertifikaten](working-with-certificates.md) und Gewusst [wie: Konfigurieren eines Ports mit einem SSL-Zertifikat](how-to-configure-a-port-with-an-ssl-certificate.md). In der folgenden Tabelle werden die verschiedenen Merkmale des Szenarios beschrieben.  
  
|Merkmal|BESCHREIBUNG|  
|--------------------|-----------------|  
|Sicherheitsmodus|Transport|  
|Interoperabilität|Mit vorhandenen Webdienstclients und Diensten.|  
|Authentifizierung (Server)<br /><br /> Authentifizierung (Client)|Ja (mit einem SSL-Zertifikat)<br /><br /> Ja (mit einem X.509-Zertifikat)|  
|Datenintegrität|Ja|  
|Datenvertraulichkeit|Ja|  
|Transport|HTTPS|  
|Bindung|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="configure-the-service"></a>Konfigurieren des Diensts  

 Da der Dienst in diesem Szenario unter IIS gehostet wird, wird er mit einer Datei "web.config" konfiguriert. Die folgende Datei "web.config" zeigt, wie die <xref:System.ServiceModel.WSHttpBinding> zur Verwendung von Transportsicherheit und X.509-Clientanmeldeinformationen konfiguriert wird.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <protocolMapping>  
      <add scheme="https" binding="wsHttpBinding" />  
    </protocolMapping>  
    <bindings>  
      <wsHttpBinding>  
        <!-- configure wsHttp binding with Transport security mode and clientCredentialType as Certificate -->  
        <binding>  
          <security mode="Transport">  
            <transport clientCredentialType="Certificate"/>
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>
           <serviceDebug includeExceptionDetailInFaults="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="configure-the-client"></a>Konfigurieren des Clients  

 Der Client kann im Code oder in einer Datei "app.config" konfiguriert werden. Das folgende Beispiel zeigt, wie Sie den Client im Code konfigurieren.  
  
```csharp
// Create the binding.  
var myBinding = new WSHttpBinding();  
myBinding.Security.Mode = SecurityMode.Transport;  
myBinding.Security.Transport.ClientCredentialType =  
   HttpClientCredentialType.Certificate;  
  
// Create the endpoint address. Note that the machine name
// must match the subject or DNS field of the X.509 certificate  
// used to authenticate the service.
var ea = new  
   EndpointAddress("https://localhost/CalculatorService/service.svc");  
  
// Create the client. The code for the calculator
// client is not shown here. See the sample applications  
// for examples of the calculator code.  
var cc =  
   new CalculatorClient(myBinding, ea);  
  
// The client must specify a certificate trusted by the server.  
cc.ClientCredentials.ClientCertificate.SetCertificate(  
    StoreLocation.CurrentUser,  
    StoreName.My,  
    X509FindType.FindBySubjectName,  
    "contoso.com");  
  
// Begin using the client.  
Console.WriteLine(cc.Add(100, 1111));  
//...  
cc.Close();  
```  
  
 Alternativ können Sie den Client wie im folgenden Beispiel dargestellt in einer Datei "app.config" konfigurieren:  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <!-- this endpoint has an https: address -->  
      <endpoint address=" https://localhost/CalculatorService/service.svc "
                behaviorConfiguration="endpointCredentialBehavior"  
                binding="wsHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.Samples.TransportSecurity.ICalculator"/>  
    </client>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="endpointCredentialBehavior">  
          <clientCredentials>  
            <clientCertificate findValue="contoso.com"  
                               storeLocation="CurrentUser"  
                               storeName="My"  
                               x509FindType="FindBySubjectName" />  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <!-- configure wsHttpbinding with Transport security mode  
                   and clientCredentialType as Certificate -->  
        <binding name="Binding1">  
          <security mode="Transport">  
            <transport clientCredentialType="Certificate"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  </system.serviceModel>  
  
<startup><supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.0"/></startup></configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Sicherheitsübersicht](security-overview.md)
- [Sicherheitsmodell für Windows Server AppFabric](/previous-versions/appfabric/ee677202(v=azure.10))

---
title: "Transportsicherheit mit Zertifikatauthentifizierung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3d726b71-4d8b-4581-a3bb-02b9af51d11b
caps.latest.revision: 20
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 20
---
# Transportsicherheit mit Zertifikatauthentifizierung
In diesem Thema wird die Server\- und Clientauthentifizierung mit X.509\-Zertifikaten bei Verwendung der Transportsicherheit behandelt.Weitere Informationen zu X.509\-Zertifikaten finden Sie unter [X.509\-Zertifikate mit öffentlichem Schlüssel](http://msdn.microsoft.com/library/bb540819\(VS.85\).aspx).Zertifikate müssen von einer Zertifizierungsstelle ausgestellt werden, bei der es sich oft um einen Drittanbieter\-Zertifikataussteller handelt.In einer Windows Server\-Domäne können Sie Active Directory\-Zertifikatdienste verwenden, um Zertifikate für Clientcomputer in der Domäne auszustellen.Weitere Informationen finden Sie unter [Windows 2008 R2\-Zertifikatdienste](http://go.microsoft.com/fwlink/?LinkID=209949&clcid=0x407).In diesem Szenario wird der Dienst unter Internetinformationsdienste \(IIS\) konfiguriert mit Secure Sockets Layer \(SSL\) gehostet.Der Dienst ist mit einem SSL\-Zertifikat \(X.509\) konfiguriert, um Clients das Überprüfen der Identität des Servers zu ermöglichen.Der Client ist ebenfalls mit einem X.509\-Zertifikat konfiguriert, das es dem Dienst ermöglicht, die Identität des Clients zu überprüfen.Das Zertifikat des Servers muss für den Client vertrauenswürdig sein und das Zertifikat des Clients für den Server.Die eigentlichen Mechanismen, anhand derer der Dienst und der Client die Identität des anderen überprüfen, werden in diesem Thema nicht behandelt.Weitere Informationen finden Sie unter ["Digitale Signatur" auf Wikipedia](http://go.microsoft.com/fwlink/?LinkId=253157).  
  
 In diesem Szenario wird das im folgenden Diagramm dargestellte Anforderungs\-\/Antwortnachrichtenmuster implementiert.  
  
 ![Sichere Übertragung mit Zertifikaten](../../../../docs/framework/wcf/feature-details/media/8f7b8968-899f-4538-a9e8-0eaa872a291c.gif "8f7b8968\-899f\-4538\-a9e8\-0eaa872a291c")  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zur Verwendung eines Zertifikats mit einem Dienst finden Sie unter [Verwenden von Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) und [Vorgehensweise: Konfigurieren eines Anschlusses mit einem SSL\-Zertifikat](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).In der folgenden Tabelle werden die verschiedenen Merkmale des Szenarios beschrieben.  
  
|Merkmal|Beschreibung|  
|-------------|------------------|  
|Sicherheitsmodus|Transport|  
|Interoperabilität|Mit vorhandenen Webdienstclients und Diensten.|  
|Authentifizierung \(Server\)<br /><br /> Authentifizierung \(Client\)|Ja \(mit einem SSL\-Zertifikat\)<br /><br /> Ja \(mit einem X.509\-Zertifikat\)|  
|Datenintegrität|Ja|  
|Datenvertraulichkeit|Ja|  
|Transport|HTTPS|  
|Bindung|<xref:System.ServiceModel.WSHttpBinding>|  
  
## Konfigurieren des Diensts  
 Da der Dienst in diesem Szenario unter IIS gehostet wird, wird er mit einer Datei "web.config" konfiguriert.Die folgende Datei "web.config" zeigt, wie die <xref:System.ServiceModel.WSHttpBinding> zur Verwendung von Transportsicherheit und X.509\-Clientanmeldeinformationen konfiguriert wird.  
  
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
  
## Konfigurieren des Clients  
 Der Client kann im Code oder in einer Datei "app.config" konfiguriert werden.Das folgende Beispiel zeigt, wie Sie den Client im Code konfigurieren.  
  
```vb  
// Create the binding.  
WSHttpBinding myBinding = new WSHttpBinding();  
myBinding.Security.Mode = SecurityMode.Transport;  
myBinding.Security.Transport.ClientCredentialType =  
   HttpClientCredentialType.Certificate;  
  
// Create the endpoint address. Note that the machine name   
// must match the subject or DNS field of the X.509 certificate  
// used to authenticate the service.   
EndpointAddress ea = new  
   EndpointAddress("https://localhost/CalculatorService/service.svc");  
  
// Create the client. The code for the calculator   
// client is not shown here. See the sample applications  
// for examples of the calculator code.  
CalculatorClient cc =  
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
  
## Siehe auch  
 [Übersicht über die Sicherheit](../../../../docs/framework/wcf/feature-details/security-overview.md)   
 [Sicherheitsmodell für Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x407)
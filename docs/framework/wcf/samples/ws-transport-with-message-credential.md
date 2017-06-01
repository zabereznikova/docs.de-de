---
title: "WS-Transport mit Nachrichtenanmeldeinformationen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0d092f3a-b309-439b-920b-66d8f46a0e3c
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# WS-Transport mit Nachrichtenanmeldeinformationen
In diesem Beispiel wird die Verwendung der SSL\-Transportsicherheit in Verbindung mit Clientanmeldeinformationen veranschaulicht, die in der Nachricht übertragen werden.In diesem Beispiel wird die `wsHttpBinding`\-Bindung verwendet.  
  
 Standardmäßig stellt die `wsHttpBinding`\-Bindung die HTTP\-Kommunikation bereit.Wenn die Bindung für Transportsicherheit konfiguriert ist, unterstützt sie HTTPS\-Kommunikation.HTTPS stellt Vertraulichkeit und Integritätsschutz für die über die Verbindung übertragenen Nachrichten bereit.Die Authentifizierungsmechanismen, die zum Authentifizieren des Clients beim Dienst verwendet werden können, sind jedoch auf die Mechanismen beschränkt, die der HTTPS\-Transport unterstützt.`TransportWithMessageCredential` bietet einen [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Sicherheitsmodus, durch den diese Einschränkung umgangen werden kann.Wenn dieser Sicherheitsmodus konfiguriert ist, werden mithilfe der Transportsicherheit Vertraulichkeit und Integrität für die übertragenen Nachrichten bereitgestellt und die Dienstauthentifizierung durchgeführt.Die Clientauthentifizierung wird jedoch ausgeführt, indem die Clientanmeldeinformationen direkt in der Nachricht übertragen werden. So können Sie einen beliebigen Typ von Anmeldeinformationen, der vom Nachrichtensicherheitsmodus unterstützt wird, für die Clientauthentifizierung verwenden und gleichzeitig die bessere Leistung des Transportsicherheitsmodus nutzen.  
  
 In diesem Beispiel wird der `UserName`\-Anmeldeinformationstyp verwendet, um den Client beim Dienst zu authentifizieren.  
  
 Dieses Beispiel basiert auf dem [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md), das einen Rechnerdienst implementiert.Die `wsHttpBinding`\-Bindung wird in den Anwendungskonfigurationsdateien für den Client und den Dienst angegeben und konfiguriert.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Der Programmcode im Beispiel stimmt fast vollständig mit dem des Diensts in [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md) überein.Es gibt einen zusätzlichen vom Dienstvertrag bereitgestellten Vorgang: `GetCallerIdentity`.Dieser Vorgang gibt den Namen der Identität des Aufrufers an den Aufrufer zurück.  
  
```  
public string GetCallerIdentity()  
{  
    // Use ServiceSecurityContext.WindowsIdentity to get the name of the caller.  
    return ServiceSecurityContext.Current.WindowsIdentity.Name;  
}  
```  
  
 Sie müssen ein Zertifikat erstellen und es mithilfe des Assistenten für Webserverzertifikate zuweisen, bevor Sie das Beispiel erstellen und ausführen.Durch die Endpunktdefinition und Bindungsdefinition in den Einstellungen der Konfigurationsdatei wird der `TransportWithMessageCredential`\-Sicherheitsmodus aktiviert, wie in der folgenden Beispielkonfiguration für den Client dargestellt.  
  
```  
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
  
 Für die angegebene Adresse wird das https:\/\/\-Schema verwendet.Die Bindungskonfiguration legt den Sicherheitsmodus auf `TransportWithMessageCredential` fest.Der gleiche Sicherheitsmodus muss in der Datei "Web.config" für den Dienst angegeben werden.  
  
 Da das in diesem Beispiel verwendete Zertifikat ein mit Makecert.exe erstelltes Testzertifikat ist, wird eine Sicherheitswarnung angezeigt, wenn Sie versuchen, in Ihrem Browser auf eine https:\-Adresse wie https:\/\/localhost\/servicemodelsamples\/service.svc zuzugreifen.Damit der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Client mit einem vorhandenen Testzertifikat arbeiten kann, wurde auf dem Client zusätzlicher Code hinzugefügt, um die Sicherheitswarnung zu unterdrücken.Dieser Code und die begleitende Klasse sind bei der Verwendung von Produktionszertifikaten nicht erforderlich.  
  
```  
// WARNING: This code is only needed for test certificates such as those created by makecert. It is   
// not recommended for production code.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
```  
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
  
### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Stellen Sie sicher, dass Sie die [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
2.  Stellen Sie sicher, dass Sie die [Installationsanleitung für IIS\-Serverzertifikate \(Internetinformationsdienste\)](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md) ausgeführt haben.  
  
3.  Zum Erstellen der C\#\- oder Visual Basic .NET\-Edition der Lösung befolgen Sie die unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md) aufgeführten Anweisungen.  
  
4.  Wenn Sie das Beispiel in einer Konfiguration mit einem einzigen Computer oder computerübergreifend ausführen möchten, befolgen Sie die unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md) aufgeführten Anweisungen.  
  
## Siehe auch
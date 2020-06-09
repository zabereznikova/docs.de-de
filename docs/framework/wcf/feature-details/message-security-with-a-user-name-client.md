---
title: Nachrichtensicherheit über einen Benutzernamenclient
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 36335cb9-76b8-4443-92c7-44f081eabb21
ms.openlocfilehash: 9447487012cae370d35880e5b780465f9434051b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602621"
---
# <a name="message-security-with-a-user-name-client"></a>Nachrichtensicherheit über einen Benutzernamenclient
Die folgende Abbildung zeigt einen Windows Communication Foundation (WCF)-Dienst und einen Client, der mithilfe der Sicherheit auf Nachrichten Ebene gesichert wird. Der Dienst wird über ein X.509-Zertifikat authentifiziert. Der Client wird über den Benutzernamen und das Kennwort authentifiziert.  
  
 Eine Beispielanwendung finden Sie unter [Message Security User Name](../samples/message-security-user-name.md).  
  
 ![Nachrichtensicherheit durch Benutzernamenauthentifizierung](media/1fb10a61-7e1d-42f5-b1af-195bfee5b3c6.gif "1b10a61-7e1d-42b5-B1AF-195bfee5b3c6")  
  
|Merkmal|BESCHREIBUNG|  
|--------------------|-----------------|  
|Sicherheitsmodus|`Message`|  
|Interoperabilität|Nur Windows Communication Foundation (WCF)|  
|Authentifizierung (Server)|Für die erste Aushandlung ist eine Serverauthentifizierung erforderlich|  
|Authentifizierung (Client)|Benutzername/Kennwort|  
|Integrität|Ja, mit freigegebenem Sicherheitskontext|  
|Vertraulichkeit|Ja, mit freigegebenem Sicherheitskontext|  
|Transport|HTTP|  
|Bindung|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a>Dienst  
 Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt. Führen Sie einen der folgenden Schritte aus:  
  
- Erstellen Sie einen separaten Dienst, indem Sie den Code ohne Konfiguration verwenden.  
  
- Erstellen Sie mit der angegebenen Konfiguration einen Dienst, aber definieren Sie keine Endpunkte.  
  
### <a name="code"></a>Code  
 Im folgenden Code wird gezeigt, wie ein Dienstendpunkt, der Nachrichtensicherheit verwendet, erstellt wird.  
  
 [!code-csharp[C_SecurityScenarios#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#9)]
 [!code-vb[C_SecurityScenarios#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#9)]  
  
### <a name="configuration"></a>Konfiguration  
 Die folgende Konfiguration kann statt des Codes verwendet werden:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ServiceCredentialsBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"
                                storeLocation="LocalMachine"  
                                storeName="My"
                                x509FindType="FindBySubjectName" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="ServiceCredentialsBehavior"  
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"  
                  binding="wsHttpBinding"  
                  bindingConfiguration="MessageAndUserName"  
                  name="SecuredByTransportEndpoint"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="MessageAndUserName">  
          <security mode="Message">
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a>Client  
  
### <a name="code"></a>Code  
 Der folgende Code erstellt den Client. Die Bindung bezieht sich auf den Nachrichtensicherheitsmodus, und der Clientanmeldeinformationstyp wird auf `UserName` festgelegt. Der Benutzername und das Kennwort können nur mit Code (nicht konfigurierbar) angegeben werden. Der Code zum Zurückgeben des Benutzernamens und des Kennworts ist hier nicht gezeigt, da dies auf Anwendungsebene erfolgen muss. Verwenden Sie z. B. ein Windows Forms-Dialogfeld, um vom Benutzer Daten abzufragen.  
  
 [!code-csharp[C_SecurityScenarios#16](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#16)]
 [!code-vb[C_SecurityScenarios#16](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#16)]  
  
### <a name="configuration"></a>Konfiguration  
 Der folgende Code dient zum Konfigurieren des Clients. Die Bindung bezieht sich auf den Nachrichtensicherheitsmodus, und der Clientanmeldeinformationstyp wird auf `UserName` festgelegt. Der Benutzername und das Kennwort können nur mit Code (nicht konfigurierbar) angegeben werden.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <dns value ="Contoso.com" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Sicherheitsübersicht](security-overview.md)
- [Nachrichtensicherheit – Benutzername](../samples/message-security-user-name.md)
- [Dienstidentität und Authentifizierung](service-identity-and-authentication.md)
- [\<identity>](../../configure-apps/file-schema/wcf/identity.md)
- [Sicherheitsmodell für Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))

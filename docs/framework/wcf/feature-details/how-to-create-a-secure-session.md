---
title: 'Vorgehensweise: Erstellen einer sicheren Sitzung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], creating a session
ms.assetid: b6f42b5a-bbf7-45cf-b917-7ec9fa7ae110
ms.openlocfilehash: 80973a31050cf1ede03d4a3919066c62625ae590
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593411"
---
# <a name="how-to-create-a-secure-session"></a>Vorgehensweise: Erstellen einer sicheren Sitzung
Mit Ausnahme der- [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) Bindung verwenden die vom System bereitgestellten Bindungen in Windows Communication Foundation (WCF) automatisch sichere Sitzungen, wenn die Nachrichten Sicherheit aktiviert ist.  
  
 Standardmäßig überleben sichere Sitzungen keine Webserver, die wiederverwendet werden. Wenn eine sichere Sitzung eingerichtet wird, speichern der Client und der Dienst den Schlüssel zwischen, der der sicheren Sitzung zugeordnet ist. Beim Austauschen der Nachrichten wird nur ein Bezeichner des zwischengespeicherten Schlüssels ausgetauscht. Wenn der Webserver wiederverwendet wird, wird der Cache ebenfalls wiederverwendet. Der Webserver kann den im Cache zwischengespeicherten Schlüssel für den Bezeichner dann nicht abrufen. Wenn dies geschieht, wird für den Client eine Ausnahme ausgelöst. Sichere Sitzungen, die ein Token für den Sicherheitszustandskontext verwenden, bleiben auch nach Wiederverwenden eines Webservers aktiv. Weitere Informationen zum Verwenden eines Zustands behafteten SCT in einer sicheren Sitzung finden Sie unter Gewusst [wie: Erstellen eines Sicherheitskontext Tokens für eine sichere Sitzung](how-to-create-a-security-context-token-for-a-secure-session.md).  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-one-of-the-system-provided-bindings"></a>So geben Sie an, dass ein Dienst sichere Sitzungen verwendet, indem er eine der vom System bereitgestellten Bindungen nutzt  
  
- Konfigurieren Sie einen Dienst so, dass er eine vom System bereitgestellte Bindung verwendet, die die Nachrichtensicherheit unterstützt.  
  
     Mit Ausnahme der- [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) Bindung verwendet WCF automatisch sichere Sitzungen, wenn die vom System bereitgestellten Bindungen für die Verwendung der Nachrichten Sicherheit konfiguriert sind. In der folgenden Tabelle sind die vom System bereitgestellten Bindungen aufgeführt, die die Nachrichtensicherheit unterstützen. Außerdem ist angegeben, ob die Nachrichtensicherheit der standardmäßige Sicherheitsmechanismus ist.  
  
    |Vom System bereitgestellte Bindung|Konfigurationselement|Nachrichtensicherheit standardmäßig aktiviert|  
    |------------------------------|---------------------------|------------------------------------|  
    |<xref:System.ServiceModel.BasicHttpBinding>|[\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md)|Nein |  
    |<xref:System.ServiceModel.WSHttpBinding>|[\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md)|Ja|  
    |<xref:System.ServiceModel.WSDualHttpBinding>|[\<wsDualHttpBinding>](../../configure-apps/file-schema/wcf/wsdualhttpbinding.md)|Ja|  
    |<xref:System.ServiceModel.WSFederationHttpBinding>|[\<wsFederationHttpBinding>](../../configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|Ja|  
    |<xref:System.ServiceModel.NetTcpBinding>|[\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md)|Nein|  
    |<xref:System.ServiceModel.NetMsmqBinding>|[\<netMsmqBinding>](../../configure-apps/file-schema/wcf/netmsmqbinding.md)|Nein|  
  
     Im folgenden Codebeispiel wird die-Konfiguration verwendet, um eine Bindung mit dem Namen anzugeben, die `wsHttpBinding_Calculator` [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) , Nachrichten Sicherheit und sichere Sitzungen verwendet.  
  
    ```xml  
    <bindings>  
      <WSHttpBinding>  
       <binding name = "wsHttpBinding_Calculator">  
         <security mode="Message">  
           <message clientCredentialType="Windows"/>  
         </security>  
        </binding>  
      </WSHttpBinding>  
    </bindings>  
    ```  
  
     Im folgenden Codebeispiel wird angegeben, dass [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) , die Nachrichten Sicherheit und sichere Sitzungen verwendet werden, um den Dienst zu sichern `secureCalculator` .  
  
     [!code-csharp[c_CreateSecureSession#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#1)]
     [!code-vb[c_CreateSecureSession#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#1)]  
  
    > [!NOTE]
    > Sichere Sitzungen können für das ausgeschaltet werden [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) , indem das- `establishSecurityContext` Attribut auf festgelegt wird `false` . Für die anderen vom System bereitgestellten Bindungen können Sie sichere Sitzungen nur deaktivieren, indem Sie eine benutzerdefinierte Bindung erstellen.  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-a-custom-binding"></a>So geben Sie an, dass ein Dienst mithilfe einer benutzerdefinierten Bindung sichere Sitzungen verwendet  
  
- Erstellen Sie eine benutzerdefinierte Bindung, die angibt, dass SOAP-Nachrichten mithilfe einer sicheren Sitzung geschützt sind.  
  
     Weitere Informationen zum Erstellen einer benutzerdefinierten Bindung finden Sie unter Gewusst [wie: Anpassen einer vom System bereitgestellten Bindung](../extending/how-to-customize-a-system-provided-binding.md).  
  
     Im folgenden Codebeispiel wird die Konfiguration verwendet, um eine benutzerdefinierte Bindung anzugeben, die Nachrichten mithilfe einer sicheren Sitzung bearbeitet.  
  
    ```xml  
    <bindings>  
      <!-- configure a custom binding -->  
      <customBinding>  
        <binding name="customBinding_Calculator">  
          <security authenticationMode="SecureConversation" />  
          <secureConversationBootstrap authenticationMode="SspiNegotiated" />  
          <textMessageEncoding messageVersion="Soap12WSAddressing10" writeEncoding="utf-8"/>  
          <httpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
     Das folgende Codebeispiel erstellt eine benutzerdefinierte Bindung, die den <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>-Authentifizierungsmodus verwendet, um eine sichere Sitzung mithilfe eines Bootstrap-Vorgangs zu starten.  
  
     [!code-csharp[c_CreateSecureSession#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#2)]
     [!code-vb[c_CreateSecureSession#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#2)]  
  
## <a name="see-also"></a>Weitere Informationen

- [WCF-Bindungsübersicht](../bindings-overview.md)

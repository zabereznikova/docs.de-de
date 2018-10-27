---
title: 'Vorgehensweise: Erstellen einer sicheren Sitzung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], creating a session
ms.assetid: b6f42b5a-bbf7-45cf-b917-7ec9fa7ae110
ms.openlocfilehash: c0e5281d227d343d8734809b27b57d8a2bead627
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185801"
---
# <a name="how-to-create-a-secure-session"></a>Vorgehensweise: Erstellen einer sicheren Sitzung
Mit Ausnahme von der [ \<BasicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) binden, verwenden die vom System bereitgestellten Bindungen in der Windows Communication Foundation (WCF) automatisch sichere Sitzungen, wenn die nachrichtensicherheit aktiviert ist.  
  
 Standardmäßig überleben sichere Sitzungen keine Webserver, die wiederverwendet werden. Wenn eine sichere Sitzung eingerichtet wird, speichern der Client und der Dienst den Schlüssel zwischen, der der sicheren Sitzung zugeordnet ist. Beim Austauschen der Nachrichten wird nur ein Bezeichner des zwischengespeicherten Schlüssels ausgetauscht. Wenn der Webserver wiederverwendet wird, wird der Cache ebenfalls wiederverwendet. Der Webserver kann den im Cache zwischengespeicherten Schlüssel für den Bezeichner dann nicht abrufen. Wenn dies geschieht, wird für den Client eine Ausnahme ausgelöst. Sichere Sitzungen, die ein zustandsbehaftetes Token für den Sicherheitskontext verwenden, bleiben auch nach Wiederverwenden eines Webservers aktiv. Weitere Informationen zur Verwendung eines zustandsbehafteten SCT in sicheren Sitzungen finden Sie unter [Vorgehensweise: Erstellen Sie ein Token für den Sicherheitskontext für eine Sicherheitssitzung](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-one-of-the-system-provided-bindings"></a>So geben Sie an, dass ein Dienst sichere Sitzungen verwendet, indem er eine der vom System bereitgestellten Bindungen nutzt  
  
-   Konfigurieren Sie einen Dienst so, dass er eine vom System bereitgestellte Bindung verwendet, die die Nachrichtensicherheit unterstützt.  
  
     Mit Ausnahme von der [ \<BasicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) binden, wenn vom System bereitgestellten Bindungen konfiguriert sind, automatisch mit nachrichtensicherheit, WCF sichere Sitzungen verwendet. In der folgenden Tabelle sind die vom System bereitgestellten Bindungen aufgeführt, die die Nachrichtensicherheit unterstützen. Außerdem ist angegeben, ob die Nachrichtensicherheit der standardmäßige Sicherheitsmechanismus ist.  
  
    |Vom System bereitgestellte Bindung|Konfigurationselement|Nachrichtensicherheit standardmäßig aktiviert|  
    |------------------------------|---------------------------|------------------------------------|  
    |<xref:System.ServiceModel.BasicHttpBinding>|[\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)|Nein|  
    |<xref:System.ServiceModel.WSHttpBinding>|[\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|Ja|  
    |<xref:System.ServiceModel.WSDualHttpBinding>|[\<wsDualHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)|Ja|  
    |<xref:System.ServiceModel.WSFederationHttpBinding>|[\<wsFederationHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|Ja|  
    |<xref:System.ServiceModel.NetTcpBinding>|[\<netTcpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)|Nein|  
    |<xref:System.ServiceModel.NetMsmqBinding>|[\<netMsmqBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|Nein|  
  
     Das folgende Codebeispiel verwendet die Konfiguration zum Angeben einer Bindung, die mit dem Namen `wsHttpBinding_Calculator` , verwendet der [ \<WsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), die nachrichtensicherheit und sichere Sitzungen.  
  
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
  
     Das folgende Codebeispiel gibt an, dass die [ \<WsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), die nachrichtensicherheit und sichere Sitzungen werden zum Schützen der `secureCalculator` Service.  
  
     [!code-csharp[c_CreateSecureSession#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#1)]
     [!code-vb[c_CreateSecureSession#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#1)]  
  
    > [!NOTE]
    >  Sichere Sitzungen deaktiviert werden für die [ <wsHttpBinding> ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) durch Festlegen der `establishSecurityContext` -Attribut auf `false`. Für die anderen vom System bereitgestellten Bindungen können Sie sichere Sitzungen nur deaktivieren, indem Sie eine benutzerdefinierte Bindung erstellen.  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-a-custom-binding"></a>So geben Sie an, dass ein Dienst mithilfe einer benutzerdefinierten Bindung sichere Sitzungen verwendet  
  
-   Erstellen Sie eine benutzerdefinierte Bindung, die angibt, dass SOAP-Nachrichten mithilfe einer sicheren Sitzung geschützt sind.  
  
     Weitere Informationen zum Erstellen einer benutzerdefinierten Bindung finden Sie unter [wie: Anpassen einer System-provided Bindung](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [WCF-Bindungsübersicht](../../../../docs/framework/wcf/bindings-overview.md)

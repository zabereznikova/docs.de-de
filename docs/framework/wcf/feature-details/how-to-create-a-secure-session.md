---
title: "Vorgehensweise: Erstellen einer sicheren Sitzung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Sicherheit [WCF], Erstellen einer Sitzung"
ms.assetid: b6f42b5a-bbf7-45cf-b917-7ec9fa7ae110
caps.latest.revision: 10
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 10
---
# Vorgehensweise: Erstellen einer sicheren Sitzung
Mit Ausnahme der [\<basicHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)\-Bindung verwenden die vom System bereitgestellten Bindungen in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] automatisch sichere Sitzungen, wenn die Nachrichtensicherheit aktiviert ist.  
  
 Standardmäßig überleben sichere Sitzungen keine Webserver, die wiederverwendet werden.  Wenn eine sichere Sitzung eingerichtet wird, speichern der Client und der Dienst den Schlüssel zwischen, der der sicheren Sitzung zugeordnet ist.  Beim Austauschen der Nachrichten wird nur ein Bezeichner des zwischengespeicherten Schlüssels ausgetauscht.  Wenn der Webserver wiederverwendet wird, wird der Cache ebenfalls wiederverwendet. Der Webserver kann den im Cache zwischengespeicherten Schlüssel für den Bezeichner dann nicht abrufen.  Wenn dies geschieht, wird für den Client eine Ausnahme ausgelöst.  Sichere Sitzungen, die ein Token für den Sicherheitszustandskontext verwenden, bleiben auch nach Wiederverwenden eines Webservers aktiv.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zur Verwendung eines zustandsbehafteten SCT in sicheren Sitzungen finden Sie unter [Vorgehensweise: Erstellen eines Tokens für den Sicherheitskontext einer sicheren Sitzung](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).  
  
### So geben Sie an, dass ein Dienst sichere Sitzungen verwendet, indem er eine der vom System bereitgestellten Bindungen nutzt  
  
-   Konfigurieren Sie einen Dienst so, dass er eine vom System bereitgestellte Bindung verwendet, die die Nachrichtensicherheit unterstützt.  
  
     Mit Ausnahme der [\<basicHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)\-Bindung verwendet [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] automatisch sichere Sitzungen, wenn die vom System bereitgestellten Bindungen für die Verwendung der Nachrichtensicherheit konfiguriert sind.  In der folgenden Tabelle sind die vom System bereitgestellten Bindungen aufgeführt, die die Nachrichtensicherheit unterstützen. Außerdem ist angegeben, ob die Nachrichtensicherheit der standardmäßige Sicherheitsmechanismus ist.  
  
    |Vom System bereitgestellte Bindung|Konfigurationselement|Nachrichtensicherheit standardmäßig aktiviert|  
    |----------------------------------------|---------------------------|---------------------------------------------------|  
    |<xref:System.ServiceModel.BasicHttpBinding>|[\<basicHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)|Nein|  
    |<xref:System.ServiceModel.WSHttpBinding>|[\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|Ja|  
    |<xref:System.ServiceModel.WSDualHttpBinding>|[\<wsDualHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)|Ja|  
    |<xref:System.ServiceModel.WSFederationHttpBinding>|[\<wsFederationHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|Ja|  
    |<xref:System.ServiceModel.NetTcpBinding>|[\<netTcpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)|Nein|  
    |<xref:System.ServiceModel.NetMsmqBinding>|[\<NetMsmqBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|Nein|  
  
     Im folgenden Codebeispiel wird die Konfiguration verwendet, um eine Bindung mit dem Namen `wsHttpBinding_Calculator` anzugeben, die das [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), die Nachrichtensicherheit und sichere Sitzungen verwendet.  
  
    ```  
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
  
     Im folgenden Codebeispiel wird angegeben, dass das [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), die Nachrichtensicherheit und sichere Sitzungen verwendet werden, um die Sicherheit des `secureCalculator`\-Dienstes zu gewährleisten.  
  
     [!code-csharp[c_CreateSecureSession#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#1)]
     [!code-vb[c_CreateSecureSession#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#1)]  
  
    > [!NOTE]
    >  Sie können sichere Sitzungen für das [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) deaktivieren, indem Sie das `establishSecurityContext`\-Attribut auf `false` festlegen.  Für die anderen vom System bereitgestellten Bindungen können Sie sichere Sitzungen nur deaktivieren, indem Sie eine benutzerdefinierte Bindung erstellen.  
  
### So geben Sie an, dass ein Dienst mithilfe einer benutzerdefinierten Bindung sichere Sitzungen verwendet  
  
-   Erstellen Sie eine benutzerdefinierte Bindung, die angibt, dass SOAP\-Nachrichten mithilfe einer sicheren Sitzung geschützt sind.  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zur Erstellung einer benutzerdefinierten Bindung finden Sie unter [Vorgehensweise: Anpassen einer vom System bereitgestellten Bindung](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).  
  
     Im folgenden Codebeispiel wird die Konfiguration verwendet, um eine benutzerdefinierte Bindung anzugeben, die Nachrichten mithilfe einer sicheren Sitzung bearbeitet.  
  
    ```  
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
  
     Das folgende Codebeispiel erstellt eine benutzerdefinierte Bindung, die den <xref:System.ServiceModel.Configuration.AuthenticationMode>\-Authentifizierungsmodus verwendet, um eine sichere Sitzung mithilfe eines Bootstrap\-Vorgangs zu starten.  
  
     [!code-csharp[c_CreateSecureSession#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#2)]
     [!code-vb[c_CreateSecureSession#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#2)]  
  
## Siehe auch  
 [WCF\-Bindungsübersicht](../../../../docs/framework/wcf/bindings-overview.md)
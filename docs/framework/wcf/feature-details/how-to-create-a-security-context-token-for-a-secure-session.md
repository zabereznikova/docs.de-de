---
title: "Vorgehensweise: Erstellen eines Tokens f&#252;r den Sicherheitskontext einer sicheren Sitzung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 640676b6-c75a-4ff7-aea4-b1a1524d71b2
caps.latest.revision: 14
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 14
---
# Vorgehensweise: Erstellen eines Tokens f&#252;r den Sicherheitskontext einer sicheren Sitzung
Durch das Verwenden eines zustandsbehafteten Sicherheitskontexttokens \(SCT\) in einer sicheren Sitzung, kann die Sitzung verhindern, dass der Dienst wiederverwendet wird.Wenn beispielsweise ein zustandsbehaftetes SCT in einer sicheren Sitzung verwendet wird und die IIS \(Internet Information Services\) zurückgesetzt werden, gehen die Sitzungsdaten, die dem Dienst zugewiesen sind, verloren.Zu den Sitzungsdaten gehört auch ein SCT\-Token\-Cache.Wenn ein Client also das nächste Mal dem Dienst einen zustandsbehafteten SCT sendet, wird ein Fehler zurückgegeben, da der diesem SCT zugewiesene Schlüssel nicht abgerufen werden kann.Wenn jedoch ein zustandsbehafteter SCT verwendet wird, enthält das SCT den diesem SCT zugewiesenen Schlüssel.Da der Schlüssel im SCT enthalten ist und somit auch in der Nachricht, wird die sichere Sitzung nicht von der Wiederverwendung des Dienstes beeinträchtigt.Standardmäßig verwendet [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] zustandslose SCTs in einer sicheren Sitzung.Dieses Thema erläutert, wie Sie zustandsbehaftete SCTs in einer sicheren Sitzung verwenden können.  
  
> [!NOTE]
>  Zustandsbehaftete SCTs können nicht in einer sicheren Sitzung verwendet werden, die einen Vertrag einschließt, der vom <xref:System.ServiceModel.Channels.IDuplexChannel> abgeleitet wird.  
  
> [!NOTE]
>  Bei Anwendungen, die zustandsbehaftete SCTs in einer sicheren Sitzung verwenden, muss die Thread\-Identität des Dienstes ein Benutzerkonto sein, dem ein Benutzerprofil zugewiesen ist.Wenn der Dienst unter einem Konto ausgeführt wird, für das kein Benutzerprofil festgelegt wurde, z. B. ein `Local Service`, wird möglicherweise eine Ausnahme ausgegeben.  
  
> [!NOTE]
>  Wenn ein Identitätswechsel auf Windows XP erforderlich ist, verwenden Sie eine sichere Sitzung ohne zustandsbehaftetes SCT.Wenn ein Token für den Sicherheitszustandskontext \(SCT\) mit einem Identitätswechsel verwendet werden, wird eine <xref:System.InvalidOperationException> ausgelöst.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Nicht unterstützte Szenarien](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).  
  
### So verwenden Sie zustandsbehaftete SCTs in einer sicheren Sitzung  
  
-   Erstellen Sie eine benutzerdefinierte Bindung, die angibt, dass SOAP\-Nachrichten durch eine sichere Sitzung mit einem zustandsbehafteten SCT geschützt sind.  
  
    1.  Definieren Sie eine benutzerdefinierte Bindung, indem Sie für den Dienst der Konfigurationsdatei ein [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) hinzufügen.  
  
        ```  
        <customBinding>  
        ```  
  
    2.  Fügen Sie ein untergeordnetes [\<Bindung\>](../../../../docs/framework/misc/binding.md)[\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) hinzu.  
  
         Geben Sie einen Bindungsnamen an, indem Sie das `name`\-Attribut auf einen eindeutigen Namen in der Konfigurationsdatei festlegen.  
  
        ```  
        <binding name="StatefulSCTSecureSession">  
        ```  
  
    3.  Geben Sie den Authentifizierungsmodus für Nachrichten an, die an diesen und von diesem Dienst gesendet werden, indem Sie ein untergeordnetes [\<Sicherheit\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)\-Element zum [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) hinzufügen.  
  
         Legen Sie fest, dass eine sichere Sitzung verwendet wird, indem Sie das `authenticationMode`\-Attribut auf `SecureConversation` setzen.Legen Sie fest, dass zustandsbehaftete SCTs verwendet werden, indem Sie das `requireSecurityContextCancellation`\-Attribut auf `false` setzen.  
  
        ```  
        <security authenticationMode="SecureConversation"  
                  requireSecurityContextCancellation="false">  
        ```  
  
    4.  Geben Sie beim Einrichten der sicheren Sitzung an, wie der Client authentifiziert wird, indem Sie ein untergeordnetes [\<secureConversationBootstrap\>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)\-Element zur [\<Sicherheit\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) hinzufügen.  
  
         Geben Sie an, wie der Client authentifiziert wird, indem Sie das `authenticationMode`\-Attribut setzen.  
  
        ```  
        <secureConversationBootstrap authenticationMode="UserNameForCertificate" />  
        ```  
  
    5.  Geben Sie die Nachrichtenverschlüsselung an, indem Sie ein Codierungselement hinzufügen, z. B. [\<textMessageEncoding\>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).  
  
        ```  
        <textMessageEncoding />  
        ```  
  
    6.  Geben Sie den Transport an, indem Sie ein Transportelement hinzufügen, z. B. das [\<httpTransport\>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md).  
  
        ```  
        <httpTransport />  
        ```  
  
     Im folgenden Codebeispiel wird die Konfiguration verwendet, um eine benutzerdefinierte Bindung anzugeben, die Nachrichten mit zustandsbehafteten SCTs in einer sicheren Sitzung verwenden können.  
  
    ```  
    <customBinding>  
      <binding name="StatefulSCTSecureSession">  
        <security authenticationMode="SecureConversation"  
                  requireSecurityContextCancellation="false">  
          <secureConversationBootstrap authenticationMode="UserNameForCertificate" />  
        </security>  
        <textMessageEncoding />  
        <httpTransport />  
      </binding>  
    </customBinding>  
    ```  
  
## Beispiel  
 Das folgende Codebeispiel erstellt eine benutzerdefinierte Bindung, die den <xref:System.ServiceModel.Configuration.AuthenticationMode>\-Authentifizierungsmodus verwendet, um eine sichere Sitzung mithilfe eines Bootstrap\-Vorgangs zu starten.  
  
 [!code-csharp[c_CreateStatefulSCT#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createstatefulsct/cs/secureservice.cs#2)]
 [!code-vb[c_CreateStatefulSCT#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createstatefulsct/vb/secureservice.vb#2)]  
  
 Wenn die Windows\-Authentifizierung zusammen mit einem zustandsbehafteten SCT verwendet wird, füllt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nicht die <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A>\-Eigenschaft mit der tatsächlichen Identität des Anrufers aus, sondern legt die Eigenschaft auf den Wert Anonym fest.Da die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Sicherheit den Inhalt des Dienstsicherheitskontextes für jede Anfrage vom eingehenden SCT neu erstellen muss, verfolgt der Server nicht die Sicherheitssitzung im Speicher.Da die <xref:System.Security.Principal.WindowsIdentity>\-Instanz nicht in das SCT serialisiert werden kann, gibt die <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A>\-Eigenschaft eine anonyme Identität zurück.  
  
 Die folgende Konfiguration weist dieses Verhalten auf.  
  
```  
<customBinding>  
  <binding name="Cancellation">  
       <textMessageEncoding />  
        <security   
            requireSecurityContextCancellation="false">  
              <secureConversationBootstrap />  
      </security>  
    <httpTransport />  
  </binding>  
</customBinding>  
  
```  
  
## Siehe auch  
 [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
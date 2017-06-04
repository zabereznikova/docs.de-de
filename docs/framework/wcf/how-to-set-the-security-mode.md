---
title: "Vorgehensweise: Festlegen des Sicherheitsmodus | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Mode-Eigenschaft"
  - "WCF, Sicherheit"
  - "WCF, Sicherheitsmodus"
ms.assetid: 6e01dd9f-b5dd-4474-b24c-06e124de4ff7
caps.latest.revision: 22
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 22
---
# Vorgehensweise: Festlegen des Sicherheitsmodus
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] verfügt über drei allgemeine Sicherheitsmodi, die in den meisten vordefinierten Bindungen vorhanden sind: Transport, Message und TransportWithMessageCredential. Zwei weitere Modi sind bindungsspezifisch: "TransportCredentialOnly" ist nur in der <xref:System.ServiceModel.BasicHttpBinding> und "Both" nur in der <xref:System.ServiceModel.NetMsmqBinding> verfügbar.In diesem Thema werden jedoch die drei allgemeinen Sicherheitsmodi behandelt: <xref:System.ServiceModel.SecurityMode>, <xref:System.ServiceModel.SecurityMode> und <xref:System.ServiceModel.SecurityMode>.  
  
 Diese Modi werden nicht von allen vordefinierten Bindungen unterstützt.In diesem Thema wird der Modus mit der <xref:System.ServiceModel.WSHttpBinding>\-Klasse und mit der <xref:System.ServiceModel.NetTcpBinding>\-Klasse festgelegt, und es wird veranschaulicht, wie der Modus programmgesteuert und in der Konfiguration festgelegt werden kann.  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)] zur [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Sicherheit finden Sie unter [Übersicht über die Sicherheit](../../../docs/framework/wcf/feature-details/security-overview.md), [Sichern von Diensten](../../../docs/framework/wcf/securing-services.md) und [Sichern von Diensten und Clients](../../../docs/framework/wcf/feature-details/securing-services-and-clients.md).[!INCLUDE[crabout](../../../includes/crabout-md.md)] zur Transportsicherheit und Nachrichtensicherheit finden Sie unter [Transportsicherheit](../../../docs/framework/wcf/feature-details/transport-security.md) und [Nachrichtensicherheit](../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
  
### So legen Sie den Sicherheitsmodus im Code fest  
  
1.  Erstellen Sie eine Instanz der Bindungsklasse, die Sie verwenden.Eine Liste vordefinierter Bindungen finden Sie unter [Vom System bereitgestellte Bindungen](../../../docs/framework/wcf/system-provided-bindings.md).In diesem Codebeispiel wird eine Instanz der <xref:System.ServiceModel.WSHttpBinding>\-Klasse erstellt.  
  
2.  Legen Sie die `Mode`\-Eigenschaft des Objekts fest, das von der `Security`\-Eigenschaft zurückgegeben wird.  
  
     [!code-csharp[c_SettingSecurityMode#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#1)]
     [!code-vb[c_SettingSecurityMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#1)]  
  
     Sie können den Modus auch auf Message festlegen, wie im folgenden Code veranschaulicht wird.  
  
     [!code-csharp[c_SettingSecurityMode#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#2)]
     [!code-vb[c_SettingSecurityMode#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#2)]  
  
     Sie können den Modus auch auf TransportWithMessageCredentials festlegen, wie im folgenden Code veranschaulicht wird.  
  
     [!code-csharp[c_SettingSecurityMode#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#3)]
     [!code-vb[c_SettingSecurityMode#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#3)]  
  
3.  Sie können den Modus auch im Konstruktor der Bindung festlegen, wie im folgenden Codebeispiel veranschaulicht wird.  
  
     [!code-csharp[c_SettingSecurityMode#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#4)]
     [!code-vb[c_SettingSecurityMode#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#4)]  
  
## Festlegen der ClientCredentialType\-Eigenschaft  
 Durch Festlegen des Modus auf einen der drei Werte wird bestimmt, wie Sie die `ClientCredentialType`\-Eigenschaft festlegen können.Wenn Sie beispielsweise die <xref:System.ServiceModel.WSHttpBinding>\-Klasse verwenden, müssen Sie die <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A>\-Eigenschaft der <xref:System.ServiceModel.HttpTransportSecurity>\-Klasse auf einen entsprechenden Wert festlegen, wenn der Modus auf `Transport` festgelegt wird.  
  
#### So legen Sie die ClientCredentialType\-Eigenschaft für den Transport\-Modus fest  
  
1.  Erstellen Sie eine Instanz der Bindung.  
  
2.  Legen Sie die `Mode`\-Eigenschaft auf `Transport` fest.  
  
3.  Legen Sie für die `ClientCredential`\-Eigenschaft einen geeigneten Wert fest.Im folgenden Code wird die Eigenschaft auf `Windows` festgelegt.  
  
     [!code-csharp[c_SettingSecurityMode#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#5)]
     [!code-vb[c_SettingSecurityMode#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#5)]  
  
#### So legen Sie die ClientCredentialType\-Eigenschaft für den Message\-Modus fest  
  
1.  Erstellen Sie eine Instanz der Bindung.  
  
2.  Legen Sie die `Mode`\-Eigenschaft auf `Message` fest.  
  
3.  Legen Sie für die `ClientCredential`\-Eigenschaft einen geeigneten Wert fest.Im folgenden Code wird die Eigenschaft auf `Certificate` festgelegt.  
  
     [!code-csharp[c_SettingSecurityMode#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#6)]
     [!code-vb[c_SettingSecurityMode#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#6)]  
  
#### So legen Sie die Mode\-Eigenschaft und die ClientCredentialType\-Eigenschaft in der Konfiguration fest  
  
1.  Fügen Sie dem [\<Bindungen\>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)\-Element der Konfigurationsdatei ein entsprechendes Bindungselement hinzu.Im folgenden Beispiel wird ein [\<wsHttpBinding\>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)\-Element hinzugefügt.  
  
2.  Fügen Sie ein `<binding>``name-Element hinzu, und legen Sie das` \-Attribut auf einen geeigneten Wert fest.  
  
3.  Fügen Sie ein `<security>``mode-Element hinzu, und legen Sie das` `Message-Attribut auf` `Transport,` `TransportWithMessageCredential oder`  fest.  
  
4.  Fügen Sie ein `<transport>`\-Element hinzu, und legen Sie das `clientCredential`\-Attribut auf einen entsprechenden Wert fest, wenn der Modus auf `Transport` festgelegt ist.  
  
     Im folgenden Beispiel wird der Modus auf "`Transport"` festgelegt, und anschließend wird das `clientCredentialType`\-Attribut des `<transport>`\-Elements auf "`Windows"` festgelegt.  
  
    ```  
    <wsHttpBinding>  
    <binding name="TransportSecurity">  
        <security mode="Transport" />  
           <transport clientCredentialType = "Windows" />  
        </security>  
    </binding>  
    </wsHttpBinding >  
    ```  
  
     Sie können auch den `security mode` auf "`Message"` festlegen und anschließend ein `<"message">`\-Element angeben.Im folgenden Beispiel wird der `clientCredentialType` auf "`Certificate"` festgelegt.  
  
    ```  
    <wsHttpBinding>  
    <binding name="MessageSecurity">  
        <security mode="Message" />  
           <message clientCredentialType = "Certificate" />  
        </security>  
    </binding>  
    </wsHttpBinding >  
    ```  
  
     Die Verwendung des <xref:System.ServiceModel.BasicHttpSecurityMode>\-Werts unterliegt besonderen Bedingungen, die nachfolgend beschrieben werden.  
  
### Verwenden von TransportWithMessageCredential  
 Wenn Sie den Sicherheitsmodus auf `TransportWithMessageCredential` festlegen, wird der tatsächliche Mechanismus, der die Sicherheitseinstellungen auf Transportebene bereitstellt, vom Transport bestimmt.Beispielsweise verwendet das HTTP\-Protokoll Secure Sockets Layer \(SSL\) über HTTP \(HTTPS\).Daher werden alle Festlegungen der `ClientCredentialType`\-Eigenschaft eines Transportsicherheitsobjekts \(z. B. <xref:System.ServiceModel.HttpTransportSecurity>\) ignoriert.Dies bedeutet, dass Sie nur den `ClientCredentialType` des Nachrichtensicherheitsobjekts festlegen können \(für die `WSHttpBinding` das <xref:System.ServiceModel.NonDualMessageSecurityOverHttp>\-Objekt\).  
  
 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Vorgehensweise: Verwenden von Transportsicherheit und Nachrichtenanmeldeinformationen](../../../docs/framework/wcf/feature-details/how-to-use-transport-security-and-message-credentials.md).  
  
## Siehe auch  
 [Vorgehensweise: Konfigurieren eines Anschlusses mit einem SSL\-Zertifikat](../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)   
 [Vorgehensweise: Verwenden von Transportsicherheit und Nachrichtenanmeldeinformationen](../../../docs/framework/wcf/feature-details/how-to-use-transport-security-and-message-credentials.md)   
 [Transportsicherheit](../../../docs/framework/wcf/feature-details/transport-security.md)   
 [Nachrichtensicherheit](../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)   
 [Übersicht über die Sicherheit](../../../docs/framework/wcf/feature-details/security-overview.md)   
 [Vom System bereitgestellte Bindungen](../../../docs/framework/wcf/system-provided-bindings.md)   
 [\<Sicherheit\>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)   
 [\<Sicherheit\>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)   
 [\<Sicherheit\>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)
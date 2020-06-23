---
title: 'Vorgehensweise: Festlegen des Sicherheitsmodus'
description: 'Erfahren Sie, wie Sie die drei allgemeinen WCF-Sicherheitsmodi für die meisten vordefinierten Bindungen festlegen: Transport, Message und TransportWithMessageCredential.'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Mode property
- WCF, security mode
- WCF, security
ms.assetid: 6e01dd9f-b5dd-4474-b24c-06e124de4ff7
ms.openlocfilehash: 2f834e1930b7676592f6cbc29a577424d75ebc01
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244542"
---
# <a name="how-to-set-the-security-mode"></a>Vorgehensweise: Festlegen des Sicherheitsmodus

Die Windows Communication Foundation (WCF)-Sicherheit verfügt über drei allgemeine Sicherheitsmodi, die für die meisten vordefinierten Bindungen gefunden werden: Transport, Message und "Transport with Message Credential". Zwei weitere Modi sind bindungsspezifisch: „TransportCredentialOnly“ ist nur in der <xref:System.ServiceModel.BasicHttpBinding> und „Both“ nur in der <xref:System.ServiceModel.NetMsmqBinding> verfügbar. In diesem Thema werden jedoch die drei allgemeinen Sicherheitsmodi behandelt: <xref:System.ServiceModel.SecurityMode.Transport>, <xref:System.ServiceModel.SecurityMode.Message> und <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.

Diese Modi werden nicht von allen vordefinierten Bindungen unterstützt. In diesem Thema wird der Modus mit der <xref:System.ServiceModel.WSHttpBinding>-Klasse und mit der <xref:System.ServiceModel.NetTcpBinding>-Klasse festgelegt, und es wird veranschaulicht, wie der Modus programmgesteuert und in der Konfiguration festgelegt werden kann.

Weitere Informationen finden Sie unter WCF-Sicherheit, [Übersicht über die Sicherheit](./feature-details/security-overview.md), [Sichern von Diensten](securing-services.md)und [Sichern von Diensten und Clients](./feature-details/securing-services-and-clients.md). Weitere Informationen zum Transportmodus und zur Nachricht finden Sie unter [Transportsicherheit](./feature-details/transport-security.md) und [Nachrichten Sicherheit](./feature-details/message-security-in-wcf.md).

## <a name="to-set-the-security-mode-in-code"></a>So legen Sie den Sicherheitsmodus im Code fest

1. Erstellen Sie eine Instanz der Bindungsklasse, die Sie verwenden. Eine Liste der vordefinierten Bindungen finden Sie unter vom [System bereitgestellte Bindungen](system-provided-bindings.md). In diesem Codebeispiel wird eine Instanz der <xref:System.ServiceModel.WSHttpBinding>-Klasse erstellt.

2. Legen Sie die `Mode`-Eigenschaft des Objekts fest, das von der `Security`-Eigenschaft zurückgegeben wird.

     [!code-csharp[c_SettingSecurityMode#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#1)]
     [!code-vb[c_SettingSecurityMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#1)]

     Sie können den Modus auch auf Message festlegen, wie im folgenden Code veranschaulicht wird.

     [!code-csharp[c_SettingSecurityMode#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#2)]
     [!code-vb[c_SettingSecurityMode#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#2)]

     Sie können den Modus auch auf TransportWithMessageCredentials festlegen, wie im folgenden Code veranschaulicht wird.

     [!code-csharp[c_SettingSecurityMode#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#3)]
     [!code-vb[c_SettingSecurityMode#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#3)]

3. Sie können den Modus auch im Konstruktor der Bindung festlegen, wie im folgenden Codebeispiel veranschaulicht wird.

     [!code-csharp[c_SettingSecurityMode#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#4)]
     [!code-vb[c_SettingSecurityMode#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#4)]

## <a name="setting-the-clientcredentialtype-property"></a>Festlegen der ClientCredentialType-Eigenschaft

Durch Festlegen des Modus auf einen der drei Werte wird bestimmt, wie Sie die `ClientCredentialType`-Eigenschaft festlegen können. Wenn Sie beispielsweise die <xref:System.ServiceModel.WSHttpBinding>-Klasse verwenden, müssen Sie die `Transport`-Eigenschaft der <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A>-Klasse auf einen entsprechenden Wert festlegen, wenn der Modus auf <xref:System.ServiceModel.HttpTransportSecurity> festgelegt wird.

### <a name="to-set-the-clientcredentialtype-property-for-transport-mode"></a>So legen Sie die ClientCredentialType-Eigenschaft für den Transport-Modus fest

1. Erstellen Sie eine Instanz der Bindung.

2. Legen Sie die `Mode` -Eigenschaft auf `Transport`fest.

3. Legen Sie für die `ClientCredential`-Eigenschaft einen geeigneten Wert fest. Im folgenden Code wird die Eigenschaft auf `Windows` festgelegt.

     [!code-csharp[c_SettingSecurityMode#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#5)]
     [!code-vb[c_SettingSecurityMode#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#5)]

### <a name="to-set-the-clientcredentialtype-property-for-message-mode"></a>So legen Sie die ClientCredentialType-Eigenschaft für den Message-Modus fest

1. Erstellen Sie eine Instanz der Bindung.

2. Legen Sie die `Mode` -Eigenschaft auf `Message`fest.

3. Legen Sie für die `ClientCredential`-Eigenschaft einen geeigneten Wert fest. Im folgenden Code wird die Eigenschaft auf `Certificate` festgelegt.

     [!code-csharp[c_SettingSecurityMode#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#6)]
     [!code-vb[c_SettingSecurityMode#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#6)]

### <a name="to-set-the-mode-and-clientcredentialtype-property-in-configuration"></a>So legen Sie die Mode-Eigenschaft und die ClientCredentialType-Eigenschaft in der Konfiguration fest

1. Fügen Sie dem- [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) Element der Konfigurationsdatei ein entsprechendes Bindungs Element hinzu. Im folgenden Beispiel wird ein-Element hinzugefügt [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) .

2. Fügen Sie ein `<binding>` -Element hinzu, und legen Sie dessen- `name` Attribut auf einen geeigneten Wert fest

3. Fügen Sie ein `<security>` -Element hinzu, und legen Sie das- `mode` Attribut auf `Message` , `Transport` oder fest `TransportWithMessageCredential` .

4. Fügen Sie ein `Transport``<transport>`-Element hinzu, und legen Sie das -Attribut auf einen entsprechenden Wert fest, wenn der Modus auf `clientCredential` festgelegt ist.

     Im folgenden Beispiel wird der Modus auf "`Transport"` festgelegt, und anschließend wird das `clientCredentialType`-Attribut des `<transport>`-Elements auf "`Windows"` festgelegt.

    ```xml
    <wsHttpBinding>
    <binding name="TransportSecurity">
        <security mode="Transport" >
           <transport clientCredentialType = "Windows" />
        </security>
    </binding>
    </wsHttpBinding >
    ```

     Sie können auch den `security mode` auf "`Message"` festlegen und anschließend ein `<"message">`-Element angeben. Im folgenden Beispiel wird der `clientCredentialType` auf `Certificate"` festgelegt.

    ```xml
    <wsHttpBinding>
    <binding name="MessageSecurity">
        <security mode="Message" >
           <message clientCredentialType = "Certificate" />
        </security>
    </binding>
    </wsHttpBinding >
    ```

     Die Verwendung des <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential>-Werts unterliegt besonderen Bedingungen, die nachfolgend beschrieben werden.

### <a name="using-transportwithmessagecredential"></a>Verwenden von TransportWithMessageCredential

Wenn Sie den Sicherheitsmodus auf `TransportWithMessageCredential` festlegen, wird der tatsächliche Mechanismus, der die Sicherheitseinstellungen auf Transportebene bereitstellt, vom Transport bestimmt. Beispielsweise verwendet das HTTP-Protokoll Secure Sockets Layer (SSL) über HTTP (HTTPS). Daher werden alle Festlegungen der `ClientCredentialType`-Eigenschaft eines Transportsicherheitsobjekts (z. B. <xref:System.ServiceModel.HttpTransportSecurity>) ignoriert.  Dies bedeutet, dass Sie nur den `ClientCredentialType` des Nachrichtensicherheitsobjekts festlegen können (für die `WSHttpBinding`-Bindung, das <xref:System.ServiceModel.NonDualMessageSecurityOverHttp>-Objekt).

Weitere Informationen finden Sie unter Vorgehens [Weise: Verwenden von Transport Sicherheit und Nachrichten Anmelde](./feature-details/how-to-use-transport-security-and-message-credentials.md)Informationen.

## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Konfigurieren eines Anschlusses mit einem SSL-Zertifikat](./feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)
- [Vorgehensweise: Verwenden von Transportsicherheit und Nachrichtenanmeldeinformationen](./feature-details/how-to-use-transport-security-and-message-credentials.md)
- [Transport Sicherheit](./feature-details/transport-security.md)
- [Nachrichtensicherheit](./feature-details/message-security-in-wcf.md)
- [Sicherheitsübersicht](./feature-details/security-overview.md)
- [Vom System bereitgestellte Bindungen](system-provided-bindings.md)
- [\<security>](../configure-apps/file-schema/wcf/security-of-wshttpbinding.md)
- [\<security>](../configure-apps/file-schema/wcf/security-of-basichttpbinding.md)
- [\<security>](../configure-apps/file-schema/wcf/security-of-nettcpbinding.md)

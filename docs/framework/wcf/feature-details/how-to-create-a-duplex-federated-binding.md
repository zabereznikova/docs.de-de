---
title: 'Vorgehensweise: Erstellen einer Bindung mit Duplexverbund'
ms.date: 03/30/2017
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
ms.openlocfilehash: e93651ce9fe9dae55c299fcb061da6bdc4b6bc5e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598969"
---
# <a name="how-to-create-a-duplex-federated-binding"></a>Vorgehensweise: Erstellen einer Bindung mit Duplexverbund

<xref:System.ServiceModel.WSFederationHttpBinding> unterstützt lediglich Datagramm- sowie Anforderung/Antwort-Nachrichtenaustauschverträge. Für die Verwendung des Duplexnachrichtenaustauschvertrags muss eine benutzerdefinierte Bindung erstellt werden. In den folgenden Verfahren wird gezeigt, wie dies in der Konfiguration umgesetzt werden kann. Verwendet werden die Nachrichtenmodussicherheit bei HTTP und TCP sowie die Sicherheit im gemischten Modus bei TCP. Beispielcode mit allen drei Bindungen finden Sie am Ende dieses Themas.

Die Bindung kann auch im Code erstellt werden. Eine Beschreibung des zu erstellenden Bindungs Element Stapels finden Sie unter Gewusst [wie: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).

## <a name="to-create-a-duplex-federated-custom-binding-with-http"></a>So erstellen Sie eine benutzerdefinierte Bindung mit HTTP und Duplexverbund

1. Erstellen Sie im- [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) Knoten der Konfigurationsdatei ein- [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) Element.

2. [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md)Erstellen Sie im-Element ein- [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) Element, bei dem das- `name` Attribut auf festgelegt ist `FederationDuplexHttpMessageSecurityBinding` .

3. [\<binding>](../../configure-apps/file-schema/wcf/bindings.md)Erstellen Sie im-Element ein- [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) Element, bei dem das- `authenticationMode` Attribut auf festgelegt ist `SecureConversation` .

4. [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md)Erstellen Sie im-Element ein- [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) Element, bei dem das- `authenticationMode` Attribut auf oder festgelegt ist `IssuedTokenForCertificate` `IssuedTokenForSslNegotiated` .

5. Erstellen Sie nach dem- [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) Element ein leeres- [\<compositeDuplex>](../../configure-apps/file-schema/wcf/compositeduplex.md) Element.

6. Erstellen Sie nach dem- [\<compositeDuplex>](../../configure-apps/file-schema/wcf/compositeduplex.md) Element ein leeres- [\<oneWay>](../../configure-apps/file-schema/wcf/oneway.md) Element.

7. Erstellen Sie nach dem- [\<oneWay>](../../configure-apps/file-schema/wcf/oneway.md) Element ein leeres- [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md) Element.

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a>So erstellen Sie eine benutzerdefinierte Bindung mit TCP-Nachrichtensicherheitsmodus und Duplexverbund

1. Erstellen Sie im- [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) Knoten der Konfigurationsdatei ein- [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) Element.

2. [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md)Erstellen Sie im-Element ein- [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) Element, bei dem das- `name` Attribut auf festgelegt ist `FederationDuplexTcpMessageSecurityBinding` .

3. [\<binding>](../../configure-apps/file-schema/wcf/bindings.md)Erstellen Sie im-Element ein- [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) Element, bei dem das- `authenticationMode` Attribut auf festgelegt ist `SecureConversation` .

4. [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md)Erstellen Sie im-Element ein- [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) Element, bei dem das- `authenticationMode` Attribut auf oder festgelegt ist `IssuedTokenForCertificate` `IssuedTokenForSslNegotiated` .

5. Erstellen Sie nach dem- [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) Element ein leeres- [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) Element.

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a>So erstellen Sie eine benutzerdefinierte Bindung mit gemischtem TCP-Sicherheitsmodus und Duplexverbund

1. Erstellen Sie im- [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) Knoten der Konfigurationsdatei ein- [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) Element.

2. [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md)Erstellen Sie im-Element ein- [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) Element, bei dem das- `name` Attribut auf festgelegt ist `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding` .

3. [\<binding>](../../configure-apps/file-schema/wcf/bindings.md)Erstellen Sie im-Element ein- [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) Element, bei dem das- `authenticationMode` Attribut auf festgelegt ist `SecureConversation` .

4. [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md)Erstellen Sie im-Element ein- [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) Element, bei dem das- `authenticationMode` Attribut auf oder festgelegt ist `IssuedTokenForCertificate` `IssuedTokenForSslNegotiated` .

5. Erstellen Sie nach dem- [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) Element ein leeres- [\<sslStreamSecurity>](../../configure-apps/file-schema/wcf/sslstreamsecurity.md) Element.

6. Erstellen Sie nach dem- [\<sslStreamSecurity>](../../configure-apps/file-schema/wcf/sslstreamsecurity.md) Element ein leeres- [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) Element.

## <a name="code-sample"></a>Codebeispiel

### <a name="sample-with-3-bindings"></a>Beispiel mit drei Bindungen

1. Fügen Sie den folgenden Code in die Konfigurationsdatei ein:

## <a name="example"></a>Beispiel

```xml
<bindings>
   <customBinding>
      <binding name="FederationDuplexHttpMessageSecurityBinding">
<!-- duplex contract requires secure conversation with require cancellation = true -->
          <security authenticationMode="SecureConversation">
              <secureConversationBootstrap authenticationMode="IssuedTokenForSslNegotiated" />
          </security>
          <compositeDuplex />
          <oneWay />
          <httpTransport />
       </binding>
<!-- duplex over https is not supported -->
       <binding name="FederationDuplexTcpMessageSecurityBinding">
<!-- duplex contract requires secure conversation with require cancellation = true -->
          <security authenticationMode="SecureConversation">
              <secureConversationBootstrap authenticationMode="IssuedTokenForSslNegotiated" />
          </security>
          <tcpTransport />
       </binding>
       <binding name="FederationDuplexTcpTransportSecurityWithMessageCredentialsBinding">
<!-- duplex contract requires secure conversation with require cancellation = true -->
          <security authenticationMode="SecureConversation">
              <secureConversationBootstrap authenticationMode="IssuedTokenOverTransport" />
          </security>
<!-- requireClientCertificate = true or <windowsStreamSecurity /> can be used, but does not make sense for most scenarios -->
          <sslStreamSecurity />
          <tcpTransport />
       </binding>
    </customBinding>
</bindings>
```

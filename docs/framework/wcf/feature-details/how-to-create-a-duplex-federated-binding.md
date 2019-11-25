---
title: 'Vorgehensweise: Erstellen einer Bindung mit Duplexverbund'
ms.date: 03/30/2017
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
ms.openlocfilehash: 3ecd9e2dbeb30bb255cbf66488b50a9b20219431
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141719"
---
# <a name="how-to-create-a-duplex-federated-binding"></a>Vorgehensweise: Erstellen einer Bindung mit Duplexverbund

<xref:System.ServiceModel.WSFederationHttpBinding> unterstützt lediglich Datagramm- sowie Anforderung/Antwort-Nachrichtenaustauschverträge. Für die Verwendung des Duplexnachrichtenaustauschvertrags muss eine benutzerdefinierte Bindung erstellt werden. In den folgenden Verfahren wird gezeigt, wie dies in der Konfiguration umgesetzt werden kann. Verwendet werden die Nachrichtenmodussicherheit bei HTTP und TCP sowie die Sicherheit im gemischten Modus bei TCP. Beispielcode mit allen drei Bindungen finden Sie am Ende dieses Themas.

Die Bindung kann auch im Code erstellt werden. Eine Beschreibung des zu erstellenden Bindungs Element Stapels finden Sie unter Gewusst [wie: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).

## <a name="to-create-a-duplex-federated-custom-binding-with-http"></a>So erstellen Sie eine benutzerdefinierte Bindung mit HTTP und Duplexverbund

1. Erstellen Sie im Knoten [\<Bindungen >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) der Konfigurationsdatei ein [\<CustomBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) Element.

2. Erstellen Sie innerhalb des [\<CustomBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) -Elements eine [\<Binding >](../../configure-apps/file-schema/wcf/bindings.md) -Element, wobei das `name`-Attribut auf `FederationDuplexHttpMessageSecurityBinding`festgelegt ist.

3. Erstellen Sie innerhalb des [\<Binding >](../../configure-apps/file-schema/wcf/bindings.md) -Elements ein [\<Security->](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) Element, wobei das `authenticationMode`-Attribut auf `SecureConversation`festgelegt ist.

4. Erstellen Sie innerhalb des [\<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) -Elements ein [\<secureConversationBootstrap->](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) Element, bei dem das `authenticationMode`-Attribut auf `IssuedTokenForCertificate` oder `IssuedTokenForSslNegotiated`festgelegt ist.

5. Erstellen Sie nach dem [\<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) -Element ein leeres [\<compositeDuplex->](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) Element.

6. Erstellen Sie nach dem [\<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) -Element ein leeres [\<OneWay->](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) Element.

7. Erstellen Sie nach dem [\<OneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) -Element ein leeres [\<httpTransport->](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) Element.

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a>So erstellen Sie eine benutzerdefinierte Bindung mit TCP-Nachrichtensicherheitsmodus und Duplexverbund

1. Erstellen Sie im Knoten [\<Bindungen >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) der Konfigurationsdatei ein [\<CustomBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) Element.

2. Erstellen Sie innerhalb des [\<CustomBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) -Elements eine [\<Binding >](../../configure-apps/file-schema/wcf/bindings.md) -Element, wobei das `name`-Attribut auf `FederationDuplexTcpMessageSecurityBinding`festgelegt ist.

3. Erstellen Sie innerhalb des [\<Binding >](../../configure-apps/file-schema/wcf/bindings.md) -Elements ein [\<Security->](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) Element, wobei das `authenticationMode`-Attribut auf `SecureConversation`festgelegt ist.

4. Erstellen Sie innerhalb des [\<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) -Elements ein [\<secureConversationBootstrap->](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) Element, bei dem das `authenticationMode`-Attribut auf `IssuedTokenForCertificate` oder `IssuedTokenForSslNegotiated`festgelegt ist.

5. Erstellen Sie nach dem [\<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) -Element ein leeres [\<TcpTransport->](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) Element.

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a>So erstellen Sie eine benutzerdefinierte Bindung mit gemischtem TCP-Sicherheitsmodus und Duplexverbund

1. Erstellen Sie im Knoten [\<Bindungen >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) der Konfigurationsdatei ein [\<CustomBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) Element.

2. Erstellen Sie innerhalb des [\<CustomBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) -Elements eine [\<Binding >](../../configure-apps/file-schema/wcf/bindings.md) -Element, wobei das `name`-Attribut auf `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`festgelegt ist.

3. Erstellen Sie innerhalb des [\<Binding >](../../configure-apps/file-schema/wcf/bindings.md) -Elements ein [\<Security->](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) Element, wobei das `authenticationMode`-Attribut auf `SecureConversation`festgelegt ist.

4. Erstellen Sie innerhalb des [\<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) -Elements ein [\<secureConversationBootstrap->](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) Element, bei dem das `authenticationMode`-Attribut auf `IssuedTokenForCertificate` oder `IssuedTokenForSslNegotiated`festgelegt ist.

5. Erstellen Sie nach dem [\<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) -Element ein leeres [\<sslStreamSecurity->](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) Element.

6. Erstellen Sie nach dem [\<sslStreamSecurity->](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) Element ein leeres [\<TcpTransport->](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) Element.

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

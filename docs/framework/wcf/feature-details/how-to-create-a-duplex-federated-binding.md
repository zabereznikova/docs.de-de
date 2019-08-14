---
title: 'Vorgehensweise: Erstellen einer Bindung mit Duplexverbund'
ms.date: 03/30/2017
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
ms.openlocfilehash: 71c970fa45d7d4ccd55fceddb2360d0aa0a768f8
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972063"
---
# <a name="how-to-create-a-duplex-federated-binding"></a>Vorgehensweise: Erstellen einer Bindung mit Duplexverbund

<xref:System.ServiceModel.WSFederationHttpBinding> unterstützt lediglich Datagramm- sowie Anforderung/Antwort-Nachrichtenaustauschverträge. Für die Verwendung des Duplexnachrichtenaustauschvertrags muss eine benutzerdefinierte Bindung erstellt werden. In den folgenden Verfahren wird gezeigt, wie dies in der Konfiguration umgesetzt werden kann. Verwendet werden die Nachrichtenmodussicherheit bei HTTP und TCP sowie die Sicherheit im gemischten Modus bei TCP. Beispielcode mit allen drei Bindungen finden Sie am Ende dieses Themas.

Die Bindung kann auch im Code erstellt werden. Eine Beschreibung des zu erstellenden Bindungs Element Stapels finden [Sie unter Gewusst wie: Erstellen Sie eine benutzerdefinierte Bindung mithilfe von SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).

## <a name="to-create-a-duplex-federated-custom-binding-with-http"></a>So erstellen Sie eine benutzerdefinierte Bindung mit HTTP und Duplexverbund

1. Erstellen Sie im Knoten [ Bindungen>derKonfigurationsdateieincustomBinding->Element.\<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

2. Erstellen Sie innerhalb des [ \<CustomBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) Elements eine [ \<Bindung >](../../../../docs/framework/misc/binding.md) -Element `name` , dessen- `FederationDuplexHttpMessageSecurityBinding`Attribut auf festgelegt ist.

3. Erstellen Sie innerhalb des [ \<Bindungs >](../../../../docs/framework/misc/binding.md) Elements ein [ \<Sicherheits >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) Element, bei `authenticationMode` dem das- `SecureConversation`Attribut auf festgelegt ist.

4. Erstellen Sie innerhalb des [ \<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) -Elements ein [ \<secureConversationBootstrap->](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) Element, bei dem `IssuedTokenForCertificate` das `IssuedTokenForSslNegotiated` `authenticationMode` -Attribut auf oder festgelegt ist.

5. Erstellen Sie nach dem [ \<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) -Element ein leeres [ \<compositeDuplex->](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) Element.

6. Erstellen Sie nach dem [ \<Element compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) ein leeres [ \<OneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) -Element.

7. Erstellen Sie nach dem [ \<OneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) -Element ein leeres [ \<httpTransport->](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) Element.

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a>So erstellen Sie eine benutzerdefinierte Bindung mit TCP-Nachrichtensicherheitsmodus und Duplexverbund

1. Erstellen Sie im Knoten [ Bindungen>derKonfigurationsdateieincustomBinding->Element.\<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

2. Erstellen Sie innerhalb des [ \<CustomBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) Elements eine [ \<Bindung >](../../../../docs/framework/misc/binding.md) -Element `name` , dessen- `FederationDuplexTcpMessageSecurityBinding`Attribut auf festgelegt ist.

3. Erstellen Sie innerhalb des [ \<Bindungs >](../../../../docs/framework/misc/binding.md) Elements ein [ \<Sicherheits >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) Element, bei `authenticationMode` dem das- `SecureConversation`Attribut auf festgelegt ist.

4. Erstellen Sie innerhalb des [ \<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) -Elements ein [ \<secureConversationBootstrap->](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) Element, bei dem `IssuedTokenForCertificate` das `IssuedTokenForSslNegotiated` `authenticationMode` -Attribut auf oder festgelegt ist.

5. Erstellen Sie nach dem [ \<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) -Element ein leeres [ \<TcpTransport->](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) Element.

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a>So erstellen Sie eine benutzerdefinierte Bindung mit gemischtem TCP-Sicherheitsmodus und Duplexverbund

1. Erstellen Sie im Knoten [ Bindungen>derKonfigurationsdateieincustomBinding->Element.\<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

2. Erstellen Sie innerhalb des [ \<CustomBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) Elements eine [ \<Bindung >](../../../../docs/framework/misc/binding.md) -Element `name` , dessen- `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`Attribut auf festgelegt ist.

3. Erstellen Sie innerhalb des [ \<Bindungs >](../../../../docs/framework/misc/binding.md) Elements ein [ \<Sicherheits >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) Element, bei `authenticationMode` dem das- `SecureConversation`Attribut auf festgelegt ist.

4. Erstellen Sie innerhalb des [ \<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) -Elements ein [ \<secureConversationBootstrap->](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) Element, bei dem `IssuedTokenForCertificate` das `IssuedTokenForSslNegotiated` `authenticationMode` -Attribut auf oder festgelegt ist.

5. Erstellen Sie nach dem [ \<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) -Element ein leeres [ \<sslStreamSecurity->](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) Element.

6. Erstellen Sie nach dem [ \<>-Element sslStreamSecurity](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) ein leeres [ \<TcpTransport->](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) Element.

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

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
# <a name="how-to-create-a-duplex-federated-binding"></a><span data-ttu-id="e4c92-102">Vorgehensweise: Erstellen einer Bindung mit Duplexverbund</span><span class="sxs-lookup"><span data-stu-id="e4c92-102">How to: Create a Duplex Federated Binding</span></span>

<span data-ttu-id="e4c92-103"><xref:System.ServiceModel.WSFederationHttpBinding> unterstützt lediglich Datagramm- sowie Anforderung/Antwort-Nachrichtenaustauschverträge.</span><span class="sxs-lookup"><span data-stu-id="e4c92-103"><xref:System.ServiceModel.WSFederationHttpBinding> only supports the datagram and request/reply message exchange contracts.</span></span> <span data-ttu-id="e4c92-104">Für die Verwendung des Duplexnachrichtenaustauschvertrags muss eine benutzerdefinierte Bindung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e4c92-104">To use the duplex message exchange contract, you must create a custom binding.</span></span> <span data-ttu-id="e4c92-105">In den folgenden Verfahren wird gezeigt, wie dies in der Konfiguration umgesetzt werden kann. Verwendet werden die Nachrichtenmodussicherheit bei HTTP und TCP sowie die Sicherheit im gemischten Modus bei TCP.</span><span class="sxs-lookup"><span data-stu-id="e4c92-105">The following procedures show how to do this in configuration, using Message mode security for the HTTP and TCP transports, and using mixed mode security for the TCP transport.</span></span> <span data-ttu-id="e4c92-106">Beispielcode mit allen drei Bindungen finden Sie am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="e4c92-106">Sample code showing all 3 bindings is at the end of this topic.</span></span>

<span data-ttu-id="e4c92-107">Die Bindung kann auch im Code erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e4c92-107">You can also create the binding in code.</span></span> <span data-ttu-id="e4c92-108">Eine Beschreibung des zu erstellenden Bindungs Element Stapels finden Sie unter Gewusst [wie: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="e4c92-108">For a description of the binding elements stack to create, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-http"></a><span data-ttu-id="e4c92-109">So erstellen Sie eine benutzerdefinierte Bindung mit HTTP und Duplexverbund</span><span class="sxs-lookup"><span data-stu-id="e4c92-109">To create a duplex federated custom binding with HTTP</span></span>

1. <span data-ttu-id="e4c92-110">Erstellen Sie im Knoten [\<Bindungen >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) der Konfigurationsdatei ein [\<CustomBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="e4c92-110">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="e4c92-111">Erstellen Sie innerhalb des [\<CustomBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) -Elements eine [\<Binding >](../../configure-apps/file-schema/wcf/bindings.md) -Element, wobei das `name`-Attribut auf `FederationDuplexHttpMessageSecurityBinding`festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e4c92-111">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element with the `name` attribute set to `FederationDuplexHttpMessageSecurityBinding`.</span></span>

3. <span data-ttu-id="e4c92-112">Erstellen Sie innerhalb des [\<Binding >](../../configure-apps/file-schema/wcf/bindings.md) -Elements ein [\<Security->](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) Element, wobei das `authenticationMode`-Attribut auf `SecureConversation`festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e4c92-112">Inside the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="e4c92-113">Erstellen Sie innerhalb des [\<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) -Elements ein [\<secureConversationBootstrap->](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) Element, bei dem das `authenticationMode`-Attribut auf `IssuedTokenForCertificate` oder `IssuedTokenForSslNegotiated`festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e4c92-113">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="e4c92-114">Erstellen Sie nach dem [\<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) -Element ein leeres [\<compositeDuplex->](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) Element.</span><span class="sxs-lookup"><span data-stu-id="e4c92-114">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element.</span></span>

6. <span data-ttu-id="e4c92-115">Erstellen Sie nach dem [\<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) -Element ein leeres [\<OneWay->](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) Element.</span><span class="sxs-lookup"><span data-stu-id="e4c92-115">Following the [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element, create an empty [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element.</span></span>

7. <span data-ttu-id="e4c92-116">Erstellen Sie nach dem [\<OneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) -Element ein leeres [\<httpTransport->](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) Element.</span><span class="sxs-lookup"><span data-stu-id="e4c92-116">Following the [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element, create an empty [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) element.</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a><span data-ttu-id="e4c92-117">So erstellen Sie eine benutzerdefinierte Bindung mit TCP-Nachrichtensicherheitsmodus und Duplexverbund</span><span class="sxs-lookup"><span data-stu-id="e4c92-117">To create a duplex federated custom binding with TCP message security mode</span></span>

1. <span data-ttu-id="e4c92-118">Erstellen Sie im Knoten [\<Bindungen >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) der Konfigurationsdatei ein [\<CustomBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="e4c92-118">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="e4c92-119">Erstellen Sie innerhalb des [\<CustomBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) -Elements eine [\<Binding >](../../configure-apps/file-schema/wcf/bindings.md) -Element, wobei das `name`-Attribut auf `FederationDuplexTcpMessageSecurityBinding`festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e4c92-119">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element with the `name` attribute set to `FederationDuplexTcpMessageSecurityBinding`.</span></span>

3. <span data-ttu-id="e4c92-120">Erstellen Sie innerhalb des [\<Binding >](../../configure-apps/file-schema/wcf/bindings.md) -Elements ein [\<Security->](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) Element, wobei das `authenticationMode`-Attribut auf `SecureConversation`festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e4c92-120">Inside the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="e4c92-121">Erstellen Sie innerhalb des [\<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) -Elements ein [\<secureConversationBootstrap->](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) Element, bei dem das `authenticationMode`-Attribut auf `IssuedTokenForCertificate` oder `IssuedTokenForSslNegotiated`festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e4c92-121">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="e4c92-122">Erstellen Sie nach dem [\<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) -Element ein leeres [\<TcpTransport->](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) Element.</span><span class="sxs-lookup"><span data-stu-id="e4c92-122">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a><span data-ttu-id="e4c92-123">So erstellen Sie eine benutzerdefinierte Bindung mit gemischtem TCP-Sicherheitsmodus und Duplexverbund</span><span class="sxs-lookup"><span data-stu-id="e4c92-123">To create a duplex federated custom binding with TCP mixed security mode</span></span>

1. <span data-ttu-id="e4c92-124">Erstellen Sie im Knoten [\<Bindungen >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) der Konfigurationsdatei ein [\<CustomBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="e4c92-124">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="e4c92-125">Erstellen Sie innerhalb des [\<CustomBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) -Elements eine [\<Binding >](../../configure-apps/file-schema/wcf/bindings.md) -Element, wobei das `name`-Attribut auf `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e4c92-125">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element with the `name` attribute set to `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span></span>

3. <span data-ttu-id="e4c92-126">Erstellen Sie innerhalb des [\<Binding >](../../configure-apps/file-schema/wcf/bindings.md) -Elements ein [\<Security->](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) Element, wobei das `authenticationMode`-Attribut auf `SecureConversation`festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e4c92-126">Inside the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="e4c92-127">Erstellen Sie innerhalb des [\<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) -Elements ein [\<secureConversationBootstrap->](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) Element, bei dem das `authenticationMode`-Attribut auf `IssuedTokenForCertificate` oder `IssuedTokenForSslNegotiated`festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e4c92-127">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="e4c92-128">Erstellen Sie nach dem [\<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) -Element ein leeres [\<sslStreamSecurity->](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) Element.</span><span class="sxs-lookup"><span data-stu-id="e4c92-128">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element.</span></span>

6. <span data-ttu-id="e4c92-129">Erstellen Sie nach dem [\<sslStreamSecurity->](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) Element ein leeres [\<TcpTransport->](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) Element.</span><span class="sxs-lookup"><span data-stu-id="e4c92-129">Following the [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>

## <a name="code-sample"></a><span data-ttu-id="e4c92-130">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="e4c92-130">Code Sample</span></span>

### <a name="sample-with-3-bindings"></a><span data-ttu-id="e4c92-131">Beispiel mit drei Bindungen</span><span class="sxs-lookup"><span data-stu-id="e4c92-131">Sample with 3 Bindings</span></span>

1. <span data-ttu-id="e4c92-132">Fügen Sie den folgenden Code in die Konfigurationsdatei ein:</span><span class="sxs-lookup"><span data-stu-id="e4c92-132">Insert the following code into your configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="e4c92-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e4c92-133">Example</span></span>

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

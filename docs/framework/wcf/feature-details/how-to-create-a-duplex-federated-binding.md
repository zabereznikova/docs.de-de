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
# <a name="how-to-create-a-duplex-federated-binding"></a><span data-ttu-id="25565-102">Vorgehensweise: Erstellen einer Bindung mit Duplexverbund</span><span class="sxs-lookup"><span data-stu-id="25565-102">How to: Create a Duplex Federated Binding</span></span>

<span data-ttu-id="25565-103"><xref:System.ServiceModel.WSFederationHttpBinding> unterstützt lediglich Datagramm- sowie Anforderung/Antwort-Nachrichtenaustauschverträge.</span><span class="sxs-lookup"><span data-stu-id="25565-103"><xref:System.ServiceModel.WSFederationHttpBinding> only supports the datagram and request/reply message exchange contracts.</span></span> <span data-ttu-id="25565-104">Für die Verwendung des Duplexnachrichtenaustauschvertrags muss eine benutzerdefinierte Bindung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="25565-104">To use the duplex message exchange contract, you must create a custom binding.</span></span> <span data-ttu-id="25565-105">In den folgenden Verfahren wird gezeigt, wie dies in der Konfiguration umgesetzt werden kann. Verwendet werden die Nachrichtenmodussicherheit bei HTTP und TCP sowie die Sicherheit im gemischten Modus bei TCP.</span><span class="sxs-lookup"><span data-stu-id="25565-105">The following procedures show how to do this in configuration, using Message mode security for the HTTP and TCP transports, and using mixed mode security for the TCP transport.</span></span> <span data-ttu-id="25565-106">Beispielcode mit allen drei Bindungen finden Sie am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="25565-106">Sample code showing all 3 bindings is at the end of this topic.</span></span>

<span data-ttu-id="25565-107">Die Bindung kann auch im Code erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="25565-107">You can also create the binding in code.</span></span> <span data-ttu-id="25565-108">Eine Beschreibung des zu erstellenden Bindungs Element Stapels finden [Sie unter Gewusst wie: Erstellen Sie eine benutzerdefinierte Bindung mithilfe von SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="25565-108">For a description of the binding elements stack to create, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-http"></a><span data-ttu-id="25565-109">So erstellen Sie eine benutzerdefinierte Bindung mit HTTP und Duplexverbund</span><span class="sxs-lookup"><span data-stu-id="25565-109">To create a duplex federated custom binding with HTTP</span></span>

1. <span data-ttu-id="25565-110">Erstellen Sie im Knoten [ Bindungen>derKonfigurationsdateieincustomBinding->Element.\<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="25565-110">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="25565-111">Erstellen Sie innerhalb des [ \<CustomBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) Elements eine [ \<Bindung >](../../../../docs/framework/misc/binding.md) -Element `name` , dessen- `FederationDuplexHttpMessageSecurityBinding`Attribut auf festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="25565-111">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexHttpMessageSecurityBinding`.</span></span>

3. <span data-ttu-id="25565-112">Erstellen Sie innerhalb des [ \<Bindungs >](../../../../docs/framework/misc/binding.md) Elements ein [ \<Sicherheits >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) Element, bei `authenticationMode` dem das- `SecureConversation`Attribut auf festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="25565-112">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="25565-113">Erstellen Sie innerhalb des [ \<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) -Elements ein [ \<secureConversationBootstrap->](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) Element, bei dem `IssuedTokenForCertificate` das `IssuedTokenForSslNegotiated` `authenticationMode` -Attribut auf oder festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="25565-113">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="25565-114">Erstellen Sie nach dem [ \<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) -Element ein leeres [ \<compositeDuplex->](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) Element.</span><span class="sxs-lookup"><span data-stu-id="25565-114">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element.</span></span>

6. <span data-ttu-id="25565-115">Erstellen Sie nach dem [ \<Element compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) ein leeres [ \<OneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) -Element.</span><span class="sxs-lookup"><span data-stu-id="25565-115">Following the [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element, create an empty [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element.</span></span>

7. <span data-ttu-id="25565-116">Erstellen Sie nach dem [ \<OneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) -Element ein leeres [ \<httpTransport->](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) Element.</span><span class="sxs-lookup"><span data-stu-id="25565-116">Following the [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element, create an empty [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) element.</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a><span data-ttu-id="25565-117">So erstellen Sie eine benutzerdefinierte Bindung mit TCP-Nachrichtensicherheitsmodus und Duplexverbund</span><span class="sxs-lookup"><span data-stu-id="25565-117">To create a duplex federated custom binding with TCP message security mode</span></span>

1. <span data-ttu-id="25565-118">Erstellen Sie im Knoten [ Bindungen>derKonfigurationsdateieincustomBinding->Element.\<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="25565-118">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="25565-119">Erstellen Sie innerhalb des [ \<CustomBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) Elements eine [ \<Bindung >](../../../../docs/framework/misc/binding.md) -Element `name` , dessen- `FederationDuplexTcpMessageSecurityBinding`Attribut auf festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="25565-119">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpMessageSecurityBinding`.</span></span>

3. <span data-ttu-id="25565-120">Erstellen Sie innerhalb des [ \<Bindungs >](../../../../docs/framework/misc/binding.md) Elements ein [ \<Sicherheits >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) Element, bei `authenticationMode` dem das- `SecureConversation`Attribut auf festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="25565-120">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="25565-121">Erstellen Sie innerhalb des [ \<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) -Elements ein [ \<secureConversationBootstrap->](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) Element, bei dem `IssuedTokenForCertificate` das `IssuedTokenForSslNegotiated` `authenticationMode` -Attribut auf oder festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="25565-121">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="25565-122">Erstellen Sie nach dem [ \<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) -Element ein leeres [ \<TcpTransport->](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) Element.</span><span class="sxs-lookup"><span data-stu-id="25565-122">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a><span data-ttu-id="25565-123">So erstellen Sie eine benutzerdefinierte Bindung mit gemischtem TCP-Sicherheitsmodus und Duplexverbund</span><span class="sxs-lookup"><span data-stu-id="25565-123">To create a duplex federated custom binding with TCP mixed security mode</span></span>

1. <span data-ttu-id="25565-124">Erstellen Sie im Knoten [ Bindungen>derKonfigurationsdateieincustomBinding->Element.\<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="25565-124">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="25565-125">Erstellen Sie innerhalb des [ \<CustomBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) Elements eine [ \<Bindung >](../../../../docs/framework/misc/binding.md) -Element `name` , dessen- `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`Attribut auf festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="25565-125">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span></span>

3. <span data-ttu-id="25565-126">Erstellen Sie innerhalb des [ \<Bindungs >](../../../../docs/framework/misc/binding.md) Elements ein [ \<Sicherheits >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) Element, bei `authenticationMode` dem das- `SecureConversation`Attribut auf festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="25565-126">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="25565-127">Erstellen Sie innerhalb des [ \<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) -Elements ein [ \<secureConversationBootstrap->](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) Element, bei dem `IssuedTokenForCertificate` das `IssuedTokenForSslNegotiated` `authenticationMode` -Attribut auf oder festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="25565-127">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="25565-128">Erstellen Sie nach dem [ \<Security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) -Element ein leeres [ \<sslStreamSecurity->](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) Element.</span><span class="sxs-lookup"><span data-stu-id="25565-128">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element.</span></span>

6. <span data-ttu-id="25565-129">Erstellen Sie nach dem [ \<>-Element sslStreamSecurity](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) ein leeres [ \<TcpTransport->](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) Element.</span><span class="sxs-lookup"><span data-stu-id="25565-129">Following the [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>

## <a name="code-sample"></a><span data-ttu-id="25565-130">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="25565-130">Code Sample</span></span>

### <a name="sample-with-3-bindings"></a><span data-ttu-id="25565-131">Beispiel mit drei Bindungen</span><span class="sxs-lookup"><span data-stu-id="25565-131">Sample with 3 Bindings</span></span>

1. <span data-ttu-id="25565-132">Fügen Sie den folgenden Code in die Konfigurationsdatei ein:</span><span class="sxs-lookup"><span data-stu-id="25565-132">Insert the following code into your configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="25565-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="25565-133">Example</span></span>

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

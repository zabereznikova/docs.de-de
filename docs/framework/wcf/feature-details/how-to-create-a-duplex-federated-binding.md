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
# <a name="how-to-create-a-duplex-federated-binding"></a><span data-ttu-id="924b1-102">Vorgehensweise: Erstellen einer Bindung mit Duplexverbund</span><span class="sxs-lookup"><span data-stu-id="924b1-102">How to: Create a Duplex Federated Binding</span></span>

<span data-ttu-id="924b1-103"><xref:System.ServiceModel.WSFederationHttpBinding> unterstützt lediglich Datagramm- sowie Anforderung/Antwort-Nachrichtenaustauschverträge.</span><span class="sxs-lookup"><span data-stu-id="924b1-103"><xref:System.ServiceModel.WSFederationHttpBinding> only supports the datagram and request/reply message exchange contracts.</span></span> <span data-ttu-id="924b1-104">Für die Verwendung des Duplexnachrichtenaustauschvertrags muss eine benutzerdefinierte Bindung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="924b1-104">To use the duplex message exchange contract, you must create a custom binding.</span></span> <span data-ttu-id="924b1-105">In den folgenden Verfahren wird gezeigt, wie dies in der Konfiguration umgesetzt werden kann. Verwendet werden die Nachrichtenmodussicherheit bei HTTP und TCP sowie die Sicherheit im gemischten Modus bei TCP.</span><span class="sxs-lookup"><span data-stu-id="924b1-105">The following procedures show how to do this in configuration, using Message mode security for the HTTP and TCP transports, and using mixed mode security for the TCP transport.</span></span> <span data-ttu-id="924b1-106">Beispielcode mit allen drei Bindungen finden Sie am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="924b1-106">Sample code showing all 3 bindings is at the end of this topic.</span></span>

<span data-ttu-id="924b1-107">Die Bindung kann auch im Code erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="924b1-107">You can also create the binding in code.</span></span> <span data-ttu-id="924b1-108">Eine Beschreibung des zu erstellenden Bindungs Element Stapels finden Sie unter Gewusst [wie: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="924b1-108">For a description of the binding elements stack to create, see [How to: Create a Custom Binding Using the SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-http"></a><span data-ttu-id="924b1-109">So erstellen Sie eine benutzerdefinierte Bindung mit HTTP und Duplexverbund</span><span class="sxs-lookup"><span data-stu-id="924b1-109">To create a duplex federated custom binding with HTTP</span></span>

1. <span data-ttu-id="924b1-110">Erstellen Sie im- [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) Knoten der Konfigurationsdatei ein- [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="924b1-110">In the [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="924b1-111">[\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md)Erstellen Sie im-Element ein- [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) Element, bei dem das- `name` Attribut auf festgelegt ist `FederationDuplexHttpMessageSecurityBinding` .</span><span class="sxs-lookup"><span data-stu-id="924b1-111">Inside the [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element with the `name` attribute set to `FederationDuplexHttpMessageSecurityBinding`.</span></span>

3. <span data-ttu-id="924b1-112">[\<binding>](../../configure-apps/file-schema/wcf/bindings.md)Erstellen Sie im-Element ein- [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) Element, bei dem das- `authenticationMode` Attribut auf festgelegt ist `SecureConversation` .</span><span class="sxs-lookup"><span data-stu-id="924b1-112">Inside the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element, create a [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="924b1-113">[\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md)Erstellen Sie im-Element ein- [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) Element, bei dem das- `authenticationMode` Attribut auf oder festgelegt ist `IssuedTokenForCertificate` `IssuedTokenForSslNegotiated` .</span><span class="sxs-lookup"><span data-stu-id="924b1-113">Inside the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="924b1-114">Erstellen Sie nach dem- [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) Element ein leeres- [\<compositeDuplex>](../../configure-apps/file-schema/wcf/compositeduplex.md) Element.</span><span class="sxs-lookup"><span data-stu-id="924b1-114">Following the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<compositeDuplex>](../../configure-apps/file-schema/wcf/compositeduplex.md) element.</span></span>

6. <span data-ttu-id="924b1-115">Erstellen Sie nach dem- [\<compositeDuplex>](../../configure-apps/file-schema/wcf/compositeduplex.md) Element ein leeres- [\<oneWay>](../../configure-apps/file-schema/wcf/oneway.md) Element.</span><span class="sxs-lookup"><span data-stu-id="924b1-115">Following the [\<compositeDuplex>](../../configure-apps/file-schema/wcf/compositeduplex.md) element, create an empty [\<oneWay>](../../configure-apps/file-schema/wcf/oneway.md) element.</span></span>

7. <span data-ttu-id="924b1-116">Erstellen Sie nach dem- [\<oneWay>](../../configure-apps/file-schema/wcf/oneway.md) Element ein leeres- [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md) Element.</span><span class="sxs-lookup"><span data-stu-id="924b1-116">Following the [\<oneWay>](../../configure-apps/file-schema/wcf/oneway.md) element, create an empty [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md) element.</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a><span data-ttu-id="924b1-117">So erstellen Sie eine benutzerdefinierte Bindung mit TCP-Nachrichtensicherheitsmodus und Duplexverbund</span><span class="sxs-lookup"><span data-stu-id="924b1-117">To create a duplex federated custom binding with TCP message security mode</span></span>

1. <span data-ttu-id="924b1-118">Erstellen Sie im- [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) Knoten der Konfigurationsdatei ein- [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="924b1-118">In the [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="924b1-119">[\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md)Erstellen Sie im-Element ein- [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) Element, bei dem das- `name` Attribut auf festgelegt ist `FederationDuplexTcpMessageSecurityBinding` .</span><span class="sxs-lookup"><span data-stu-id="924b1-119">Inside the [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element with the `name` attribute set to `FederationDuplexTcpMessageSecurityBinding`.</span></span>

3. <span data-ttu-id="924b1-120">[\<binding>](../../configure-apps/file-schema/wcf/bindings.md)Erstellen Sie im-Element ein- [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) Element, bei dem das- `authenticationMode` Attribut auf festgelegt ist `SecureConversation` .</span><span class="sxs-lookup"><span data-stu-id="924b1-120">Inside the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element, create a [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="924b1-121">[\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md)Erstellen Sie im-Element ein- [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) Element, bei dem das- `authenticationMode` Attribut auf oder festgelegt ist `IssuedTokenForCertificate` `IssuedTokenForSslNegotiated` .</span><span class="sxs-lookup"><span data-stu-id="924b1-121">Inside the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="924b1-122">Erstellen Sie nach dem- [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) Element ein leeres- [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) Element.</span><span class="sxs-lookup"><span data-stu-id="924b1-122">Following the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a><span data-ttu-id="924b1-123">So erstellen Sie eine benutzerdefinierte Bindung mit gemischtem TCP-Sicherheitsmodus und Duplexverbund</span><span class="sxs-lookup"><span data-stu-id="924b1-123">To create a duplex federated custom binding with TCP mixed security mode</span></span>

1. <span data-ttu-id="924b1-124">Erstellen Sie im- [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) Knoten der Konfigurationsdatei ein- [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="924b1-124">In the [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="924b1-125">[\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md)Erstellen Sie im-Element ein- [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) Element, bei dem das- `name` Attribut auf festgelegt ist `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding` .</span><span class="sxs-lookup"><span data-stu-id="924b1-125">Inside the [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element with the `name` attribute set to `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span></span>

3. <span data-ttu-id="924b1-126">[\<binding>](../../configure-apps/file-schema/wcf/bindings.md)Erstellen Sie im-Element ein- [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) Element, bei dem das- `authenticationMode` Attribut auf festgelegt ist `SecureConversation` .</span><span class="sxs-lookup"><span data-stu-id="924b1-126">Inside the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element, create a [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="924b1-127">[\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md)Erstellen Sie im-Element ein- [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) Element, bei dem das- `authenticationMode` Attribut auf oder festgelegt ist `IssuedTokenForCertificate` `IssuedTokenForSslNegotiated` .</span><span class="sxs-lookup"><span data-stu-id="924b1-127">Inside the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="924b1-128">Erstellen Sie nach dem- [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) Element ein leeres- [\<sslStreamSecurity>](../../configure-apps/file-schema/wcf/sslstreamsecurity.md) Element.</span><span class="sxs-lookup"><span data-stu-id="924b1-128">Following the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<sslStreamSecurity>](../../configure-apps/file-schema/wcf/sslstreamsecurity.md) element.</span></span>

6. <span data-ttu-id="924b1-129">Erstellen Sie nach dem- [\<sslStreamSecurity>](../../configure-apps/file-schema/wcf/sslstreamsecurity.md) Element ein leeres- [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) Element.</span><span class="sxs-lookup"><span data-stu-id="924b1-129">Following the [\<sslStreamSecurity>](../../configure-apps/file-schema/wcf/sslstreamsecurity.md) element, create an empty [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>

## <a name="code-sample"></a><span data-ttu-id="924b1-130">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="924b1-130">Code Sample</span></span>

### <a name="sample-with-3-bindings"></a><span data-ttu-id="924b1-131">Beispiel mit drei Bindungen</span><span class="sxs-lookup"><span data-stu-id="924b1-131">Sample with 3 Bindings</span></span>

1. <span data-ttu-id="924b1-132">Fügen Sie den folgenden Code in die Konfigurationsdatei ein:</span><span class="sxs-lookup"><span data-stu-id="924b1-132">Insert the following code into your configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="924b1-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="924b1-133">Example</span></span>

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

---
title: 'Vorgehensweise: Erstellen einer Bindung mit Duplexverbund'
ms.date: 03/30/2017
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
ms.openlocfilehash: 510faa0b1d791b1d164c55e9fa32daafa559d56c
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59346235"
---
# <a name="how-to-create-a-duplex-federated-binding"></a><span data-ttu-id="106d9-102">Vorgehensweise: Erstellen einer Bindung mit Duplexverbund</span><span class="sxs-lookup"><span data-stu-id="106d9-102">How to: Create a Duplex Federated Binding</span></span>
<xref:System.ServiceModel.WSFederationHttpBinding> <span data-ttu-id="106d9-103">unterstützt nur die Datagramm- sowie Anforderung/Antwort-nachrichtenaustauschverträge.</span><span class="sxs-lookup"><span data-stu-id="106d9-103">only supports the datagram and request/reply message exchange contracts.</span></span> <span data-ttu-id="106d9-104">Für die Verwendung des Duplexnachrichtenaustauschvertrags muss eine benutzerdefinierte Bindung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="106d9-104">To use the duplex message exchange contract, you must create a custom binding.</span></span> <span data-ttu-id="106d9-105">In den folgenden Verfahren wird gezeigt, wie dies in der Konfiguration umgesetzt werden kann. Verwendet werden die Nachrichtenmodussicherheit bei HTTP und TCP sowie die Sicherheit im gemischten Modus bei TCP.</span><span class="sxs-lookup"><span data-stu-id="106d9-105">The following procedures show how to do this in configuration, using Message mode security for the HTTP and TCP transports, and using mixed mode security for the TCP transport.</span></span> <span data-ttu-id="106d9-106">Beispielcode mit allen drei Bindungen finden Sie am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="106d9-106">Sample code showing all 3 bindings is at the end of this topic.</span></span>  
  
 <span data-ttu-id="106d9-107">Die Bindung kann auch im Code erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="106d9-107">You can also create the binding in code.</span></span> <span data-ttu-id="106d9-108">Eine Beschreibung des bindungsstapels Elemente erstellen, finden Sie unter [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="106d9-108">For a description of the binding elements stack to create, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-http"></a><span data-ttu-id="106d9-109">So erstellen Sie eine benutzerdefinierte Bindung mit HTTP und Duplexverbund</span><span class="sxs-lookup"><span data-stu-id="106d9-109">To create a duplex federated custom binding with HTTP</span></span>  
  
1. <span data-ttu-id="106d9-110">In der [ \<Bindungen >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) Knoten, der die XML-Konfigurationsdatei erstellt einen [ \<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="106d9-110">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>  
  
2. <span data-ttu-id="106d9-111">In der [ \<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) Element erstellen eine [ \<Bindung >](../../../../docs/framework/misc/binding.md) -Element mit der `name` -Attributsatz auf `FederationDuplexHttpMessageSecurityBinding`.</span><span class="sxs-lookup"><span data-stu-id="106d9-111">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexHttpMessageSecurityBinding`.</span></span>  
  
3. <span data-ttu-id="106d9-112">In der [ \<Bindung >](../../../../docs/framework/misc/binding.md) Element erstellen eine [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) -Element mit der `authenticationMode` -Attributsatz auf `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="106d9-112">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4. <span data-ttu-id="106d9-113">In der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) Element erstellen eine [ \<SecureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) -Element mit der `authenticationMode` -Attributsatz auf `IssuedTokenForCertificate` oder `IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="106d9-113">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5. <span data-ttu-id="106d9-114">Nach der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) -Element, erstellen Sie eine leere [ \<CompositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) Element.</span><span class="sxs-lookup"><span data-stu-id="106d9-114">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element.</span></span>  
  
6. <span data-ttu-id="106d9-115">Nach der [ \<CompositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) -Element, erstellen Sie eine leere [ \<OneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) Element.</span><span class="sxs-lookup"><span data-stu-id="106d9-115">Following the [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element, create an empty [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element.</span></span>  
  
7. <span data-ttu-id="106d9-116">Nach der [ \<OneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) -Element, erstellen Sie eine leere [ \<HttpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) Element.</span><span class="sxs-lookup"><span data-stu-id="106d9-116">Following the [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element, create an empty [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) element.</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a><span data-ttu-id="106d9-117">So erstellen Sie eine benutzerdefinierte Bindung mit TCP-Nachrichtensicherheitsmodus und Duplexverbund</span><span class="sxs-lookup"><span data-stu-id="106d9-117">To create a duplex federated custom binding with TCP message security mode</span></span>  
  
1. <span data-ttu-id="106d9-118">In der [ \<Bindungen >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) Knoten, der die XML-Konfigurationsdatei erstellt einen [ \<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="106d9-118">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>   
  
2. <span data-ttu-id="106d9-119">In der [ \<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) Element erstellen eine [ \<Bindung >](../../../../docs/framework/misc/binding.md) -Element mit der `name` -Attributsatz auf `FederationDuplexTcpMessageSecurityBinding`.</span><span class="sxs-lookup"><span data-stu-id="106d9-119">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpMessageSecurityBinding`.</span></span>  
  
3. <span data-ttu-id="106d9-120">In der [ \<Bindung >](../../../../docs/framework/misc/binding.md) Element erstellen eine [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) -Element mit der `authenticationMode` -Attributsatz auf `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="106d9-120">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4. <span data-ttu-id="106d9-121">In der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) Element erstellen eine [ \<SecureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) -Element mit der `authenticationMode` -Attributsatz auf `IssuedTokenForCertificate` oder `IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="106d9-121">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5. <span data-ttu-id="106d9-122">Nach der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) -Element, erstellen Sie eine leere [ \<TcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) Element.</span><span class="sxs-lookup"><span data-stu-id="106d9-122">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a><span data-ttu-id="106d9-123">So erstellen Sie eine benutzerdefinierte Bindung mit gemischtem TCP-Sicherheitsmodus und Duplexverbund</span><span class="sxs-lookup"><span data-stu-id="106d9-123">To create a duplex federated custom binding with TCP mixed security mode</span></span>  
  
1. <span data-ttu-id="106d9-124">In der [ \<Bindungen >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) Knoten, der die XML-Konfigurationsdatei erstellt einen [ \<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="106d9-124">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>   
  
2. <span data-ttu-id="106d9-125">In der [ \<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) Element erstellen eine [ \<Bindung >](../../../../docs/framework/misc/binding.md) -Element mit der `name` -Attributsatz auf `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span><span class="sxs-lookup"><span data-stu-id="106d9-125">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span></span>  
  
3. <span data-ttu-id="106d9-126">In der [ \<Bindung >](../../../../docs/framework/misc/binding.md) Element erstellen eine [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) -Element mit der `authenticationMode` -Attributsatz auf `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="106d9-126">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4. <span data-ttu-id="106d9-127">In der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) Element erstellen eine [ \<SecureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) -Element mit der `authenticationMode` -Attributsatz auf `IssuedTokenForCertificate` oder `IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="106d9-127">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5. <span data-ttu-id="106d9-128">Nach der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) -Element, erstellen Sie eine leere [ \<SslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) Element.</span><span class="sxs-lookup"><span data-stu-id="106d9-128">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element.</span></span>  
  
6. <span data-ttu-id="106d9-129">Nach der [ \<SslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) -Element, erstellen Sie eine leere [ \<TcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) Element.</span><span class="sxs-lookup"><span data-stu-id="106d9-129">Following the [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>  
  
## <a name="code-sample"></a><span data-ttu-id="106d9-130">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="106d9-130">Code Sample</span></span>  
  
#### <a name="sample-with-3-bindings"></a><span data-ttu-id="106d9-131">Beispiel mit drei Bindungen</span><span class="sxs-lookup"><span data-stu-id="106d9-131">Sample with 3 Bindings</span></span>  
  
1. <span data-ttu-id="106d9-132">Fügen Sie den folgenden Code in die Konfigurationsdatei ein:</span><span class="sxs-lookup"><span data-stu-id="106d9-132">Insert the following code into your configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="106d9-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="106d9-133">Example</span></span>  
  
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

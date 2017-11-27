---
title: 'Vorgehensweise: Erstellen einer Bindung mit Duplexverbund'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0a682b84a90e64e0242a3490986cb526c7f028b8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-a-duplex-federated-binding"></a><span data-ttu-id="ac068-102">Vorgehensweise: Erstellen einer Bindung mit Duplexverbund</span><span class="sxs-lookup"><span data-stu-id="ac068-102">How to: Create a Duplex Federated Binding</span></span>
<span data-ttu-id="ac068-103"><xref:System.ServiceModel.WSFederationHttpBinding> unterstützt lediglich Datagramm- sowie Anforderung/Antwort-Nachrichtenaustauschverträge.</span><span class="sxs-lookup"><span data-stu-id="ac068-103"><xref:System.ServiceModel.WSFederationHttpBinding> only supports the datagram and request/reply message exchange contracts.</span></span> <span data-ttu-id="ac068-104">Für die Verwendung des Duplexnachrichtenaustauschvertrags muss eine benutzerdefinierte Bindung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ac068-104">To use the duplex message exchange contract, you must create a custom binding.</span></span> <span data-ttu-id="ac068-105">In den folgenden Verfahren wird gezeigt, wie dies in der Konfiguration umgesetzt werden kann. Verwendet werden die Nachrichtenmodussicherheit bei HTTP und TCP sowie die Sicherheit im gemischten Modus bei TCP.</span><span class="sxs-lookup"><span data-stu-id="ac068-105">The following procedures show how to do this in configuration, using Message mode security for the HTTP and TCP transports, and using mixed mode security for the TCP transport.</span></span> <span data-ttu-id="ac068-106">Beispielcode mit allen drei Bindungen finden Sie am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="ac068-106">Sample code showing all 3 bindings is at the end of this topic.</span></span>  
  
 <span data-ttu-id="ac068-107">Die Bindung kann auch im Code erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ac068-107">You can also create the binding in code.</span></span> <span data-ttu-id="ac068-108">Eine Beschreibung des bindungsstapels Elemente erstellen, finden Sie unter [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="ac068-108">For a description of the binding elements stack to create, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-http"></a><span data-ttu-id="ac068-109">So erstellen Sie eine benutzerdefinierte Bindung mit HTTP und Duplexverbund</span><span class="sxs-lookup"><span data-stu-id="ac068-109">To create a duplex federated custom binding with HTTP</span></span>  
  
1.  <span data-ttu-id="ac068-110">In der [ \<Bindungen >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) Knoten, der die XML-Konfigurationsdatei erstellen eine [ \<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="ac068-110">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>  
  
2.  <span data-ttu-id="ac068-111">Innerhalb der [ \<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) Element, erstellen Sie eine [ \<Bindung >](../../../../docs/framework/misc/binding.md) Element mit der `name` -Attributsatz zur `FederationDuplexHttpMessageSecurityBinding`.</span><span class="sxs-lookup"><span data-stu-id="ac068-111">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexHttpMessageSecurityBinding`.</span></span>  
  
3.  <span data-ttu-id="ac068-112">Innerhalb der [ \<Bindung >](../../../../docs/framework/misc/binding.md) Element, erstellen Sie eine [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) Element mit der `authenticationMode` -Attributsatz zur `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="ac068-112">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4.  <span data-ttu-id="ac068-113">Innerhalb der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) Element, erstellen Sie eine [ \<SecureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) Element mit der `authenticationMode` -Attributsatz zur `IssuedTokenForCertificate` oder `IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="ac068-113">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5.  <span data-ttu-id="ac068-114">Nach der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) Element, erstellen Sie eine leere [ \<CompositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) Element.</span><span class="sxs-lookup"><span data-stu-id="ac068-114">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element.</span></span>  
  
6.  <span data-ttu-id="ac068-115">Nach der [ \<CompositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) Element, erstellen Sie eine leere [ \<OneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) Element.</span><span class="sxs-lookup"><span data-stu-id="ac068-115">Following the [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element, create an empty [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element.</span></span>  
  
7.  <span data-ttu-id="ac068-116">Nach der [ \<OneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) Element, erstellen Sie eine leere [ \<HttpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) Element.</span><span class="sxs-lookup"><span data-stu-id="ac068-116">Following the [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element, create an empty [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) element.</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a><span data-ttu-id="ac068-117">So erstellen Sie eine benutzerdefinierte Bindung mit TCP-Nachrichtensicherheitsmodus und Duplexverbund</span><span class="sxs-lookup"><span data-stu-id="ac068-117">To create a duplex federated custom binding with TCP message security mode</span></span>  
  
1.  <span data-ttu-id="ac068-118">In der [ \<Bindungen >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) Knoten, der die XML-Konfigurationsdatei erstellen eine [ \<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="ac068-118">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>   
  
2.  <span data-ttu-id="ac068-119">Innerhalb der [ \<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) Element, erstellen Sie eine [ \<Bindung >](../../../../docs/framework/misc/binding.md) Element mit der `name` -Attributsatz zur `FederationDuplexTcpMessageSecurityBinding`.</span><span class="sxs-lookup"><span data-stu-id="ac068-119">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpMessageSecurityBinding`.</span></span>  
  
3.  <span data-ttu-id="ac068-120">Innerhalb der [ \<Bindung >](../../../../docs/framework/misc/binding.md) Element, erstellen Sie eine [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) Element mit der `authenticationMode` -Attributsatz zur `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="ac068-120">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4.  <span data-ttu-id="ac068-121">Innerhalb der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) Element, erstellen Sie eine [ \<SecureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) Element mit der `authenticationMode` -Attributsatz zur `IssuedTokenForCertificate` oder `IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="ac068-121">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5.  <span data-ttu-id="ac068-122">Nach der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) Element, erstellen Sie eine leere [ \<TcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) Element.</span><span class="sxs-lookup"><span data-stu-id="ac068-122">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a><span data-ttu-id="ac068-123">So erstellen Sie eine benutzerdefinierte Bindung mit gemischtem TCP-Sicherheitsmodus und Duplexverbund</span><span class="sxs-lookup"><span data-stu-id="ac068-123">To create a duplex federated custom binding with TCP mixed security mode</span></span>  
  
1.  <span data-ttu-id="ac068-124">In der [ \<Bindungen >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) Knoten, der die XML-Konfigurationsdatei erstellen eine [ \<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="ac068-124">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>   
  
2.  <span data-ttu-id="ac068-125">Innerhalb der [ \<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) Element, erstellen Sie eine [ \<Bindung >](../../../../docs/framework/misc/binding.md) Element mit der `name` -Attributsatz zur `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span><span class="sxs-lookup"><span data-stu-id="ac068-125">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span></span>  
  
3.  <span data-ttu-id="ac068-126">Innerhalb der [ \<Bindung >](../../../../docs/framework/misc/binding.md) Element, erstellen Sie eine [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) Element mit der `authenticationMode` -Attributsatz zur `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="ac068-126">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4.  <span data-ttu-id="ac068-127">Innerhalb der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) Element, erstellen Sie eine [ \<SecureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) Element mit der `authenticationMode` -Attributsatz zur `IssuedTokenForCertificate` oder `IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="ac068-127">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5.  <span data-ttu-id="ac068-128">Nach der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) Element, erstellen Sie eine leere [ \<SslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) Element.</span><span class="sxs-lookup"><span data-stu-id="ac068-128">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element.</span></span>  
  
6.  <span data-ttu-id="ac068-129">Nach der [ \<SslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) Element, erstellen Sie eine leere [ \<TcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) Element.</span><span class="sxs-lookup"><span data-stu-id="ac068-129">Following the [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>  
  
## <a name="code-sample"></a><span data-ttu-id="ac068-130">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="ac068-130">Code Sample</span></span>  
  
#### <a name="sample-with-3-bindings"></a><span data-ttu-id="ac068-131">Beispiel mit drei Bindungen</span><span class="sxs-lookup"><span data-stu-id="ac068-131">Sample with 3 Bindings</span></span>  
  
1.  <span data-ttu-id="ac068-132">Fügen Sie den folgenden Code in die Konfigurationsdatei ein:</span><span class="sxs-lookup"><span data-stu-id="ac068-132">Insert the following code into your configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac068-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ac068-133">Example</span></span>  
  
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

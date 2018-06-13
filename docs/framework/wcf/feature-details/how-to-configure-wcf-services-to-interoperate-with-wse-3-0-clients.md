---
title: 'Vorgehensweise: Konfigurieren von WCF-Diensten für die Zusammenarbeit mit WSE3.0-Clients'
ms.date: 03/30/2017
ms.assetid: 0f38c4a0-49a6-437c-bdde-ad1d138d3c4a
ms.openlocfilehash: 174ecd279f9380136532ce0d5105b7a71b6d88da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33495108"
---
# <a name="how-to-configure-wcf-services-to-interoperate-with-wse-30-clients"></a><span data-ttu-id="c169d-102">Vorgehensweise: Konfigurieren von WCF-Diensten für die Zusammenarbeit mit WSE3.0-Clients</span><span class="sxs-lookup"><span data-stu-id="c169d-102">How to: Configure WCF Services to Interoperate with WSE 3.0 Clients</span></span>
<span data-ttu-id="c169d-103">Windows Communication Foundation (WCF)-Dienste sind auf Transportebene mit Web Services Enhancements 3.0 für Microsoft .NET (WSE)-Clients kompatibel, wenn WCF-Dienste konfiguriert sind, verwenden Sie die Version vom August 2004 des WS-Addressing-Spezifikation.</span><span class="sxs-lookup"><span data-stu-id="c169d-103">Windows Communication Foundation (WCF) services are wire-level compatible with Web Services Enhancements 3.0 for Microsoft .NET (WSE) clients when WCF services are configured to use the August 2004 version of the WS-Addressing specification.</span></span>  
  
### <a name="to-enable-a-wcf-service-to-interoperate-with-wse-30-clients"></a><span data-ttu-id="c169d-104">So konfigurieren Sie einen WCF-Dienst für die Zusammenarbeit mit WSE3.0-Clients</span><span class="sxs-lookup"><span data-stu-id="c169d-104">To enable a WCF service to interoperate with WSE 3.0 clients</span></span>  
  
1.  <span data-ttu-id="c169d-105">Definieren Sie eine benutzerdefinierte Bindung für den WCF-Dienst.</span><span class="sxs-lookup"><span data-stu-id="c169d-105">Define a custom binding for the WCF service.</span></span>  
  
     <span data-ttu-id="c169d-106">Es muss eine benutzerdefinierte Bindung erstellt werden, um anzugeben, dass die Version der WS-Adressierungsspezifikation vom August 2004 für die Nachrichtencodierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c169d-106">To specify that the August 2004 version of the WS-Addressing specification is used for message encoding, a custom binding must be created.</span></span>  
  
    1.  <span data-ttu-id="c169d-107">Fügen Sie ein untergeordnetes [ \<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) auf die [ \<Bindungen >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) der Konfigurationsdatei des Diensts.</span><span class="sxs-lookup"><span data-stu-id="c169d-107">Add a child [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) to the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) of the service's configuration file.</span></span>  
  
    2.  <span data-ttu-id="c169d-108">Geben Sie einen Namen für die Bindung, die durch Hinzufügen einer [ \<Bindung >](../../../../docs/framework/misc/binding.md) auf die [ \<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) verwendet wird und die `name` Attribut.</span><span class="sxs-lookup"><span data-stu-id="c169d-108">Specify a name for the binding, by adding a [\<binding>](../../../../docs/framework/misc/binding.md) to the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) and setting the `name` attribute.</span></span>  
  
    3.  <span data-ttu-id="c169d-109">Geben Sie einen Authentifizierungsmodus und die Version der WS-Security-Spezifikationen, die verwendet werden, um Nachrichten zu sichern, die mit WSE 3.0 kompatibel sind, indem Sie ein untergeordnetes Element hinzufügen [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) auf die [ \<binden >](../../../../docs/framework/misc/binding.md).</span><span class="sxs-lookup"><span data-stu-id="c169d-109">Specify an authentication mode and the version of the WS-Security specifications that are used to secure messages that are compatible with WSE 3.0, by adding a child [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) to the [\<binding>](../../../../docs/framework/misc/binding.md).</span></span>  
  
         <span data-ttu-id="c169d-110">Legen den Authentifizierungsmodus, zum Festlegen der `authenicationMode` Attribut von der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="c169d-110">To set the authentication mode, set the `authenicationMode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span> <span data-ttu-id="c169d-111">Ein Authentifizierungsmodus ist mit einer sofort verwendbaren WSE 3.0-Sicherheitsassertion vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="c169d-111">An authentication mode is roughly equivalent to a turnkey security assertion in WSE 3.0.</span></span> <span data-ttu-id="c169d-112">Die folgende Tabelle ordnet Authentifizierungsmodi in WCF Sicherheitsassertionen in WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="c169d-112">The following table maps authentication modes in WCF to turnkey security assertions in WSE 3.0.</span></span>  
  
        |<span data-ttu-id="c169d-113">WCF-Authentifizierungsmodus</span><span class="sxs-lookup"><span data-stu-id="c169d-113">WCF Authentication Mode</span></span>|<span data-ttu-id="c169d-114">Sofort verwendbare WSE 3.0-Sicherheitsassertion</span><span class="sxs-lookup"><span data-stu-id="c169d-114">WSE 3.0 turnkey security assertion</span></span>|  
        |-----------------------------|----------------------------------------|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>|`anonymousForCertificateSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.Kerberos>|`kerberosSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate10Security`*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate11Security`*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameOverTransport>|`usernameOverTransportSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameForCertificate>|`usernameForCertificateSecurity`|  
  
         <span data-ttu-id="c169d-115">\* Einer der Hauptunterschiede zwischen den `mutualCertificate10Security` und `mutualCertificate11Security` Sicherheitsassertionen ist die Version der WS-Security-Spezifikation, die WSE zum Sichern der SOAP-Nachrichten verwendet.</span><span class="sxs-lookup"><span data-stu-id="c169d-115">\* One of the primary differences between the `mutualCertificate10Security` and `mutualCertificate11Security` turnkey security assertions is the version of the WS-Security specification that WSE uses to secure the SOAP messages.</span></span> <span data-ttu-id="c169d-116">Für `mutualCertificate10Security` wird WS-Security 1.0 verwendet, wohingegen WS-Security 1.1 für `mutualCertificate11Security` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c169d-116">For `mutualCertificate10Security`, WS-Security 1.0 is used, whereas WS-Security 1.1 is used for `mutualCertificate11Security`.</span></span> <span data-ttu-id="c169d-117">Für WCF-Version der WS-Security-Spezifikation wird angegeben, der `messageSecurityVersion` Attribut von der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="c169d-117">For WCF, the version of the WS-Security specification is specified in the `messageSecurityVersion` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span>  
  
         <span data-ttu-id="c169d-118">Um die Version der WS-Security-Spezifikation festgelegt, die zum Sichern von SOAP-Nachrichten verwendet wird, legen Sie die `messageSecurityVersion` Attribut von der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="c169d-118">To set the version of the WS-Security specification that is used to secure SOAP messages, set the `messageSecurityVersion` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span> <span data-ttu-id="c169d-119">Für die Zusammenarbeit mit WSE 3.0 legen Sie den Wert des `messageSecurityVersion`-Attributs auf <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A> fest.</span><span class="sxs-lookup"><span data-stu-id="c169d-119">To interoperate with WSE 3.0, set the value of the `messageSecurityVersion` attribute to <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.</span></span>  
  
    4.  <span data-ttu-id="c169d-120">Gibt an, dass die Version vom August 2004 des WS-Addressing-Spezifikation durch Hinzufügen von WCF verwendet wird eine [ \<TextMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md) und legen Sie die `messageVersion` auf seinen Wert auf <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>.</span><span class="sxs-lookup"><span data-stu-id="c169d-120">Specify that the August 2004 version of the WS-Addressing specification is used by WCF by adding a [\<textMessageEncoding>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md) and set the `messageVersion` to its value to <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="c169d-121">Wenn Sie SOAP 1.2 verwenden, legen Sie das `messageVersion`-Attribut auf <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A> fest.</span><span class="sxs-lookup"><span data-stu-id="c169d-121">When you are using SOAP 1.2, set the `messageVersion` attribute to <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.</span></span>  
  
2.  <span data-ttu-id="c169d-122">Geben Sie an, dass der Dienst die benutzerdefinierte Bindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="c169d-122">Specify that the service uses the custom binding.</span></span>  
  
    1.  <span data-ttu-id="c169d-123">Legen Sie die `binding` Attribut des der [ \<Endpunkt >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) Element `customBinding`.</span><span class="sxs-lookup"><span data-stu-id="c169d-123">Set the `binding` attribute of the [\<endpoint>](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element to `customBinding`.</span></span>  
  
    2.  <span data-ttu-id="c169d-124">Festlegen der `bindingConfiguration` Attribut des der [ \<Endpunkt >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) Element im angegebenen Wert der `name` Attribut des der [ \<Bindung >](../../../../docs/framework/misc/binding.md) für das benutzerdefinierte die Bindung.</span><span class="sxs-lookup"><span data-stu-id="c169d-124">Set the `bindingConfiguration` attribute of the [\<endpoint>](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element to the value specified in the `name` attribute of the [\<binding>](../../../../docs/framework/misc/binding.md) for the custom binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c169d-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c169d-125">Example</span></span>  
 <span data-ttu-id="c169d-126">Das folgende Codebeispiel gibt an, dass `Service.HelloWorldService` eine benutzerdefinierte Bindung zur Zusammenarbeit mit WSE 3.0-Clients verwendet.</span><span class="sxs-lookup"><span data-stu-id="c169d-126">The following code example specifies that the `Service.HelloWorldService` uses a custom binding to interoperate with WSE 3.0 clients.</span></span> <span data-ttu-id="c169d-127">Die benutzerdefinierte Bindung gibt an, dass die Version der WS-Adressierungsspezifikation vom August 2004 und die Spezifikationen von WS-Security 1.1 zum Codieren der ausgetauschten Nachrichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c169d-127">The custom binding specifies that the August 2004 version of the WS-Addressing and the WS-Security 1.1 set of specifications are used to encode the exchanged messages.</span></span> <span data-ttu-id="c169d-128">Die Nachrichten werden mit dem <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>-Authentifizierungsmodus geschützt.</span><span class="sxs-lookup"><span data-stu-id="c169d-128">The messages are secured using the <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate> authentication mode.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service   
        behaviorConfiguration="ServiceBehavior"   
        name="Service.HelloWorldService">  
        <endpoint binding="customBinding" address=""  
          bindingConfiguration="ServiceBinding"  
          contract="Service.IHelloWorld"></endpoint>  
      </service>  
    </services>  
  
    <bindings>  
      <customBinding>  
        <binding name="ServiceBinding">  
          <security authenticationMode="AnonymousForCertificate"  
                  messageProtectionOrder="SignBeforeEncrypt"  
                  messageSecurityVersion="WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10"  
                  requireDerivedKeys="false">  
          </security>  
          <textMessageEncoding messageVersion ="Soap11WSAddressingAugust2004"></textMessageEncoding>  
          <httpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    <behaviors>  
      <behavior name="ServiceBehavior" returnUnknownExceptionsAsFaults="true">  
        <serviceCredentials>  
          <serviceCertificate findValue="CN=WCFQuickstartServer" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectDistinguishedName"/>  
        </serviceCredentials>  
      </behavior>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c169d-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c169d-129">See Also</span></span>  
 [<span data-ttu-id="c169d-130">Vorgehensweise: Anpassen einer vom System bereitgestellten Bindung</span><span class="sxs-lookup"><span data-stu-id="c169d-130">How to: Customize a System-Provided Binding</span></span>](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)

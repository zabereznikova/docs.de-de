---
title: 'Vorgehensweise: Konfigurieren von WCF-Diensten für die Zusammenarbeit mit WSE3.0-Clients'
ms.date: 03/30/2017
ms.assetid: 0f38c4a0-49a6-437c-bdde-ad1d138d3c4a
ms.openlocfilehash: 600b9c28d92f9e2b6e4d586b052cc5762d591521
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599060"
---
# <a name="how-to-configure-wcf-services-to-interoperate-with-wse-30-clients"></a><span data-ttu-id="30cb1-102">Vorgehensweise: Konfigurieren von WCF-Diensten für die Zusammenarbeit mit WSE3.0-Clients</span><span class="sxs-lookup"><span data-stu-id="30cb1-102">How to: Configure WCF Services to Interoperate with WSE 3.0 Clients</span></span>

<span data-ttu-id="30cb1-103">Windows Communication Foundation (WCF)-Dienste sind auf Wire-Ebene kompatibel mit Webdienst Erweiterungen 3,0 für Microsoft .net (WSE)-Clients, wenn WCF-Dienste für die Verwendung der WS-Adressierungs Spezifikation vom August 2004 konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="30cb1-103">Windows Communication Foundation (WCF) services are wire-level compatible with Web Services Enhancements 3.0 for Microsoft .NET (WSE) clients when WCF services are configured to use the August 2004 version of the WS-Addressing specification.</span></span>

### <a name="to-enable-a-wcf-service-to-interoperate-with-wse-30-clients"></a><span data-ttu-id="30cb1-104">So konfigurieren Sie einen WCF-Dienst für die Zusammenarbeit mit WSE3.0-Clients</span><span class="sxs-lookup"><span data-stu-id="30cb1-104">To enable a WCF service to interoperate with WSE 3.0 clients</span></span>

1. <span data-ttu-id="30cb1-105">Definieren Sie eine benutzerdefinierte Bindung für den WCF-Dienst.</span><span class="sxs-lookup"><span data-stu-id="30cb1-105">Define a custom binding for the WCF service.</span></span>

    <span data-ttu-id="30cb1-106">Es muss eine benutzerdefinierte Bindung erstellt werden, um anzugeben, dass die Version der WS-Adressierungsspezifikation vom August 2004 für die Nachrichtencodierung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="30cb1-106">To specify that the August 2004 version of the WS-Addressing specification is used for message encoding, a custom binding must be created.</span></span>

    1. <span data-ttu-id="30cb1-107">Fügen Sie der der [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) Konfigurationsdatei des dienstaners ein untergeordnetes Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="30cb1-107">Add a child [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) to the [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) of the service's configuration file.</span></span>

    2. <span data-ttu-id="30cb1-108">Geben Sie einen Namen für die Bindung an, indem Sie einen hinzufügen [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) und das- `name` Attribut festlegen.</span><span class="sxs-lookup"><span data-stu-id="30cb1-108">Specify a name for the binding, by adding a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) to the [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) and setting the `name` attribute.</span></span>

    3. <span data-ttu-id="30cb1-109">Geben Sie einen Authentifizierungsmodus und die Version der WS-Security-Spezifikationen an, die zum Sichern von Nachrichten verwendet werden, die mit WSE 3,0 kompatibel sind, indem Sie dem ein untergeordnetes Element hinzufügen [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) .</span><span class="sxs-lookup"><span data-stu-id="30cb1-109">Specify an authentication mode and the version of the WS-Security specifications that are used to secure messages that are compatible with WSE 3.0, by adding a child [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) to the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md).</span></span>

        <span data-ttu-id="30cb1-110">Um den Authentifizierungsmodus festzulegen, legen Sie das- `authenticationMode` Attribut von fest [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="30cb1-110">To set the authentication mode, set the `authenticationMode` attribute of the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span> <span data-ttu-id="30cb1-111">Ein Authentifizierungsmodus ist mit einer sofort verwendbaren WSE 3.0-Sicherheitsassertion vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="30cb1-111">An authentication mode is roughly equivalent to a turnkey security assertion in WSE 3.0.</span></span> <span data-ttu-id="30cb1-112">In der folgenden Tabelle sind die Authentifizierungs Modi in WCF den schlüsselfertigen Sicherheits Assertionen in WSE 3,0 zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="30cb1-112">The following table maps authentication modes in WCF to turnkey security assertions in WSE 3.0.</span></span>

        |<span data-ttu-id="30cb1-113">WCF-Authentifizierungsmodus</span><span class="sxs-lookup"><span data-stu-id="30cb1-113">WCF Authentication Mode</span></span>|<span data-ttu-id="30cb1-114">Sofort verwendbare WSE 3.0-Sicherheitsassertion</span><span class="sxs-lookup"><span data-stu-id="30cb1-114">WSE 3.0 turnkey security assertion</span></span>|
        |-----------------------------|----------------------------------------|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>|`anonymousForCertificateSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.Kerberos>|`kerberosSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate10Security`*|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate11Security`*|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameOverTransport>|`usernameOverTransportSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameForCertificate>|`usernameForCertificateSecurity`|

        <span data-ttu-id="30cb1-115">\*Einer der Hauptunterschiede zwischen der und der sofort einsetzbaren Sicherheits Assertionen `mutualCertificate10Security` `mutualCertificate11Security` ist die Version der WS-Security-Spezifikation, die von WSE zum Sichern der SOAP-Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="30cb1-115">\* One of the primary differences between the `mutualCertificate10Security` and `mutualCertificate11Security` turnkey security assertions is the version of the WS-Security specification that WSE uses to secure the SOAP messages.</span></span> <span data-ttu-id="30cb1-116">Für `mutualCertificate10Security` wird WS-Security 1.0 verwendet, wohingegen WS-Security 1.1 für `mutualCertificate11Security` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="30cb1-116">For `mutualCertificate10Security`, WS-Security 1.0 is used, whereas WS-Security 1.1 is used for `mutualCertificate11Security`.</span></span> <span data-ttu-id="30cb1-117">Für WCF wird die Version der WS-Security-Spezifikation im- `messageSecurityVersion` Attribut von angegeben [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="30cb1-117">For WCF, the version of the WS-Security specification is specified in the `messageSecurityVersion` attribute of the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span>

        <span data-ttu-id="30cb1-118">Um die Version der WS-Security-Spezifikation festzulegen, die zum Sichern von SOAP-Nachrichten verwendet wird, legen Sie das- `messageSecurityVersion` Attribut von fest [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) .</span><span class="sxs-lookup"><span data-stu-id="30cb1-118">To set the version of the WS-Security specification that is used to secure SOAP messages, set the `messageSecurityVersion` attribute of the [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span> <span data-ttu-id="30cb1-119">Für die Zusammenarbeit mit WSE 3.0 legen Sie den Wert des `messageSecurityVersion`-Attributs auf <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A> fest.</span><span class="sxs-lookup"><span data-stu-id="30cb1-119">To interoperate with WSE 3.0, set the value of the `messageSecurityVersion` attribute to <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.</span></span>

    4. <span data-ttu-id="30cb1-120">Geben Sie an, dass die Version vom August 2004 der WS-Adressierungs Spezifikation von WCF verwendet wird, indem Sie eine hinzufügen [\<textMessageEncoding>](../../configure-apps/file-schema/wcf/textmessageencoding.md) und den `messageVersion` Wert auf festlegen <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A> .</span><span class="sxs-lookup"><span data-stu-id="30cb1-120">Specify that the August 2004 version of the WS-Addressing specification is used by WCF by adding a [\<textMessageEncoding>](../../configure-apps/file-schema/wcf/textmessageencoding.md) and set the `messageVersion` to its value to <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>.</span></span>

        > [!NOTE]
        > <span data-ttu-id="30cb1-121">Wenn Sie SOAP 1.2 verwenden, legen Sie das `messageVersion`-Attribut auf <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A> fest.</span><span class="sxs-lookup"><span data-stu-id="30cb1-121">When you are using SOAP 1.2, set the `messageVersion` attribute to <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.</span></span>

2. <span data-ttu-id="30cb1-122">Geben Sie an, dass der Dienst die benutzerdefinierte Bindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="30cb1-122">Specify that the service uses the custom binding.</span></span>

    1. <span data-ttu-id="30cb1-123">Legen Sie das- `binding` Attribut des- [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) Elements auf fest `customBinding` .</span><span class="sxs-lookup"><span data-stu-id="30cb1-123">Set the `binding` attribute of the [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) element to `customBinding`.</span></span>

    2. <span data-ttu-id="30cb1-124">Legen Sie das- `bindingConfiguration` Attribut des- [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) Elements auf den Wert fest, der im- `name` Attribut der [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) für die benutzerdefinierte Bindung angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="30cb1-124">Set the `bindingConfiguration` attribute of the [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) element to the value specified in the `name` attribute of the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) for the custom binding.</span></span>

## <a name="example"></a><span data-ttu-id="30cb1-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="30cb1-125">Example</span></span>

<span data-ttu-id="30cb1-126">Das folgende Codebeispiel gibt an, dass `Service.HelloWorldService` eine benutzerdefinierte Bindung zur Zusammenarbeit mit WSE 3.0-Clients verwendet.</span><span class="sxs-lookup"><span data-stu-id="30cb1-126">The following code example specifies that the `Service.HelloWorldService` uses a custom binding to interoperate with WSE 3.0 clients.</span></span> <span data-ttu-id="30cb1-127">Die benutzerdefinierte Bindung gibt an, dass die Version der WS-Adressierungsspezifikation vom August 2004 und die Spezifikationen von WS-Security 1.1 zum Codieren der ausgetauschten Nachrichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="30cb1-127">The custom binding specifies that the August 2004 version of the WS-Addressing and the WS-Security 1.1 set of specifications are used to encode the exchanged messages.</span></span> <span data-ttu-id="30cb1-128">Die Nachrichten werden mit dem <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>-Authentifizierungsmodus geschützt.</span><span class="sxs-lookup"><span data-stu-id="30cb1-128">The messages are secured using the <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate> authentication mode.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="30cb1-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="30cb1-129">See also</span></span>

- [<span data-ttu-id="30cb1-130">Vorgehensweise: Anpassen einer vom System bereitgestellten Bindung</span><span class="sxs-lookup"><span data-stu-id="30cb1-130">How to: Customize a System-Provided Binding</span></span>](../extending/how-to-customize-a-system-provided-binding.md)

---
title: <message> von <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: 5a4a4e8b645ee2c607988ac3031af537c93ca8c0
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736761"
---
# <a name="message-of-netmsmqbinding"></a><span data-ttu-id="ae596-102">\<-Nachrichten > \<NetMsmqBinding-></span><span class="sxs-lookup"><span data-stu-id="ae596-102">\<message> of \<netMsmqBinding></span></span>

<span data-ttu-id="ae596-103">Definiert die SOAP-Nachrichtensicherheitseinstellungen für diese `netMsmqBinding`-Bindung.</span><span class="sxs-lookup"><span data-stu-id="ae596-103">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>

<span data-ttu-id="ae596-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ae596-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ae596-105">&nbsp; &nbsp;[ **\<system. Service Model->** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="ae596-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ae596-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="ae596-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="ae596-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<NetMsmqBinding**](netmsmqbinding.md) ></span><span class="sxs-lookup"><span data-stu-id="ae596-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)</span></span>\
<span data-ttu-id="ae596-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="ae596-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="ae596-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Sicherheit >** ](security-of-netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="ae596-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netmsmqbinding.md)</span></span>\
<span data-ttu-id="ae596-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Meldung** ></span><span class="sxs-lookup"><span data-stu-id="ae596-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="ae596-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="ae596-111">Syntax</span></span>

```xml
<netMsmqBinding>
  <binding>
    <security>
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
    </security>
  </binding>
</netMsmqBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ae596-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ae596-112">Attributes and Elements</span></span>

<span data-ttu-id="ae596-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ae596-113">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ae596-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="ae596-114">Attributes</span></span>

|<span data-ttu-id="ae596-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="ae596-115">Attribute</span></span>|<span data-ttu-id="ae596-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ae596-116">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="ae596-117">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="ae596-117">algorithmSuite</span></span>|<span data-ttu-id="ae596-118">Legt die Nachrichtenverschlüsselungs- und Key Wrap-Algorithmen fest, die die nachrichtenbasierte Sicherheit für über den MSMQ-Transport gesendete Nachrichten sicherstellen.</span><span class="sxs-lookup"><span data-stu-id="ae596-118">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="ae596-119">Der Standardwert ist `Aes256`sein.</span><span class="sxs-lookup"><span data-stu-id="ae596-119">The default value is `Aes256`.</span></span> <span data-ttu-id="ae596-120">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="ae596-120">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|
|<span data-ttu-id="ae596-121">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="ae596-121">clientCredentialType</span></span>|<span data-ttu-id="ae596-122">Gibt den Anmeldeinformationstyp an, der bei der Clientauthentifizierung für über den MSMQ-Transport gesendete Nachrichten verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ae596-122">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="ae596-123">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="ae596-123">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ae596-124">-None: Dies ermöglicht es dem Dienst, mit anonymen Clients zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="ae596-124">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="ae596-125">Weder der Dienst noch der Client erfordern Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="ae596-125">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="ae596-126">-Windows: Dadurch kann der SOAP-Austausch im authentifizierten Kontext von Windows-Anmelde Informationen erfolgen.</span><span class="sxs-lookup"><span data-stu-id="ae596-126">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="ae596-127">Dies führt immer zur Durchführung einer auf Kerberos basierenden Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="ae596-127">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="ae596-128">-Username: Dadurch kann der Dienst verlangen, dass der Client mit Benutzernamen Anmelde Informationen authentifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="ae596-128">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="ae596-129">Die Anmelde Informationen müssen in diesem Fall mithilfe des `clientCredentials` Verhaltens Vorsicht angegeben werden **:** Windows Communication Foundation (WCF) unterstützt nicht das Senden eines Kenn Wort Hashwerts oder das Ableiten von Schlüsseln mithilfe eines Kennworts und die Verwendung solcher Schlüssel für die Nachrichten Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="ae596-129">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  Windows Communication Foundation (WCF) does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="ae596-130">Daher erzwingt WCF, dass der Exchange-Schutz bei Verwendung von Benutzernamen-Anmelde Informationen geschützt ist.</span><span class="sxs-lookup"><span data-stu-id="ae596-130">Therefore, WCF enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="ae596-131">Für diesen Modus ist es erforderlich, dass das Dienstzertifikat auf dem Client mithilfe des `clientCredential`-Verhaltens und `serviceCertificate` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ae596-131">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="ae596-132">-Certificate: Dadurch kann der Dienst verlangen, dass der Client mit einem Zertifikat authentifiziert werden muss.</span><span class="sxs-lookup"><span data-stu-id="ae596-132">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="ae596-133">Die Clientanmeldeinformationen müssen in diesem Fall über das `clientCredentials`-Verhalten angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ae596-133">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="ae596-134">In diesem Fall müssen die Dienstanmeldeinformationen mit dem `clientCredentials`-Verhalten durch Bereitstellen von `serviceCertificate` angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ae596-134">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="ae596-135">-CardSpace: Dies ermöglicht es dem Dienst zu verlangen, dass der Client mithilfe eines CardSpace authentifiziert werden muss.</span><span class="sxs-lookup"><span data-stu-id="ae596-135">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="ae596-136">`serviceCertificate` muss im `clientCredential`-Verhalten bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ae596-136">The `serviceCertificate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="ae596-137">Der Standardwert ist `Windows`sein.</span><span class="sxs-lookup"><span data-stu-id="ae596-137">The default value is `Windows`.</span></span> <span data-ttu-id="ae596-138">Dieses Attribut ist vom Typ <xref:System.ServiceModel.MessageCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="ae596-138">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="ae596-139">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ae596-139">Child Elements</span></span>

<span data-ttu-id="ae596-140">Keiner</span><span class="sxs-lookup"><span data-stu-id="ae596-140">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ae596-141">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ae596-141">Parent Elements</span></span>

|<span data-ttu-id="ae596-142">Element</span><span class="sxs-lookup"><span data-stu-id="ae596-142">Element</span></span>|<span data-ttu-id="ae596-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ae596-143">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ae596-144">\<Security ></span><span class="sxs-lookup"><span data-stu-id="ae596-144">\<security></span></span>](security-of-netmsmqbinding.md)|<span data-ttu-id="ae596-145">Definiert die Sicherheitseinstellungen für eine Bindung.</span><span class="sxs-lookup"><span data-stu-id="ae596-145">Defines the security settings for a binding.</span></span>|

## <a name="see-also"></a><span data-ttu-id="ae596-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae596-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>
- <xref:System.ServiceModel.MessageSecurityOverMsmq>
- [<span data-ttu-id="ae596-147">Warteschlangen in WCF</span><span class="sxs-lookup"><span data-stu-id="ae596-147">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="ae596-148">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="ae596-148">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="ae596-149">Bindungen</span><span class="sxs-lookup"><span data-stu-id="ae596-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ae596-150">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="ae596-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="ae596-151">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="ae596-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="ae596-152">\<binding ></span><span class="sxs-lookup"><span data-stu-id="ae596-152">\<binding></span></span>](bindings.md)

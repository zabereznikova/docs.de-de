---
title: <message> von <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: 5a4a4e8b645ee2c607988ac3031af537c93ca8c0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736761"
---
# <a name="message-of-netmsmqbinding"></a><span data-ttu-id="3d9b6-102">\<message> von \<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="3d9b6-102">\<message> of \<netMsmqBinding></span></span>

<span data-ttu-id="3d9b6-103">Definiert die SOAP-Nachrichtensicherheitseinstellungen für diese `netMsmqBinding`-Bindung.</span><span class="sxs-lookup"><span data-stu-id="3d9b6-103">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  

## <a name="syntax"></a><span data-ttu-id="3d9b6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3d9b6-104">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="3d9b6-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3d9b6-105">Attributes and Elements</span></span>

<span data-ttu-id="3d9b6-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3d9b6-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="3d9b6-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="3d9b6-107">Attributes</span></span>

|<span data-ttu-id="3d9b6-108">attribute</span><span class="sxs-lookup"><span data-stu-id="3d9b6-108">Attribute</span></span>|<span data-ttu-id="3d9b6-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3d9b6-109">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="3d9b6-110">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="3d9b6-110">algorithmSuite</span></span>|<span data-ttu-id="3d9b6-111">Legt die Nachrichtenverschlüsselungs- und Key Wrap-Algorithmen fest, die die nachrichtenbasierte Sicherheit für über den MSMQ-Transport gesendete Nachrichten sicherstellen.</span><span class="sxs-lookup"><span data-stu-id="3d9b6-111">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="3d9b6-112">Der Standardwert ist `Aes256`.</span><span class="sxs-lookup"><span data-stu-id="3d9b6-112">The default value is `Aes256`.</span></span> <span data-ttu-id="3d9b6-113">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="3d9b6-113">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|
|<span data-ttu-id="3d9b6-114">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="3d9b6-114">clientCredentialType</span></span>|<span data-ttu-id="3d9b6-115">Gibt den Anmeldeinformationstyp an, der bei der Clientauthentifizierung für über den MSMQ-Transport gesendete Nachrichten verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3d9b6-115">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="3d9b6-116">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="3d9b6-116">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="3d9b6-117">-None: Dies ermöglicht es dem Dienst, mit anonymen Clients zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="3d9b6-117">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="3d9b6-118">Weder der Dienst noch der Client erfordern Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="3d9b6-118">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="3d9b6-119">-Windows: Dadurch kann der SOAP-Austausch im authentifizierten Kontext von Windows-Anmelde Informationen erfolgen.</span><span class="sxs-lookup"><span data-stu-id="3d9b6-119">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="3d9b6-120">Dies führt immer zur Durchführung einer auf Kerberos basierenden Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="3d9b6-120">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="3d9b6-121">-Username: Dadurch kann der Dienst verlangen, dass der Client mit Benutzernamen Anmelde Informationen authentifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="3d9b6-121">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="3d9b6-122">Die Anmelde Informationen müssen in diesem Fall mit dem `clientCredentials` Verhaltens Vorsicht angegeben werden **:** Windows Communication Foundation (WCF) unterstützt nicht das Senden eines Kenn Wort Hashwerts oder das Ableiten von Schlüsseln mithilfe eines Kennworts und die Verwendung solcher Schlüssel für die Nachrichten Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="3d9b6-122">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  Windows Communication Foundation (WCF) does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="3d9b6-123">Daher wird in WCF bei Verwendung von UserName-Anmeldeinformationen ein gesicherter Austausch erzwungen.</span><span class="sxs-lookup"><span data-stu-id="3d9b6-123">Therefore, WCF enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="3d9b6-124">Für diesen Modus ist es erforderlich, dass das Dienstzertifikat auf dem Client mithilfe des `clientCredential`-Verhaltens und `serviceCertificate` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3d9b6-124">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="3d9b6-125">-Certificate: Dadurch kann der Dienst verlangen, dass der Client mit einem Zertifikat authentifiziert werden muss.</span><span class="sxs-lookup"><span data-stu-id="3d9b6-125">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="3d9b6-126">Die Clientanmeldeinformationen müssen in diesem Fall über das `clientCredentials`-Verhalten angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3d9b6-126">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="3d9b6-127">In diesem Fall müssen die Dienstanmeldeinformationen mit dem `clientCredentials`-Verhalten durch Bereitstellen von `serviceCertificate` angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3d9b6-127">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="3d9b6-128">-CardSpace: Dies ermöglicht es dem Dienst zu verlangen, dass der Client mithilfe eines CardSpace authentifiziert werden muss.</span><span class="sxs-lookup"><span data-stu-id="3d9b6-128">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="3d9b6-129">`serviceCertificate` muss im `clientCredential`-Verhalten bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="3d9b6-129">The `serviceCertificate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="3d9b6-130">Der Standardwert ist `Windows`.</span><span class="sxs-lookup"><span data-stu-id="3d9b6-130">The default value is `Windows`.</span></span> <span data-ttu-id="3d9b6-131">Dieses Attribut ist vom Typ <xref:System.ServiceModel.MessageCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="3d9b6-131">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="3d9b6-132">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3d9b6-132">Child Elements</span></span>

<span data-ttu-id="3d9b6-133">Keine</span><span class="sxs-lookup"><span data-stu-id="3d9b6-133">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3d9b6-134">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3d9b6-134">Parent Elements</span></span>

|<span data-ttu-id="3d9b6-135">Element</span><span class="sxs-lookup"><span data-stu-id="3d9b6-135">Element</span></span>|<span data-ttu-id="3d9b6-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3d9b6-136">Description</span></span>|
|-------------|-----------------|
|[\<security>](security-of-netmsmqbinding.md)|<span data-ttu-id="3d9b6-137">Definiert die Sicherheitseinstellungen für eine Bindung.</span><span class="sxs-lookup"><span data-stu-id="3d9b6-137">Defines the security settings for a binding.</span></span>|

## <a name="see-also"></a><span data-ttu-id="3d9b6-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3d9b6-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>
- <xref:System.ServiceModel.MessageSecurityOverMsmq>
- [<span data-ttu-id="3d9b6-139">Warteschlangen in WCF</span><span class="sxs-lookup"><span data-stu-id="3d9b6-139">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="3d9b6-140">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="3d9b6-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="3d9b6-141">Bindungen</span><span class="sxs-lookup"><span data-stu-id="3d9b6-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3d9b6-142">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="3d9b6-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="3d9b6-143">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="3d9b6-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)

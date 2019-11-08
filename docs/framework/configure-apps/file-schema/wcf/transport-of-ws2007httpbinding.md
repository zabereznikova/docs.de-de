---
title: <transport> von <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: 0cd20c607b0c4ddd3ecfd806d38ba63b4a5c5a25
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732760"
---
# <a name="transport-of-ws2007httpbinding"></a><span data-ttu-id="ccbe8-102">\<Transport > von \<WS2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="ccbe8-102">\<transport> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="ccbe8-103">Definiert die Authentifizierungseinstellungen für den HTTP-Transport.</span><span class="sxs-lookup"><span data-stu-id="ccbe8-103">Defines authentication settings for the HTTP transport.</span></span>  
  
<span data-ttu-id="ccbe8-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ccbe8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ccbe8-105">&nbsp; &nbsp;[ **\<system. Service Model->** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="ccbe8-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ccbe8-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="ccbe8-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="ccbe8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<WS2007HttpBinding >** ](ws2007httpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="ccbe8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)</span></span>\
<span data-ttu-id="ccbe8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="ccbe8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="ccbe8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Sicherheit >** ](security-of-ws2007httpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="ccbe8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-ws2007httpbinding.md)</span></span>\
<span data-ttu-id="ccbe8-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Transport >**</span><span class="sxs-lookup"><span data-stu-id="ccbe8-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccbe8-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="ccbe8-111">Syntax</span></span>  
  
```xml  
<transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
           proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
           realm="string" />
```  
  
## <a name="type"></a><span data-ttu-id="ccbe8-112">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="ccbe8-112">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ccbe8-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ccbe8-113">Attributes and Elements</span></span>  
 <span data-ttu-id="ccbe8-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ccbe8-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ccbe8-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="ccbe8-115">Attributes</span></span>  
  
|<span data-ttu-id="ccbe8-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="ccbe8-116">Attribute</span></span>|<span data-ttu-id="ccbe8-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ccbe8-117">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="ccbe8-118">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="ccbe8-118">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="ccbe8-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="ccbe8-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="ccbe8-120">Gibt die Anmeldeinformationen an, die verwendet werden, um den Client bei einem Domänenproxy zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="ccbe8-120">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="ccbe8-121">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="ccbe8-121">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="ccbe8-122">Der Authentifizierungsbereich für die Hashwert- oder Basisauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="ccbe8-122">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="ccbe8-123">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ccbe8-123">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="ccbe8-124">Ein Authentifizierungsbereich gibt mindestens den Namen des Hosts an, der die Authentifizierung durchführt.</span><span class="sxs-lookup"><span data-stu-id="ccbe8-124">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="ccbe8-125">Er kann auch eine Auflistung von Benutzern angeben, die Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="ccbe8-125">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="ccbe8-126">Ein Benutzer kann den Authentifizierungsbereich abfragen, um zu bestimmen, welche der verschiedenen möglichen Benutzernamen und Kennwörter verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="ccbe8-126">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="ccbe8-127">clientCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="ccbe8-127">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="ccbe8-128">Wert</span><span class="sxs-lookup"><span data-stu-id="ccbe8-128">Value</span></span>|<span data-ttu-id="ccbe8-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ccbe8-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ccbe8-130">Keiner</span><span class="sxs-lookup"><span data-stu-id="ccbe8-130">None</span></span>|<span data-ttu-id="ccbe8-131">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="ccbe8-131">Security is disabled.</span></span>|  
|<span data-ttu-id="ccbe8-132">Standard</span><span class="sxs-lookup"><span data-stu-id="ccbe8-132">Basic</span></span>|<span data-ttu-id="ccbe8-133">Verwendet die Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="ccbe8-133">Uses basic authentication.</span></span>|  
|<span data-ttu-id="ccbe8-134">Digest</span><span class="sxs-lookup"><span data-stu-id="ccbe8-134">Digest</span></span>|<span data-ttu-id="ccbe8-135">Verwendet Digestauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="ccbe8-135">Uses digest authentication.</span></span>|  
|<span data-ttu-id="ccbe8-136">Ntlm</span><span class="sxs-lookup"><span data-stu-id="ccbe8-136">Ntlm</span></span>|<span data-ttu-id="ccbe8-137">Verwendet als Ausweichlösung die NTLM-Authentifizierung für eine Windows-Domäne.</span><span class="sxs-lookup"><span data-stu-id="ccbe8-137">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="ccbe8-138">Windows</span><span class="sxs-lookup"><span data-stu-id="ccbe8-138">Windows</span></span>|<span data-ttu-id="ccbe8-139">Verwendet die integrierte Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="ccbe8-139">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="ccbe8-140">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="ccbe8-140">Certificate</span></span>|<span data-ttu-id="ccbe8-141">Verwendet X.509-Zertifikate zum Authentifizieren des Clients.</span><span class="sxs-lookup"><span data-stu-id="ccbe8-141">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="ccbe8-142">proxyCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="ccbe8-142">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="ccbe8-143">Wert</span><span class="sxs-lookup"><span data-stu-id="ccbe8-143">Value</span></span>|<span data-ttu-id="ccbe8-144">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ccbe8-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ccbe8-145">Keiner</span><span class="sxs-lookup"><span data-stu-id="ccbe8-145">None</span></span>|<span data-ttu-id="ccbe8-146">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="ccbe8-146">Security is disabled.</span></span>|  
|<span data-ttu-id="ccbe8-147">Standard</span><span class="sxs-lookup"><span data-stu-id="ccbe8-147">Basic</span></span>|<span data-ttu-id="ccbe8-148">Verwendet die Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="ccbe8-148">Uses basic authentication.</span></span>|  
|<span data-ttu-id="ccbe8-149">Digest</span><span class="sxs-lookup"><span data-stu-id="ccbe8-149">Digest</span></span>|<span data-ttu-id="ccbe8-150">Verwendet Digestauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="ccbe8-150">Uses digest authentication.</span></span>|  
|<span data-ttu-id="ccbe8-151">Ntlm</span><span class="sxs-lookup"><span data-stu-id="ccbe8-151">Ntlm</span></span>|<span data-ttu-id="ccbe8-152">Verwendet als Ausweichlösung NTLM für eine Windows-Domäne.</span><span class="sxs-lookup"><span data-stu-id="ccbe8-152">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="ccbe8-153">Windows</span><span class="sxs-lookup"><span data-stu-id="ccbe8-153">Windows</span></span>|<span data-ttu-id="ccbe8-154">Verwendet die integrierte Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="ccbe8-154">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="ccbe8-155">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="ccbe8-155">Certificate</span></span>|<span data-ttu-id="ccbe8-156">Verwendet X.509-Zertifikate zum Authentifizieren des Clients.</span><span class="sxs-lookup"><span data-stu-id="ccbe8-156">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ccbe8-157">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ccbe8-157">Child Elements</span></span>  
 <span data-ttu-id="ccbe8-158">Keiner</span><span class="sxs-lookup"><span data-stu-id="ccbe8-158">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ccbe8-159">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ccbe8-159">Parent Elements</span></span>  
  
|<span data-ttu-id="ccbe8-160">Element</span><span class="sxs-lookup"><span data-stu-id="ccbe8-160">Element</span></span>|<span data-ttu-id="ccbe8-161">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ccbe8-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ccbe8-162">\<Security ></span><span class="sxs-lookup"><span data-stu-id="ccbe8-162">\<security></span></span>](security-of-ws2007httpbinding.md)|<span data-ttu-id="ccbe8-163">Stellt die Sicherheitsfunktionen des [\<WS2007HttpBinding->](ws2007httpbinding.md) Elements dar.</span><span class="sxs-lookup"><span data-stu-id="ccbe8-163">Represents the security capabilities of the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ccbe8-164">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ccbe8-164">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>
- [<span data-ttu-id="ccbe8-165">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="ccbe8-165">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="ccbe8-166">Bindungen</span><span class="sxs-lookup"><span data-stu-id="ccbe8-166">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ccbe8-167">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="ccbe8-167">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="ccbe8-168">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="ccbe8-168">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="ccbe8-169">\<binding ></span><span class="sxs-lookup"><span data-stu-id="ccbe8-169">\<binding></span></span>](bindings.md)

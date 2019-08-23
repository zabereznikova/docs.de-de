---
title: <transport> von <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: ce8b2acb7d87b094958e20ca0b6cca9fc8266a8d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911983"
---
# <a name="transport-of-ws2007httpbinding"></a><span data-ttu-id="f9bda-102">\<Transport > von \<WS2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="f9bda-102">\<transport> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="f9bda-103">Definiert die Authentifizierungseinstellungen für den HTTP-Transport.</span><span class="sxs-lookup"><span data-stu-id="f9bda-103">Defines authentication settings for the HTTP transport.</span></span>  
  
 <span data-ttu-id="f9bda-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f9bda-104">\<system.serviceModel></span></span>  
<span data-ttu-id="f9bda-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="f9bda-105">\<bindings></span></span>  
<span data-ttu-id="f9bda-106">\<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="f9bda-106">\<ws2007HttpBinding></span></span>  
<span data-ttu-id="f9bda-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="f9bda-107">\<binding></span></span>  
<span data-ttu-id="f9bda-108">\<security></span><span class="sxs-lookup"><span data-stu-id="f9bda-108">\<security></span></span>  
<span data-ttu-id="f9bda-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="f9bda-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9bda-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="f9bda-110">Syntax</span></span>  
  
```xml  
<transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
           proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
           realm="string" />
```  
  
## <a name="type"></a><span data-ttu-id="f9bda-111">Typ</span><span class="sxs-lookup"><span data-stu-id="f9bda-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9bda-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f9bda-112">Attributes and Elements</span></span>  
 <span data-ttu-id="f9bda-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f9bda-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9bda-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="f9bda-114">Attributes</span></span>  
  
|<span data-ttu-id="f9bda-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="f9bda-115">Attribute</span></span>|<span data-ttu-id="f9bda-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f9bda-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="f9bda-117">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="f9bda-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="f9bda-118">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="f9bda-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="f9bda-119">Gibt die Anmeldeinformationen an, die verwendet werden, um den Client bei einem Domänenproxy zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="f9bda-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="f9bda-120">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="f9bda-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="f9bda-121">Der Authentifizierungsbereich für die Hashwert- oder Basisauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="f9bda-121">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="f9bda-122">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f9bda-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="f9bda-123">Ein Authentifizierungsbereich gibt mindestens den Namen des Hosts an, der die Authentifizierung durchführt.</span><span class="sxs-lookup"><span data-stu-id="f9bda-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="f9bda-124">Er kann auch eine Auflistung von Benutzern angeben, die Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="f9bda-124">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="f9bda-125">Ein Benutzer kann den Authentifizierungsbereich abfragen, um zu bestimmen, welche der verschiedenen möglichen Benutzernamen und Kennwörter verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="f9bda-125">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="f9bda-126">clientCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="f9bda-126">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="f9bda-127">Wert</span><span class="sxs-lookup"><span data-stu-id="f9bda-127">Value</span></span>|<span data-ttu-id="f9bda-128">Description</span><span class="sxs-lookup"><span data-stu-id="f9bda-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f9bda-129">None</span><span class="sxs-lookup"><span data-stu-id="f9bda-129">None</span></span>|<span data-ttu-id="f9bda-130">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f9bda-130">Security is disabled.</span></span>|  
|<span data-ttu-id="f9bda-131">Einfach</span><span class="sxs-lookup"><span data-stu-id="f9bda-131">Basic</span></span>|<span data-ttu-id="f9bda-132">Verwendet die Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="f9bda-132">Uses basic authentication.</span></span>|  
|<span data-ttu-id="f9bda-133">Digest</span><span class="sxs-lookup"><span data-stu-id="f9bda-133">Digest</span></span>|<span data-ttu-id="f9bda-134">Verwendet Digestauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="f9bda-134">Uses digest authentication.</span></span>|  
|<span data-ttu-id="f9bda-135">Ntlm</span><span class="sxs-lookup"><span data-stu-id="f9bda-135">Ntlm</span></span>|<span data-ttu-id="f9bda-136">Verwendet als Ausweichlösung die NTLM-Authentifizierung für eine Windows-Domäne.</span><span class="sxs-lookup"><span data-stu-id="f9bda-136">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="f9bda-137">Windows</span><span class="sxs-lookup"><span data-stu-id="f9bda-137">Windows</span></span>|<span data-ttu-id="f9bda-138">Verwendet die integrierte Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="f9bda-138">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="f9bda-139">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="f9bda-139">Certificate</span></span>|<span data-ttu-id="f9bda-140">Verwendet X.509-Zertifikate zum Authentifizieren des Clients.</span><span class="sxs-lookup"><span data-stu-id="f9bda-140">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="f9bda-141">proxyCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="f9bda-141">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="f9bda-142">Wert</span><span class="sxs-lookup"><span data-stu-id="f9bda-142">Value</span></span>|<span data-ttu-id="f9bda-143">Description</span><span class="sxs-lookup"><span data-stu-id="f9bda-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f9bda-144">None</span><span class="sxs-lookup"><span data-stu-id="f9bda-144">None</span></span>|<span data-ttu-id="f9bda-145">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f9bda-145">Security is disabled.</span></span>|  
|<span data-ttu-id="f9bda-146">Einfach</span><span class="sxs-lookup"><span data-stu-id="f9bda-146">Basic</span></span>|<span data-ttu-id="f9bda-147">Verwendet die Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="f9bda-147">Uses basic authentication.</span></span>|  
|<span data-ttu-id="f9bda-148">Digest</span><span class="sxs-lookup"><span data-stu-id="f9bda-148">Digest</span></span>|<span data-ttu-id="f9bda-149">Verwendet Digestauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="f9bda-149">Uses digest authentication.</span></span>|  
|<span data-ttu-id="f9bda-150">Ntlm</span><span class="sxs-lookup"><span data-stu-id="f9bda-150">Ntlm</span></span>|<span data-ttu-id="f9bda-151">Verwendet als Ausweichlösung NTLM für eine Windows-Domäne.</span><span class="sxs-lookup"><span data-stu-id="f9bda-151">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="f9bda-152">Windows</span><span class="sxs-lookup"><span data-stu-id="f9bda-152">Windows</span></span>|<span data-ttu-id="f9bda-153">Verwendet die integrierte Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="f9bda-153">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="f9bda-154">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="f9bda-154">Certificate</span></span>|<span data-ttu-id="f9bda-155">Verwendet X.509-Zertifikate zum Authentifizieren des Clients.</span><span class="sxs-lookup"><span data-stu-id="f9bda-155">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f9bda-156">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f9bda-156">Child Elements</span></span>  
 <span data-ttu-id="f9bda-157">None</span><span class="sxs-lookup"><span data-stu-id="f9bda-157">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f9bda-158">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f9bda-158">Parent Elements</span></span>  
  
|<span data-ttu-id="f9bda-159">Element</span><span class="sxs-lookup"><span data-stu-id="f9bda-159">Element</span></span>|<span data-ttu-id="f9bda-160">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f9bda-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9bda-161">\<security></span><span class="sxs-lookup"><span data-stu-id="f9bda-161">\<security></span></span>](security-of-ws2007httpbinding.md)|<span data-ttu-id="f9bda-162">Stellt die Sicherheitsfunktionen des [ \<WS2007HttpBinding->](ws2007httpbinding.md) Elements dar.</span><span class="sxs-lookup"><span data-stu-id="f9bda-162">Represents the security capabilities of the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f9bda-163">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9bda-163">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>
- [<span data-ttu-id="f9bda-164">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="f9bda-164">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="f9bda-165">Bindungen</span><span class="sxs-lookup"><span data-stu-id="f9bda-165">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f9bda-166">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="f9bda-166">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="f9bda-167">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="f9bda-167">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="f9bda-168">\<binding></span><span class="sxs-lookup"><span data-stu-id="f9bda-168">\<binding></span></span>](../../../misc/binding.md)

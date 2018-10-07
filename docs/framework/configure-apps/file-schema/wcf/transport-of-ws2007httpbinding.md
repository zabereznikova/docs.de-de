---
title: '&lt;transport&gt; von &lt;ws2007HttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: 5c7e96beee2fc1e4780729e56f10a52b63dde4e8
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2018
ms.locfileid: "48841416"
---
# <a name="lttransportgt-of-ltws2007httpbindinggt"></a><span data-ttu-id="b842f-102">&lt;transport&gt; von &lt;ws2007HttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="b842f-102">&lt;transport&gt; of &lt;ws2007HttpBinding&gt;</span></span>
<span data-ttu-id="b842f-103">Definiert die Authentifizierungseinstellungen für den HTTP-Transport.</span><span class="sxs-lookup"><span data-stu-id="b842f-103">Defines authentication settings for the HTTP transport.</span></span>  
  
 <span data-ttu-id="b842f-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b842f-104">\<system.serviceModel></span></span>  
<span data-ttu-id="b842f-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="b842f-105">\<bindings></span></span>  
<span data-ttu-id="b842f-106">\<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="b842f-106">\<ws2007HttpBinding></span></span>  
<span data-ttu-id="b842f-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="b842f-107">\<binding></span></span>  
<span data-ttu-id="b842f-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="b842f-108">\<security></span></span>  
<span data-ttu-id="b842f-109">\<Transport ></span><span class="sxs-lookup"><span data-stu-id="b842f-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b842f-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="b842f-110">Syntax</span></span>  
  
```  
transport clientCredentialType =   
       "Basic/Certificate/Digest/None/Ntlm/Windows"  
       proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
       realm="string"   
```  
  
## <a name="type"></a><span data-ttu-id="b842f-111">Typ</span><span class="sxs-lookup"><span data-stu-id="b842f-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b842f-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b842f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b842f-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b842f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b842f-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="b842f-114">Attributes</span></span>  
  
|<span data-ttu-id="b842f-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="b842f-115">Attribute</span></span>|<span data-ttu-id="b842f-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b842f-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="b842f-117">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="b842f-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="b842f-118">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="b842f-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="b842f-119">Gibt die Anmeldeinformationen an, die verwendet werden, um den Client bei einem Domänenproxy zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="b842f-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="b842f-120">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="b842f-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="b842f-121">Der Authentifizierungsbereich für die Digest- oder Basisauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="b842f-121">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="b842f-122">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="b842f-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="b842f-123">Ein Authentifizierungsbereich gibt mindestens den Namen des Hosts an, der die Authentifizierung durchführt.</span><span class="sxs-lookup"><span data-stu-id="b842f-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="b842f-124">Er kann auch eine Auflistung von Benutzern angeben, die Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="b842f-124">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="b842f-125">Ein Benutzer kann den Authentifizierungsbereich abfragen, um zu bestimmen, welche der verschiedenen möglichen Benutzernamen und Kennwörter verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="b842f-125">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="b842f-126">clientCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="b842f-126">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="b842f-127">Wert</span><span class="sxs-lookup"><span data-stu-id="b842f-127">Value</span></span>|<span data-ttu-id="b842f-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b842f-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b842f-129">Keine</span><span class="sxs-lookup"><span data-stu-id="b842f-129">None</span></span>|<span data-ttu-id="b842f-130">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="b842f-130">Security is disabled.</span></span>|  
|<span data-ttu-id="b842f-131">Standard</span><span class="sxs-lookup"><span data-stu-id="b842f-131">Basic</span></span>|<span data-ttu-id="b842f-132">Verwendet die Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="b842f-132">Uses basic authentication.</span></span>|  
|<span data-ttu-id="b842f-133">Digest</span><span class="sxs-lookup"><span data-stu-id="b842f-133">Digest</span></span>|<span data-ttu-id="b842f-134">Verwendet Digestauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="b842f-134">Uses digest authentication.</span></span>|  
|<span data-ttu-id="b842f-135">Ntlm</span><span class="sxs-lookup"><span data-stu-id="b842f-135">Ntlm</span></span>|<span data-ttu-id="b842f-136">Verwendet als Ausweichlösung die NTLM-Authentifizierung für eine Windows-Domäne.</span><span class="sxs-lookup"><span data-stu-id="b842f-136">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="b842f-137">Windows</span><span class="sxs-lookup"><span data-stu-id="b842f-137">Windows</span></span>|<span data-ttu-id="b842f-138">Verwendet die integrierte Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="b842f-138">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="b842f-139">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="b842f-139">Certificate</span></span>|<span data-ttu-id="b842f-140">Verwendet X.509-Zertifikate zum Authentifizieren des Clients.</span><span class="sxs-lookup"><span data-stu-id="b842f-140">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="b842f-141">proxyCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="b842f-141">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="b842f-142">Wert</span><span class="sxs-lookup"><span data-stu-id="b842f-142">Value</span></span>|<span data-ttu-id="b842f-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b842f-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b842f-144">Keine</span><span class="sxs-lookup"><span data-stu-id="b842f-144">None</span></span>|<span data-ttu-id="b842f-145">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="b842f-145">Security is disabled.</span></span>|  
|<span data-ttu-id="b842f-146">Standard</span><span class="sxs-lookup"><span data-stu-id="b842f-146">Basic</span></span>|<span data-ttu-id="b842f-147">Verwendet die Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="b842f-147">Uses basic authentication.</span></span>|  
|<span data-ttu-id="b842f-148">Digest</span><span class="sxs-lookup"><span data-stu-id="b842f-148">Digest</span></span>|<span data-ttu-id="b842f-149">Verwendet Digestauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="b842f-149">Uses digest authentication.</span></span>|  
|<span data-ttu-id="b842f-150">Ntlm</span><span class="sxs-lookup"><span data-stu-id="b842f-150">Ntlm</span></span>|<span data-ttu-id="b842f-151">Verwendet als Ausweichlösung NTLM für eine Windows-Domäne.</span><span class="sxs-lookup"><span data-stu-id="b842f-151">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="b842f-152">Windows</span><span class="sxs-lookup"><span data-stu-id="b842f-152">Windows</span></span>|<span data-ttu-id="b842f-153">Verwendet die integrierte Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="b842f-153">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="b842f-154">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="b842f-154">Certificate</span></span>|<span data-ttu-id="b842f-155">Verwendet X.509-Zertifikate zum Authentifizieren des Clients.</span><span class="sxs-lookup"><span data-stu-id="b842f-155">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b842f-156">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b842f-156">Child Elements</span></span>  
 <span data-ttu-id="b842f-157">Keiner</span><span class="sxs-lookup"><span data-stu-id="b842f-157">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b842f-158">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b842f-158">Parent Elements</span></span>  
  
|<span data-ttu-id="b842f-159">Element</span><span class="sxs-lookup"><span data-stu-id="b842f-159">Element</span></span>|<span data-ttu-id="b842f-160">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b842f-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b842f-161">\<security></span><span class="sxs-lookup"><span data-stu-id="b842f-161">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-ws2007httpbinding.md)|<span data-ttu-id="b842f-162">Gibt die Sicherheitsfunktionen von der [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="b842f-162">Represents the security capabilities of the [\<ws2007HttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b842f-163">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b842f-163">See Also</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>  
 [<span data-ttu-id="b842f-164">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="b842f-164">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="b842f-165">Bindungen</span><span class="sxs-lookup"><span data-stu-id="b842f-165">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="b842f-166">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="b842f-166">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="b842f-167">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="b842f-167">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="b842f-168">\<binding></span><span class="sxs-lookup"><span data-stu-id="b842f-168">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)

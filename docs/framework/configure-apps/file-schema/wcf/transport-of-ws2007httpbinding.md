---
title: <transport> von <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: 60e8758d653848176ca3f287e253bd7990e78470
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162048"
---
# <a name="transport-of-ws2007httpbinding"></a><span data-ttu-id="72b79-102">\<transport> von \<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="72b79-102">\<transport> of \<ws2007HttpBinding></span></span>

<span data-ttu-id="72b79-103">Definiert die Authentifizierungseinstellungen für den HTTP-Transport.</span><span class="sxs-lookup"><span data-stu-id="72b79-103">Defines authentication settings for the HTTP transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="72b79-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="72b79-104">Syntax</span></span>  
  
```xml  
<transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
           proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
           realm="string" />
```  
  
## <a name="type"></a><span data-ttu-id="72b79-105">Typ</span><span class="sxs-lookup"><span data-stu-id="72b79-105">Type</span></span>  

 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="72b79-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="72b79-106">Attributes and Elements</span></span>  

 <span data-ttu-id="72b79-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="72b79-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="72b79-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="72b79-108">Attributes</span></span>  
  
|<span data-ttu-id="72b79-109">attribute</span><span class="sxs-lookup"><span data-stu-id="72b79-109">Attribute</span></span>|<span data-ttu-id="72b79-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="72b79-110">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="72b79-111">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="72b79-111">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="72b79-112">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="72b79-112">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="72b79-113">Gibt die Anmeldeinformationen an, die verwendet werden, um den Client bei einem Domänenproxy zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="72b79-113">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="72b79-114">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="72b79-114">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="72b79-115">Der Authentifizierungsbereich für die Hashwert- oder Basisauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="72b79-115">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="72b79-116">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="72b79-116">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="72b79-117">Ein Authentifizierungsbereich gibt mindestens den Namen des Hosts an, der die Authentifizierung durchführt.</span><span class="sxs-lookup"><span data-stu-id="72b79-117">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="72b79-118">Er kann auch eine Auflistung von Benutzern angeben, die Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="72b79-118">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="72b79-119">Ein Benutzer kann den Authentifizierungsbereich abfragen, um zu bestimmen, welche der verschiedenen möglichen Benutzernamen und Kennwörter verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="72b79-119">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="72b79-120">clientCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="72b79-120">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="72b79-121">Wert</span><span class="sxs-lookup"><span data-stu-id="72b79-121">Value</span></span>|<span data-ttu-id="72b79-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="72b79-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="72b79-123">Keine</span><span class="sxs-lookup"><span data-stu-id="72b79-123">None</span></span>|<span data-ttu-id="72b79-124">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="72b79-124">Security is disabled.</span></span>|  
|<span data-ttu-id="72b79-125">Basic</span><span class="sxs-lookup"><span data-stu-id="72b79-125">Basic</span></span>|<span data-ttu-id="72b79-126">Verwendet die Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="72b79-126">Uses basic authentication.</span></span>|  
|<span data-ttu-id="72b79-127">Digest</span><span class="sxs-lookup"><span data-stu-id="72b79-127">Digest</span></span>|<span data-ttu-id="72b79-128">Verwendet Digestauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="72b79-128">Uses digest authentication.</span></span>|  
|<span data-ttu-id="72b79-129">Ntlm</span><span class="sxs-lookup"><span data-stu-id="72b79-129">Ntlm</span></span>|<span data-ttu-id="72b79-130">Verwendet als Ausweichlösung die NTLM-Authentifizierung für eine Windows-Domäne.</span><span class="sxs-lookup"><span data-stu-id="72b79-130">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="72b79-131">Windows</span><span class="sxs-lookup"><span data-stu-id="72b79-131">Windows</span></span>|<span data-ttu-id="72b79-132">Verwendet die integrierte Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="72b79-132">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="72b79-133">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="72b79-133">Certificate</span></span>|<span data-ttu-id="72b79-134">Verwendet X.509-Zertifikate zum Authentifizieren des Clients.</span><span class="sxs-lookup"><span data-stu-id="72b79-134">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="72b79-135">proxyCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="72b79-135">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="72b79-136">Wert</span><span class="sxs-lookup"><span data-stu-id="72b79-136">Value</span></span>|<span data-ttu-id="72b79-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="72b79-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="72b79-138">Keine</span><span class="sxs-lookup"><span data-stu-id="72b79-138">None</span></span>|<span data-ttu-id="72b79-139">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="72b79-139">Security is disabled.</span></span>|  
|<span data-ttu-id="72b79-140">Basic</span><span class="sxs-lookup"><span data-stu-id="72b79-140">Basic</span></span>|<span data-ttu-id="72b79-141">Verwendet die Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="72b79-141">Uses basic authentication.</span></span>|  
|<span data-ttu-id="72b79-142">Digest</span><span class="sxs-lookup"><span data-stu-id="72b79-142">Digest</span></span>|<span data-ttu-id="72b79-143">Verwendet Digestauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="72b79-143">Uses digest authentication.</span></span>|  
|<span data-ttu-id="72b79-144">Ntlm</span><span class="sxs-lookup"><span data-stu-id="72b79-144">Ntlm</span></span>|<span data-ttu-id="72b79-145">Verwendet als Ausweichlösung NTLM für eine Windows-Domäne.</span><span class="sxs-lookup"><span data-stu-id="72b79-145">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="72b79-146">Windows</span><span class="sxs-lookup"><span data-stu-id="72b79-146">Windows</span></span>|<span data-ttu-id="72b79-147">Verwendet die integrierte Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="72b79-147">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="72b79-148">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="72b79-148">Certificate</span></span>|<span data-ttu-id="72b79-149">Verwendet X.509-Zertifikate zum Authentifizieren des Clients.</span><span class="sxs-lookup"><span data-stu-id="72b79-149">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="72b79-150">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="72b79-150">Child Elements</span></span>  

 <span data-ttu-id="72b79-151">Keine</span><span class="sxs-lookup"><span data-stu-id="72b79-151">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="72b79-152">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="72b79-152">Parent Elements</span></span>  
  
|<span data-ttu-id="72b79-153">Element</span><span class="sxs-lookup"><span data-stu-id="72b79-153">Element</span></span>|<span data-ttu-id="72b79-154">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="72b79-154">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-ws2007httpbinding.md)|<span data-ttu-id="72b79-155">Stellt die Sicherheitsfunktionen des- [\<ws2007HttpBinding>](ws2007httpbinding.md) Elements dar.</span><span class="sxs-lookup"><span data-stu-id="72b79-155">Represents the security capabilities of the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="72b79-156">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="72b79-156">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>
- [<span data-ttu-id="72b79-157">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="72b79-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="72b79-158">Bindungen</span><span class="sxs-lookup"><span data-stu-id="72b79-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="72b79-159">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="72b79-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="72b79-160">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="72b79-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)

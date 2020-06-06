---
title: <transport> von <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: 0cd20c607b0c4ddd3ecfd806d38ba63b4a5c5a25
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73732760"
---
# <a name="transport-of-ws2007httpbinding"></a><span data-ttu-id="1227b-102">\<transport> von \<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="1227b-102">\<transport> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="1227b-103">Definiert die Authentifizierungseinstellungen für den HTTP-Transport.</span><span class="sxs-lookup"><span data-stu-id="1227b-103">Defines authentication settings for the HTTP transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="1227b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1227b-104">Syntax</span></span>  
  
```xml  
<transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
           proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
           realm="string" />
```  
  
## <a name="type"></a><span data-ttu-id="1227b-105">type</span><span class="sxs-lookup"><span data-stu-id="1227b-105">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1227b-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1227b-106">Attributes and Elements</span></span>  
 <span data-ttu-id="1227b-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1227b-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1227b-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="1227b-108">Attributes</span></span>  
  
|<span data-ttu-id="1227b-109">attribute</span><span class="sxs-lookup"><span data-stu-id="1227b-109">Attribute</span></span>|<span data-ttu-id="1227b-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1227b-110">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="1227b-111">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="1227b-111">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="1227b-112">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="1227b-112">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="1227b-113">Gibt die Anmeldeinformationen an, die verwendet werden, um den Client bei einem Domänenproxy zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="1227b-113">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="1227b-114">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="1227b-114">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="1227b-115">Der Authentifizierungsbereich für die Hashwert- oder Basisauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="1227b-115">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="1227b-116">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="1227b-116">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="1227b-117">Ein Authentifizierungsbereich gibt mindestens den Namen des Hosts an, der die Authentifizierung durchführt.</span><span class="sxs-lookup"><span data-stu-id="1227b-117">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="1227b-118">Er kann auch eine Auflistung von Benutzern angeben, die Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="1227b-118">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="1227b-119">Ein Benutzer kann den Authentifizierungsbereich abfragen, um zu bestimmen, welche der verschiedenen möglichen Benutzernamen und Kennwörter verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="1227b-119">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="1227b-120">clientCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="1227b-120">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="1227b-121">Wert</span><span class="sxs-lookup"><span data-stu-id="1227b-121">Value</span></span>|<span data-ttu-id="1227b-122">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1227b-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1227b-123">Keine</span><span class="sxs-lookup"><span data-stu-id="1227b-123">None</span></span>|<span data-ttu-id="1227b-124">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="1227b-124">Security is disabled.</span></span>|  
|<span data-ttu-id="1227b-125">Basic</span><span class="sxs-lookup"><span data-stu-id="1227b-125">Basic</span></span>|<span data-ttu-id="1227b-126">Verwendet die Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="1227b-126">Uses basic authentication.</span></span>|  
|<span data-ttu-id="1227b-127">Digest</span><span class="sxs-lookup"><span data-stu-id="1227b-127">Digest</span></span>|<span data-ttu-id="1227b-128">Verwendet Digestauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="1227b-128">Uses digest authentication.</span></span>|  
|<span data-ttu-id="1227b-129">Ntlm</span><span class="sxs-lookup"><span data-stu-id="1227b-129">Ntlm</span></span>|<span data-ttu-id="1227b-130">Verwendet als Ausweichlösung die NTLM-Authentifizierung für eine Windows-Domäne.</span><span class="sxs-lookup"><span data-stu-id="1227b-130">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="1227b-131">Windows</span><span class="sxs-lookup"><span data-stu-id="1227b-131">Windows</span></span>|<span data-ttu-id="1227b-132">Verwendet die integrierte Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="1227b-132">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="1227b-133">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="1227b-133">Certificate</span></span>|<span data-ttu-id="1227b-134">Verwendet X.509-Zertifikate zum Authentifizieren des Clients.</span><span class="sxs-lookup"><span data-stu-id="1227b-134">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="1227b-135">proxyCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="1227b-135">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="1227b-136">Wert</span><span class="sxs-lookup"><span data-stu-id="1227b-136">Value</span></span>|<span data-ttu-id="1227b-137">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1227b-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1227b-138">Keine</span><span class="sxs-lookup"><span data-stu-id="1227b-138">None</span></span>|<span data-ttu-id="1227b-139">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="1227b-139">Security is disabled.</span></span>|  
|<span data-ttu-id="1227b-140">Basic</span><span class="sxs-lookup"><span data-stu-id="1227b-140">Basic</span></span>|<span data-ttu-id="1227b-141">Verwendet die Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="1227b-141">Uses basic authentication.</span></span>|  
|<span data-ttu-id="1227b-142">Digest</span><span class="sxs-lookup"><span data-stu-id="1227b-142">Digest</span></span>|<span data-ttu-id="1227b-143">Verwendet Digestauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="1227b-143">Uses digest authentication.</span></span>|  
|<span data-ttu-id="1227b-144">Ntlm</span><span class="sxs-lookup"><span data-stu-id="1227b-144">Ntlm</span></span>|<span data-ttu-id="1227b-145">Verwendet als Ausweichlösung NTLM für eine Windows-Domäne.</span><span class="sxs-lookup"><span data-stu-id="1227b-145">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="1227b-146">Windows</span><span class="sxs-lookup"><span data-stu-id="1227b-146">Windows</span></span>|<span data-ttu-id="1227b-147">Verwendet die integrierte Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="1227b-147">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="1227b-148">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="1227b-148">Certificate</span></span>|<span data-ttu-id="1227b-149">Verwendet X.509-Zertifikate zum Authentifizieren des Clients.</span><span class="sxs-lookup"><span data-stu-id="1227b-149">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1227b-150">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1227b-150">Child Elements</span></span>  
 <span data-ttu-id="1227b-151">Keine</span><span class="sxs-lookup"><span data-stu-id="1227b-151">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1227b-152">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1227b-152">Parent Elements</span></span>  
  
|<span data-ttu-id="1227b-153">Element</span><span class="sxs-lookup"><span data-stu-id="1227b-153">Element</span></span>|<span data-ttu-id="1227b-154">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1227b-154">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-ws2007httpbinding.md)|<span data-ttu-id="1227b-155">Stellt die Sicherheitsfunktionen des- [\<ws2007HttpBinding>](ws2007httpbinding.md) Elements dar.</span><span class="sxs-lookup"><span data-stu-id="1227b-155">Represents the security capabilities of the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1227b-156">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1227b-156">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>
- [<span data-ttu-id="1227b-157">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="1227b-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="1227b-158">Bindungen</span><span class="sxs-lookup"><span data-stu-id="1227b-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="1227b-159">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="1227b-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="1227b-160">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="1227b-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)

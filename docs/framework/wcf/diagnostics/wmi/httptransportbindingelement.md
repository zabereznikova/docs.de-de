---
title: HttpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 088a7bce-6bb2-4839-ad74-f68d4b1aa0f9
ms.openlocfilehash: 2be32591c4844cc6d5d0f02916dd1563bb15dc2a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288787"
---
# <a name="httptransportbindingelement"></a><span data-ttu-id="ee351-102">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="ee351-102">HttpTransportBindingElement</span></span>

<span data-ttu-id="ee351-103">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="ee351-103">HttpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee351-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ee351-104">Syntax</span></span>  
  
```csharp
class HttpTransportBindingElement : TransportBindingElement  
{  
  boolean AllowCookies;  
  string AuthenticationScheme;  
  boolean BypassProxyOnLocal;  
  string HostNameComparisonMode;  
  boolean KeepAliveEnabled;  
  sint32 MaxBufferSize;  
  string ProxyAddress;  
  string ProxyAuthenticationScheme;  
  string Realm;  
  string TransferMode;  
  boolean UnsafeConnectionNtlmAuthentication;  
  boolean UseDefaultWebProxy;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ee351-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="ee351-105">Methods</span></span>  

 <span data-ttu-id="ee351-106">Die HttpTransportBindingElement-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="ee351-106">The HttpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ee351-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ee351-107">Properties</span></span>  

 <span data-ttu-id="ee351-108">Die HttpTransportBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="ee351-108">The HttpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="allowcookies"></a><span data-ttu-id="ee351-109">AllowCookies</span><span class="sxs-lookup"><span data-stu-id="ee351-109">AllowCookies</span></span>  

 <span data-ttu-id="ee351-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="ee351-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="ee351-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ee351-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ee351-112">Ein Wert, der angibt, ob der Client Cookies akzeptiert und bei zukünftigen Anfragen weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="ee351-112">A value that indicates whether the client accepts cookies and propagates them on future requests.</span></span>  
  
### <a name="authenticationscheme"></a><span data-ttu-id="ee351-113">Authentifizierungsschemas</span><span class="sxs-lookup"><span data-stu-id="ee351-113">AuthenticationScheme</span></span>  

 <span data-ttu-id="ee351-114">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="ee351-114">Data type: string</span></span>  
  
 <span data-ttu-id="ee351-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ee351-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ee351-116">Das Authentifizierungsschema, das zum Authentifizieren von Clientanforderungen verwendet wird, die von einem HTTP-Listener verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="ee351-116">The authentication scheme used to authenticate client requests being processed by an HTTP listener.</span></span>  
  
### <a name="bypassproxyonlocal"></a><span data-ttu-id="ee351-117">BypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="ee351-117">BypassProxyOnLocal</span></span>  

 <span data-ttu-id="ee351-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="ee351-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="ee351-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ee351-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ee351-120">Ein Wert, der angibt, ob Proxys für lokale Adressen ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="ee351-120">A value that indicates whether proxies are ignored for local addresses.</span></span>  
  
### <a name="hostnamecomparisonmode"></a><span data-ttu-id="ee351-121">HostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="ee351-121">HostNameComparisonMode</span></span>  

 <span data-ttu-id="ee351-122">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="ee351-122">Data type: string</span></span>  
  
 <span data-ttu-id="ee351-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ee351-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ee351-124">Ein Wert, der angibt, ob der Hostname zum Erreichen des Dienstes bei übereinstimmendem URI verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ee351-124">A value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>  
  
### <a name="keepaliveenabled"></a><span data-ttu-id="ee351-125">KeepAliveEnabled</span><span class="sxs-lookup"><span data-stu-id="ee351-125">KeepAliveEnabled</span></span>  

 <span data-ttu-id="ee351-126">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="ee351-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="ee351-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ee351-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ee351-128">Bei Aktivierung werden HTTP-Verbindungen unabhängig von der Aktivitätsebene beibehalten.</span><span class="sxs-lookup"><span data-stu-id="ee351-128">When enabled, HTTP connections are kept alive regardless of activity level.</span></span>  
  
### <a name="maxbuffersize"></a><span data-ttu-id="ee351-129">MaxBufferSize</span><span class="sxs-lookup"><span data-stu-id="ee351-129">MaxBufferSize</span></span>  

 <span data-ttu-id="ee351-130">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="ee351-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="ee351-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ee351-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ee351-132">Die maximale Größe des Pufferpools.</span><span class="sxs-lookup"><span data-stu-id="ee351-132">The maximum size of the buffer pool.</span></span>  
  
### <a name="proxyaddress"></a><span data-ttu-id="ee351-133">ProxyAddress</span><span class="sxs-lookup"><span data-stu-id="ee351-133">ProxyAddress</span></span>  

 <span data-ttu-id="ee351-134">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="ee351-134">Data type: string</span></span>  
  
 <span data-ttu-id="ee351-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ee351-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ee351-136">Ein URI, der die Adresse des Proxys enthält, der für HTTP-Anforderungen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ee351-136">A URI that contains the address of the proxy to use for HTTP requests.</span></span>  
  
### <a name="proxyauthenticationscheme"></a><span data-ttu-id="ee351-137">ProxyAuthenticationScheme</span><span class="sxs-lookup"><span data-stu-id="ee351-137">ProxyAuthenticationScheme</span></span>  

 <span data-ttu-id="ee351-138">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="ee351-138">Data type: string</span></span>  
  
 <span data-ttu-id="ee351-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ee351-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ee351-140">Das Authentifizierungsschema, das zum Authentifizieren von Clientanforderungen verwendet wird, die von einem HTTP-Proxy verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="ee351-140">The authentication scheme used to authenticate client requests being processed by an HTTP proxy.</span></span>  
  
### <a name="realm"></a><span data-ttu-id="ee351-141">Realm</span><span class="sxs-lookup"><span data-stu-id="ee351-141">Realm</span></span>  

 <span data-ttu-id="ee351-142">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="ee351-142">Data type: string</span></span>  
  
 <span data-ttu-id="ee351-143">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ee351-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ee351-144">Der Authentifizierungsbereich.</span><span class="sxs-lookup"><span data-stu-id="ee351-144">The authentication realm.</span></span>  
  
### <a name="transfermode"></a><span data-ttu-id="ee351-145">TransferMode</span><span class="sxs-lookup"><span data-stu-id="ee351-145">TransferMode</span></span>  

 <span data-ttu-id="ee351-146">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="ee351-146">Data type: string</span></span>  
  
 <span data-ttu-id="ee351-147">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ee351-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ee351-148">Ein Wert, der angibt, ob Meldungen bei einer Anforderung oder Antwort gepuffert oder per Stream übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="ee351-148">A value that specifies whether messages are buffered or streamed or a request or response.</span></span>  
  
### <a name="unsafeconnectionntlmauthentication"></a><span data-ttu-id="ee351-149">UnsafeConnectionNtlmAuthentication</span><span class="sxs-lookup"><span data-stu-id="ee351-149">UnsafeConnectionNtlmAuthentication</span></span>  

 <span data-ttu-id="ee351-150">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="ee351-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="ee351-151">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ee351-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ee351-152">Ein Wert, der angibt, ob die Freigabe nicht sicherer Verbindungen auf dem Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ee351-152">A value that indicates whether Unsafe Connection Sharing is enabled on the server.</span></span>  
  
### <a name="usedefaultwebproxy"></a><span data-ttu-id="ee351-153">UseDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="ee351-153">UseDefaultWebProxy</span></span>  

 <span data-ttu-id="ee351-154">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="ee351-154">Data type: boolean</span></span>  
  
 <span data-ttu-id="ee351-155">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="ee351-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ee351-156">Ein Wert, der angibt, ob die Proxyeinstellungen auf dem Computer anstatt der benutzerspezifischen Einstellungen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ee351-156">A value that indicates whether the machine-wide proxy settings are used rather than the user specific settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee351-157">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ee351-157">Requirements</span></span>  
  
|<span data-ttu-id="ee351-158">MOF</span><span class="sxs-lookup"><span data-stu-id="ee351-158">MOF</span></span>|<span data-ttu-id="ee351-159">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ee351-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ee351-160">Namespace</span><span class="sxs-lookup"><span data-stu-id="ee351-160">Namespace</span></span>|<span data-ttu-id="ee351-161">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ee351-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ee351-162">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ee351-162">See also</span></span>

- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>

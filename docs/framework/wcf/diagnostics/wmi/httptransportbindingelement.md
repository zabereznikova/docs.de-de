---
title: HttpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 088a7bce-6bb2-4839-ad74-f68d4b1aa0f9
ms.openlocfilehash: 1975fd2e04a5c9cdb68bc838802abafbd781b7e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33487019"
---
# <a name="httptransportbindingelement"></a><span data-ttu-id="b3899-102">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="b3899-102">HttpTransportBindingElement</span></span>
<span data-ttu-id="b3899-103">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="b3899-103">HttpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3899-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b3899-104">Syntax</span></span>  
  
```  
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
  
## <a name="methods"></a><span data-ttu-id="b3899-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="b3899-105">Methods</span></span>  
 <span data-ttu-id="b3899-106">Die HttpTransportBindingElement-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="b3899-106">The HttpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b3899-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b3899-107">Properties</span></span>  
 <span data-ttu-id="b3899-108">Die HttpTransportBindingElement-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="b3899-108">The HttpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="allowcookies"></a><span data-ttu-id="b3899-109">AllowCookies</span><span class="sxs-lookup"><span data-stu-id="b3899-109">AllowCookies</span></span>  
 <span data-ttu-id="b3899-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="b3899-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="b3899-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b3899-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b3899-112">Ein Wert, der angibt, ob der Client Cookies akzeptiert und bei zukünftigen Anfragen weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="b3899-112">A value that indicates whether the client accepts cookies and propagates them on future requests.</span></span>  
  
### <a name="authenticationscheme"></a><span data-ttu-id="b3899-113">Authentifizierungsschemas</span><span class="sxs-lookup"><span data-stu-id="b3899-113">AuthenticationScheme</span></span>  
 <span data-ttu-id="b3899-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="b3899-114">Data type: string</span></span>  
  
 <span data-ttu-id="b3899-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b3899-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b3899-116">Das Authentifizierungsschema, das zum Authentifizieren von Clientanforderungen verwendet wird, die von einem HTTP-Listener verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="b3899-116">The authentication scheme used to authenticate client requests being processed by an HTTP listener.</span></span>  
  
### <a name="bypassproxyonlocal"></a><span data-ttu-id="b3899-117">BypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="b3899-117">BypassProxyOnLocal</span></span>  
 <span data-ttu-id="b3899-118">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="b3899-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="b3899-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b3899-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b3899-120">Ein Wert, der angibt, ob Proxys für lokale Adressen ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="b3899-120">A value that indicates whether proxies are ignored for local addresses.</span></span>  
  
### <a name="hostnamecomparisonmode"></a><span data-ttu-id="b3899-121">HostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="b3899-121">HostNameComparisonMode</span></span>  
 <span data-ttu-id="b3899-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="b3899-122">Data type: string</span></span>  
  
 <span data-ttu-id="b3899-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b3899-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b3899-124">Ein Wert, der angibt, ob der Hostname zum Erreichen des Dienstes bei übereinstimmendem URI verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b3899-124">A value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>  
  
### <a name="keepaliveenabled"></a><span data-ttu-id="b3899-125">KeepAliveEnabled</span><span class="sxs-lookup"><span data-stu-id="b3899-125">KeepAliveEnabled</span></span>  
 <span data-ttu-id="b3899-126">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="b3899-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="b3899-127">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b3899-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b3899-128">Bei Aktivierung werden HTTP-Verbindungen unabhängig von der Aktivitätsebene beibehalten.</span><span class="sxs-lookup"><span data-stu-id="b3899-128">When enabled, HTTP connections are kept alive regardless of activity level.</span></span>  
  
### <a name="maxbuffersize"></a><span data-ttu-id="b3899-129">MaxBufferSize</span><span class="sxs-lookup"><span data-stu-id="b3899-129">MaxBufferSize</span></span>  
 <span data-ttu-id="b3899-130">Datentyp: sint32</span><span class="sxs-lookup"><span data-stu-id="b3899-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="b3899-131">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b3899-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b3899-132">Die maximale Größe des Pufferpools.</span><span class="sxs-lookup"><span data-stu-id="b3899-132">The maximum size of the buffer pool.</span></span>  
  
### <a name="proxyaddress"></a><span data-ttu-id="b3899-133">ProxyAddress</span><span class="sxs-lookup"><span data-stu-id="b3899-133">ProxyAddress</span></span>  
 <span data-ttu-id="b3899-134">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="b3899-134">Data type: string</span></span>  
  
 <span data-ttu-id="b3899-135">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b3899-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b3899-136">Ein URI, der die Adresse des Proxys enthält, der für HTTP-Anforderungen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b3899-136">A URI that contains the address of the proxy to use for HTTP requests.</span></span>  
  
### <a name="proxyauthenticationscheme"></a><span data-ttu-id="b3899-137">ProxyAuthenticationScheme</span><span class="sxs-lookup"><span data-stu-id="b3899-137">ProxyAuthenticationScheme</span></span>  
 <span data-ttu-id="b3899-138">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="b3899-138">Data type: string</span></span>  
  
 <span data-ttu-id="b3899-139">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b3899-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b3899-140">Das Authentifizierungsschema, das zum Authentifizieren von Clientanforderungen verwendet wird, die von einem HTTP-Proxy verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="b3899-140">The authentication scheme used to authenticate client requests being processed by an HTTP proxy.</span></span>  
  
### <a name="realm"></a><span data-ttu-id="b3899-141">Bereich</span><span class="sxs-lookup"><span data-stu-id="b3899-141">Realm</span></span>  
 <span data-ttu-id="b3899-142">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="b3899-142">Data type: string</span></span>  
  
 <span data-ttu-id="b3899-143">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b3899-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b3899-144">Der Authentifizierungsbereich.</span><span class="sxs-lookup"><span data-stu-id="b3899-144">The authentication realm.</span></span>  
  
### <a name="transfermode"></a><span data-ttu-id="b3899-145">TransferMode</span><span class="sxs-lookup"><span data-stu-id="b3899-145">TransferMode</span></span>  
 <span data-ttu-id="b3899-146">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="b3899-146">Data type: string</span></span>  
  
 <span data-ttu-id="b3899-147">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b3899-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b3899-148">Ein Wert, der angibt, ob Meldungen bei einer Anforderung oder Antwort gepuffert oder per Stream übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="b3899-148">A value that specifies whether messages are buffered or streamed or a request or response.</span></span>  
  
### <a name="unsafeconnectionntlmauthentication"></a><span data-ttu-id="b3899-149">UnsafeConnectionNtlmAuthentication</span><span class="sxs-lookup"><span data-stu-id="b3899-149">UnsafeConnectionNtlmAuthentication</span></span>  
 <span data-ttu-id="b3899-150">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="b3899-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="b3899-151">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b3899-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b3899-152">Ein Wert, der angibt, ob die Freigabe nicht sicherer Verbindungen auf dem Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b3899-152">A value that indicates whether Unsafe Connection Sharing is enabled on the server.</span></span>  
  
### <a name="usedefaultwebproxy"></a><span data-ttu-id="b3899-153">UseDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="b3899-153">UseDefaultWebProxy</span></span>  
 <span data-ttu-id="b3899-154">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="b3899-154">Data type: boolean</span></span>  
  
 <span data-ttu-id="b3899-155">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b3899-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b3899-156">Ein Wert, der angibt, ob die Proxyeinstellungen auf dem Computer anstatt der benutzerspezifischen Einstellungen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b3899-156">A value that indicates whether the machine-wide proxy settings are used rather than the user specific settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3899-157">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b3899-157">Requirements</span></span>  
  
|<span data-ttu-id="b3899-158">MOF</span><span class="sxs-lookup"><span data-stu-id="b3899-158">MOF</span></span>|<span data-ttu-id="b3899-159">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="b3899-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b3899-160">Namespace</span><span class="sxs-lookup"><span data-stu-id="b3899-160">Namespace</span></span>|<span data-ttu-id="b3899-161">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b3899-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b3899-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3899-162">See Also</span></span>  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>

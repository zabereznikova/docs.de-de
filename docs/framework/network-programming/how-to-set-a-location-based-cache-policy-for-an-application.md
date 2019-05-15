---
title: 'Vorgehensweise: Festlegen einer speicherortbasierten Cacherichtlinie für eine Anwendung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- expliciting defining cache behavior
- location-based cache policies
- local cache
- request cache policies
- cache [.NET Framework], location-based policies
ms.assetid: 683bb88e-3411-4f46-9686-3411b6ba511c
ms.openlocfilehash: 1bbbb558134e5f11537de0efef594be2b964cdcb
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64647373"
---
# <a name="how-to-set-a-location-based-cache-policy-for-an-application"></a><span data-ttu-id="6c460-102">Vorgehensweise: Festlegen einer speicherortbasierten Cacherichtlinie für eine Anwendung</span><span class="sxs-lookup"><span data-stu-id="6c460-102">How to: Set a Location-Based Cache Policy for an Application</span></span>
<span data-ttu-id="6c460-103">Speicherortbasierte Cacherichtlinien ermöglichen einer Anwendung, das Cacheverhalten basierend auf dem Speicherort der angeforderten Ressource explizit zu definieren.</span><span class="sxs-lookup"><span data-stu-id="6c460-103">Location-based cache policies allow an application to explicitly define caching behavior based on the location of the requested resource.</span></span> <span data-ttu-id="6c460-104">In diesem Thema wird veranschaulicht, wie Sie eine Cacherichtlinie programmgesteuert festlegen können.</span><span class="sxs-lookup"><span data-stu-id="6c460-104">This topic demonstrates setting the cache policy programmatically.</span></span> <span data-ttu-id="6c460-105">Weitere Informationen zum Festlegen der Richtlinie für eine Anwendung mithilfe der Konfigurationsdateien finden Sie unter [\<requestCaching>-Element (Netzwerkeinstellungen)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="6c460-105">For information on setting the policy for an application using the configuration files, see [\<requestCaching> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md).</span></span>  
  
### <a name="to-set-a-location-based-cache-policy-for-an-application"></a><span data-ttu-id="6c460-106">Festlegen einer speicherortbasierten Cacherichtlinie für eine Anwendung</span><span class="sxs-lookup"><span data-stu-id="6c460-106">To set a location-based cache policy for an application</span></span>  
  
1. <span data-ttu-id="6c460-107">Erstellen Sie ein <xref:System.Net.Cache.RequestCachePolicy>- oder <xref:System.Net.Cache.HttpRequestCachePolicy>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="6c460-107">Create a <xref:System.Net.Cache.RequestCachePolicy> or <xref:System.Net.Cache.HttpRequestCachePolicy> object.</span></span>  
  
2. <span data-ttu-id="6c460-108">Legen Sie das Richtlinienobjekt als Standard für die Anwendungsdomäne fest.</span><span class="sxs-lookup"><span data-stu-id="6c460-108">Set the policy object as the default for the application domain.</span></span>  
  
### <a name="to-set-a-policy-that-takes-requested-resources-from-a-cache"></a><span data-ttu-id="6c460-109">Festlegen einer Richtlinie, die angeforderte Ressourcen aus einem Cache abruft</span><span class="sxs-lookup"><span data-stu-id="6c460-109">To set a policy that takes requested resources from a cache</span></span>  
  
- <span data-ttu-id="6c460-110">Erstellen Sie eine Richtlinie, die die angeforderten Ressourcen, falls verfügbar, aus einem Cache abruft, indem Sie die Cacheebene auf <xref:System.Net.Cache.HttpRequestCacheLevel.CacheIfAvailable> festlegen. Sind keine Ressourcen verfügbar, sendet die Richtlinie Anforderungen an den Server.</span><span class="sxs-lookup"><span data-stu-id="6c460-110">Create a policy that takes requested resources from a cache if available, and otherwise, sends requests to the server, by setting the cache level to <xref:System.Net.Cache.HttpRequestCacheLevel.CacheIfAvailable>.</span></span> <span data-ttu-id="6c460-111">Eine Anforderung kann von einem beliebigen Cache zwischen Client und Server erfüllt werden, einschließlich eines Remotecaches.</span><span class="sxs-lookup"><span data-stu-id="6c460-111">A request can be fulfilled by any cache between the client and server, including remote caches.</span></span>  
  
    ```csharp  
    public static void UseCacheIfAvailable()  
    {  
        HttpRequestCachePolicy policy = new HttpRequestCachePolicy  
            (HttpRequestCacheLevel.CacheIfAvailable);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub UseCacheIfAvailable()  
        Dim policy As New HttpRequestCachePolicy _  
             (HttpRequestCacheLevel.CacheIfAvailable)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### <a name="to-set-a-policy-that-prevents-any-cache-from-supplying-resources"></a><span data-ttu-id="6c460-112">Festlegen einer Richtlinie, die die Bereitstellung von Ressourcen durch einen Cache verhindert</span><span class="sxs-lookup"><span data-stu-id="6c460-112">To set a policy that prevents any cache from supplying resources</span></span>  
  
- <span data-ttu-id="6c460-113">Erstellen Sie eine Richtlinie, die verhindert, dass ein beliebiger Cache die angeforderten Ressourcen bereitstellt, indem Sie die Cacheebene auf <xref:System.Net.Cache.HttpRequestCacheLevel.NoCacheNoStore> festlegen.</span><span class="sxs-lookup"><span data-stu-id="6c460-113">Create a policy that prevents any cache from supplying requested resources by setting the cache level to <xref:System.Net.Cache.HttpRequestCacheLevel.NoCacheNoStore>.</span></span> <span data-ttu-id="6c460-114">Diese Richtlinienebene entfernt die Ressource, sofern vorhanden, aus dem lokalen Cache, und gibt den Remotecaches an, dass sie die Ressource auch entfernen sollen.</span><span class="sxs-lookup"><span data-stu-id="6c460-114">This policy level removes the resource from the local cache if it is present and indicates to remote caches that they should also remove the resource.</span></span>  
  
    ```csharp  
    public static void DoNotUseCache()  
    {  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy   
            (HttpRequestCacheLevel.NoCacheNoStore);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub DoNotUseCache()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.NoCacheNoStore)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### <a name="to-set-a-policy-that-returns-requested-resources-only-if-they-are-in-the-local-cache"></a><span data-ttu-id="6c460-115">Festlegen einer Richtlinie, die angeforderte Ressourcen nur zurückgibt, wenn sie im lokalen Cache sind</span><span class="sxs-lookup"><span data-stu-id="6c460-115">To set a policy that returns requested resources only if they are in the local cache</span></span>  
  
- <span data-ttu-id="6c460-116">Erstellen Sie eine Richtlinie, die die angeforderten Ressourcen nur zurückgibt, wenn sie sich im lokalen Cache befinden, indem Sie die Cacheebene auf <xref:System.Net.Cache.HttpRequestCacheLevel.CacheOnly> festlegen.</span><span class="sxs-lookup"><span data-stu-id="6c460-116">Create a policy that returns requested resources only if they are in the local cache by setting the cache level to <xref:System.Net.Cache.HttpRequestCacheLevel.CacheOnly>.</span></span> <span data-ttu-id="6c460-117">Befindet sich die angeforderte Ressource nicht im Cache, wird eine <xref:System.Net.WebException>-Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="6c460-117">If the requested resource is not in the cache, a <xref:System.Net.WebException> exception is thrown.</span></span>  
  
    ```csharp  
    public static void OnlyUseCache()  
    {  
        HttpRequestCachePolicy policy = new HttpRequestCachePolicy   
            (HttpRequestCacheLevel.CacheOnly);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub OnlyUseCache()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.CacheOnly)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### <a name="to-set-a-policy-that-prevents-the-local-cache-from-supplying-resources"></a><span data-ttu-id="6c460-118">Festlegen einer Richtlinie, die die Bereitstellung von Ressourcen durch den lokalen Cache verhindert</span><span class="sxs-lookup"><span data-stu-id="6c460-118">To set a policy that prevents the local cache from supplying resources</span></span>  
  
- <span data-ttu-id="6c460-119">Erstellen Sie eine Richtlinie, die verhindert, dass der lokale Cache die angeforderten Ressourcen bereitstellt, indem Sie die Cacheebene auf <xref:System.Net.Cache.HttpRequestCacheLevel.Refresh> festlegen.</span><span class="sxs-lookup"><span data-stu-id="6c460-119">Create a policy that prevents the local cache from supplying requested resources by setting the cache level to <xref:System.Net.Cache.HttpRequestCacheLevel.Refresh>.</span></span> <span data-ttu-id="6c460-120">Befindet sich die angeforderte Ressource in einem Zwischen-Cache und wird erneut erfolgreich überprüft, kann der Zwischen-Cache die angeforderte Ressource bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6c460-120">If the requested resource is in an intermediate cache and is successfully revalidated, the intermediate cache can supply the requested resource.</span></span>  
  
    ```csharp  
    public static void DoNotUseLocalCache()  
    {  
     HttpRequestCachePolicy policy = new HttpRequestCachePolicy   
            (HttpRequestCacheLevel.Refresh);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub DoNotUseLocalCache()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.Refresh)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### <a name="to-set-a-policy-that-prevents-any-cache-from-supplying-requested-resources"></a><span data-ttu-id="6c460-121">Festlegen einer Richtlinie, die die Bereitstellung von angeforderten Ressourcen durch einen Cache verhindert</span><span class="sxs-lookup"><span data-stu-id="6c460-121">To set a policy that prevents any cache from supplying requested resources</span></span>  
  
- <span data-ttu-id="6c460-122">Erstellen Sie eine Richtlinie, die verhindert, dass ein beliebiger Cache die angeforderten Ressourcen bereitstellt, indem Sie die Cacheebene auf <xref:System.Net.Cache.HttpRequestCacheLevel.Reload> festlegen.</span><span class="sxs-lookup"><span data-stu-id="6c460-122">Create a policy that prevents any cache from supplying requested resources by setting the cache level to <xref:System.Net.Cache.HttpRequestCacheLevel.Reload>.</span></span> <span data-ttu-id="6c460-123">Die vom Server zurückgegebene Ressource kann im Cache gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="6c460-123">The resource returned by the server can be stored in the cache.</span></span>  
  
    ```csharp  
    public static void SendToServer()  
    {  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy   
            (HttpRequestCacheLevel.Reload);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub SendToServer()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.Reload)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
### <a name="to-set-a-policy-that-allows-any-cache-to-supply-requested-resources-if-the-resource-on-the-server-is-not-newer-than-the-cached-copy"></a><span data-ttu-id="6c460-124">Festlegen einer Richtlinie, die die Bereitstellung von angeforderten Ressourcen durch einen Cache ermöglicht, wenn die Ressource im Server nicht neuer ist als die zwischengespeicherte Kopie</span><span class="sxs-lookup"><span data-stu-id="6c460-124">To set a policy that allows any cache to supply requested resources if the resource on the server is not newer than the cached copy</span></span>  
  
- <span data-ttu-id="6c460-125">Erstellen Sie eine Richtlinie, die die Bereitstellung von angeforderten Ressourcen durch einen Cache ermöglicht, wenn die Ressource im Server nicht neuer ist als die zwischengespeicherte Kopie, indem Sie die Cacheebene auf <xref:System.Net.Cache.HttpRequestCacheLevel.Revalidate> festlegen.</span><span class="sxs-lookup"><span data-stu-id="6c460-125">Create a policy that allows any cache to supply requested resources if the resource on the server is not newer than the cached copy by setting the cache level to <xref:System.Net.Cache.HttpRequestCacheLevel.Revalidate>.</span></span>  
  
    ```csharp  
    public static void CheckServer()  
    {  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy  
             (HttpRequestCacheLevel.Revalidate);  
        HttpWebRequest.DefaultCachePolicy = policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Sub CheckServer()  
        Dim policy As New HttpRequestCachePolicy _  
            (HttpRequestCacheLevel.Revalidate)  
        HttpWebRequest.DefaultCachePolicy = policy  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6c460-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c460-126">See also</span></span>

- [<span data-ttu-id="6c460-127">Cacheverwaltung für Netzwerkanwendungen</span><span class="sxs-lookup"><span data-stu-id="6c460-127">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)
- [<span data-ttu-id="6c460-128">Cacherichtlinie</span><span class="sxs-lookup"><span data-stu-id="6c460-128">Cache Policy</span></span>](../../../docs/framework/network-programming/cache-policy.md)
- [<span data-ttu-id="6c460-129">Speicherortbasierte Cacherichtlinien</span><span class="sxs-lookup"><span data-stu-id="6c460-129">Location-Based Cache Policies</span></span>](../../../docs/framework/network-programming/location-based-cache-policies.md)
- [<span data-ttu-id="6c460-130">Zeitbasierte Cacherichtlinien</span><span class="sxs-lookup"><span data-stu-id="6c460-130">Time-Based Cache Policies</span></span>](../../../docs/framework/network-programming/time-based-cache-policies.md)
- [<span data-ttu-id="6c460-131">\<requestCaching>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="6c460-131">\<requestCaching> Element (Network Settings)</span></span>](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)

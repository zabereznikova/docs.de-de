---
title: 'Vorgehensweise: Anpassen einer zeitbasierten Cacherichtlinie'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time-based cache policies
- customizing time-based cache policies
- cache [.NET Framework], time-based policies
ms.assetid: 8d84f936-2376-4356-9264-03162e0f9279
ms.openlocfilehash: 1a2ba404e333eeec2a23758c834876d0df5aba81
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73040630"
---
# <a name="how-to-customize-a-time-based-cache-policy"></a><span data-ttu-id="72254-102">Vorgehensweise: Anpassen einer zeitbasierten Cacherichtlinie</span><span class="sxs-lookup"><span data-stu-id="72254-102">How to: customize a time-based cache policy</span></span>

<span data-ttu-id="72254-103">Wenn Sie eine zeitbasierte Cacherichtlinie erstellen, können Sie das Cacheverhalten anpassen, indem Sie Werte für das maximale Alter, die minimale Aktualität, die maximale Überalterung oder das Datum für die Cachesynchronisierung angeben.</span><span class="sxs-lookup"><span data-stu-id="72254-103">When creating a time-based cache policy, you can customize caching behavior by specifying values for maximum age, minimum freshness, maximum staleness, or cache synchronization date.</span></span> <span data-ttu-id="72254-104">Das <xref:System.Net.Cache.HttpRequestCachePolicy>-Objekt enthält mehrere Konstruktoren, mit denen Sie gültige Kombinationen dieser Werte angeben können.</span><span class="sxs-lookup"><span data-stu-id="72254-104">The <xref:System.Net.Cache.HttpRequestCachePolicy> object provides several constructors that allow you to specify valid combinations of these values.</span></span>

## <a name="to-create-a-time-based-cache-policy-that-uses-a-cache-synchronization-date"></a><span data-ttu-id="72254-105">Erstellen einer zeitbasierten Cacherichtlinie, die ein Datum für die Cachesynchronisierung verwendet</span><span class="sxs-lookup"><span data-stu-id="72254-105">To create a time-based cache policy that uses a cache synchronization date</span></span>

<span data-ttu-id="72254-106">Erstellen Sie eine zeitbasierte Cacherichtlinie, die ein Datum für die Cachesynchronisierung verwendet, indem Sie das <xref:System.DateTime>-Objekt an den <xref:System.Net.Cache.HttpRequestCachePolicy>-Konstruktor übergeben:</span><span class="sxs-lookup"><span data-stu-id="72254-106">Create a time-based cache policy that uses a cache synchronization date by passing a <xref:System.DateTime> object to the <xref:System.Net.Cache.HttpRequestCachePolicy> constructor:</span></span>

```csharp
public static HttpRequestCachePolicy CreateLastSyncPolicy(DateTime when)
{
    var policy = new HttpRequestCachePolicy(when);
    Console.WriteLine("When: {0}", when);
    Console.WriteLine(policy.ToString());
    return policy;
}
```

```vb
Public Shared Function CreateLastSyncPolicy([when] As DateTime) As HttpRequestCachePolicy
    Dim policy As New HttpRequestCachePolicy([when])
    Console.WriteLine("When: {0}", [when])
    Console.WriteLine(policy.ToString())
    Return policy
End Function
```

<span data-ttu-id="72254-107">Die Ausgabe ähnelt Folgendem:</span><span class="sxs-lookup"><span data-stu-id="72254-107">The output is similar to the following:</span></span>

```output
When: 1/14/2004 8:07:30 AM
Level:Default CacheSyncDate:1/14/2004 8:07:30 AM
```

## <a name="to-create-a-time-based-cache-policy-that-is-based-on-minimum-freshness"></a><span data-ttu-id="72254-108">Erstellen einer zeitbasierten Cacherichtlinie, die auf minimaler Aktualität basiert</span><span class="sxs-lookup"><span data-stu-id="72254-108">To create a time-based cache policy that is based on minimum freshness</span></span>

<span data-ttu-id="72254-109">Erstellen Sie eine zeitbasierte Cacherichtlinie, die auf minimaler Aktualität basiert, indem Sie <xref:System.Net.Cache.HttpCacheAgeControl.MinFresh> als den `cacheAgeControl`-Parameterwert festlegen und ein <xref:System.TimeSpan>-Objekt an den <xref:System.Net.Cache.HttpRequestCachePolicy>-Konstruktor übergeben:</span><span class="sxs-lookup"><span data-stu-id="72254-109">Create a time-based cache policy that is based on minimum freshness by specifying <xref:System.Net.Cache.HttpCacheAgeControl.MinFresh> as the `cacheAgeControl` parameter value and passing a <xref:System.TimeSpan> object to the <xref:System.Net.Cache.HttpRequestCachePolicy> constructor:</span></span>

```csharp
public static HttpRequestCachePolicy CreateMinFreshPolicy(TimeSpan span)
{
    var policy = new HttpRequestCachePolicy(HttpCacheAgeControl.MinFresh, span);
    Console.WriteLine(policy.ToString());
    return policy;
}
```

```vb
Public Shared Function CreateMinFreshPolicy(span As TimeSpan) As HttpRequestCachePolicy
    Dim policy As New HttpRequestCachePolicy(HttpCacheAgeControl.MinFresh, span)
    Console.WriteLine(policy.ToString())
    Return policy
End Function
```

<span data-ttu-id="72254-110">Für den folgenden Aufruf:</span><span class="sxs-lookup"><span data-stu-id="72254-110">For the following invocation:</span></span>

```csharp
CreateMinFreshPolicy(new TimeSpan(1,0,0));
```

<span data-ttu-id="72254-111">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="72254-111">The output is:</span></span>

```output
Level:Default MinFresh:3600
```

## <a name="to-create-a-time-based-cache-policy-that-is-based-on-minimum-freshness-and-maximum-age"></a><span data-ttu-id="72254-112">Erstellen einer zeitbasierten Cacherichtlinie, die auf maximalem Alter basiert</span><span class="sxs-lookup"><span data-stu-id="72254-112">To create a time-based cache policy that is based on minimum freshness and maximum age</span></span>

<span data-ttu-id="72254-113">Erstellen Sie eine zeitbasierte Cacherichtlinie, die auf minimaler Aktualität und maximalem Alter basiert, indem Sie <xref:System.Net.Cache.HttpCacheAgeControl.MaxAgeAndMinFresh> als den `cacheAgeControl`-Parameterwert festlegen und zwei <xref:System.TimeSpan>-Objekte an den <xref:System.Net.Cache.HttpRequestCachePolicy>-Konstruktor übergeben. Einer davon gibt das maximale Alter für die Ressourcen an, der andere die minimale Aktualität, die für ein Objekt zugelassen ist, das aus dem Cache zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="72254-113">Create a time-based cache policy that is based on minimum freshness and maximum age by specifying <xref:System.Net.Cache.HttpCacheAgeControl.MaxAgeAndMinFresh> as the `cacheAgeControl` parameter value and passing two <xref:System.TimeSpan> objects to the <xref:System.Net.Cache.HttpRequestCachePolicy> constructor, one to specify the maximum age for resources and a second to specify the minimum freshness permitted for an object returned from the cache:</span></span>

```csharp
public static HttpRequestCachePolicy CreateFreshAndAgePolicy(TimeSpan freshMinimum, TimeSpan ageMaximum)
{
    var policy = new HttpRequestCachePolicy(HttpCacheAgeControl.MaxAgeAndMinFresh, ageMaximum, freshMinimum);
    Console.WriteLine(policy.ToString());
    return policy;
}
```

```vb
Public Shared Function CreateFreshAndAgePolicy(freshMinimum As TimeSpan, ageMaximum As TimeSpan) As HttpRequestCachePolicy
    Dim policy As New HttpRequestCachePolicy(HttpCacheAgeControl.MaxAgeAndMinFresh, ageMaximum, freshMinimum)
    Console.WriteLine(policy.ToString())
    Return policy
End Function
```

<span data-ttu-id="72254-114">Für den folgenden Aufruf:</span><span class="sxs-lookup"><span data-stu-id="72254-114">For the following invocation:</span></span>
  
```csharp
CreateFreshAndAgePolicy(new TimeSpan(5,0,0), new TimeSpan(10,0,0));  
```  

<span data-ttu-id="72254-115">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="72254-115">The output is:</span></span>
  
```output
Level:Default MaxAge:36000 MinFresh:18000  
```  
  
## <a name="see-also"></a><span data-ttu-id="72254-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="72254-116">See also</span></span>

- [<span data-ttu-id="72254-117">Cacheverwaltung für Netzwerkanwendungen</span><span class="sxs-lookup"><span data-stu-id="72254-117">Cache Management for Network Applications</span></span>](cache-management-for-network-applications.md)
- [<span data-ttu-id="72254-118">Cacherichtlinie</span><span class="sxs-lookup"><span data-stu-id="72254-118">Cache Policy</span></span>](cache-policy.md)
- [<span data-ttu-id="72254-119">Speicherortbasierte Cacherichtlinien</span><span class="sxs-lookup"><span data-stu-id="72254-119">Location-Based Cache Policies</span></span>](location-based-cache-policies.md)
- [<span data-ttu-id="72254-120">Zeitbasierte Cacherichtlinien</span><span class="sxs-lookup"><span data-stu-id="72254-120">Time-Based Cache Policies</span></span>](time-based-cache-policies.md)
- [<span data-ttu-id="72254-121">\<requestCaching>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="72254-121">\<requestCaching> Element (Network Settings)</span></span>](../configure-apps/file-schema/network/requestcaching-element-network-settings.md)

---
title: 'Gewusst wie: Anpassen einer zeitbasierten Cacherichtlinie'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time-based cache policies
- customizing time-based cache policies
- cache [.NET Framework], time-based policies
ms.assetid: 8d84f936-2376-4356-9264-03162e0f9279
caps.latest.revision: "15"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 86e56a2caed3ae7644b567c2e4af207689017c63
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-customize-a-time-based-cache-policy"></a>Gewusst wie: Anpassen einer zeitbasierten Cacherichtlinie
Wenn Sie eine zeitbasierte Cacherichtlinie erstellen, können Sie das Cacheverhalten anpassen, indem Sie Werte für das maximale Alter, die minimale Aktualität, die maximale Überalterung oder das Datum für die Cachesynchronisierung angeben. Das <xref:System.Net.Cache.HttpRequestCachePolicy>-Objekt enthält mehrere Konstruktoren, mit denen Sie gültige Kombinationen dieser Werte angeben können.  
  
### <a name="to-create-a-time-based-cache-policy-that-uses-a-cache-synchronization-date"></a>Erstellen einer zeitbasierten Cacherichtlinie, die ein Datum für die Cachesynchronisierung verwendet  
  
-   Erstellen Sie eine zeitbasierte Cacherichtlinie, die ein Datum für die Cachesynchronisierung verwendet, indem Sie das <xref:System.DateTime>-Objekt an den <xref:System.Net.Cache.HttpRequestCachePolicy>-Konstruktor übergeben.  
  
    ```csharp  
    public static HttpRequestCachePolicy CreateLastSyncPolicy(DateTime when)  
    {  
        HttpRequestCachePolicy policy =   
            new HttpRequestCachePolicy(when);  
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
  
 Die Ausgabe ähnelt Folgendem:  
  
```  
When: 1/14/2004 8:07:30 AM  
Level:Default CacheSyncDate:1/14/2004 8:07:30 AM  
```  
  
### <a name="to-create-a-time-based-cache-policy-that-is-based-on-minimum-freshness"></a>Erstellen einer zeitbasierten Cacherichtlinie, die auf minimaler Aktualität basiert  
  
-   Erstellen Sie eine zeitbasierte Cacherichtlinie, die auf minimaler Aktualität basiert, indem Sie <xref:System.Net.Cache.HttpCacheAgeControl.MinFresh> als den `cacheAgeControl`-Parameterwert festlegen und ein <xref:System.TimeSpan>-Objekt an den <xref:System.Net.Cache.HttpRequestCachePolicy>-Konstruktor übergeben.  
  
    ```csharp  
    public static HttpRequestCachePolicy CreateMinFreshPolicy(TimeSpan span)  
    {  
        HttpRequestCachePolicy policy =   
            new HttpRequestCachePolicy(HttpCacheAgeControl.MinFresh, span);  
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
  
 Für den folgenden Aufruf:  
  
```  
CreateMinFreshPolicy(new TimeSpan(1,0,0));  
```  
  
```  
Level:Default MinFresh:3600  
```  
  
### <a name="to-create-a-time-based-cache-policy-that-is-based-on-minimum-freshness-and-maximum-age"></a>Erstellen einer zeitbasierten Cacherichtlinie, die auf maximalem Alter basiert  
  
-   Erstellen Sie eine zeitbasierte Cacherichtlinie, die auf minimaler Aktualität und maximalem Alter basiert, indem Sie <xref:System.Net.Cache.HttpCacheAgeControl.MaxAgeAndMinFresh> als den `cacheAgeControl`-Parameterwert festlegen und zwei <xref:System.TimeSpan>-Objekte an den <xref:System.Net.Cache.HttpRequestCachePolicy>-Konstruktor übergeben. Einer davon gibt das maximale Alter für die Ressourcen an, der andere die minimale Aktualität, die für ein Objekt zugelassen ist, das aus dem Cache zurückgegeben wird.  
  
    ```csharp  
    public static HttpRequestCachePolicy CreateFreshAndAgePolicy(TimeSpan freshMinimum, TimeSpan ageMaximum)  
    {  
        HttpRequestCachePolicy policy =   
        new HttpRequestCachePolicy(HttpCacheAgeControl.MaxAgeAndMinFresh, ageMaximum, freshMinimum);  
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
  
 Für den folgenden Aufruf:  
  
```  
CreateFreshAndAgePolicy(new TimeSpan(5,0,0), new TimeSpan(10,0,0));  
```  
  
```  
Level:Default MaxAge:36000 MinFresh:18000  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Cacheverwaltung für Netzwerkanwendungen](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 [Cacherichtlinie](../../../docs/framework/network-programming/cache-policy.md)  
 [Speicherortbasierte Cacherichtlinien](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 [Zeitbasierte Cacherichtlinien](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 [\<requestCaching>-Element (Netzwerkeinstellungen)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)

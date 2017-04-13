---
title: "Gewusst wie: Anpassen einer zeitbasierten Cacherichtlinie | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Zeitbasierte Cacherichtlinien"
  - "Anpassen zeitbasierter Cacherichtlinien"
  - "Cache [.NET Framework], Zeitbasierte Richtlinien"
ms.assetid: 8d84f936-2376-4356-9264-03162e0f9279
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 15
---
# Gewusst wie: Anpassen einer zeitbasierten Cacherichtlinie
Wenn Sie eine zeitbasierte Cacherichtlinie erstellen, können Sie Cachingverhalten anpassen, indem Sie Werte für Höchstalter, minimale Aktualität, maximale Abgestandenheit oder Cachesynchronisierungsdatum angeben.  Das <xref:System.Net.Cache.HttpRequestCachePolicy>\-Objekt stellt mehrere Konstruktoren, die es Ihnen ermöglichen, gültige Kombinationen dieser Werte anzugeben.  
  
### So fügen Sie eine zeitbasierte Cacherichtlinie erstellen, die ein Cachesynchronisierungsdatum verwendet  
  
-   Erstellen Sie eine zeitbasierte Cacherichtlinie, die ein Cachesynchronisierungsdatum verwendet, indem ein <xref:System.DateTime><xref:System.Net.Cache.HttpRequestCachePolicy>\-Objekt an den Konstruktor übergibt.  
  
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
  
 Die Ausgabe lautet folgendermaßen:  
  
```  
When: 1/14/2004 8:07:30 AM  
Level:Default CacheSyncDate:1/14/2004 8:07:30 AM  
```  
  
### So fügen Sie eine zeitbasierte Cacherichtlinie erstellen, die auf der minimale Aktualität ist  
  
-   Erstellen Sie eine zeitbasierte Cacherichtlinie, die auf der minimale Aktualität ist, indem <xref:System.Net.Cache.HttpCacheAgeControl> als der `cacheAgeControl`\-Parameterwert angibt und ein <xref:System.TimeSpan><xref:System.Net.Cache.HttpRequestCachePolicy>\-Objekt an den Konstruktor übergibt.  
  
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
  
### So fügen Sie eine zeitbasierte Cacherichtlinie erstellen, die auf der minimale Aktualität und Höchstalter ist  
  
-   Erstellen Sie eine zeitbasierte Cacherichtlinie, die auf der minimale Aktualität und Höchstalter ist, indem <xref:System.Net.Cache.HttpCacheAgeControl> als der `cacheAgeControl`\-Parameterwert angibt und zwei <xref:System.TimeSpan>\-Objekte in den <xref:System.Net.Cache.HttpRequestCachePolicy>\-Konstruktor übergibt, einer, um den Höchstalters anzugeben, sodass Ressourcen und eine zweite die minimale Aktualität angibt, die für ein Objekt erlaubt ist, das aus dem Cache zurückgegeben wird.  
  
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
  
## Siehe auch  
 [Cacheverwaltung für Netzwerkanwendungen](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [Cacherichtlinie](../../../docs/framework/network-programming/cache-policy.md)   
 [Speicherortbasierte Cacherichtlinien](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [zeitbasierte Cacherichtlinien](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [\<requestCaching\>\-Element \(Netzwerkeinstellungen\)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)
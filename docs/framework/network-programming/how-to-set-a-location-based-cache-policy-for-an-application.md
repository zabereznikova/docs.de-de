---
title: "Gewusst wie: Festlegen einer speicherortbasierten Cacherichtlinie f&#252;r eine Anwendung | Microsoft Docs"
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
  - "Explizites Definieren von Cacheverhalten"
  - "Speicherortbasierte Cacherichtlinien"
  - "Lokaler Cache"
  - "Anforderung von Cacherichtlinien"
  - "Cache [.NET Framework], Speicherortbasierte Richtlinien"
ms.assetid: 683bb88e-3411-4f46-9686-3411b6ba511c
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# Gewusst wie: Festlegen einer speicherortbasierten Cacherichtlinie f&#252;r eine Anwendung
Ortsbasierte Cacherichtlinien können in einer Anwendung, Zwischenspeicherung auf der Grundlage der Position der angeforderten Ressource explizit zu definieren.  In diesem Thema werden die Cacherichtlinie programmgesteuert festlegen.  Weitere Informationen zum Festlegen der Richtlinie für eine Anwendung mithilfe der Konfigurationsdateien, finden Sie unter [\<requestCaching\>\-Element \(Netzwerkeinstellungen\)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md).  
  
### So fügen Sie eine ortsbasierte Cacherichtlinie für eine Anwendung festlegen  
  
1.  Erstellen Sie ein <xref:System.Net.Cache.RequestCachePolicy> oder <xref:System.Net.Cache.HttpRequestCachePolicy>\-Objekt.  
  
2.  Legen Sie das Richtlinienobjekt als Standard für die Anwendungsdomäne fest.  
  
### Um eine Richtlinie festzulegen die akzeptiert Anwendungstest Ressourcen von einem Cache an  
  
-   Erstellen Sie eine Richtlinie, die angeforderte Ressourcen von einem Cache verwendet, sofern verfügbar und andernfalls, Anforderungen an den Server, indem das Festlegen des Cache sendet, der zu <xref:System.Net.Cache.HttpRequestCacheLevel> einstellen.  Eine Anforderung kann von jedem Cache zwischen Client und Server, einschließlich Remote Cache erfüllt werden.  
  
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
  
### So fügen Sie eine Richtlinien festlegen, die jeden Cache am Angeben von Ressourcen verhindert  
  
-   Erstellen Sie eine Richtlinie, die jeden Cache am Angeben von angeforderten Ressourcen verhindert, indem es den Cache festgelegt wird, der zu <xref:System.Net.Cache.HttpRequestCacheLevel> einstellen.  Diese Richtlinienebene entfernt die Ressource aus dem lokalen Cache, wenn vorhanden ist und gibt an den Cache an, dass die Ressource auch entfernt werden kann.  
  
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
  
### Um eine Richtlinie festzulegen die zurückgibt Anwendungstest Ressourcen an nur bei im lokalen Cache sind  
  
-   Erstellen Sie eine Richtlinie, die angeforderte Ressourcen zurückgibt, wenn sie im lokalen Cache befinden, indem der Cache festlegen, der auf <xref:System.Net.Cache.HttpRequestCacheLevel> einstellen.  Wenn die angeforderte Ressource nicht im Cache befindet, wird eine Ausnahme ausgelöst. <xref:System.Net.WebException>  
  
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
  
### So fügen Sie eine Richtlinien festlegen, die den lokalen Cache am Angeben von Ressourcen verhindert  
  
-   Erstellen Sie eine Richtlinie, die den lokalen Cache am Angeben von angeforderten Ressourcen verhindert, indem es den Cache festgelegt wird, der zu <xref:System.Net.Cache.HttpRequestCacheLevel> einstellen.  Wenn die angeforderte Ressource in einem Zwischencachen ist und erfolgreich neu überprüft wird, kann der Zwischencache die angeforderte Ressource bereitstellen.  
  
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
  
### So fügen Sie eine Richtlinien festlegen, die jeden Cache am Angeben von angeforderten Ressourcen verhindert  
  
-   Erstellen Sie eine Richtlinie, die jeden Cache am Angeben von angeforderten Ressourcen verhindert, indem es den Cache festgelegt wird, der zu <xref:System.Net.Cache.HttpRequestCacheLevel> einstellen.  Die Ressource, die vom Server zurückgegeben wird, kann im Cache gespeichert werden.  
  
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
  
### Um eine Richtlinie festzulegen die jeden Cache von werden zulässig sind Ressourcen wenn die Ressourcen auf dem Server nicht neuer ist als die zwischengespeicherte Kopie an  
  
-   Erstellen Sie eine Richtlinie, die jeden Cache zu Zubehör angeforderten Ressourcen, wenn die Ressource auf dem Server nicht neuer ist als die zwischengespeicherte Kopie können, indem Sie den Cache festgelegt wird, der zu <xref:System.Net.Cache.HttpRequestCacheLevel> einstellen.  
  
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
  
## Siehe auch  
 [Cacheverwaltung für Netzwerkanwendungen](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [Cacherichtlinie](../../../docs/framework/network-programming/cache-policy.md)   
 [Speicherortbasierte Cacherichtlinien](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [zeitbasierte Cacherichtlinien](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [\<requestCaching\>\-Element \(Netzwerkeinstellungen\)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)
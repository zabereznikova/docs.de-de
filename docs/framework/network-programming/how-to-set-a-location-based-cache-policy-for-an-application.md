---
title: 'Gewusst wie: Festlegen einer speicherortbasierten Cacherichtlinie für eine Anwendung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- explicitly defining cache behavior
- location-based cache policies
- local cache
- request cache policies
- cache [.NET Framework], location-based policies
ms.assetid: 683bb88e-3411-4f46-9686-3411b6ba511c
ms.openlocfilehash: 6fe569e781b005461ea41e3d6b90859666f9601a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180782"
---
# <a name="how-to-set-a-location-based-cache-policy-for-an-application"></a>Gewusst wie: Festlegen einer speicherortbasierten Cacherichtlinie für eine Anwendung
Speicherortbasierte Cacherichtlinien ermöglichen einer Anwendung, das Cacheverhalten basierend auf dem Speicherort der angeforderten Ressource explizit zu definieren. In diesem Thema wird veranschaulicht, wie Sie eine Cacherichtlinie programmgesteuert festlegen können. Weitere Informationen zum Festlegen der Richtlinie für eine Anwendung mithilfe der Konfigurationsdateien finden Sie unter [\<requestCaching>-Element (Netzwerkeinstellungen)](../configure-apps/file-schema/network/requestcaching-element-network-settings.md).  
  
### <a name="to-set-a-location-based-cache-policy-for-an-application"></a>Festlegen einer speicherortbasierten Cacherichtlinie für eine Anwendung  
  
1. Erstellen Sie ein <xref:System.Net.Cache.RequestCachePolicy>- oder <xref:System.Net.Cache.HttpRequestCachePolicy>-Objekt.  
  
2. Legen Sie das Richtlinienobjekt als Standard für die Anwendungsdomäne fest.  
  
### <a name="to-set-a-policy-that-takes-requested-resources-from-a-cache"></a>Festlegen einer Richtlinie, die angeforderte Ressourcen aus einem Cache abruft  
  
- Erstellen Sie eine Richtlinie, die die angeforderten Ressourcen, falls verfügbar, aus einem Cache abruft, indem Sie die Cacheebene auf <xref:System.Net.Cache.HttpRequestCacheLevel.CacheIfAvailable> festlegen. Sind keine Ressourcen verfügbar, sendet die Richtlinie Anforderungen an den Server. Eine Anforderung kann von einem beliebigen Cache zwischen Client und Server erfüllt werden, einschließlich eines Remotecaches.  
  
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
  
### <a name="to-set-a-policy-that-prevents-any-cache-from-supplying-resources"></a>Festlegen einer Richtlinie, die die Bereitstellung von Ressourcen durch einen Cache verhindert  
  
- Erstellen Sie eine Richtlinie, die verhindert, dass ein beliebiger Cache die angeforderten Ressourcen bereitstellt, indem Sie die Cacheebene auf <xref:System.Net.Cache.HttpRequestCacheLevel.NoCacheNoStore> festlegen. Diese Richtlinienebene entfernt die Ressource, sofern vorhanden, aus dem lokalen Cache, und gibt den Remotecaches an, dass sie die Ressource auch entfernen sollen.  
  
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
  
### <a name="to-set-a-policy-that-returns-requested-resources-only-if-they-are-in-the-local-cache"></a>Festlegen einer Richtlinie, die angeforderte Ressourcen nur zurückgibt, wenn sie im lokalen Cache sind  
  
- Erstellen Sie eine Richtlinie, die die angeforderten Ressourcen nur zurückgibt, wenn sie sich im lokalen Cache befinden, indem Sie die Cacheebene auf <xref:System.Net.Cache.HttpRequestCacheLevel.CacheOnly> festlegen. Befindet sich die angeforderte Ressource nicht im Cache, wird eine <xref:System.Net.WebException>-Ausnahme ausgelöst.  
  
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
  
### <a name="to-set-a-policy-that-prevents-the-local-cache-from-supplying-resources"></a>Festlegen einer Richtlinie, die die Bereitstellung von Ressourcen durch den lokalen Cache verhindert  
  
- Erstellen Sie eine Richtlinie, die verhindert, dass der lokale Cache die angeforderten Ressourcen bereitstellt, indem Sie die Cacheebene auf <xref:System.Net.Cache.HttpRequestCacheLevel.Refresh> festlegen. Befindet sich die angeforderte Ressource in einem Zwischen-Cache und wird erneut erfolgreich überprüft, kann der Zwischen-Cache die angeforderte Ressource bereitstellen.  
  
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
  
### <a name="to-set-a-policy-that-prevents-any-cache-from-supplying-requested-resources"></a>Festlegen einer Richtlinie, die die Bereitstellung von angeforderten Ressourcen durch einen Cache verhindert  
  
- Erstellen Sie eine Richtlinie, die verhindert, dass ein beliebiger Cache die angeforderten Ressourcen bereitstellt, indem Sie die Cacheebene auf <xref:System.Net.Cache.HttpRequestCacheLevel.Reload> festlegen. Die vom Server zurückgegebene Ressource kann im Cache gespeichert werden.  
  
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
  
### <a name="to-set-a-policy-that-allows-any-cache-to-supply-requested-resources-if-the-resource-on-the-server-is-not-newer-than-the-cached-copy"></a>Festlegen einer Richtlinie, die die Bereitstellung von angeforderten Ressourcen durch einen Cache ermöglicht, wenn die Ressource im Server nicht neuer ist als die zwischengespeicherte Kopie  
  
- Erstellen Sie eine Richtlinie, die die Bereitstellung von angeforderten Ressourcen durch einen Cache ermöglicht, wenn die Ressource im Server nicht neuer ist als die zwischengespeicherte Kopie, indem Sie die Cacheebene auf <xref:System.Net.Cache.HttpRequestCacheLevel.Revalidate> festlegen.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Cacheverwaltung für Netzwerkanwendungen](cache-management-for-network-applications.md)
- [Cacherichtlinie](cache-policy.md)
- [Speicherortbasierte Cacherichtlinien](location-based-cache-policies.md)
- [Zeitbasierte Cacherichtlinien](time-based-cache-policies.md)
- [\<requestCaching>-Element (Netzwerkeinstellungen)](../configure-apps/file-schema/network/requestcaching-element-network-settings.md)

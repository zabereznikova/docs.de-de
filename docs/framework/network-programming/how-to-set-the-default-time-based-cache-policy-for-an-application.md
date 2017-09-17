---
title: "Gewusst wie: Festlegen der standardmäßigen zeitbasierten Cacherichtlinie für eine Anwendung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- time-based cache policies
- cache [.NET Framework], time-based policies
- default time-based cache policy
ms.assetid: 6bfce066-a2e7-4add-a05e-85c12ec9f07f
caps.latest.revision: 9
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f462c55919025b92014a99d73b9a6b779465f98e
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="how-to-set-the-default-time-based-cache-policy-for-an-application"></a>Gewusst wie: Festlegen der standardmäßigen zeitbasierten Cacherichtlinie für eine Anwendung
Die zeitbasierte Standardcacherichtlinie ermöglicht es einer Anwendung, dass deren Cacheverhalten von den Headern definiert werden, die mit den zwischengespeicherten Ressourcen gesendet werden. Außerdem wird das Cacheverhalten ermöglicht, das in Abschnitt 13 und 14 des RFC 2616, verfügbar unter [http://www.ietf.org](http://www.ietf.org/), definiert wird. Dies ist das angemessene Cacheverhalten für die meisten Anwendungen.  
  
### <a name="to-set-the-default-automatic-policy-for-an-application"></a>Festlegen der automatischen Standardrichtlinie für eine Anwendung  
  
1.  Erstellen Sie ein zeitbasiertes Standardrichtlinienobjekt.  
  
2.  Legen Sie das Richtlinienobjekt als Standard für die Anwendungsdomäne fest.  
  
## <a name="example"></a>Beispiel  
 Die beiden Beispiele in diesem Abschnitt erzeugen identische Richtlinien.  
  
 Im folgenden Beispiel wird eine zeitbasierte Standardrichtlinie erstellt und als Standard für die Anwendungsdomäne festgelegt.  
  
```csharp  
public static void SetDefaultTimeBasedPolicy ()  
{  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy ();  
    HttpWebRequest.DefaultCachePolicy = policy ;  
}  
```  
  
```vb  
Public Shared Sub SetDefaultTimeBasedPolicy ()  
    Dim policy = New HttpRequestCachePolicy ()  
    HttpWebRequest.DefaultCachePolicy = policy  
End Sub  
```  
  
 Sie können auch eine zeitbasierte Standardrichtlinie erstellen, indem Sie die <xref:System.Net.Cache.RequestCachePolicy>-Klasse wie im folgenden Beispiel dargestellt verwenden:  
  
```csharp  
public static void SetDefaultTimeBasedPolicy2()  
{  
    RequestCachePolicy policy = new RequestCachePolicy ();  
    HttpWebRequest.DefaultCachePolicy = policy ;  
}  
```  
  
```vb  
Public Shared Sub SetDefaultTimeBasedPolicy2()  
    Dim policy As New RequestCachePolicy()  
    HttpWebRequest.DefaultCachePolicy = policy  
End Sub  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Cacheverwaltung für Netzwerkanwendungen](../../../docs/framework/network-programming/cache-management-for-network-applications.md)   
 [Cache Policy (Cacherichtlinie)](../../../docs/framework/network-programming/cache-policy.md)   
 [Location-Based Cache Policies (Speicherortbasierte Cacherichtlinien)](../../../docs/framework/network-programming/location-based-cache-policies.md)   
 [Time-Based Cache Policies (Zeitbasierte Cacherichtlinien)](../../../docs/framework/network-programming/time-based-cache-policies.md)   
 [\<requestCaching>-Element (Netzwerkeinstellungen)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)


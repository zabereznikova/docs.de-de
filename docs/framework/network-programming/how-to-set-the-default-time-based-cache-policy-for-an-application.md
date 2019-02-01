---
title: 'Vorgehensweise: Festlegen der zeitbasierten Standardcacherichtlinie für eine Anwendung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time-based cache policies
- cache [.NET Framework], time-based policies
- default time-based cache policy
ms.assetid: 6bfce066-a2e7-4add-a05e-85c12ec9f07f
ms.openlocfilehash: d40b0ffbe514429ed24eaa5d0c2ce2d52c80d37d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54608952"
---
# <a name="how-to-set-the-default-time-based-cache-policy-for-an-application"></a>Vorgehensweise: Festlegen der zeitbasierten Standardcacherichtlinie für eine Anwendung
Mit der standardmäßigen zeitbasierten Cacherichtlinie kann das Cacheverhalten einer Anwendung von den Headern definiert werden, die mit der zwischengespeicherten Ressource gesendet werden. Außerdem wird das Cacheverhalten ermöglicht, das in Abschnitt 13 und 14 des RFC 2616 definiert wird, verfügbar auf der Website der [Internet Engineering Task Force (IETF)](https://www.ietf.org/). Dies ist das angemessene Cacheverhalten für die meisten Anwendungen.  
  
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
- [Cacheverwaltung für Netzwerkanwendungen](../../../docs/framework/network-programming/cache-management-for-network-applications.md)
- [Cacherichtlinie](../../../docs/framework/network-programming/cache-policy.md)
- [Speicherortbasierte Cacherichtlinien](../../../docs/framework/network-programming/location-based-cache-policies.md)
- [Zeitbasierte Cacherichtlinien](../../../docs/framework/network-programming/time-based-cache-policies.md)
- [\<requestCaching>-Element (Netzwerkeinstellungen)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)

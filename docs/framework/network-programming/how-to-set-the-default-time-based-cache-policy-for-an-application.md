---
title: 'Gewusst wie: Festlegen der standardmäßigen zeitbasierten Cacherichtlinie für eine Anwendung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time-based cache policies
- cache [.NET Framework], time-based policies
- default time-based cache policy
ms.assetid: 6bfce066-a2e7-4add-a05e-85c12ec9f07f
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 021a13b9124cf54712643e33cbf0ca77ec828b27
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33396671"
---
# <a name="how-to-set-the-default-time-based-cache-policy-for-an-application"></a><span data-ttu-id="83492-102">Gewusst wie: Festlegen der standardmäßigen zeitbasierten Cacherichtlinie für eine Anwendung</span><span class="sxs-lookup"><span data-stu-id="83492-102">How to: Set the Default Time-Based Cache Policy for an Application</span></span>
<span data-ttu-id="83492-103">Die zeitbasierte Standardcacherichtlinie ermöglicht es einer Anwendung, dass deren Cacheverhalten von den Headern definiert werden, die mit den zwischengespeicherten Ressourcen gesendet werden. Außerdem wird das Cacheverhalten ermöglicht, das in Abschnitt 13 und 14 des RFC 2616, verfügbar unter [http://www.ietf.org](http://www.ietf.org/), definiert wird. Dies ist das angemessene Cacheverhalten für die meisten Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="83492-103">The default time-based cache policy allows an application to have its cache behavior defined by the headers sent with the cached resource and the cache behavior defined in sections 13 and 14 of RFC 2616, available at [http://www.ietf.org](http://www.ietf.org/). This is the appropriate cache behavior for most applications.</span></span>  
  
### <a name="to-set-the-default-automatic-policy-for-an-application"></a><span data-ttu-id="83492-104">Festlegen der automatischen Standardrichtlinie für eine Anwendung</span><span class="sxs-lookup"><span data-stu-id="83492-104">To set the default automatic policy for an application</span></span>  
  
1.  <span data-ttu-id="83492-105">Erstellen Sie ein zeitbasiertes Standardrichtlinienobjekt.</span><span class="sxs-lookup"><span data-stu-id="83492-105">Create a default time-based policy object.</span></span>  
  
2.  <span data-ttu-id="83492-106">Legen Sie das Richtlinienobjekt als Standard für die Anwendungsdomäne fest.</span><span class="sxs-lookup"><span data-stu-id="83492-106">Set the policy object as the default for the application domain.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83492-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="83492-107">Example</span></span>  
 <span data-ttu-id="83492-108">Die beiden Beispiele in diesem Abschnitt erzeugen identische Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="83492-108">The two examples in this section produce identical policies.</span></span>  
  
 <span data-ttu-id="83492-109">Im folgenden Beispiel wird eine zeitbasierte Standardrichtlinie erstellt und als Standard für die Anwendungsdomäne festgelegt.</span><span class="sxs-lookup"><span data-stu-id="83492-109">The following example creates a default time-based policy and sets it as the default for the application domain.</span></span>  
  
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
  
 <span data-ttu-id="83492-110">Sie können auch eine zeitbasierte Standardrichtlinie erstellen, indem Sie die <xref:System.Net.Cache.RequestCachePolicy>-Klasse wie im folgenden Beispiel dargestellt verwenden:</span><span class="sxs-lookup"><span data-stu-id="83492-110">You can also create the default time-based cache policy using the <xref:System.Net.Cache.RequestCachePolicy> class as shown in the following example:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="83492-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83492-111">See Also</span></span>  
 [<span data-ttu-id="83492-112">Cacheverwaltung für Netzwerkanwendungen</span><span class="sxs-lookup"><span data-stu-id="83492-112">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 [<span data-ttu-id="83492-113">Cacherichtlinie</span><span class="sxs-lookup"><span data-stu-id="83492-113">Cache Policy</span></span>](../../../docs/framework/network-programming/cache-policy.md)  
 [<span data-ttu-id="83492-114">Speicherortbasierte Cacherichtlinien</span><span class="sxs-lookup"><span data-stu-id="83492-114">Location-Based Cache Policies</span></span>](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 [<span data-ttu-id="83492-115">Zeitbasierte Cacherichtlinien</span><span class="sxs-lookup"><span data-stu-id="83492-115">Time-Based Cache Policies</span></span>](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 [<span data-ttu-id="83492-116">\<requestCaching>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="83492-116">\<requestCaching> Element (Network Settings)</span></span>](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)

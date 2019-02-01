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
# <a name="how-to-set-the-default-time-based-cache-policy-for-an-application"></a><span data-ttu-id="35558-102">Vorgehensweise: Festlegen der zeitbasierten Standardcacherichtlinie für eine Anwendung</span><span class="sxs-lookup"><span data-stu-id="35558-102">How to: Set the Default Time-Based Cache Policy for an Application</span></span>
<span data-ttu-id="35558-103">Mit der standardmäßigen zeitbasierten Cacherichtlinie kann das Cacheverhalten einer Anwendung von den Headern definiert werden, die mit der zwischengespeicherten Ressource gesendet werden. Außerdem wird das Cacheverhalten ermöglicht, das in Abschnitt 13 und 14 des RFC 2616 definiert wird, verfügbar auf der Website der [Internet Engineering Task Force (IETF)](https://www.ietf.org/).</span><span class="sxs-lookup"><span data-stu-id="35558-103">The default time-based cache policy allows an application to have its cache behavior defined by the headers sent with the cached resource and the cache behavior defined in sections 13 and 14 of RFC 2616, available at [Internet Engineering Task Force (IETF)](https://www.ietf.org/) website.</span></span> <span data-ttu-id="35558-104">Dies ist das angemessene Cacheverhalten für die meisten Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="35558-104">This is the appropriate cache behavior for most applications.</span></span>  
  
### <a name="to-set-the-default-automatic-policy-for-an-application"></a><span data-ttu-id="35558-105">Festlegen der automatischen Standardrichtlinie für eine Anwendung</span><span class="sxs-lookup"><span data-stu-id="35558-105">To set the default automatic policy for an application</span></span>  
  
1.  <span data-ttu-id="35558-106">Erstellen Sie ein zeitbasiertes Standardrichtlinienobjekt.</span><span class="sxs-lookup"><span data-stu-id="35558-106">Create a default time-based policy object.</span></span>  
  
2.  <span data-ttu-id="35558-107">Legen Sie das Richtlinienobjekt als Standard für die Anwendungsdomäne fest.</span><span class="sxs-lookup"><span data-stu-id="35558-107">Set the policy object as the default for the application domain.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35558-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="35558-108">Example</span></span>  
 <span data-ttu-id="35558-109">Die beiden Beispiele in diesem Abschnitt erzeugen identische Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="35558-109">The two examples in this section produce identical policies.</span></span>  
  
 <span data-ttu-id="35558-110">Im folgenden Beispiel wird eine zeitbasierte Standardrichtlinie erstellt und als Standard für die Anwendungsdomäne festgelegt.</span><span class="sxs-lookup"><span data-stu-id="35558-110">The following example creates a default time-based policy and sets it as the default for the application domain.</span></span>  
  
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
  
 <span data-ttu-id="35558-111">Sie können auch eine zeitbasierte Standardrichtlinie erstellen, indem Sie die <xref:System.Net.Cache.RequestCachePolicy>-Klasse wie im folgenden Beispiel dargestellt verwenden:</span><span class="sxs-lookup"><span data-stu-id="35558-111">You can also create the default time-based cache policy using the <xref:System.Net.Cache.RequestCachePolicy> class as shown in the following example:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="35558-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35558-112">See also</span></span>
- [<span data-ttu-id="35558-113">Cacheverwaltung für Netzwerkanwendungen</span><span class="sxs-lookup"><span data-stu-id="35558-113">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)
- [<span data-ttu-id="35558-114">Cacherichtlinie</span><span class="sxs-lookup"><span data-stu-id="35558-114">Cache Policy</span></span>](../../../docs/framework/network-programming/cache-policy.md)
- [<span data-ttu-id="35558-115">Speicherortbasierte Cacherichtlinien</span><span class="sxs-lookup"><span data-stu-id="35558-115">Location-Based Cache Policies</span></span>](../../../docs/framework/network-programming/location-based-cache-policies.md)
- [<span data-ttu-id="35558-116">Zeitbasierte Cacherichtlinien</span><span class="sxs-lookup"><span data-stu-id="35558-116">Time-Based Cache Policies</span></span>](../../../docs/framework/network-programming/time-based-cache-policies.md)
- [<span data-ttu-id="35558-117">\<requestCaching>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="35558-117">\<requestCaching> Element (Network Settings)</span></span>](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)

---
title: "Entschärfung: Benutzerdefinierte IMessageFilter.PreFilterMessage-Implementierungen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9cf47c5b-0bb2-45df-9437-61cd7e7c2f4d
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: b37d1d7ff75aebfcdf3e849931a5d2b3924d5d7a
ms.openlocfilehash: fe7290f3a887f2c4d52e52a6aff708e0e9fe415f
ms.contentlocale: de-de
ms.lasthandoff: 09/06/2017

---
# <a name="mitigation-custom-imessagefilterprefiltermessage-implementations"></a><span data-ttu-id="be80a-102">Entschärfung: Benutzerdefinierte IMessageFilter.PreFilterMessage-Implementierungen</span><span class="sxs-lookup"><span data-stu-id="be80a-102">Mitigation: Custom IMessageFilter.PreFilterMessage Implementations</span></span>
<span data-ttu-id="be80a-103">In Windows Forms-Apps für Versionen des .NET Frameworks ab [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] kann eine benutzerdefinierte <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName>-Implementierung Meldungen beim Aufruf der <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName>-Methode sicher filtern, wenn die <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName>-Implementierung:</span><span class="sxs-lookup"><span data-stu-id="be80a-103">In Windows Forms apps that target versions of the .NET Framework starting with the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], a custom <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName> implementation can safely filter messages when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName> method is called if the <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName> implementation:</span></span>  
  
-   <span data-ttu-id="be80a-104">Mindestens eine der folgenden Aktionen ausführt:</span><span class="sxs-lookup"><span data-stu-id="be80a-104">Does one or both of the following:</span></span>  
  
    -   <span data-ttu-id="be80a-105">Hinzufügen eines Meldungsfilters durch Aufrufen der <xref:System.Windows.Forms.Application.AddMessageFilter%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="be80a-105">Adds a message filter by calling the <xref:System.Windows.Forms.Application.AddMessageFilter%2A> method.</span></span>  
  
    -   <span data-ttu-id="be80a-106">Entfernen eines Meldungsfilters durch Aufrufen der <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="be80a-106">Removes a message filter by calling the <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A> method.</span></span> <span data-ttu-id="be80a-107">-Methode.</span><span class="sxs-lookup"><span data-stu-id="be80a-107">method.</span></span>  
  
-   <span data-ttu-id="be80a-108">**Und** Nachrichten durch Aufrufen der <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=fullName>-Methode abruft.</span><span class="sxs-lookup"><span data-stu-id="be80a-108">**And** pumps messages by calling the <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=fullName> method.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="be80a-109">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="be80a-109">Impact</span></span>  
 <span data-ttu-id="be80a-110">Diese Änderung betrifft nur Windows Forms-Apps, die auf Versionen von .NET Framework ausgerichtet sind, die mit [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] beginnen.</span><span class="sxs-lookup"><span data-stu-id="be80a-110">This change only affects Windows Forms apps that target versions of the .NET Framework starting with the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].</span></span>  
  
 <span data-ttu-id="be80a-111">Für Windows Forms-Apps, die auf vorherige Versionen von .NET Framework ausgerichtet sind, lösen solche Implementierungen in einigen Fällen beim Aufrufen der <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName>-Methode eine <xref:System.IndexOutOfRangeException>-Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="be80a-111">For Windows Forms apps that target previous versions of the .NET Framework, such implementations in some cases throw an <xref:System.IndexOutOfRangeException> exception when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName> method is called</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="be80a-112">Problemumgehung</span><span class="sxs-lookup"><span data-stu-id="be80a-112">Mitigation</span></span>  
 <span data-ttu-id="be80a-113">Ist diese Änderung nicht erwünscht, kann sie für Apps, die für [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] oder höhere Versionen vorgesehen sind, abgelehnt werden. Dazu muss dem [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)-Abschnitt der Konfigurationsdatei der App die folgende Konfigurationseinstellung hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="be80a-113">If this change is undesirable, apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] or a later version can opt out of it by adding the following configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=true" />   
</runtime>  
```  
  
 <span data-ttu-id="be80a-114">Für Apps, die für frühere Versionen von .NET Framework vorgesehen sind, aber unter [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] oder einer höheren Version ausgeführt werden, kann dieses Verhalten übernommen werden, indem dem [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)-Abschnitt der Konfigurationsdatei der Anwendung die folgende Konfigurationseinstellung hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="be80a-114">In addition, apps that target previous versions of the .NET Framework but are running under the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] or a later version can opt in to this behavior by adding the following configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=false" />   
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="be80a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be80a-115">See Also</span></span>  
 [<span data-ttu-id="be80a-116">Neuausrichtungsänderungen</span><span class="sxs-lookup"><span data-stu-id="be80a-116">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)


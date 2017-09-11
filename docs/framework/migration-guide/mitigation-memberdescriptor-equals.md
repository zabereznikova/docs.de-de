---
title: "Entschärfung: MemberDescriptor.Equals"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf3735f0-0dd4-4bef-b4b0-575264e10f39
caps.latest.revision: 7
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4989d3c2611b500063158955f102931902e1ab32
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-memberdescriptorequals"></a><span data-ttu-id="42cba-102">Entschärfung: MemberDescriptor.Equals</span><span class="sxs-lookup"><span data-stu-id="42cba-102">Mitigation: MemberDescriptor.Equals</span></span>
<span data-ttu-id="42cba-103">Beginnend mit Apps für [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] hat sich die Implementierung der <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName>-Methode geändert.</span><span class="sxs-lookup"><span data-stu-id="42cba-103">Starting with apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], the implementation of the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> method has changed.</span></span> <span data-ttu-id="42cba-104">Da die Methoden `System.ComponentModel.EventDescriptor.Equals` und `System.ComponentModel.PropertyDescriptor.Equals` die Basisklassenimplementierung erben, wirkt sich die Änderung auch auf diese Methoden aus.</span><span class="sxs-lookup"><span data-stu-id="42cba-104">Because the `System.ComponentModel.EventDescriptor.Equals` and  `System.ComponentModel.PropertyDescriptor.Equals` methods inherit the base class implementation, the change also affects these methods.</span></span>  
  
 <span data-ttu-id="42cba-105">In Apps, die auf ältere Versionen von .NET Framework als [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] ausgerichtet sind, hat ein Teil der Prüfung auf Gleichheit durch die <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName>-Methode fälschlicherweise die <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName>-Eigenschaft eines Objekts mit der <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName>-Eigenschaft eines anderen verglichen.</span><span class="sxs-lookup"><span data-stu-id="42cba-105">In apps that target versions of the .NET Framework prior to [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], a portion of the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> method's test for equality  incorrectly compared the <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName> property of one object with the <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> property of the other.</span></span> <span data-ttu-id="42cba-106">Beginnend mit Apps für [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] vergleicht die <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName>-Methode die <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName>-Eigenschaft von zwei Objekten.</span><span class="sxs-lookup"><span data-stu-id="42cba-106">Starting with apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> method compares the <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> property of the two objects.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="42cba-107">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="42cba-107">Impact</span></span>  
 <span data-ttu-id="42cba-108">Diese Änderung implementiert den Test auf Gleichheit für <xref:System.ComponentModel.MemberDescriptor?displayProperty=fullName>-Objekte ordnungsgemäß und sollte nur minimale Auswirkungen haben.</span><span class="sxs-lookup"><span data-stu-id="42cba-108">This change correctly implements the test for equality for <xref:System.ComponentModel.MemberDescriptor?displayProperty=fullName> objects and should have minimal impact.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="42cba-109">Problemumgehung</span><span class="sxs-lookup"><span data-stu-id="42cba-109">Mitigation</span></span>  
 <span data-ttu-id="42cba-110">Es stehen zwei Problemumgehungen zur Verfügung, wenn Ihre App für [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] oder eine spätere Version von .NET-Framework vorgesehen ist und von der <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName>-Methode abhängt, die manchmal `false` zurückgibt, wenn die Memberdeskriptoren gleichwertig sind:</span><span class="sxs-lookup"><span data-stu-id="42cba-110">Two workarounds are available if your app targets the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or a later version of the .NET Framework and it depends on the  <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> method sometimes returning `false` when member descriptors are equivalent:</span></span>  
  
-   <span data-ttu-id="42cba-111">Sie können sich gegen diese Änderung entscheiden, ohne Ihren Quellcode zu ändern, indem Sie Folgendes zum Abschnitt [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) Ihrer app.config-Datei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="42cba-111">You can opt out of this change without modifying your source code by adding the following to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value = "Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true" />  
     </runtime>  
    ```  
  
-   <span data-ttu-id="42cba-112">Sie können Ihren Quellcode ändern, um das vorherige Verhalten wiederherzustellen, indem Sie die Eigenschaften <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName> und <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> nach dem Aufrufen der <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName>-Methode manuell vergleichen, wie es im folgenden Codefragment geschieht.</span><span class="sxs-lookup"><span data-stu-id="42cba-112">You can modify your source code to restore the previous behavior by manually comparing the  <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName> and <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> properties after calling the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> method, as the following code fragment does.</span></span>  
  
    ```csharp  
    if (memberDescriptor1.Equals(memberDescriptor2) &   
        memberDescriptor1.Description.Equals(memberDescriptor2.Category)) {  
          // Code to execute if true.  
    }  
    else {  
          // Code to execute if false.     
    }  
    ```  
  
    ```  
    If memberDescriptor1.Equals(memberDescriptor2) And   
        memberDescriptor1.Description.Equals(memberDescriptor2.Category)  
          // Code to execute if True.  
    Else  
          // Code to execute if False.     
    End If  
    ```  
  
 <span data-ttu-id="42cba-113">Für Apps mit [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] und früheren Versionen als Zielplattform können Sie diese Änderung aktivieren, indem Sie Ihrer app.config-Datei den folgenden Wert hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="42cba-113">For apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and earlier versions, you can enable this change by adding the following value to your app.config file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true />  
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="42cba-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42cba-114">See Also</span></span>  
 <span data-ttu-id="42cba-115">[Neuausrichtungsänderungen](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md) </span><span class="sxs-lookup"><span data-stu-id="42cba-115">[Retargeting Changes](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md) </span></span>  
 [<span data-ttu-id="42cba-116">Anwendungskompatibilität in 4.6.2</span><span class="sxs-lookup"><span data-stu-id="42cba-116">Application Compatibility in 4.6.2</span></span>](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-2.md)


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
# <a name="mitigation-memberdescriptorequals"></a>Entschärfung: MemberDescriptor.Equals
Beginnend mit Apps für [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] hat sich die Implementierung der <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName>-Methode geändert. Da die Methoden `System.ComponentModel.EventDescriptor.Equals` und `System.ComponentModel.PropertyDescriptor.Equals` die Basisklassenimplementierung erben, wirkt sich die Änderung auch auf diese Methoden aus.  
  
 In Apps, die auf ältere Versionen von .NET Framework als [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] ausgerichtet sind, hat ein Teil der Prüfung auf Gleichheit durch die <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName>-Methode fälschlicherweise die <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName>-Eigenschaft eines Objekts mit der <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName>-Eigenschaft eines anderen verglichen. Beginnend mit Apps für [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] vergleicht die <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName>-Methode die <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName>-Eigenschaft von zwei Objekten.  
  
## <a name="impact"></a>Auswirkungen  
 Diese Änderung implementiert den Test auf Gleichheit für <xref:System.ComponentModel.MemberDescriptor?displayProperty=fullName>-Objekte ordnungsgemäß und sollte nur minimale Auswirkungen haben.  
  
## <a name="mitigation"></a>Problemumgehung  
 Es stehen zwei Problemumgehungen zur Verfügung, wenn Ihre App für [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] oder eine spätere Version von .NET-Framework vorgesehen ist und von der <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName>-Methode abhängt, die manchmal `false` zurückgibt, wenn die Memberdeskriptoren gleichwertig sind:  
  
-   Sie können sich gegen diese Änderung entscheiden, ohne Ihren Quellcode zu ändern, indem Sie Folgendes zum Abschnitt [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) Ihrer app.config-Datei hinzufügen:  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value = "Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true" />  
     </runtime>  
    ```  
  
-   Sie können Ihren Quellcode ändern, um das vorherige Verhalten wiederherzustellen, indem Sie die Eigenschaften <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName> und <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName> nach dem Aufrufen der <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName>-Methode manuell vergleichen, wie es im folgenden Codefragment geschieht.  
  
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
  
 Für Apps mit [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] und früheren Versionen als Zielplattform können Sie diese Änderung aktivieren, indem Sie Ihrer app.config-Datei den folgenden Wert hinzufügen:  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true />  
</runtime>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Neuausrichtungsänderungen](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)   
 [Anwendungskompatibilität in 4.6.2](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-2.md)


---
title: "Entschärfung: MemberDescriptor.Equals | Microsoft-Dokumentation"
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 409f06f4dfbe7be50dd2c487e49d3d4d8a477539
ms.contentlocale: de-de
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-memberdescriptorequals"></a>Entschärfung: MemberDescriptor.Equals
Von Apps für die Zielplattform [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] an hat sich die Implementierung der <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName>-Methode geändert. Da die Methoden `System.ComponentModel.EventDescriptor.Equals` und `System.ComponentModel.PropertyDescriptor.Equals` die Basisklassenimplementierung erben, wirkt sich die Änderung auch auf diese Methoden aus.  
  
 In Apps mit Zielversionen von .NET Framework vor [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] hat ein Teil der Gleichheitsprüfung der Methode <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName> fälschlicherweise die <xref:System.ComponentModel.MemberDescriptor.Category%2A?displayProperty=fullName>-Eigenschaft eines Objekts mit der <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName>-Eigenschaft des anderen verglichen. In Apps für die Zielplattform [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] oder höher vergleicht die <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName>-Methode die <xref:System.ComponentModel.MemberDescriptor.Description%2A?displayProperty=fullName>-Eigenschaften der zwei Objekte.  
  
## <a name="impact"></a>Auswirkungen  
 Durch diese Änderung wird die Gleichheitsprüfung für <xref:System.ComponentModel.MemberDescriptor?displayProperty=fullName>-Objekte ordnungsgemäß implementiert, und der Einfluss sollte minimal sein.  
  
## <a name="mitigation"></a>Problemumgehung  
 Es stehen zwei Problemumgehungen zur Verfügung, wenn Ihre App für [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] oder eine spätere Version von .NET Framework vorgesehen ist und von der <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName>-Methode abhängt, die manchmal `false` zurückgibt, wenn die Memberdeskriptoren gleichbedeutend sind:  
  
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


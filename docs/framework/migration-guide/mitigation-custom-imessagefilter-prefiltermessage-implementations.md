---
title: "Entschärfung: Benutzerdefinierte IMessageFilter.PreFilterMessage-Implementierungen | Microsoft-Dokumentation"
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
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d85c827b414cc94410a921bfae9ce3e1764d22ea
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-custom-imessagefilterprefiltermessage-implementations"></a>Entschärfung: Benutzerdefinierte IMessageFilter.PreFilterMessage-Implementierungen
In Windows Forms-Apps, die auf Versionen von .NET Framework ausgerichtet sind, die mit [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] beginnen, kann eine benutzerdefinierte <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName>-Implementierung Nachrichten sicher filtern, wenn die <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName>-Methode aufgerufen wird, falls Folgendes für die <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName>-Implementierung gilt:  
  
-   Mindestens eine der folgenden Aktionen ausführt:  
  
    -   Fügt einen Nachrichtenfilter durch Aufrufen der Methode <xref:System.Windows.Forms.Application.AddMessageFilter%2A> hinzu.  
  
    -   Entfernt einen Nachrichtenfilter durch Aufrufen der Methode <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A>. -Methode.  
  
-   **Und** ruft Nachrichten durch Aufrufen der <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=fullName>-Methode ab.  
  
## <a name="impact"></a>Auswirkungen  
 Diese Änderung betrifft nur Windows Forms-Apps, die auf Versionen von .NET Framework ausgerichtet sind, die mit [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] beginnen.  
  
 Für Windows Forms-Apps, die auf frühere Versionen von .NET Framework ausgerichtet sind, lösen diese Implementierungen in solchen Fällen eine <xref:System.IndexOutOfRangeException>-Ausnahme aus, wenn die <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName>-Methode aufgerufen wird.  
  
## <a name="mitigation"></a>Entschärfung  
 Ist diese Änderung nicht erwünscht, kann sie für Apps, die für [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] oder höhere Versionen vorgesehen sind, abgelehnt werden. Dazu muss dem [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)-Abschnitt der Konfigurationsdatei der App die folgende Konfigurationseinstellung hinzugefügt werden:  
  
```xml  
  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=true" />   
</runtime>  
  
```  
  
 Für Apps, die für frühere Versionen von .NET Framework vorgesehen sind, aber unter [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] oder einer höheren Version ausgeführt werden, kann dieses Verhalten übernommen werden, indem dem [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)-Abschnitt der Konfigurationsdatei der Anwendung die folgende Konfigurationseinstellung hinzugefügt wird:  
  
```xml  
  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=false" />   
</runtime>  
  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Neuausrichtungsänderungen](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)

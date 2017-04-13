---
title: "Problemumgehung: Benutzerdefinierte IMessageFilter.PreFilterMessage-Implementierungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9cf47c5b-0bb2-45df-9437-61cd7e7c2f4d
caps.latest.revision: 5
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 2
---
# Problemumgehung: Benutzerdefinierte IMessageFilter.PreFilterMessage-Implementierungen
In Windows Forms\-Apps, die auf [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] ausgerichtet sind, kann eine benutzerdefinierte <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName>\-Implementierung Meldungen beim Aufruf der <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName>\-Methode sicher filtern, wenn die <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName>\-Implementierung:  
  
-   Mindestens eine der folgenden Aktionen ausführt:  
  
    -   Hinzufügen eines Meldungsfilters durch Aufrufen der <xref:System.Windows.Forms.Application.AddMessageFilter%2A>\-Methode.  
  
    -   Entfernen eines Meldungsfilters durch Aufrufen der <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A>\-Methode. \-Methode.  
  
-   **Und** ruft Nachrichten durch Aufrufen der <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=fullName>\-Methode ab.  
  
## Auswirkungen  
 Diese Änderung wirkt sich nur auf Windows Forms\-Apps aus, die für [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] vorgesehen sind.  
  
 Für Windows Forms\-Apps, die auf vorherige Versionen von .NET Framework ausgerichtet sind, lösen solche Implementierungen in einigen Fällen beim Aufrufen der <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName>\-Methode eine <xref:System.IndexOutOfRangeException>\-Ausnahme aus.  
  
## Problemumgehung  
 Ist diese Änderung nicht erwünscht, kann sie für Apps, die für [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] vorgesehen sind, abgelehnt werden. Dazu muss dem [\<runtime\>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)\-Abschnitt der Konfigurationsdatei der App die folgende Konfigurationseinstellung hinzugefügt werden:  
  
```xml  
  
<runtime> <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=true" /> </runtime>  
  
```  
  
 Für Apps, die für frühere Versionen von .NET Framework vorgesehen sind, aber unter [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] ausgeführt werden, kann dieses Verhalten übernommen werden, indem dem [\<runtime\>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)\-Abschnitt der Konfigurationsdatei der Anwendung die folgende Konfigurationseinstellung hinzugefügt wird:  
  
```xml  
  
<runtime> <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=false" /> </runtime>  
  
```  
  
## Siehe auch  
 [Neuausrichtungsänderungen](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)
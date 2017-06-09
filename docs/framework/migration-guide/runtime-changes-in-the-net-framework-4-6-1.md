---
title: "Runtime-&#196;nderungen in .NET Framework 4.6.1 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Änderungen zur Laufzeit, .NET Framework"
  - "Änderungen zur Laufzeit, .NET Framework 4.6.1"
  - "Anwendungskompatibilität"
ms.assetid: 9d97421c-5fee-4523-98c9-a158e7e6a1ee
caps.latest.revision: 5
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 5
---
# Runtime-&#196;nderungen in .NET Framework 4.6.1
In seltenen Fällen können sich Laufzeitänderungen auf vorhandene Apps auswirken, die auf frühere Versionen von .NET Framework abzielen, jedoch in einer älteren .NET Framework-Laufzeit ausgeführt werden. Sie umfassen auch Unterschiede im Verhalten zwischen Anwendungen, die in verschiedenen .NET Framework-Laufzeitumgebungen ausgeführt werden. Die [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] enthält Änderungen in den folgenden Bereichen:  
  
-   [Windows Communication Foundation (WCF)](#WCF)  
  
-   [Windows Presentation Foundation (WPF)](#WPF)  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|WCF-Bindung mit dem `TransportWithMessageCredential` Sicherheitsmodus|Standardmäßig verwendet WCF-Bindung, die `TransportWithMessageCredential` Sicherheitsmodus lässt keine Nachrichten mit Vorzeichen "to"-Header für asymmetrischen Schlüssel. Beginnend mit apps, die Ausführung unter der [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], es ist möglich, diese Anforderung weniger streng gehandhabt und Empfangen von Nachrichten, die "Header to" nicht angemeldet haben,.|Dies ist ein Opt-in-Verhalten (Zustimmungsverhalten). Können Nachrichten mit "Header to" ohne Vorzeichen, fügen die folgende Konfigurationseinstellung, um die [ <> \> ](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) Abschnitt der Konfigurationsdatei der Anwendung:<br /><br /> `<runtime>     <AppContextSwitchOverrides value="Switch.System.ServiceModel.AllowUnsignedToHeader=true" />  </runtime>`<br /><br /> Da diese Einstellung eine Opt-in-Funktion ist, sollte sie sich nicht auf das Verhalten vorhandener Apps auswirken.|Kante|  
  
<a name="WPF"></a>   
## <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|<xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName>|Wenn ein <xref:System.Windows.Controls.ItemsControl> zeigt eine Auflistung mit Virtualisierung (<xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A> = `true`) und Durchführen eines Bildlaufs Element (<xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A>=<xref:System.Windows.Controls.ScrollUnit?displayProperty=fullName>), und wenn das Steuerelement einen zum Anzeigen eines Elements Bildlauf, dessen Höhe in Pixel unterscheidet sich von seiner Nachbarn, die <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> führt eine Iteration durch alle Elemente in der Auflistung.   Die Benutzeroberfläche reagiert während dieser Iteration;  Wenn die Auflistung groß ist, kann dies als ein hängen wahrgenommen werden.<br /><br /> Diese Iteration tritt auf, in anderen Fällen sogar in Versionen vor der [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]. Tritt z. B. beim Durchführen eines Bildlaufs Pixel (<xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A>=<xref:System.Windows.Controls.ScrollUnit?displayProperty=fullName>) ausführt, wenn ein Element mit einer anderen Pixelhöhe und beim Durchführen eines Bildlaufs Element hierarchische Daten (z. B. in einer <xref:System.Windows.Controls.TreeView> Steuerelement oder ein <xref:System.Windows.Controls.ItemsControl> mit Gruppierung aktiviert) ausführt, wenn ein Element mit einer unterschiedlichen Anzahl von untergeordneten Elemente als seine Nachbarn.<br /><br /> Im Fall der Element-Bildlauf und andere Pixel Höhe die Iteration wurde in eingeführt, die [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] zur Behebung von Fehlern in das Layout der hierarchischen Daten.  Es ist nicht erforderlich, wenn die Daten flach ist (weist keine Hierarchie), und die [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] nicht in diesem Fall tun.|Bei die Iteration in der [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] , jedoch nicht in früheren Versionen – d. h. wenn die <xref:System.Windows.Controls.ItemsControl> ist Element Bildlauf eine flache Liste mit Elementen, die von anderen Pixelhöhe – es gibt zwei Abhilfen:<br /><br /> Installieren Sie die [.NET Framework 4.6.2](../../../docs/framework/install/guide-for-developers.md).<br /><br /> Installieren Sie [Hotfix HR 1605](https://support.microsoft.com/en-us/kb/3154529) für die [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].|Nebenversion|  
  
## <a name="see-also"></a>Siehe auch  
 [Anwendungskompatibilität in 4.6.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)
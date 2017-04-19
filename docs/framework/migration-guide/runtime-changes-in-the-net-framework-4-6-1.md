---
title: "Laufzeitänderungen in .NET Framework 4.6.1 | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- runtime changes, .NET Framework
- runtime changes, .NET Framework 4.6.1
- application compatibility
ms.assetid: 9d97421c-5fee-4523-98c9-a158e7e6a1ee
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b8c6ec4d0bad4a769fb4d19a98c9e8a4eda0db78
ms.lasthandoff: 04/18/2017

---
# <a name="runtime-changes-in-the-net-framework-461"></a>Runtime-Änderungen in .NET Framework 4.6.1
In seltenen Fällen können sich Laufzeitänderungen auf vorhandene Apps auswirken, die auf frühere Versionen von .NET Framework abzielen, jedoch in einer älteren .NET Framework-Laufzeit ausgeführt werden. Sie umfassen auch Unterschiede im Verhalten zwischen Anwendungen, die in verschiedenen .NET Framework-Laufzeitumgebungen ausgeführt werden. [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] umfasst Änderungen in folgenden Bereichen:  
  
-   [Windows Communication Foundation (WCF)](#WCF)  
  
-   [Windows Presentation Foundation (WPF)](#WPF)  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|WCF-Bindung mit dem `TransportWithMessageCredential`-Sicherheitsmodus|Standardmäßig sind für eine WCF-Bindung, für die der `TransportWithMessageCredential`-Sicherheitsmodus verwendet wird, keine Nachrichten zulässig, die einen nicht signierten „to“-Header für asymmetrische Sicherheitsschlüssel haben. Beginnend mit Apps, die unter [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] ausgeführt werden, ist es möglich, diese Anforderung aufzuweichen und Nachrichten zu empfangen, die keine signierten „to“-Header haben.|Dies ist ein Opt-in-Verhalten (Zustimmungsverhalten). Wenn Sie Nachrichten mit nicht signiertem „to“-Header zulassen möchten, fügen Sie die folgende Konfigurationseinstellung im [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)-Abschnitt der Konfigurationsdatei der App hinzu:<br /><br /> `<runtime>     <AppContextSwitchOverrides value="Switch.System.ServiceModel.AllowUnsignedToHeader=true" />  </runtime>`<br /><br /> Da diese Einstellung eine Opt-in-Funktion ist, sollte sie sich nicht auf das Verhalten vorhandener Apps auswirken.|Kante|  
  
<a name="WPF"></a>   
## <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|<xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName>|Wenn ein <xref:System.Windows.Controls.ItemsControl> eine Sammlung mithilfe von Virtualisierung (<xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A> = `true`) und Elementscrolling (<xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A>=<xref:System.Windows.Controls.ScrollUnit?displayProperty=fullName>) anzeigt, und wenn das Steuerelement zum Anzeigen eines Elements scrollt, dessen Höhe in Pixel von seinen Nachbarn abweicht, wird <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> über alle Elemente in der Auflistung wiederholt.   Die Benutzeroberfläche reagiert während dieser Iteration nicht. Wenn die Auflistung groß ist, kann dies als Hängen wahrgenommen werden.<br /><br /> Diese Iteration tritt unter anderen Umständen auf, sogar in Versionen vor [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]. Sie tritt z. B. beim Scrollen von Pixeln (<xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A>=<xref:System.Windows.Controls.ScrollUnit?displayProperty=fullName>) auf, nachdem ein Element mit einer anderen Pixelhöhe erkannt wurde sowie beim Elementscrolling für hierarchische Daten (wie beim <xref:System.Windows.Controls.TreeView>-Steuerelement oder einem <xref:System.Windows.Controls.ItemsControl> mit aktivierter Gruppierung), nachdem ein Element mit abweichender Anzahl von Nachfolgerelementen als bei seinen Nachbarn erkannt wurde.<br /><br /> Beim Elementscrolling mit abweichender Pixelhöhe wurde die Iteration in [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] eingeführt, um Fehler im Layout von hierarchischen Daten zu beheben.  Es ist nicht erforderlich, wenn die Daten unstrukturiert sind (keine Hierarchie aufweisen) und [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] es in diesem Fall nicht übernimmt.|Wenn die Iteration in [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], aber nicht in früheren Versionen auftritt – d. h. <xref:System.Windows.Controls.ItemsControl> führt das Elementscrolling einer unstrukturierten Liste von Elementen mit unterschiedlicher Pixelhöhe durch – gibt es zwei Lösungen:<br /><br /> Installieren Sie [.NET Framework 4.6.2](../../../docs/framework/install/guide-for-developers.md).<br /><br /> Installieren Sie [Hotfix HR 1605](https://support.microsoft.com/en-us/kb/3154529) für [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].|Nebenversion|  
## <a name="see-also"></a>Siehe auch  
 [Anwendungskompatibilität in 4.6.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)

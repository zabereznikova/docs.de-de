---
title: Implementierung eines clientseitigen Benutzeroberflächenautomatisierungs-Anbieters
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, client-side provider implementation
- client-side UI Automation provider, implementation
- provider implementation, UI Automation
ms.assetid: 3584c0a1-9cd0-4968-8b63-b06390890ef6
ms.openlocfilehash: e68cf69830aef88f46ff2e288c5aad548db39bdc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224460"
---
# <a name="client-side-ui-automation-provider-implementation"></a>Implementierung eines clientseitigen Benutzeroberflächenautomatisierungs-Anbieters
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: Benutzeroberflächenautomatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Mehrere verschiedene [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] -Frameworks werden innerhalb von [!INCLUDE[TLA#tla_ms](../../../includes/tlasharptla-ms-md.md)] -Betriebssystemen verwendet, darunter [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)], [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)]und [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)]. [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Informationen zu Benutzeroberflächenelementen für Clients verfügbar gemacht. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] selbst unterscheidet jedoch nicht zwischen den unterschiedlichen Steuerelementtypen, die in diesen Frameworks vorhanden sind, und den Techniken, die benötigt werden, um Informationen aus ihnen zu extrahieren. Diese Aufgabe wird Objekten, die als Anbieter bezeichnet werden, überlassen. Ein Anbieter extrahiert Informationen aus einem bestimmen Steuerelement und übergibt diese Informationen an [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], durch die diese dem Client in konsistenter Form präsentiert werden.  
  
 Anbieter können entweder serverseitig oder clientseitig vorhanden sein. Ein serverseitiger Anbieter wird vom Steuerelement selbst implementiert. [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] -Elemente implementieren Anbieter aus, wie Steuerelemente von Drittanbietern mit geschrieben [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Bedenken.  
  
 Ältere Steuerelemente, wie jene in [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] und [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] , unterstützen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]jedoch nicht direkt. Diese Steuerelemente erhalten Informationen stattdessen von Anbietern, die im Clientprozess vorhanden sind und Informationen über Steuerelemente mithilfe von prozessübergreifender Kommunikation erlangen, z. B. durch das Überwachen von Windows-Meldungen von und zu den Steuerelementen. Solche clientseitigen Anbieter werden manchmal als Proxys bezeichnet.  
  
 [!INCLUDE[TLA2#tla_winvista](../../../includes/tla2sharptla-winvista-md.md)] Stellt Anbieter für Standard [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] und Windows Forms-Steuerelemente. Zusätzlich ermöglicht ein Fallbackanbieter teilweise [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Unterstützung für alle Steuerelemente, die ihre Informationen nicht von einem anderen serverseitigen Anbieter oder Proxy erhalten, sondern über eine [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)] -Implementierung verfügen. Diese Anbieter werden automatisch geladen und sind für Clientanwendungen verfügbar.  
  
 Weitere Informationen zur Unterstützung für [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] und Windows Forms-Steuerelementen, finden Sie unter [UI Automation Support for Standard Controls](../../../docs/framework/ui-automation/ui-automation-support-for-standard-controls.md).  
  
 Anwendungen können auch andere clientseitige Anbieter registrieren.  
  
<a name="Distributing_Client-Side_Providers"></a>   
## <a name="distributing-client-side-providers"></a>Verteilen von clientseitigen Anbietern  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] erwartet clientseitige Anbieter in einer Assembly mit verwaltetem Code. Der Namespace in dieser Assembly sollte über den gleichen Namen wie die Assembly verfügen. Eine Assembly mit dem Namen „ContosoProxies.dll“ würde z. B. den ContosoProxies-Namespace enthalten. Erstellen Sie innerhalb des Namespace eine <xref:UIAutomationClientsideProviders.UIAutomationClientSideProviders> -Klasse. Erstellen Sie in der Implementierung des statischen <xref:UIAutomationClientsideProviders.UIAutomationClientSideProviders.ClientSideProviderDescriptionTable> -Felds ein Array von <xref:System.Windows.Automation.ClientSideProviderDescription> -Strukturen, zur Beschreibung der Anbieter.  
  
<a name="Registering_and_Configuring_Client-Side_Providers"></a>   
## <a name="registering-and-configuring-client-side-providers"></a>Registrieren und Konfigurieren von clientseitigen Anbietern  
 Clientseitige Anbieter in einer [!INCLUDE[TLA#tla_dll](../../../includes/tlasharptla-dll-md.md)] werden geladen, indem <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviderAssembly%2A>aufgerufen wird. Von einer Clientanwendung ist zur Nutzung der Anbieter keine weitere Aktion erforderlich.  
  
 Anbieter, die im Code des Clients implementiert sind, werden durch die Verwendung von <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>registriert. Diese Methode verwendet als Argument ein Array von <xref:System.Windows.Automation.ClientSideProviderDescription> -Strukturen, von denen jede die folgenden Eigenschaften angibt:  
  
-   Eine Rückruffunktion, die das Anbieterobjekt erstellt  
  
-   Einen Klassennamen der Steuerelemente, die Informationen vom Anbieter erhalten  
  
-   Einen Imagenamen der Anwendung (normalerweise der vollständige Name der ausführbaren Datei), der Informationen vom Anbieter erhält  
  
-   Flags, die bestimmen, wie der Klassenname mit in der Zielanwendung vorhandenen Fensterklassen verglichen wird  
  
 Die beiden letzten Parameter sind optional. Der Client gibt den Imagenamen der Zielanwendung an, wenn verschiedene Anbieter für verschiedene Anwendungen verwendet werden sollen. Der Client verwendet z. B. in einer bekannten Anwendung, die das Muster für mehrere Ansichten unterstützt, einen Anbieter für ein [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] -Listenansicht-Steuerelement und einen zweiten Anbieter für ein ähnliches Steuerelement in einer anderen bekannten Anwendung, die dieses Muster nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen eines clientseitigen Benutzeroberflächenautomatisierungs-Anbieters](../../../docs/framework/ui-automation/create-a-client-side-ui-automation-provider.md)
- [Implementierung von Benutzeroberflächenautomatisierungs-Anbietern in einer Clientanwendung](../../../docs/framework/ui-automation/implement-ui-automation-providers-in-a-client-application.md)

---
title: Implementierung eines clientseitigen Benutzeroberflächenautomatisierungs-Anbieters
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, client-side provider implementation
- client-side UI Automation provider, implementation
- provider implementation, UI Automation
ms.assetid: 3584c0a1-9cd0-4968-8b63-b06390890ef6
ms.openlocfilehash: 03df282022c39673a7e160dd5d79bdadd0c7adda
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433993"
---
# <a name="client-side-ui-automation-provider-implementation"></a>Implementierung eines clientseitigen Benutzeroberflächenautomatisierungs-Anbieters
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 Several different [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] frameworks are in use within Microsoft operating systems, including [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)], [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)], and [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)]. [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] macht Informationen zu Benutzeroberflächenelementen für Clients verfügbar. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] selbst unterscheidet jedoch nicht zwischen den unterschiedlichen Steuerelementtypen, die in diesen Frameworks vorhanden sind, und den Techniken, die benötigt werden, um Informationen aus ihnen zu extrahieren. Diese Aufgabe wird Objekten, die als Anbieter bezeichnet werden, überlassen. Ein Anbieter extrahiert Informationen aus einem bestimmen Steuerelement und übergibt diese Informationen an [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], durch die diese dem Client in konsistenter Form präsentiert werden.  
  
 Anbieter können entweder serverseitig oder clientseitig vorhanden sein. Ein serverseitiger Anbieter wird vom Steuerelement selbst implementiert. [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] -Elemente implementieren Anbieter. Dies kann auch von Steuerelementen eines Drittanbieters durchgeführt werden, wenn diese unter mit Blick auf [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] geschrieben wurden.  
  
 Ältere Steuerelemente, wie jene in [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] und [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] , unterstützen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]jedoch nicht direkt. Diese Steuerelemente erhalten Informationen stattdessen von Anbietern, die im Clientprozess vorhanden sind und Informationen über Steuerelemente mithilfe von prozessübergreifender Kommunikation erlangen, z. B. durch das Überwachen von Windows-Meldungen von und zu den Steuerelementen. Solche clientseitigen Anbieter werden manchmal als Proxys bezeichnet.  
  
 Windows Vista supplies providers for standard [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] and Windows Forms controls. In addition, a fallback provider gives partial [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] support to any control that is not served by another server-side provider or proxy but has a Microsoft Active Accessibility implementation. Diese Anbieter werden automatisch geladen und sind für Clientanwendungen verfügbar.  
  
 For more information on support for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] and Windows Forms controls, see [UI Automation Support for Standard Controls](ui-automation-support-for-standard-controls.md).  
  
 Anwendungen können auch andere clientseitige Anbieter registrieren.  
  
<a name="Distributing_Client-Side_Providers"></a>   
## <a name="distributing-client-side-providers"></a>Verteilen von clientseitigen Anbietern  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] erwartet clientseitige Anbieter in einer Assembly mit verwaltetem Code. Der Namespace in dieser Assembly sollte über den gleichen Namen wie die Assembly verfügen. Eine Assembly mit dem Namen „ContosoProxies.dll“ würde z. B. den ContosoProxies-Namespace enthalten. Erstellen Sie innerhalb des Namespace eine <xref:UIAutomationClientsideProviders.UIAutomationClientSideProviders> -Klasse. Erstellen Sie in der Implementierung des statischen <xref:UIAutomationClientsideProviders.UIAutomationClientSideProviders.ClientSideProviderDescriptionTable> -Felds ein Array von <xref:System.Windows.Automation.ClientSideProviderDescription> -Strukturen, zur Beschreibung der Anbieter.  
  
<a name="Registering_and_Configuring_Client-Side_Providers"></a>   
## <a name="registering-and-configuring-client-side-providers"></a>Registrieren und Konfigurieren von clientseitigen Anbietern  
 Client-side providers in a dynamic-link library (DLL) are loaded by calling <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviderAssembly%2A>. Von einer Clientanwendung ist zur Nutzung der Anbieter keine weitere Aktion erforderlich.  
  
 Anbieter, die im Code des Clients implementiert sind, werden durch die Verwendung von <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>registriert. Diese Methode verwendet als Argument ein Array von <xref:System.Windows.Automation.ClientSideProviderDescription> -Strukturen, von denen jede die folgenden Eigenschaften angibt:  
  
- Eine Rückruffunktion, die das Anbieterobjekt erstellt  
  
- Einen Klassennamen der Steuerelemente, die Informationen vom Anbieter erhalten  
  
- Einen Imagenamen der Anwendung (normalerweise der vollständige Name der ausführbaren Datei), der Informationen vom Anbieter erhält  
  
- Flags, die bestimmen, wie der Klassenname mit in der Zielanwendung vorhandenen Fensterklassen verglichen wird  
  
 Die beiden letzten Parameter sind optional. Der Client gibt den Imagenamen der Zielanwendung an, wenn verschiedene Anbieter für verschiedene Anwendungen verwendet werden sollen. Der Client verwendet z. B. in einer bekannten Anwendung, die das Muster für mehrere Ansichten unterstützt, einen Anbieter für ein [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] -Listenansicht-Steuerelement und einen zweiten Anbieter für ein ähnliches Steuerelement in einer anderen bekannten Anwendung, die dieses Muster nicht unterstützt.  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen eines clientseitigen Benutzeroberflächenautomatisierungs-Anbieters](create-a-client-side-ui-automation-provider.md)
- [Implementierung von Benutzeroberflächenautomatisierungs-Anbietern in einer Clientanwendung](implement-ui-automation-providers-in-a-client-application.md)

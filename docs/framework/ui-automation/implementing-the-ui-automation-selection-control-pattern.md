---
title: Implementieren des Selection-Steuerelementmusters der Benutzeroberflächenautomatisierung
description: Lesen Sie die Richtlinien und Konventionen für das Implementieren des Auswahl Steuerungs Musters in der Benutzeroberflächen Automatisierung. Siehe erforderliche Member für die ISelectionProvider-Schnittstelle.
ms.date: 03/30/2017
helpviewer_keywords:
- Selection control pattern
- UI Automation, Selection control pattern
- control patterns, Selection
ms.assetid: 449c3068-a5d6-4f66-84c6-1bcc7dd4d209
ms.openlocfilehash: 7ce6b9765dfd15be320f01151ca0b91393508e55
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96237507"
---
# <a name="implementing-the-ui-automation-selection-control-pattern"></a>Implementieren des Selection-Steuerelementmusters der Benutzeroberflächenautomatisierung

> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 Dieses Thema enthält Richtlinien und Konventionen für das Implementieren von <xref:System.Windows.Automation.Provider.ISelectionProvider>, einschließlich Informationen über Ereignisse und Eigenschaften. Links zu zusätzlichen Referenzen sind am Ende dieses Themas aufgelistet.  
  
 Das <xref:System.Windows.Automation.SelectionPattern> -Steuerelementmuster wird zur Unterstützung von Steuerelementen verwendet, die als Container für eine Auflistung von auswählbaren untergeordneten Elementen dienen. Die untergeordneten Elemente dieses Elements müssen <xref:System.Windows.Automation.Provider.ISelectionItemProvider>implementieren. Beispiele für Steuerelemente, die dieses Steuerelementmuster implementieren, finden Sie unter [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a>Implementierungsrichtlinien und -konventionen  

 Beachten Sie beim Implementieren des Selection-Steuerelementmusters die folgenden Richtlinien und Konventionen:  
  
- Steuerelemente, die <xref:System.Windows.Automation.Provider.ISelectionProvider> implementieren, gestatten die Einfach- oder Mehrfachauswahl von untergeordneten Elementen. Listenfelder, Listenansichten und Strukturansichten unterstützen z. B. die Mehrfachauswahl, während Kombinationsfelder, Schieberegler und Optionsfeldgruppen die Einfachauswahl unterstützen.  
  
- Steuerelemente, die über ein Minimum, Maximum und einen zusammenhängenden Bereich verfügen, z. B. **Lautstärke** -Schieberegler, sollten <xref:System.Windows.Automation.Provider.IRangeValueProvider> anstelle von <xref:System.Windows.Automation.Provider.ISelectionProvider>implementieren.  
  
- Steuerelemente mit einfacher Auswahl, die untergeordnete Steuerelemente verwalten, die implementieren <xref:System.Windows.Automation.Provider.IRawElementProviderFragmentRoot> , z. b. der **Bildschirmauflösung** -Schieberegler im Dialogfeld **Anzeigeeigenschaften** oder das **Farb** Auswahl-Auswahl Steuerelement von Microsoft Word (unten dargestellt), sollten implementieren. ihre untergeordneten Elemente <xref:System.Windows.Automation.Provider.ISelectionProvider> sollten sowohl <xref:System.Windows.Automation.Provider.IRawElementProviderFragment> als auch implementieren <xref:System.Windows.Automation.Provider.ISelectionItemProvider> .  
  
 ![Farbauswahl mit ausgewählter Farbe Gelb.](./media/uia-valuepattern-colorpicker.png "UIA_ValuePattern_ColorPicker")  
Beispiel für eine Zuordnung zwischen Farbmustern und Zeichenfolgen  
  
- Menüs unterstützen keine <xref:System.Windows.Automation.SelectionPattern>. Wenn Sie mit Menü Elementen arbeiten, die Grafiken und Text enthalten (z. b. die Elemente im **Vorschau** Bereich im Menü **Ansicht** in Microsoft Outlook) und den Zustand übermitteln müssen, sollten Sie implementieren <xref:System.Windows.Automation.Provider.IToggleProvider> .  
  
<a name="Required_Members_for_ISelectionProvider"></a>

## <a name="required-members-for-iselectionprovider"></a>Erforderliche Member für ISelectionProvider  

 Die folgenden Eigenschaften, Methoden und Ereignisse sind für die <xref:System.Windows.Automation.Provider.ISelectionProvider> -Schnittstelle erforderlich.  
  
|Erforderliche Member|type|Notizen|  
|----------------------|----------|-----------|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.CanSelectMultiple%2A>|Eigenschaft|Sollte durch Eigenschaften geänderte Ereignisse mithilfe von <xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A> und <xref:System.Windows.Automation.Automation.RemoveAutomationPropertyChangedEventHandler%2A>unterstützen.|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.IsSelectionRequired%2A>|Eigenschaft|Sollte durch Eigenschaften geänderte Ereignisse mithilfe von <xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A> und <xref:System.Windows.Automation.Automation.RemoveAutomationPropertyChangedEventHandler%2A>unterstützen.|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.GetSelection%2A>|Methode|Keine|  
|<xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent>|Ereignis|Dieses wird ausgelöst, wenn die Auswahl in einem Container maßgeblich geändert wurde und dies das Senden weiterer Hinzufügen- und Entfernen-Ereignisse erfordert, als die <xref:System.Windows.Automation.Provider.AutomationInteropProvider.InvalidateLimit> -Konstante gestattet.|  
  
 Die Eigenschaften <xref:System.Windows.Automation.Provider.ISelectionProvider.IsSelectionRequired%2A> und <xref:System.Windows.Automation.Provider.ISelectionProvider.CanSelectMultiple%2A> können dynamisch sein. Im anfänglichen Zustand eines Steuerelements sind z. B. möglicherweise standardmäßig keine Elemente ausgewählt, wodurch angezeigt wird, dass <xref:System.Windows.Automation.Provider.ISelectionProvider.IsSelectionRequired%2A>`false`ist. Nach dem Auswählen eines Elements muss für das Steuerelement jedoch immer mindestens ein Element ausgewählt sein. Auf ähnliche Weise kann ein Steuerelement in seltenen Fällen bei der Initialisierung die Mehrfachauswahl von Elementen gestatten, während anschließend nur noch die Einfachauswahl zulässig ist.  
  
<a name="Exceptions"></a>

## <a name="exceptions"></a>Ausnahmen  

 Anbieter müssen die folgenden Ausnahmen auslösen.  
  
|Ausnahmetyp|Bedingung|  
|--------------------|---------------|  
|<xref:System.Windows.Automation.ElementNotEnabledException>|Wenn das Steuerelement nicht aktiviert ist.|  
|<xref:System.InvalidOperationException>|Wenn das Steuerelement ausgeblendet ist.|  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung](ui-automation-control-patterns-overview.md)
- [Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter](support-control-patterns-in-a-ui-automation-provider.md)
- [Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients](ui-automation-control-patterns-for-clients.md)
- [Implementieren des SelectionItem-Steuerelementmusters der Benutzeroberflächenautomatisierung](implementing-the-ui-automation-selectionitem-control-pattern.md)
- [Übersicht über die Benutzeroberflächenautomatisierungs-Struktur](ui-automation-tree-overview.md)
- [Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung](use-caching-in-ui-automation.md)

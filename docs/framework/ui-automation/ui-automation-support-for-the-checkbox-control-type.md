---
title: Benutzeroberflächenautomatisierungs-Unterstützung für den CheckBox-Steuerelementtyp
description: Informationen zur Benutzeroberflächenautomatisierungs-Unterstützung für den CheckBox-Steuerelement Typen. Erlernen Sie die erforderliche Struktur, Eigenschaften und Steuerelement Muster.
ms.date: 03/30/2017
helpviewer_keywords:
- CheckBox control type
- control types, CheckBox
- UI Automation, CheckBox control type
ms.assetid: 9c2a0e70-3a39-4ba9-96ea-a7fe531fae9f
ms.openlocfilehash: 9baf9082a005eb27e0efa4e01345f8bef4ddb6ab
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262800"
---
# <a name="ui-automation-support-for-the-checkbox-control-type"></a>Benutzeroberflächenautomatisierungs-Unterstützung für den CheckBox-Steuerelementtyp

> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 Dieses Thema enthält Informationen über [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Unterstützung für den Steuerelementtyp „CheckBox“. In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]umfasst ein Steuerelementtyp eine Reihe von Bedingungen, die ein Steuerelement erfüllen muss, damit die <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> -Eigenschaft verwendet werden kann. Die Bedingungen schließen bestimmte Richtlinien für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaftswerte und Steuerelementmuster ein.  
  
 Ein Kontrollkästchen ist ein Objekt, mit dem ein Zustand gekennzeichnet wird und das Benutzer dazu verwenden können, diesen Zustand zu durchlaufen. Kontrollkästchen bieten dem Benutzer eine binäre Option [(Ja/Nein) oder (Ein/Aus)] oder eine tertiäre Option (Ein, Aus, Unbestimmt).  
  
 In den folgenden Abschnitten werden die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur, Eigenschaften, Steuerelementmuster und Ereignisse definiert, die für den CheckBox-Steuerelementtyp erforderlich sind. Die- [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Anforderungen gelten für alle Kontrollkästchen-Steuerelemente, ob [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] , Win32 oder Windows Forms.  
  
<a name="Required_UI_Automation_Tree_Structure"></a>

## <a name="required-ui-automation-tree-structure"></a>Erforderliche Benutzeroberflächenautomatisierungs-Struktur  

 In der folgenden Tabelle werden die Steuerelementansicht und die Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur für Kontrollkästchen-Steuerelemente sowie die möglichen Inhalte jeder Ansicht beschrieben. Weitere Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur finden Sie unter [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|Steuerelementansicht|Inhaltsansicht|  
|------------------|------------------|  
|CheckBox|CheckBox|  
  
> [!NOTE]
> Kontrollkästchen haben keine untergeordnete Elemente in der Steuerelement- oder Inhaltsansicht. Wenn das Steuerelement untergeordnete Elemente enthalten muss, bedeutet dies, dass ein anderer Steuerelementtyp verwendet werden muss.  
  
### <a name="required-ui-automation-properties"></a>Erforderliche Benutzeroberflächenautomatisierungs-Eigenschaften  

 In der folgenden Tabelle werden die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaften aufgelistet, deren Werte oder Definitionen für Kontrollkästchen-Steuerelemente besonders relevant sind. Weitere Informationen zu Eigenschaften [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -finden Sie unter [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaft|Wert|Notizen|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Siehe Hinweise.|Der Wert dieser Eigenschaft muss für alle Steuerelemente in einer Anwendung eindeutig sein.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Siehe Hinweise.|Das äußere Rechteck, das das gesamte Steuerelement enthält.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Siehe Hinweise.|Unterstützt, wenn es ein umschließendes Rechteck gibt. Wenn nicht auf jeden Punkt innerhalb des umschließenden Rechtecks geklickt werden kann, und Sie spezielle Treffertests ausführen, setzen Sie die Eigenschaft außer Kraft, und stellen Sie dann einen klickbaren Punkt bereit.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|CheckBox|Dieser Wert ist für alle Benutzeroberflächen-Frameworks gleich.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|Diese Eigenschaft muss immer den Wert „True“ haben. Dies bedeutet, dass das Kontrollkästchen-Steuerelement immer in der Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Struktur enthalten sein muss.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|Diese Eigenschaft muss immer den Wert „True“ haben. Dies bedeutet, dass das Kontrollkästchen-Steuerelement immer in der Steuerelementansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Struktur enthalten sein muss.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Siehe Hinweise.|Wenn das Steuerelement den Tastaturfokus erhalten kann, muss es diese Eigenschaft unterstützen.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`Null`|Kontrollkästchen sind selbstbeschriftende Steuerelemente.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|„Kontrollkästchen“|Lokalisierte Zeichenfolge für den Steuerelementtyp „CheckBox“.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Siehe Hinweise.|Der Wert der `Name` -Eigenschaft des Kontrollkästchen-Steuerelements ist der Text, der neben dem Feld angezeigt wird, das den Umschaltzustand kennzeichnet.|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>

## <a name="required-ui-automation-control-patterns"></a>Erforderliche Benutzeroberflächenautomatisierungs-Steuerelementmuster  

 Die folgende Tabelle enthält die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Steuerelementmuster, die von allen Kontrollkästchen-Steuerelementen unterstützt werden müssen. Weitere Informationen zu Steuerelementmustern finden Sie unter [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
|Steuerelementmuster|Support|Notizen|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IToggleProvider>|Erforderlich|Ermöglicht, dass der interne Zustand des Kontrollkästchens programmgesteuert durchlaufen werden kann.|  
  
<a name="Required_UI_Automation_Events"></a>

## <a name="required-ui-automation-events"></a>Erforderliche Benutzeroberflächenautomatisierungs-Ereignisse  

 In der folgenden Tabelle sind die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignisse aufgeführt, die von allen Kontrollkästchen-Steuerelementen unterstützt werden müssen. Weitere Informationen zu Ereignissen finden Sie unter [UI Automation Events Overview](ui-automation-events-overview.md).  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignis|Support|Notizen|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Erforderlich|Keine|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keine|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keine|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keine|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Erforderlich|Keine|  
|Durch geänderte<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keine|  
  
<a name="Default_Action"></a>

## <a name="default-action"></a>Standardaktion  

 Die Standardaktion für ein Kontrollkästchen besteht darin, einem Optionsfeld den Fokus zu geben und dessen aktuellen Status umzuschalten. Wie bereits erwähnt, bieten Kontrollkästchen dem Benutzer eine binäre [(Ja/Nein) oder (Ein/Aus)] oder eine tertiäre Entscheidung (Ein, Aus, Unbestimmt). Ist das Kontrollkästchen binär, bewirkt die Standardaktion, dass aus dem Zustand „Ein“ in den Zustand „Aus“ oder aus dem Zustand „Aus“ in den Zustand „Ein“ geschaltet wird. In einem tertiären Kontrollkästchen bewirkt die Standardaktion, dass der Zustand des Kontrollkästchens so durchlaufen wird, als hätte der Benutzer aufeinanderfolgende Mausklicks an das Steuerelement gesendet.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Automation.ControlType.CheckBox>
- [Übersicht über Steuerelementtypen für Benutzeroberflächenautomatisierung](ui-automation-control-types-overview.md)
- [Übersicht über die Benutzeroberflächenautomatisierung](ui-automation-overview.md)

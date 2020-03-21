---
title: Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns
- UI Automation, control patterns
ms.assetid: cc229b33-234b-469b-ad60-f0254f32d45d
ms.openlocfilehash: f62631a15dd348b6f6ea27a82d7b45aab92ceed2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179947"
---
# <a name="ui-automation-control-patterns-overview"></a>Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 In dieser Übersicht werden [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Steuerelementmuster vorgestellt. Steuerelementmuster bieten eine Möglichkeit zum Kategorisieren und Verfügbarmachen der Funktionalität eines Steuerelements, unabhängig vom Typ des Steuerelements oder vom Erscheinungsbild des Steuerelements.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] verwendet Steuerelementmuster, um allgemeine Verhaltensweisen von Steuerelementen abzubilden. Beispielsweise verwenden Sie das Aufruf-Steuerelementmuster für Steuerelemente, die aufgerufen werden können (etwa Schaltflächen), und das Scroll-Steuerelementmuster für Steuerelemente, die Scrollleisten haben (z. B. Listenfelder, Listenansichten oder Kombinationsfelder). Da mit jedem Steuerelementmuster eine separate Funktionalität abgebildet wird, können diese kombiniert werden, um den gesamten Funktionsumfang zu beschreiben, der von einem bestimmten Steuerelement unterstützt wird.  
  
> [!NOTE]
> Zusammengesetzte Steuerelemente – Steuerelemente, die mit untergeordneten Steuerelementen erstellt wurden, die die [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] für Funktionalität bereitstellen, die vom übergeordneten Steuerelement verfügbar gemacht wird – sollten alle Steuerelementmuster implementieren, die normalerweise den untergeordneten Steuerelementen zugewiesen sind. Dagegen ist es nicht erforderlich, dass diese selben Steuerelementmuster durch die untergeordneten Steuerelemente implementiert werden.  
  
<a name="uiautomation_control_pattern_includes"></a>
## <a name="ui-automation-control-pattern-components"></a>Komponenten der Steuerelementmuster für Benutzeroberflächenautomatisierung  
 Steuerelementmuster unterstützen die Methoden, Eigenschaften, Ereignisse und Beziehungen, die dazu erforderlich sind, eine bestimmte Funktionalität zu definieren, die in einem Steuerelement verfügbar ist.  
  
- Die Beziehungen zwischen einem Benutzeroberflächenautomatisierungs-Element und dessen übergeordnetem Element sowie dessen unter- und gleichgeordneten Elementen beschreibt die Struktur des Elements innerhalb der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur.  
  
- Die Methoden ermöglichen es Benutzeroberflächenautomatisierungs-Clients, das Steuerelement zu bearbeiten.  
  
- Die Eigenschaften und Ereignisse stellen Informationen zur Funktionalität des Steuerelementmusters sowie zum Status des Steuerelements zur Verfügung.  
  
 Steuerelementmuster beziehen [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] sich auf Schnittstellen, die sich auf COM-Objekte (Component Object Model) beziehen. In COM können Sie von einem Objekt abfragen, welche Schnittstellen es unterstützt, und dann mithilfe dieser Schnittstellen auf die Funktionen zugreifen. In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]kann ein Benutzeroberflächenautomatisierungs-Client ein Steuerelement daraufhin abfragen, welche Steuerelementmuster es unterstützt, und anschließend über die Eigenschaften, Methoden, Ereignisse und Strukturen, die von den unterstützten Steuerelementmustern verfügbar gemacht werden, auf das Steuerelement zugreifen. Beispielsweise implementiert ein Benutzeroberflächenautomatisierungs-Anbieter für ein mehrzeiliges Bearbeitungsfeld eine <xref:System.Windows.Automation.Provider.IScrollProvider>-Schnittstelle. Wenn ein Client weiß, dass ein <xref:System.Windows.Automation.AutomationElement> das <xref:System.Windows.Automation.ScrollPattern> -Steuerelementmuster unterstützt, kann er die Eigenschaften, Methoden und Ereignisse, die von diesem Steuerelementmuster verfügbar gemacht werden, dazu verwenden, auf das Steuerelement oder auf Informationen über das Steuerelement zuzugreifen.  
  
<a name="uiautomation_control_pattern_client_provider"></a>
## <a name="ui-automation-providers-and-clients"></a>Benutzeroberflächenautomatisierungs-Anbieter und -Clients  
 Benutzeroberflächenautomatisierungs-Anbieter implementieren Steuerelementmuster, um das entsprechende Verhalten für eine bestimmte Funktionalität verfügbar zu machen, die vom Steuerelement unterstützt wird.  
  
 Benutzeroberflächenautomatisierungs-Clients verwenden Methoden und Eigenschaften von [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Steuerelement-Musterklassen, um Informationen über die [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]abzurufen oder Änderungen an der [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]vorzunehmen. Diese Steuerelement-Musterklassen befinden sich im <xref:System.Windows.Automation> -Namespace (z. B. <xref:System.Windows.Automation.InvokePattern> und <xref:System.Windows.Automation.SelectionPattern>).  
  
 Clients <xref:System.Windows.Automation.AutomationElement> verwenden Methoden <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A?displayProperty=nameWithType> (z. B. oder <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A?displayProperty=nameWithType>) oder die CLR-Accessoren (Common Language Runtime), um auf die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Eigenschaften eines Musters zuzugreifen. Jede Steuerelementmusterklasse verfügt über ein <xref:System.Windows.Automation.InvokePattern.Pattern?displayProperty=nameWithType> Feldelement (z. B. <xref:System.Windows.Automation.SelectionPattern.Pattern?displayProperty=nameWithType>oder ), das <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A> <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> dieses Steuerelementmuster identifiziert <xref:System.Windows.Automation.AutomationElement>und als Parameter an eine übergeben oder abgerufen werden kann.  
  
<a name="uiautomation_control_patterns_dynamic"></a>
## <a name="dynamic-control-patterns"></a>Dynamische Steuerelementmuster  
 Einige Steuerelemente unterstützen nicht immer denselben Satz von Steuerelementmustern. Steuerelementmuster gelten als unterstützt, wenn sie für einen Benutzeroberflächenautomatisierungs-Client verfügbar sind. Beispielsweise ermöglicht ein mehrzeiliges Bearbeitungsfeld nur dann vertikales Scrollen, wenn es mehr Textzeilen enthält, als in seinem Anzeigebereich angezeigt werden können. Scrollen wird deaktiviert, wenn so viel Text entfernt wurde, dass kein Scrollen mehr erforderlich ist. In diesem Beispiel wird das ScrollPattern-Steuerelementmuster dynamisch je nach aktuellem Zustand des Steuerelements unterstützt (wie viel Text befindet sich im Bearbeitungsfeld).  
  
<a name="Control_Pattern_Classes_and_Interfaces"></a>
## <a name="control-pattern-classes-and-interfaces"></a>Steuerelement-Musterklassen und -Schnittstellen  
 In der folgenden Tabelle werden die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Steuerelementmuster beschrieben. Außerdem werden in dieser Tabelle folgende Elemente aufgeführt: die Klassen, die von Benutzeroberflächenautomatisierungs-Clients für den Zugriff auf die Steuerelementmuster verwendet werden, und die Schnittstellen, die von Benutzeroberflächenautomatisierungs-Anbietern zum Implementieren der Steuerelementmuster verwendet werden.  
  
|Steuerelementmusterklasse|Anbieterschnittstelle|Beschreibung|  
|---------------------------|------------------------|-----------------|  
|<xref:System.Windows.Automation.DockPattern>|<xref:System.Windows.Automation.Provider.IDockProvider>|Wird für Steuerelemente verwendet, die in einem Dockingcontainer angedockt werden können. Beispielsweise Symbolleisten oder Toolpaletten.|  
|<xref:System.Windows.Automation.ExpandCollapsePattern>|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider>|Wird für Steuerelemente verwendet, die erweitert oder reduziert werden können. Beispielsweise Menüelemente in einer Anwendung, etwa das Menü **Datei** .|  
|<xref:System.Windows.Automation.GridPattern>|<xref:System.Windows.Automation.Provider.IGridProvider>|Wird für Steuerelemente verwendet, die Rasterfunktionen wie z. B. Größenanpassung und Verschieben in eine bestimmte Zelle unterstützen. Beispielsweise die große Symbolansicht im Windows Explorer oder einfache Tabellen ohne Kopfzeilen in Microsoft Word.|  
|<xref:System.Windows.Automation.GridItemPattern>|<xref:System.Windows.Automation.Provider.IGridItemProvider>|Wird für Steuerelemente verwendet, die Zellen innerhalb von Rastern haben. Die einzelnen Zellen müssen das GridItem-Muster unterstützen. Beispielsweise jede Zelle in der Detailansicht von Microsoft Windows Explorer.|  
|<xref:System.Windows.Automation.InvokePattern>|<xref:System.Windows.Automation.Provider.IInvokeProvider>|Wird für Steuerelemente verwendet, die aufgerufen werden können, etwa Schaltflächen.|  
|<xref:System.Windows.Automation.MultipleViewPattern>|<xref:System.Windows.Automation.Provider.IMultipleViewProvider>|Wird für Steuerelemente verwendet, die zwischen mehreren Darstellungen derselben Informationen, Daten oder untergeordneten Elemente wechseln können. Beispielsweise ein Listenansicht-Steuerelement, in dem Daten in einer Miniatur-, Kachel-, Symbol-, Listen- oder Detailansicht verfügbar sind.|  
|<xref:System.Windows.Automation.RangeValuePattern>|<xref:System.Windows.Automation.Provider.IRangeValueProvider>|Wird für Steuerelemente verwendet, die einen Bereich von Werten haben, die auf das Steuerelement angewendet werden können. Beispielsweise kann ein Drehfeld-Steuerelement, das Jahreswerte enthält, einen Bereich von 1900 bis 2010 haben, während ein anderes Drehfeld-Steuerelement, in dem Monate angezeigt werden, den Bereich von 1 bis 12 hat.|  
|<xref:System.Windows.Automation.ScrollPattern>|<xref:System.Windows.Automation.Provider.IScrollProvider>|Wird für Steuerelemente verwendet, in denen gescrollt werden kann. Beispielsweise ein Steuerelement, das Scrollleisten hat, die nur aktiv sind, wenn mehr Informationen vorhanden sind, als im Anzeigebereich des Steuerelements angezeigt werden können.|  
|<xref:System.Windows.Automation.ScrollItemPattern>|<xref:System.Windows.Automation.Provider.IScrollItemProvider>|Wird für Steuerelemente verwendet, die einzelne Elemente in einer Liste haben, die gescrollt werden kann. Beispielsweise ein Listensteuerelement, das einzelne Elementen in der Scrollliste hat, etwa ein Kombinationsfeld-Steuerelement.|  
|<xref:System.Windows.Automation.SelectionPattern>|<xref:System.Windows.Automation.Provider.ISelectionProvider>|Wird für Auswahlcontainer-Steuerelemente verwendet. Beispielsweise Listen- und Kombinationsfelder.|  
|<xref:System.Windows.Automation.SelectionItemPattern>|<xref:System.Windows.Automation.Provider.ISelectionItemProvider>|Wird für einzelne Elemente in Auswahlcontainer-Steuerelementen verwendet, z. B. Listen- und Kombinationsfelder.|  
|<xref:System.Windows.Automation.TablePattern>|<xref:System.Windows.Automation.Provider.ITableProvider>|Wird für Steuerelemente verwendet, die sowohl ein Raster als auch Überschrifteninformationen haben. Beispiel: Microsoft Excel-Arbeitsblätter.|  
|<xref:System.Windows.Automation.TableItemPattern>|<xref:System.Windows.Automation.Provider.ITableItemProvider>|Wird für Elemente in einer Tabelle verwendet.|  
|<xref:System.Windows.Automation.TextPattern>|<xref:System.Windows.Automation.Provider.ITextProvider>|Wird für Bearbeitungssteuerelemente und Dokumente verwendet, die Textinformationen verfügbar machen.|  
|<xref:System.Windows.Automation.TogglePattern>|<xref:System.Windows.Automation.Provider.IToggleProvider>|Wird für Steuerelemente verwendet, deren Zustand umgeschaltet werden kann. Beispielsweise Kontrollkästchen und aktivierbare Menüeinträge.|  
|<xref:System.Windows.Automation.TransformPattern>|<xref:System.Windows.Automation.Provider.ITransformProvider>|Wird für Steuerelemente verwendet, die in der Größe geändert, verschoben und gedreht werden können. Typische Einsatzfälle für das Transform-Steuerelementmuster sind Designer, Formulare, Grafik-Editoren und Zeichnungsanwendung.|  
|<xref:System.Windows.Automation.ValuePattern>|<xref:System.Windows.Automation.Provider.IValueProvider>|Ermöglicht Clients das Abrufen oder Festlegen eines Werts für ein Steuerelement, das keinen Wertebereich unterstützt. Beispielsweise eine Datums-/Zeitauswahl.|  
|<xref:System.Windows.Automation.WindowPattern>|<xref:System.Windows.Automation.Provider.IWindowProvider>|Macht für bestimmte Fenster spezifische Informationen verfügbar. Hierbei handelt es sich um ein grundlegendes Konzept des Microsoft Windows-Betriebssystems. Beispiele für Steuerelemente, bei denen es sich um untergeordnete Fenster der obersten Ebene handelt (Microsoft Word, Microsoft Windows Explorer usw.), untergeordnete Fenster für die Mehrdokumentschnittstelle (MDI) und Dialogfelder.|  
  
## <a name="see-also"></a>Weitere Informationen

- [Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients](ui-automation-control-patterns-for-clients.md)
- [Zuordnen von Steuerelementmustern für Benutzeroberflächenautomatisierungs-Clients](control-pattern-mapping-for-ui-automation-clients.md)
- [Übersicht über die Benutzeroberflächenautomatisierung](ui-automation-overview.md)
- [Benutzeroberflächenautomatisierungs-Eigenschaften für Clients](ui-automation-properties-for-clients.md)
- [Benutzeroberflächenautomatisierungs-Ereignisse für Clients](ui-automation-events-for-clients.md)

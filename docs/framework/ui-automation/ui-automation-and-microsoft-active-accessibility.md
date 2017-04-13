---
title: "UI Automation and Microsoft Active Accessibility | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Active Accessibility"
  - "UI Automation, Active Accessibility compared to"
  - "UI Automation, Microsoft Active Accessibility"
  - "Active Accessibility, UI Automation compared to"
ms.assetid: 87bee662-0a3e-4232-a421-20e7a5968321
caps.latest.revision: 24
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 23
---
# UI Automation and Microsoft Active Accessibility
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework\-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Klassen verwenden möchten, die im <xref:System.Windows.Automation>\-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] finden Sie auf der Seite zur [Windows\-Automatisierungs\-API: UI\-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)] war die vorherige Lösung zum Ermöglichen des Zugriffs auf Clientanwendungen.[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] ist das neue Zugriffsmodell für [!INCLUDE[TLA#tla_win](../../../includes/tlasharptla-win-md.md)] und richtet sich an die Bedürfnisse von Hilfstechnologieprodukten und automatisierte Testtools.[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] bietet gegenüber [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] viele Verbesserungen.  
  
 In diesem Thema werden die wesentlichen Features von [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] sowie die Unterschiede dieser Features zu [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] erläutert.  
  
<a name="Programming_Languages_compare"></a>   
## Programmiersprachen  
 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] basiert auf der [!INCLUDE[TLA#tla_com](../../../includes/tlasharptla-com-md.md)] mit Unterstützung für duale Schnittstellen und kann daher in C\/C\+\+, [!INCLUDE[TLA#tla_vb6](../../../includes/tlasharptla-vb6-md.md)] und Skriptsprachen programmiert werden.[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] \(einschließlich der clientseitigen Anbieterbibliothek für Standardsteuerelemente\) wurde in verwaltetem Code geschrieben und Benutzeroberflächenautomatisierungs\-Clientanwendungen werden am einfachsten mit [!INCLUDE[TLA#tla_vcshrp](../../../includes/tlasharptla-vcshrp-md.md)] oder [!INCLUDE[TLA#tla_visualbnet](../../../includes/tlasharptla-visualbnet-md.md)] programmiert. Benutzeroberflächenautomatisierungs\-Anbieter, die Schnittstellenimplementierungen darstellen, können in verwaltetem Code oder in C\/C\+\+ geschrieben werden.  
  
<a name="Support_in_Windows_Presentation_Foundation_"></a>   
## Unterstützung in der Windows Presentation Foundation  
 [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)] ist das neue Modell zum Erstellen von Benutzeroberflächen.[!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]\-Elemente bieten keine systemeigene Unterstützung für [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]. Sie unterstützen jedoch die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], die die überbrückende Unterstützung für [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]\-Clients umfasst. Nur speziell für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] geschriebene Clients können die Barrierefreiheitsfeatures von [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] optimal nutzen, z. B. die umfangreiche Unterstützung für Text.  
  
<a name="Servers_and_Clients_compare"></a>   
## Server und Clients  
 In [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] können Server und Clients direkt miteinander kommunizieren, hauptsächlich durch die Implementierung des Servers von `IAccessible`.  
  
 In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] liegt ein Kerndienst zwischen Server \(auch als Anbieter bezeichnet\) und Client. Der Kerndienst führt Aufrufe an die von Anbietern implementierten Schnittstellen aus und bietet zusätzliche Dienste, z. B. das Generieren eindeutiger Laufzeitbezeichner für Elemente. Clientanwendungen verwenden Bibliotheksfunktionen zum Aufrufen des [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Diensts.  
  
 Benutzeroberflächenautomatisierungs\-Anbieter können Informationen zu [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]\-Clients bereitstellen, während [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]\-Server Informationen zu Clientanwendungen für die Automatisierung der Benutzeroberfläche bereitstellen können. Da [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] jedoch nicht so viele Informationen wie [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] bereitstellt, sind die beiden Modelle nicht vollständig kompatibel.  
  
<a name="UI_Elements_compare"></a>   
## Benutzeroberflächenelemente  
 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] stellt [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]\-Elemente entweder als `IAccessible`\-Schnittstelle oder als untergeordneten Bezeichner dar. Es ist schwierig, zwei `IAccessible`\-Zeiger zu vergleichen, um festzustellen, ob sie auf dasselbe Element verweisen.  
  
 In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] wird jedes Element als <xref:System.Windows.Automation.AutomationElement>\-Objekt dargestellt. Der Vergleich erfolgt mithilfe des Gleichheitsoperators oder der <xref:System.Windows.Automation.AutomationElement.Equals%2A>\-Methode, die beide die eindeutigen Laufzeitbezeichner der Elemente vergleichen.  
  
<a name="Tree_Views_and_Navigation_compare"></a>   
## Strukturansichten und Navigation  
 Die [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)]\-Elemente auf dem Bildschirm können als Baumstruktur betrachtet werden, wobei der Desktop den Stamm, die Anwendungsfenster direkt untergeordnete Elemente und Elemente in Anwendungen weitere Nachfolger darstellen.  
  
 In [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] werden viele Automatisierungselemente, die für Endbenutzer nicht relevant sind, in der Struktur verfügbar gemacht. Clientanwendungen müssen alle Elemente betrachten, um die erforderlichen Elemente zu ermitteln.  
  
 Benutzeroberflächenautomatisierungs\-Clientanwendungen betrachten die [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] über eine gefilterte Ansicht. Die Ansicht enthält nur relevante Elemente: Elemente, die dem Benutzer Informationen bieten oder die Interaktion ermöglichen. Es sind vordefinierte Ansichten verfügbar, die nur Steuerelemente und nur Inhaltselemente enthalten. Zusätzlich können Anwendungen benutzerdefinierte Ansichten definieren.[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] vereinfacht die Beschreibung der [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] für den Benutzer und unterstützt die Benutzer bei der Interaktion mit der Anwendung.  
  
 Die Navigation zwischen Elementen in [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] erfolgt entweder räumlich \(z. B. beim Wechsel zum Element, das auf der linken Seite des Bildschirms liegt\), logisch \(z. B. beim Wechsel zum nächsten Menüelement oder zum nächsten Element in der Aktivierreihenfolge eines Dialogfelds\) oder hierarchisch \(z. B. beim Wechsel zum ersten untergeordneten Element in einem Container oder vom untergeordneten zum übergeordneten Element\). Die hierarchische Navigation erweist sich durch die Tatsache als kompliziert, dass untergeordnete Elemente nicht immer Objekte sind, die `IAccessible` implementieren.  
  
 In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] sind alle [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]\-Elemente <xref:System.Windows.Automation.AutomationElement>\-Objekte, die dieselbe grundlegende Funktionalität unterstützen. \(Aus Sicht des Anbieters sind sie Objekte, die eine von <xref:System.Windows.Automation.Provider.IRawElementProviderSimple> geerbte Schnittstelle implementieren.\) Die Navigation erfolgt überwiegend hierarchisch: von übergeordneten zu untergeordneten Elementen sowie von einem gleichgeordneten Element zum nächsten. \(Die Navigation zwischen gleichgeordneten Elementen weist ein logisches Element auf, da sie möglicherweise der Aktivierreihenfolge folgt.\) Sie können mithilfe der <xref:System.Windows.Automation.TreeWalker>\-Klasse von einem beliebigen Startpunkt aus über eine beliebige gefilterte Ansicht der Struktur navigieren. Sie können auch mithilfe der <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> und <xref:System.Windows.Automation.AutomationElement.FindAll%2A> zu bestimmten untergeordneten Elementen oder Nachfolgerelementen navigieren. Es ist z. B. ganz einfach, alle Elemente in einem Dialogfeld abzurufen, die ein bestimmtes Steuerelementmuster unterstützen.  
  
 Die Navigation in der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ist konsistenter als bei der [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]. Einige Elemente wie Dropdownlisten und Popupfenster werden in der [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]\-Struktur zweimal angezeigt und die Navigation von diesen Elementen kann möglicherweise zu unerwarteten Ergebnissen führen. Es ist eigentlich nicht möglich, [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] für ein Grundleistensteuerelement ordnungsgemäß zu implementieren.[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ermöglicht die erneute Zuordnung zu übergeordneten Elementen und die Neupositionierung, sodass ein Element ungeachtet der Hierarchie, die sich durch den Besitz von Fenstern ergibt, an eine beliebige Stelle in der Struktur platziert werden kann.  
  
<a name="Roles_and_Control_Types"></a>   
## Rollen und Steuerelementtypen  
 [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] verwendet die `accRole`\-Eigenschaft \(`IAccessible::get_actRole`\) zum Abrufen einer Beschreibung der Rolle des Elements in der [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], z. B. ROLE\_SYSTEM\_SLIDER oder ROLE\_SYSTEM\_MENUITEM. Die Rolle eines Elements ist der wichtigste Anhaltspunkt für seine verfügbaren Funktionen. Die Interaktion mit einem Steuerelement wird mithilfe fester Methoden wie `IAccessible::accSelect` und `IAccessible::accDoDefaultAction` erreicht. Die Interaktion zwischen der Clientanwendung und der [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] ist durch die Möglichkeiten von `IAccessible` beschränkt.  
  
 Im Gegensatz dazu entkoppelt [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] den Steuerelementtyp des Elements \(durch die <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A>\-Eigenschaft beschrieben\) größtenteils von dessen zu erwartender Funktionalität. Die Funktionalität wird durch die Steuerelementmuster bestimmt, die vom Anbieter durch Implementieren spezieller Schnittstellen unterstützt werden. Steuerelementmuster können kombiniert werden, um sämtliche Funktionen zu beschreiben, die von einem bestimmten [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]\-Element unterstützt werden. Einige Anbieter müssen ein bestimmtes Steuerelementmuster unterstützen. Der Anbieter für ein Kontrollkästchen muss z. B. ein Toggle\-Steuerelementmuster unterstützen. Andere Anbieter müssen mindestens einen Satz von Steuerelementmustern unterstützen. Eine Schaltfläche muss z. B. entweder „Toggle“ oder „Invoke“ unterstützen. Wieder andere Anbieter unterstützen überhaupt keine Steuerelementmuster. Ein Bereich, der z. B. nicht vergrößert, verkleinert, verschoben oder angedockt werden kann, besitzt keine Steuerelementmuster.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] unterstützt benutzerdefinierte Steuerelemente, die durch die <xref:System.Windows.Automation.ControlType.Custom>\-Eigenschaft gekennzeichnet sind und von der <xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty>\-Eigenschaft beschrieben werden können.  
  
 Die folgende Tabelle veranschaulicht die Zuordnung von [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]\-Rollen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Steuerelementtypen.  
  
|[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]\-Rolle|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Steuerelementtyp|  
|------------------------------------------------------------------------|---------------------------------------------------------------------------------------------|  
|ROLE\_SYSTEM\_PUSHBUTTON|Schaltfläche|  
|ROLE\_SYSTEM\_CLIENT|Kalender|  
|ROLE\_SYSTEM\_CHECKBUTTON|Kontrollkästchen|  
|ROLE\_SYSTEM\_COMBOBOX|Kombinationsfeld|  
|ROLE\_SYSTEM\_CLIENT|Benutzerdefiniert|  
|ROLE\_SYSTEM\_LIST|Datenraster|  
|ROLE\_SYSTEM\_LISTITEM|Datenelement|  
|ROLE\_SYSTEM\_DOCUMENT|Dokument|  
|ROLE\_SYSTEM\_TEXT|Bearbeiten|  
|ROLE\_SYSTEM\_GROUPING|Gruppieren|  
|ROLE\_SYSTEM\_LIST|Header|  
|ROLE\_SYSTEM\_COLUMNHEADER|Headerelement|  
|ROLE\_SYSTEM\_LINK|Link|  
|ROLE\_SYSTEM\_GRAPHIC|Bild|  
|ROLE\_SYSTEM\_LIST|Liste|  
|ROLE\_SYSTEM\_LISTITEM|Listenelement|  
|ROLE\_SYSTEM\_MENUPOPUP|Menü|  
|ROLE\_SYSTEM\_MENUBAR|Menüleiste|  
|ROLE\_SYSTEM\_MENUITEM|Menüelement|  
|ROLE\_SYSTEM\_PANE|Bereich|  
|ROLE\_SYSTEM\_PROGRESSBAR|Statusanzeige|  
|ROLE\_SYSTEM\_RADIOBUTTON|Optionsfeld|  
|ROLE\_SYSTEM\_SCROLLBAR|Bildlaufleiste|  
|ROLE\_SYSTEM\_SEPARATOR|Trennzeichen|  
|ROLE\_SYSTEM\_SLIDER|Slider|  
|ROLE\_SYSTEM\_SPINBUTTON|Spinner|  
|ROLE\_SYSTEM\_SPLITBUTTON|Trennschaltfläche|  
|ROLE\_SYSTEM\_STATUSBAR|Statusleiste|  
|ROLE\_SYSTEM\_PAGETABLIST|Registerkarte|  
|ROLE\_SYSTEM\_PAGETAB|Registerkartenelement|  
|ROLE\_SYSTEM\_TABLE|Tabelle|  
|ROLE\_SYSTEM\_STATICTEXT|Text|  
|ROLE\_SYSTEM\_INDICATOR|Ziehpunkt|  
|ROLE\_SYSTEM\_TITLEBAR|Titelleiste|  
|ROLE\_SYSTEM\_TOOLBAR|Symbolleiste|  
|ROLE\_SYSTEM\_TOOLTIP|QuickInfo|  
|ROLE\_SYSTEM\_OUTLINE|Struktur|  
|ROLE\_SYSTEM\_OUTLINEITEM|Strukturelement|  
|ROLE\_SYSTEM\_WINDOW|Fenster|  
  
 Weitere Informationen zu den verschiedenen Steuerelementtypen finden Sie unter [UI Automation Control Types](../../../docs/framework/ui-automation/ui-automation-control-types.md).  
  
<a name="States_and_Properties"></a>   
## Zustände und Eigenschaften  
 In [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] unterstützen Elemente einen gemeinsamen Satz von Eigenschaften und einige dieser Eigenschaften \(z. B. `accState`\) müssen in Abhängigkeit von der Rolle des Elements sehr unterschiedliche Dinge beschreiben. Server müssen alle Methoden von `IAccessible` implementieren, die eine Eigenschaft zurückgeben, auch solche Methoden, die für das Element nicht relevant sind.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definiert viele weitere Eigenschaften, von denen einige den Zuständen in [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] entsprechen. Manche beziehen sich auf alle Elemente, während andere nur für Steuerelementtypen und Steuerelementmuster gelten. Eigenschaften werden durch eindeutige Bezeichner unterschieden, und die meisten Eigenschaften können über eine einzelne Methode, <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> oder <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, abgerufen werden. Viele Eigenschaften können auch leicht über die <xref:System.Windows.Automation.AutomationElement.Current%2A>\- und <xref:System.Windows.Automation.AutomationElement.Cached%2A>\- Eigenschaftenaccessoren abgerufen werden.  
  
 Ein Benutzeroberflächenautomatisierungs\-Anbieter muss keine irrelevanten Eigenschaften implementieren, sondern kann einfach einen `null`\-Wert für alle nicht unterstützten Eigenschaften zurückgeben. Darüber hinaus kann der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Kerndienst einige Eigenschaften aus dem Standardfenster abrufen. Diese werden dann mit Eigenschaften vereinigt, die vom Anbieter explizit implementiert wurden.  
  
 Zusätzlich zur Unterstützung vieler weiterer Eigenschaften bietet [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] bessere Leistungen, indem es ermöglicht wird, mehrere Eigenschaften mit einem einzigen prozessübergreifenden Aufruf abzurufen.  
  
 Die folgende Tabelle zeigt die Übereinstimmung zwischen Eigenschaften der beiden Modelle.  
  
|[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]\-Eigenschaftenaccessor|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Eigenschaften\-ID|Hinweise|  
|----------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------|--------------|  
|`get_accKeyboardShortcut`|<xref:System.Windows.Automation.AutomationElement.AccessKeyProperty> oder <xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty>|`AccessKeyProperty` hat Vorrang, wenn beide vorhanden sind.|  
|`get_accName`|<xref:System.Windows.Automation.AutomationElement.NameProperty>|``|  
|`get_accRole`|<xref:System.Windows.Automation.AutomationElement.ControlTypeProperty>|Informationen zur Zuordnung von Rollen zu Steuerelementtypen finden Sie in der vorherigen Tabelle.|  
|`get_accValue`|<xref:System.Windows.Automation.ValuePattern.ValueProperty?displayProperty=fullName><br /><br /> <xref:System.Windows.Automation.RangeValuePattern.ValueProperty?displayProperty=fullName>|Dies gilt nur für Steuerelementtypen, die „ValuePattern“ oder „RangeValuePattern“ unterstützen. RangeValue\-Werte werden auf Werte zwischen 0 und 100 normalisiert, um dem MSAA\-Verhalten zu entsprechen. Value\-Elemente verwenden eine Zeichenfolge.|  
|`get_accHelp`|<xref:System.Windows.Automation.AutomationElement.HelpTextProperty>||  
|`accLocation`|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>||  
|`get_accDescription`|Nicht unterstützt in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Die `accDescription` hatte in MSAA keine eindeutige Spezifikation, was dazu geführt hat, dass Anbieter unterschiedliche Arten von Informationen in dieser Eigenschaft platziert haben.|  
|`get_accHelpTopic`|Nicht unterstützt in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]||  
  
 Die folgende Tabelle zeigt, welche [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Eigenschaften den [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]\-Zustandskonstanten entsprechen.  
  
|[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]\-Zustand|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Eigenschaft|Löst Zustandsänderung aus?|  
|--------------------------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------------------|  
|STATE\_SYSTEM\_CHECKED|Für Kontrollkästchen ist dies <xref:System.Windows.Automation.TogglePattern.ToggleStateProperty><br /><br /> Für Optionsfelder ist dies <xref:System.Windows.Automation.SelectionItemPattern.IsSelectedProperty>|J|  
|STATE\_SYSTEM\_COLLAPSED|<xref:System.Windows.Automation.ExpandCollapsePattern.ExpandCollapsePatternInformation.ExpandCollapseState%2A> \= <xref:System.Windows.Automation.ExpandCollapseState>|J|  
|STATE\_SYSTEM\_EXPANDED|<xref:System.Windows.Automation.ExpandCollapsePattern.ExpandCollapsePatternInformation.ExpandCollapseState%2A> \= <xref:System.Windows.Automation.ExpandCollapseState> oder <xref:System.Windows.Automation.ExpandCollapseState>|J|  
|STATE\_SYSTEM\_FOCUSABLE|<xref:System.Windows.Automation.AutomationElement.IsKeyboardFocusableProperty>|N|  
|STATE\_SYSTEM\_FOCUSED|<xref:System.Windows.Automation.AutomationElement.HasKeyboardFocusProperty>|N|  
|STATE\_SYSTEM\_HASPOPUP|<xref:System.Windows.Automation.ExpandCollapsePattern> für Menüelemente|N|  
|STATE\_SYSTEM\_INVISIBLE|<xref:System.Windows.Automation.AutomationElement.IsOffscreenProperty> \= True und <xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A> führt zu <xref:System.Windows.Automation.NoClickablePointException>|N|  
|STATE\_SYSTEM\_LINKED|<xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> \=<br /><br /> <xref:System.Windows.Automation.ControlType.Hyperlink>|N|  
|STATE\_SYSTEM\_MIXED|<xref:System.Windows.Automation.TogglePattern.TogglePatternInformation.ToggleState%2A> \= <xref:System.Windows.Automation.ToggleState>|N|  
|STATE\_SYSTEM\_MOVEABLE|<xref:System.Windows.Automation.TransformPattern.CanMoveProperty>|N|  
|STATE\_SYSTEM\_MUTLISELECTABLE|<xref:System.Windows.Automation.SelectionPattern.CanSelectMultipleProperty>|N|  
|STATE\_SYSTEM\_OFFSCREEN|<xref:System.Windows.Automation.AutomationElement.IsOffscreenProperty> \= True|N|  
|STATE\_SYSTEM\_PROTECTED|<xref:System.Windows.Automation.AutomationElement.IsPasswordProperty>|N|  
|STATE\_SYSTEM\_READONLY|<xref:System.Windows.Automation.RangeValuePattern.IsReadOnlyProperty?displayProperty=fullName> und <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty?displayProperty=fullName>|N|  
|STATE\_SYSTEM\_SELECTABLE|<xref:System.Windows.Automation.SelectionItemPattern> wird unterstützt|N|  
|STATE\_SYSTEM\_SELECTED|<xref:System.Windows.Automation.SelectionItemPattern.IsSelectedProperty>|N|  
|STATE\_SYSTEM\_SIZEABLE|<xref:System.Windows.Automation.TransformPattern.TransformPatternInformation.CanResize%2A>|N|  
|STATE\_SYSTEM\_UNAVAILABLE|<xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>|J|  
  
 Die folgenden Zustände wurden entweder von den meisten [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]\-Steuerelementservern nicht implementiert oder verfügen in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] über keine Entsprechung.  
  
|[!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]\-Zustand|Hinweise|  
|--------------------------------------------------------------------------|--------------|  
|STATE\_SYSTEM\_BUSY|Nicht verfügbar in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE\_SYSTEM\_DEFAULT|Nicht verfügbar in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE\_SYSTEM\_ANIMATED|Nicht verfügbar in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE\_SYSTEM\_EXTSELECTABLE|Von [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]\-Servern nicht umfassend implementiert|  
|STATE\_SYSTEM\_MARQUEED|Von [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]\-Servern nicht umfassend implementiert|  
|STATE\_SYSTEM\_SELFVOICING|Von [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]\-Servern nicht umfassend implementiert|  
|STATE\_SYSTEM\_TRAVERSED|Nicht verfügbar in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE\_SYSTEM\_ALERT\_HIGH|Von [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]\-Servern nicht umfassend implementiert|  
|STATE\_SYSTEM\_ALERT\_MEDIUM|Von [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]\-Servern nicht umfassend implementiert|  
|STATE\_SYSTEM\_ALERT\_LOW|Von [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]\-Servern nicht umfassend implementiert|  
|STATE\_SYSTEM\_FLOATING|Von [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]\-Servern nicht umfassend implementiert|  
|STATE\_SYSTEM\_HOTTRACKED|Nicht verfügbar in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
|STATE\_SYSTEM\_PRESSED|Nicht verfügbar in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|  
  
 Eine vollständige Liste von [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Eigenschaftenbezeichnern finden Sie unter [UI Automation Properties Overview](../../../docs/framework/ui-automation/ui-automation-properties-overview.md).  
  
<a name="uiautomation_events_compare"></a>   
## Ereignisse  
 Der Ereignismechanismus in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] beruht im Gegensatz zum Mechanismus in [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)] nicht auf dem Windows\-Ereignisrouting \(das eng mit Fensterhandles verbunden ist\) und erfordert von der Clientanwendung keine Einrichtung von Hooks. Abonnements von Ereignissen können nicht nur auf bestimmte Ereignisse, sondern auch auf bestimmte Teile der Struktur abgestimmt werden. Anbieter können zudem das Auslösen von Ereignissen optimieren, indem sie verfolgen, wofür Ereignisse aufgeführt werden.  
  
 Es ist für Clients außerdem einfacher, die Elemente abzurufen, die Ereignisse auslösen, da diese direkt an den Ereignisrückruf übergeben werden. Eigenschaften des Elements werden automatisch vorab abgerufen, wenn eine Cacheanforderung aktiv gewesen ist, als der Client das Ereignis abonniert hat.  
  
 In der folgende Tabelle wird die Übereinstimmung von [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]\-WinEvents und [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Ereignissen veranschaulicht.  
  
|WinEvent|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Ereignisbezeichner|  
|--------------|-----------------------------------------------------------------------------------------------|  
|EVENT\_OBJECT\_ACCELERATORCHANGE|<xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty>\-Eigenschaftenänderung|  
|EVENT\_OBJECT\_CONTENTSCROLLED|<xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty> oder eine <xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty>\-Eigenschaftenänderung für die entsprechenden Bildlaufleisten|  
|EVENT\_OBJECT\_CREATE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT\_OBJECT\_DEFACTIONCHANGE|Keine Entsprechung|  
|EVENT\_OBJECT\_DESCRIPTIONCHANGE|Keine genaue Entsprechung, vielleicht <xref:System.Windows.Automation.AutomationElement.HelpTextProperty> oder die <xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty>\-Eigenschaftenänderung|  
|EVENT\_OBJECT\_DESTROY|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT\_OBJECT\_FOCUS|<xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent>|  
|EVENT\_OBJECT\_HELPCHANGE|<xref:System.Windows.Automation.AutomationElement.HelpTextProperty>\-Änderung|  
|EVENT\_OBJECT\_HIDE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT\_OBJECT\_LOCATIONCHANGE|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>\-Eigenschaftenänderung|  
|EVENT\_OBJECT\_NAMECHANGE|<xref:System.Windows.Automation.AutomationElement.NameProperty>\-Eigenschaftenänderung|  
|EVENT\_OBJECT\_PARENTCHANGE|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT\_OBJECT\_REORDER|Nicht einheitlich verwendet in [!INCLUDE[TLA2#tla_aa](../../../includes/tla2sharptla-aa-md.md)]. In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ist kein direkt entsprechendes Ereignis definiert.|  
|EVENT\_OBJECT\_SELECTION|<xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent>|  
|EVENT\_OBJECT\_SELECTIONADD|<xref:System.Windows.Automation.SelectionItemPattern.ElementAddedToSelectionEvent>|  
|EVENT\_OBJECT\_SELECTIONREMOVE|<xref:System.Windows.Automation.SelectionItemPattern.ElementRemovedFromSelectionEvent>|  
|EVENT\_OBJECT\_SELECTIONWITHIN|Keine Entsprechung|  
|EVENT\_OBJECT\_SHOW|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|  
|EVENT\_OBJECT\_STATECHANGE|Verschiedene durch geänderte Eigenschaften ausgelöste Ereignisse|  
|EVENT\_OBJECT\_VALUECHANGE|<xref:System.Windows.Automation.RangeValuePattern.ValueProperty?displayProperty=fullName> und <xref:System.Windows.Automation.ValuePattern.ValueProperty?displayProperty=fullName> wurden geändert|  
|EVENT\_SYSTEM\_ALERT|Keine Entsprechung|  
|EVENT\_SYSTEM\_CAPTUREEND|Keine Entsprechung|  
|EVENT\_SYSTEM\_CAPTURESTART|Keine Entsprechung|  
|EVENT\_SYSTEM\_CONTEXTHELPEND|Keine Entsprechung|  
|EVENT\_SYSTEM\_CONTEXTHELPSTART|Keine Entsprechung|  
|EVENT\_SYSTEM\_DIALOGEND|<xref:System.Windows.Automation.WindowPattern.WindowClosedEvent>|  
|EVENT\_SYSTEM\_DIALOGSTART|<xref:System.Windows.Automation.WindowPattern.WindowOpenedEvent>|  
|EVENT\_SYSTEM\_DRAGDROPEND|Keine Entsprechung|  
|EVENT\_SYSTEM\_DRAGDROPSTART|Keine Entsprechung|  
|EVENT\_SYSTEM\_FOREGROUND|<xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent>|  
|EVENT\_SYSTEM\_MENUEND|<xref:System.Windows.Automation.AutomationElement.MenuClosedEvent>|  
|EVENT\_SYSTEM\_MENUPOPUPEND|<xref:System.Windows.Automation.AutomationElement.MenuClosedEvent>|  
|EVENT\_SYSTEM\_MENUPOPUPSTART|<xref:System.Windows.Automation.AutomationElement.MenuOpenedEvent>|  
|EVENT\_SYSTEM\_MENUSTART|<xref:System.Windows.Automation.AutomationElement.MenuOpenedEvent>|  
|EVENT\_SYSTEM\_MINIMIZEEND|<xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty>\-Eigenschaftenänderung|  
|EVENT\_SYSTEM\_MINIMIZESTART|<xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty>\-Eigenschaftenänderung|  
|EVENT\_SYSTEM\_MOVESIZEEND|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>\-Eigenschaftenänderung|  
|EVENT\_SYSTEM\_MOVESIZESTART|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>\-Eigenschaftenänderung|  
|EVENT\_SYSTEM\_SCROLLINGEND|<xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty> oder <xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty>\-Eigenschaftenänderung|  
|EVENT\_SYSTEM\_SCROLLINGSTART|<xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty> oder <xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty>\-Eigenschaftenänderung|  
|EVENT\_SYSTEM\_SOUND|Keine Entsprechung|  
|EVENT\_SYSTEM\_SWITCHEND|Keine Entsprechung, aber ein <xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent>\-Ereignis signalisiert, dass eine neue Anwendung den Fokus erhalten hat|  
|EVENT\_SYSTEM\_SWITCHSTART|Keine Entsprechung|  
|Keine Entsprechung|<xref:System.Windows.Automation.MultipleViewPattern.CurrentViewProperty>\-Eigenschaftenänderung|  
|Keine Entsprechung|<xref:System.Windows.Automation.ScrollPattern.HorizontallyScrollableProperty>\-Eigenschaftenänderung|  
|Keine Entsprechung|<xref:System.Windows.Automation.ScrollPattern.VerticallyScrollableProperty>\-Eigenschaftenänderung|  
|Keine Entsprechung|<xref:System.Windows.Automation.ScrollPattern.HorizontalScrollPercentProperty>\-Eigenschaftenänderung|  
|Keine Entsprechung|<xref:System.Windows.Automation.ScrollPattern.VerticalScrollPercentProperty>\-Eigenschaftenänderung|  
|Keine Entsprechung|<xref:System.Windows.Automation.ScrollPattern.HorizontalViewSizeProperty>\-Eigenschaftenänderung|  
|Keine Entsprechung|<xref:System.Windows.Automation.ScrollPattern.VerticalViewSizeProperty>\-Eigenschaftenänderung|  
|Keine Entsprechung|<xref:System.Windows.Automation.TogglePattern.ToggleStateProperty>\-Eigenschaftenänderung|  
|Keine Entsprechung|<xref:System.Windows.Automation.WindowPattern.WindowVisualStateProperty>\-Eigenschaftenänderung|  
|Keine Entsprechung|<xref:System.Windows.Automation.AutomationElement.AsyncContentLoadedEvent>\-Ereignis|  
|Keine Entsprechung|<xref:System.Windows.Automation.AutomationElement.ToolTipOpenedEvent>|  
  
<a name="Security_compare"></a>   
## Sicherheit  
 Einige `IAccessible`\-Anpassungsszenarien erfordern das Umschließen eines grundlegenden `IAccessible` und den Aufruf über dieses. Dadurch ergeben sich Sicherheitsrisiken, da eine teilweise vertrauenswürdige Komponente kein Zwischenelement eines Codepfads darstellen sollte.  
  
 Das [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Modell beseitigt die Notwendigkeit, dass Anbieter anderen Anbietercode aufrufen müssen. Der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Kerndienst führt alle erforderlichen Aggregationen aus.  
  
## Siehe auch  
 [UI Automation Fundamentals](../../../docs/framework/ui-automation/index.md)
---
title: Verwenden der AutomationID-Eigenschaft
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- AutomationId property
- UI Automation, AutomationId property
- properties, AutomationId
ms.assetid: a24e807b-d7c3-4e93-ac48-80094c4e1c90
ms.openlocfilehash: 7a172db8bcb626d78a24b546147b4e32f20f5d83
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291342"
---
# <a name="use-the-automationid-property"></a>Verwenden der AutomationID-Eigenschaft
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Dieses Thema enthält Szenarien und Codebeispiele zum Veranschaulichen, wie und wann Sie die <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> verwenden können, um ein Element in der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur zu suchen.  
  
 <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> unterscheidet ein Automatisierungselement eindeutig von dessen nebengeordneten Elementen. Weitere Informationen zu Eigenschaftenbezeichnern, die zur Identifikation von Steuerelementen dienen, finden Sie unter [UI Automation Properties Overview](ui-automation-properties-overview.md).  
  
> [!NOTE]
> Durch<xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> wird keine in der gesamten Struktur garantiert eindeutige Identität zur Verfügung gestellt. Für diese Eigenschaft sind normalerweise Container- und Bereichsinformationen erforderlich, damit sie nützlich ist. Eine Anwendung kann beispielsweise ein Menüsteuerelement mit mehreren Menüeinträgen oberster Ebene enthalten, die wiederum mehrere untergeordnete Menüeinträge aufweisen. Diese sekundären Menüeinträge könnten durch ein allgemeines Schema wie „Element1"“, „Element2“, „Element3“ usw. bezeichnet werden, wodurch doppelte Bezeichner für untergeordnete Elemente über die Menüeinträge oberster Ebene hinweg möglich sind.  
  
## <a name="scenarios"></a>Szenarien  
 Es wurden drei primäre Szenarien für Benutzeroberflächenautomatisierungs-Client-Anwendungen bestimmt, in denen <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> verwendet werden muss, damit richtige und konsistente Ergebnisse erzielt werden, wenn nach Elementen gesucht wird.  
  
> [!NOTE]
> <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> wird von allen Benutzeroberflächenautomatisierungs-Elementen in der Steuerelementansicht unterstützt. Davon ausgenommen sind lediglich Anwendungsfenster der obersten Ebene, Benutzeroberflächenautomatisierungs-Elemente, die von [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] -Steuerelementen ohne ID oder x:Uid abgeleitet wurden, und Benutzeroberflächenautomatisierungs-Elemente, die aus [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] -Steuerelementen abgeleitet wurden, die keine Steuerelement-ID haben.  
  
#### <a name="use-a-unique-and-discoverable-automationid-to-locate-a-specific-element-in-the-ui-automation-tree"></a>Suchen eines bestimmten Elements in der Benutzeroberflächenautomatisierungs-Struktur anhand einer eindeutigen und erkennbaren AutomationID  
  
- Verwenden Sie ein Tool wie z. b. UI Spy, um die <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> eines [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] relevanten Elements zu melden. Diesen Wert können Sie dann kopieren und in einer Clientanwendung (z. B. ein Testskript für spätere automatisierte Tests) einfügen. Mit dieser Vorgehensweise lässt sich der Code verringern und vereinfachen, der erforderlich ist, um ein Element zur Laufzeit zu identifizieren und zu suchen.  
  
> [!CAUTION]
> Grundsätzlich sollten Sie nur versuchen, direkt untergeordnete Elemente des Elements abzurufen, das von der <xref:System.Windows.Automation.AutomationElement.RootElement%2A>-Eigenschaft angegeben wird. Eine Suche nach Nachfolgerelementen kann hunderte oder sogar tausende Elemente durchlaufen und möglicherweise einen Stapelüberlauf verursachen. Wenn Sie versuchen, ein bestimmtes Element auf einer niedrigeren Ebene abzurufen, sollten Sie die Suche aus dem Anwendungsfenster oder aus einem Container auf niedrigerer Ebene starten.  
  
 [!code-csharp[UIAAutomationID_snip#100](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAAutomationID_snip/CSharp/FindByAutomationID.xaml.cs#100)]
 [!code-vb[UIAAutomationID_snip#100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAAutomationID_snip/VisualBasic/FindByAutomationID.xaml.vb#100)]  
  
#### <a name="use-a-persistent-path-to-return-to-a-previously-identified-automationelement"></a>Verwenden eines persistenten Pfads zum Zurückkehren zu einem vorher identifizierten AutomationElement  
  
- Möglicherweise müssen Clientanwendungen (von einfachen Testskripts bis zu robusten Aufzeichnungs- und Wiedergabeprogrammen) auf Elemente (z. B. ein Dialogfeld zum Öffnen von Dateien oder ein Menüelement) zugreifen, die zurzeit nicht instanziiert und deshalb in der Benutzeroberflächenautomatisierungs-Struktur nicht vorhanden sind. Diese Elemente können nur instanziiert werden, indem eine bestimmte Sequenz von UI-Aktionen mithilfe von Benutzeroberflächenautomatisierungs-Eigenschaften wie AutomationID, Steuerelement Mustern und Ereignislistener reproduziert oder wiedergegeben wird.
  
 [!code-csharp[UIAAutomationID_snip#UIAWorkerThread](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAAutomationID_snip/CSharp/FindByAutomationID.xaml.cs#uiaworkerthread)]
 [!code-vb[UIAAutomationID_snip#UIAWorkerThread](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAAutomationID_snip/VisualBasic/FindByAutomationID.xaml.vb#uiaworkerthread)]  
[!code-csharp[UIAAutomationID_snip#Playback](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAAutomationID_snip/CSharp/FindByAutomationID.xaml.cs#playback)]
[!code-vb[UIAAutomationID_snip#Playback](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAAutomationID_snip/VisualBasic/FindByAutomationID.xaml.vb#playback)]  
  
#### <a name="use-a-relative-path-to-return-to-a-previously-identified-automationelement"></a>Verwenden eines relativen Pfads zum Zurückkehren zu einem vorher identifizierten AutomationElement  
  
- Da AutomationID nur bei nebengeordneten Elementen garantiert eindeutig ist, haben unter bestimmten Umständen möglicherweise mehrere Elemente in der Benutzeroberflächenautomatisierungs-Struktur identische AutomationID-Eigenschaftswerte. In diesen Fällen können die Elemente anhand ihres übergeordneten Elements und ggf. ihres über-übergeordneten Elements eindeutig identifiziert werden. Beispielsweise könnte ein Entwickler eine Menüleiste mit mehreren Menüelementen bereitstellen, die jeweils mehrere untergeordnete Menüelemente haben, wobei die untergeordneten Elemente mit sequenziellen AutomationIDs wie „Element1“, „Element2“ usw. bezeichnet sind. Jedes Menüelement kann dann anhand seiner eigenen AutomationID sowie der seines übergeordneten Elements und ggf. seines über-übergeordneten Elements eindeutig identifiziert werden.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty>
- [Übersicht über die Benutzeroberflächenautomatisierungs-Struktur](ui-automation-tree-overview.md)
- [Suchen eines Benutzeroberflächenautomatisierungs-Elements anhand einer Eigenschaftenbedingung](find-a-ui-automation-element-based-on-a-property-condition.md)

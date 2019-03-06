---
title: Überlegungen zum Layout für das WindowsFormsHost-Element
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- WindowsFormsHost element layout considerations [WPF]
- dynamic layout [WPF interoperability]
- device-independent pixels
ms.assetid: 3c574597-bbde-440f-95cc-01371f1a5d9d
ms.openlocfilehash: 891254ff44926a719bb0c124e5dc098fd3f3e82e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57366542"
---
# <a name="layout-considerations-for-the-windowsformshost-element"></a>Überlegungen zum Layout für das WindowsFormsHost-Element
In diesem Thema wird beschrieben, wie die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element interagiert mit der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layoutsystem.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] für größenanpassung und Positionierung von Elementen in einem Formular oder die Seite unterschiedliche, jedoch ähnlich, Logik zu unterstützen. Bei der Erstellung einer Hybrid-Benutzeroberfläche (UI), der als Host [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] -Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element integriert, die zwei Layout-Schemas.  
  
## <a name="differences-in-layout-between-wpf-and-windows-forms"></a>Unterschiede im Layout zwischen WPF and Windows Forms  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet von Auflösung unabhängige Layout. Alle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layout Dimensionen werden mithilfe von angegeben *geräteunabhängige Pixel*. Eine geräteunabhängige Pixel ist eine 90-sechsten Zoll groß sein und Auflösungsunabhängige, um ähnliche Ergebnisse unabhängig davon, ob Sie einen Monitor 72-dpi-Wert oder einen Drucker 19.200-dpi-Rendern zu erhalten.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] basiert ebenfalls auf *dynamisches Layout*. Dies bedeutet, dass ein Element der Benutzeroberfläche auf einem Formular oder die Seite entsprechend den Inhalt, dessen übergeordneten Layoutcontainer und die Größe des verfügbaren Bildschirms anordnet. Dynamisches Layout erleichtert die Lokalisierung durch die Größe und Position von Elementen der Benutzeroberfläche automatisch anpassen, wenn die darin enthaltenen Zeichenfolgen Länge ändern.  
  
 Layout in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ist geräteabhängigen und eher statisch sein. In der Regel [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente werden auf einem Formular mithilfe von Dimensionen in Hardwarepixel angegebene absolut positioniert. Allerdings [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] unterstützt einige dynamische Layout-Funktionen, wie in der folgenden Tabelle zusammengefasst.  
  
|Layoutfunktion|Beschreibung|  
|--------------------|-----------------|  
|Automatisches Anpassen der Größe|Einige [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente ändern ihre Größe, damit ihr Inhalt ordnungsgemäß angezeigt. Weitere Informationen finden Sie unter [Übersicht über die AutoSize-Eigenschaft](../../winforms/controls/autosize-property-overview.md).|  
|Verankern und Andocken|[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Unterstützung von Steuerelementen Positionierung und größenanpassung basierend auf den übergeordneten Container. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType> und <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>.|  
|Für die automatische Skalierung|Containersteuerelemente Größe sich selbst und ihrer untergeordneten Elemente basierend auf der Auflösung des Ausgabegeräts oder die Größe, der die Standardschriftart des Containers in Pixel. Weitere Informationen finden Sie unter [automatische Skalierung in Windows Forms](../../winforms/automatic-scaling-in-windows-forms.md).|  
|Layout-Containern|Die <xref:System.Windows.Forms.FlowLayoutPanel> und <xref:System.Windows.Forms.TableLayoutPanel> Steuerelemente ordnen ihre untergeordneten Steuerelemente und ihre Größe, nach deren Inhalt.|  
  
## <a name="layout-limitations"></a>Layout-Einschränkungen  
 Im allgemeinen [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente nicht skaliert und im im größtmöglichen Umfang transformiert werden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Die folgende Liste beschreibt die bekannten Einschränkungen bei der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element versucht, integrieren Sie ihre gehosteten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] steuern, in der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layoutsystem.  
  
-   In einigen Fällen kann die Größe von [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Steuerelementen nicht geändert werden, oder die Größenänderung ist auf bestimmte Dimensionen beschränkt. Z. B. eine [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.ComboBox> -Steuerelement unterstützt nur eine einzige Höhe, die durch den Schriftgrad des Steuerelements definiert wird. In einem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dynamisches Layout, in denen Elemente vertikal werden können, einem gehosteten gestreckt <xref:System.Windows.Forms.ComboBox> -Steuerelement nicht wie erwartet gestreckt.  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Steuerelemente können nicht gedreht oder verzerrt werden. Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element löst die <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> Ereignis, wenn Sie eine Neigung oder Drehung der Transformation anwenden. Wenn Sie nicht behandeln die <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> Ereignis eine <xref:System.InvalidOperationException> ausgelöst wird.  
  
-   In den meisten Fällen unterstützen [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Steuerelemente keine proportionale Skalierung. Obwohl die gesamten Dimensionen des Steuerelements skaliert werden, können untergeordnete Steuerelemente und Komponenten des Steuerelements unter Umständen nicht wie erwartet skaliert werden. Diese Einschränkung hängt davon ab, in welcher Form das jeweilige [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Steuerelement eine Skalierung unterstützt. Darüber hinaus können Sie nicht skalieren [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente auf eine Größe von 0 Pixeln.  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuert die Unterstützung für die automatische Skalierung, in dem das Formular automatisch und seiner Steuerelemente anhand der Größe der Schriftart angepasst wird. In einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Benutzeroberfläche bewirkt eine Änderung des Schriftgrads keine Größenänderung des gesamten Layouts; einzelne Elemente können ihre Größe jedoch ggf. dynamisch anpassen.  
  
### <a name="z-order"></a>Z-Reihenfolge  
 In einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Benutzeroberfläche können Sie die Z-Reihenfolge der Elemente ändern, um ihr Verhalten bei Überlappung zu steuern. Ein gehostetes [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Steuerelement wird in einem separaten HWND gezeichnet, befindet sich also immer über [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Elementen.  
  
 Ein gehostetes [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] -Steuerelement gezeichnet wird auch über jeder <xref:System.Windows.Documents.Adorner> Elemente.  
  
## <a name="layout-behavior"></a>Layout-Verhalten  
 Die folgenden Abschnitte beschreiben bestimmte Aspekte der Layout-Verhalten beim Hosten von [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] -Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="scaling-unit-conversion-and-device-independence"></a>Skalierung, Einheitenumrechnung und Geräteunabhängigkeit  
 Wenn die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element führt Vorgänge im Zusammenhang mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Dimensionen, zwei Koordinatensysteme beteiligt sind: geräteunabhängige Pixel für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und Hardwarepixel für [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Aus diesem Grund müssen Sie die richtigen Einheit und Skalierung von Konvertierungen, um ein einheitliches Layout zu erzielen anwenden.  
  
 Die Koordinatensysteme für die Konvertierung hängt von der aktuellen geräteauflösung und Layouts oder Rendern von Transformationen angewendet, um die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element oder auf dessen Vorgänger.  
  
 Wenn das Ausgabegerät 96 dpi ist und keine Skalierung auf angewendet wurde, die <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element, ein geräteunabhängige Pixel entspricht einem Hardwarepixel.  
  
 In allen anderen Fällen erfordern Koordinatensystem zu skalieren. Die Größe des gehosteten Steuerelements wird nicht geändert. Stattdessen die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element versucht, das gehostete Steuerelement und alle untergeordneten Steuerelemente zu skalieren. Da [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] nicht vollständig unterstützt Skalierung der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element skaliert wird, in dem Umfang, die von bestimmten Steuerelementen unterstützt werden.  
  
 Überschreiben der <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A> Methode zum Bereitstellen von benutzerdefinierten Skalierungsverhalten für das gehostete Windows Forms-Steuerelement.  
  
 Neben der Skalierung der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element Rundung und Überlauffehler Fälle behandelt, wie in der folgenden Tabelle beschrieben.  
  
|Konvertierungsproblem|Beschreibung|  
|----------------------|-----------------|  
|Runden|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] geräteunabhängige Pixel-Dimensionen werden als angegeben `double`, und [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Hardware-Pixel-Dimensionen werden als angegeben `int`. In Fällen, in denen `double`-Basis Dimensionen werden in konvertiert `int`-Dimensionen basierend der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element gerundet wird, standard, damit Bruchwerte kleiner als 0,5 auf 0 abgerundet werden.|  
|Überlauf|Wenn die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element konvertiert, von `double` Werte `int` Werte Überlauf ist möglich. Werte, die größer als <xref:System.Int32.MaxValue> festgelegt <xref:System.Int32.MaxValue>.|  
  
### <a name="layout-related-properties"></a>Layoutbezogene Eigenschaften  
 Eigenschaften zum Steuern der Layout-Verhalten in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Elementen zugeordnet sind, entsprechend der von der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element. Weitere Informationen finden Sie unter [Eigenschaftenzuordnung von Windows Forms und WPF](windows-forms-and-wpf-property-mapping.md).  
  
### <a name="layout-changes-in-the-hosted-control"></a>Änderungen am Layout im gehosteten Steuerelement  
 Änderungen am Layout im gehosteten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement werden weitergegeben, um [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layoutaktualisierungen auslösen. Die <xref:System.Windows.UIElement.InvalidateMeasure%2A> Methode <xref:System.Windows.Forms.Integration.WindowsFormsHost> wird sichergestellt, dass Änderungen am Layout im gehosteten Steuerelement dazu führen, dass die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layout-Engine ausgeführt.  
  
### <a name="continuously-sized-windows-forms-controls"></a>Fortlaufend angepasst Windows Forms-Steuerelemente  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente, die kontinuierliche Skalierung vollständig unterstützen, interagieren mit der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layoutsystem. Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element verwendet die <xref:System.Windows.FrameworkElement.MeasureOverride%2A> und <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> Methoden wie gewohnt, Größe und Anordnung der gehosteten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement.  
  
### <a name="sizing-algorithm"></a>Algorithmus zur Anpassung  
 Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element verwendet das folgende Verfahren, um die Größe des gehosteten Steuerelements:  
  
1.  Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element überschreibt die <xref:System.Windows.FrameworkElement.MeasureOverride%2A> und <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> Methoden.  
  
2.  Zur Bestimmung der Größe des gehosteten Steuerelements, das <xref:System.Windows.FrameworkElement.MeasureOverride%2A> Methodenaufrufe des gehosteten Steuerelements <xref:System.Windows.Forms.Control.GetPreferredSize%2A> Methode mit einer Einschränkung übersetzt wird, von der Einschränkung, die an die <xref:System.Windows.FrameworkElement.MeasureOverride%2A> Methode.  
  
3.  Die <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> -Methode versucht, die die Einschränkung für die angegebene Größe des gehosteten Steuerelements fest.  
  
4.  Wenn des gehosteten Steuerelements <xref:System.Windows.Forms.Control.Size%2A> Eigenschaft mit die angegebene Einschränkung übereinstimmt, wird die Einschränkung wird das gehostete Steuerelement angepasst.  
  
 Wenn die <xref:System.Windows.Forms.Control.Size%2A> Eigenschaft entspricht nicht der angegebenen Einschränkung, das gehostete Steuerelement die kontinuierliche Größe nicht unterstützt. Z. B. die <xref:System.Windows.Forms.MonthCalendar> Steuerelement ermöglicht es, nur diskrete Größen. Die zulässigen Größen für dieses Steuerelement bestehen aus ganzen Zahlen (für die Anzahl der Monate) für die Höhe und Breite. In Fällen wie diesem den <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element verhält sich wie folgt:  
  
-   Wenn die <xref:System.Windows.Forms.Control.Size%2A> Eigenschaft zurückgibt, eine größere Größe als die angegebene Einschränkung, die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element schneidet das gehostete Steuerelement. Höhe und Breite werden separat behandelt, so dass das gehostete Steuerelement in beide Richtungen abgeschnitten werden kann.  
  
-   Wenn die <xref:System.Windows.Forms.Control.Size%2A> Eigenschaft gibt eine kleinere Größe als die angegebene Einschränkung, <xref:System.Windows.Forms.Integration.WindowsFormsHost> dieser Größenwert akzeptiert, und gibt den Wert, der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layoutsystem.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen in WPF](walkthrough-arranging-windows-forms-controls-in-wpf.md)
- [Anordnen von Windows Forms-Steuerelementen in WPF-Beispiel](https://go.microsoft.com/fwlink/?LinkID=159971)
- [Eigenschaftenzuordnung von Windows Forms und WPF](windows-forms-and-wpf-property-mapping.md)
- [Migration und Interoperabilität](migration-and-interoperability.md)

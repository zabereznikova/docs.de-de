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
ms.openlocfilehash: 786e3adae6c5b8167fbba00aa140d4d728308dc5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="layout-considerations-for-the-windowsformshost-element"></a>Überlegungen zum Layout für das WindowsFormsHost-Element
In diesem Thema wird beschrieben, wie die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element interagiert mit den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layoutsystem.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] unterstützen von unterschiedlichen – aber ähnlich, Logik für das Ändern der Größe und Positionierung von Elementen in einem Formular oder die Seite. Beim Erstellen einer Hybrid-Benutzeroberfläche (UI), der als Host [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] steuert in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element integriert, die zwei Layout-Schemas.  
  
## <a name="differences-in-layout-between-wpf-and-windows-forms"></a>Unterschiede im Layout WPF und Windows Forms  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Auflösungsunabhängige Layout verwendet. Alle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layout Dimensionen mit angegeben *geräteunabhängige Pixel*. Eine geräteunabhängige Pixel ist eine 90-sechsten Zoll, Größe und Auflösung unabhängig erhalten Sie ähnliche Ergebnisse unabhängig davon, ob Sie einen Monitor 72 DPI-Einstellung oder einen Drucker 19.200 DPI-Einstellung gerendert werden.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] basiert auch auf *dynamisches Layout*. Dies bedeutet, dass ein Element der Benutzeroberfläche auf einem Formular oder die Seite entsprechend seinen Inhalt, dessen übergeordneten Layoutcontainer und der verfügbaren Bildschirmgröße anordnet. Dynamisches Layout erleichtert die Lokalisierung mittels automatischer Anpassung der Größe und Position von Elementen der Benutzeroberfläche, wenn die Zeichenfolgen, die sie enthalten Länge ändern.  
  
 Layout in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] geräteabhängige und wahrscheinlicher statisch ist. In der Regel [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente absolut positioniert sind, auf ein Formular mit Dimensionen in Hardware Pixeln angegeben. Allerdings [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] unterstützt einige dynamische Layoutfunktionen aus, wie in der folgenden Tabelle zusammengefasst.  
  
|Layoutfunktion|Beschreibung|  
|--------------------|-----------------|  
|Automatisches Anpassen der Größe|Einige [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente ändern ihre Größe, damit ihr Inhalt ordnungsgemäß angezeigt. Weitere Informationen finden Sie unter [Übersicht über die AutoSize-Eigenschaft](../../../../docs/framework/winforms/controls/autosize-property-overview.md).|  
|Verankern und Andocken|[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Unterstützung von Steuerelementen positionieren und anpassen, die basierend auf den übergeordneten Container. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType> und <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>.|  
|Automatische Skalierung|Containersteuerelemente Größe sich selbst und deren untergeordnete Elemente basierend auf der Auflösung des Ausgabegeräts oder die Größe, der die Standardschriftart des Containers in Pixel. Weitere Informationen finden Sie unter [automatische Skalierung in Windows Forms](../../../../docs/framework/winforms/automatic-scaling-in-windows-forms.md).|  
|Layoutcontainern|Die <xref:System.Windows.Forms.FlowLayoutPanel> und <xref:System.Windows.Forms.TableLayoutPanel> Steuerelemente, Anordnen von deren untergeordneten Steuerelemente und Größe selbst nach deren Inhalt.|  
  
## <a name="layout-limitations"></a>Layout-Einschränkungen  
 Im allgemeinen [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente nicht skaliert und transformiert im größtmöglichen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Die folgende Liste beschreibt die bekannten Einschränkungen bei der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element versucht, auf ihre gehosteten integrieren [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] -Steuerelement auf die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layoutsystem.  
  
-   In einigen Fällen kann die Größe von [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Steuerelementen nicht geändert werden, oder die Größenänderung ist auf bestimmte Dimensionen beschränkt. Z. B. eine [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.ComboBox> Steuerelement unterstützt nur eine einzige Höhe, die durch den Schriftgrad des Steuerelements definiert ist. In einem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dynamisches Layout, in dem Elemente vertikal werden können, einen gehosteten gestreckt <xref:System.Windows.Forms.ComboBox> Steuerelement wird Schaltfläche erstreckt sich nicht wie erwartet.  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Steuerelemente können nicht gedreht oder verzerrt werden. Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element löst die <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> Ereignis, wenn Sie eine Transformation Neigung oder Drehung anwenden. Wenn Sie nicht behandeln die <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> Ereignis, eine <xref:System.InvalidOperationException> ausgelöst wird.  
  
-   In den meisten Fällen unterstützen [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Steuerelemente keine proportionale Skalierung. Obwohl die gesamten Dimensionen des Steuerelements skaliert werden, können untergeordnete Steuerelemente und Komponenten des Steuerelements unter Umständen nicht wie erwartet skaliert werden. Diese Einschränkung hängt davon ab, in welcher Form das jeweilige [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Steuerelement eine Skalierung unterstützt. Darüber hinaus können Sie nicht skaliert [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente auf eine Größe von 0 Pixeln.  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente unterstützen die automatische Skalierung, in dem das Formular automatisch selbst und seine Steuerelemente, die basierend auf der Größe der Schriftart angepasst wird. In einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Benutzeroberfläche bewirkt eine Änderung des Schriftgrads keine Größenänderung des gesamten Layouts; einzelne Elemente können ihre Größe jedoch ggf. dynamisch anpassen.  
  
### <a name="z-order"></a>Z-Reihenfolge  
 In einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Benutzeroberfläche können Sie die Z-Reihenfolge der Elemente ändern, um ihr Verhalten bei Überlappung zu steuern. Ein gehostetes [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Steuerelement wird in einem separaten HWND gezeichnet, befindet sich also immer über [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Elementen.  
  
 Ein gehostetes [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement gezeichnet wird auch auf alle <xref:System.Windows.Documents.Adorner> Elemente.  
  
## <a name="layout-behavior"></a>Layoutverhalten  
 Den folgenden Abschnitten werden spezifische Aspekte der Layoutverhalten beim Hosten von [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] steuert in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="scaling-unit-conversion-and-device-independence"></a>Skalieren, Einheitenkonvertierung und geräteunabhängige  
 Wenn die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element führt Vorgänge im Zusammenhang mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Dimensionen, zwei Koordinatensysteme sind beteiligt: geräteunabhängige Pixel für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und Hardwarepixel für [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Aus diesem Grund müssen Sie die richtigen Einheit und umrechnen, um ein konsistentes Layout zu erreichen anwenden.  
  
 Die Koordinatensysteme für die Konvertierung hängt von der aktuellen geräteauflösung und jedes Layout oder Transformationen Rendern angewendet die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element oder Vorgänger.  
  
 Wenn das Ausgabegerät 96 dpi ist und keine Skalierung auf angewendet wurde die <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element, um ein geräteunabhängige Pixel entspricht ein Hardwarepixel.  
  
 In allen anderen Fällen erfordern die Skalierung des Koordinatensystems. Das gehostete Steuerelement Größe nicht geändert werden. Stattdessen die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element versucht wird, um das gehostete Steuerelement und alle untergeordneten Steuerelemente skaliert werden. Da [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] vollständig unterstützt keine Skalierung, die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element skaliert, um den Grad von bestimmten Steuerelementen unterstützt.  
  
 Überschreiben Sie die <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A> Methode, um benutzerdefinierte Skalierungsverhalten für das gehostete Windows Forms-Steuerelement bereitzustellen.  
  
 Zusätzlich zum horizontalen, die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element behandelt Rundung und Überlauf-Fälle an, wie in der folgenden Tabelle beschrieben.  
  
|Konvertierungsproblem|Beschreibung|  
|----------------------|-----------------|  
|Runden|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] geräteunabhängige Pixel-Dimensionen werden als angegeben `double`, und [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Hardware-Pixel-Dimensionen werden als angegeben `int`. In Fällen, in denen `double`-Basis Dimensionen werden in konvertiert `int`-Dimensionen basierend die <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element verwendet standardmäßige Rundung, damit Bruchwerte kleiner als 0,5 auf 0 abgerundet werden.|  
|Überlauf|Wenn die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element konvertiert aus `double` -Werte in `int` Werte, die einen Überlauf ist möglich. Werte, die größer sind als <xref:System.Int32.MaxValue> festgelegt <xref:System.Int32.MaxValue>.|  
  
### <a name="layout-related-properties"></a>Layout-bezogene Eigenschaften  
 Eigenschaften zum Steuern der Layoutverhalten in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Elemente zugeordnet sind, entsprechend durch die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element. Weitere Informationen finden Sie unter [Eigenschaftenzuordnung von Windows Forms und WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md).  
  
### <a name="layout-changes-in-the-hosted-control"></a>Änderungen am Layout im gehosteten Steuerelement  
 Änderungen am Layout im gehosteten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement an weitergegeben werden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layout Updates auslösen. Die <xref:System.Windows.UIElement.InvalidateMeasure%2A> Methode <xref:System.Windows.Forms.Integration.WindowsFormsHost> wird sichergestellt, dass Änderungen am Layout im gehosteten Steuerelement dazu führen, dass die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layoutmodul ausgeführt.  
  
### <a name="continuously-sized-windows-forms-controls"></a>Fortlaufend angepasst Windows Forms-Steuerelementen  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelemente, die kontinuierliche Skalierung vollständig unterstützen, interagieren mit der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layoutsystem. Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element verwendet die <xref:System.Windows.FrameworkElement.MeasureOverride%2A> und <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> Methoden wie gewohnt auf die geringere Abbildgröße und Anordnen der gehosteten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement.  
  
### <a name="sizing-algorithm"></a>Sizing-Algorithmus  
 Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element verwendet das folgende Verfahren, um die Größe des gehosteten Steuerelements:  
  
1.  Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element überschreibt die <xref:System.Windows.FrameworkElement.MeasureOverride%2A> und <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> Methoden.  
  
2.  Zur Bestimmung der Größe des gehosteten Steuerelements die <xref:System.Windows.FrameworkElement.MeasureOverride%2A> Methode ruft des gehosteten Steuerelements <xref:System.Windows.Forms.Control.GetPreferredSize%2A> Methode mit einer Einschränkung übersetzt, von der Einschränkung, die zum Übergeben der <xref:System.Windows.FrameworkElement.MeasureOverride%2A> Methode.  
  
3.  Die <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> Methode versucht, die im gehostete Steuerelement auf die vorgegebene Größe-Einschränkung festgelegt.  
  
4.  Wenn des gehosteten Steuerelements <xref:System.Windows.Forms.Control.Size%2A> Eigenschaft der angegebenen Einschränkung entspricht, wird die Größe der Einschränkung des gehosteten Steuerelements angepasst.  
  
 Wenn die <xref:System.Windows.Forms.Control.Size%2A> Eigenschaft stimmt nicht mit die angegebene Einschränkung überein, das gehostete Steuerelement unterstützt keine kontinuierlichen anpassen. Z. B. die <xref:System.Windows.Forms.MonthCalendar> Steuerelement können nur diskrete Größen. Die zulässigen Größen für dieses Steuerelement bestehen aus ganzen Zahlen (welche die Anzahl der Monate) für die Höhe und Breite. In Fällen, die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element verhält sich wie folgt:  
  
-   Wenn die <xref:System.Windows.Forms.Control.Size%2A> Eigenschaft gibt eine größere Größe als die angegebene Einschränkung der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element beschneidet das gehostete Steuerelement. Höhe und Breite werden separat behandelt, sodass das gehostete Steuerelement in beide Richtungen abgeschnitten werden kann.  
  
-   Wenn die <xref:System.Windows.Forms.Control.Size%2A> Eigenschaft gibt eine geringere Größe als die angegebene Einschränkung <xref:System.Windows.Forms.Integration.WindowsFormsHost> akzeptiert diese Größenwert und gibt den Wert, der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layoutsystem.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen in WPF](../../../../docs/framework/wpf/advanced/walkthrough-arranging-windows-forms-controls-in-wpf.md)  
 [Anordnen von Windows Forms-Steuerelementen in WPF-Beispiel](http://go.microsoft.com/fwlink/?LinkID=159971)  
 [Eigenschaftenzuordnung von Windows Forms und WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)  
 [Migration und Interoperabilität](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)

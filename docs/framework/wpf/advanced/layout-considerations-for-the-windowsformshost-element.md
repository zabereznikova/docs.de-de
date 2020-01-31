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
ms.openlocfilehash: 9f97639447284b792d52cf4aa25b81f584d7291a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76787909"
---
# <a name="layout-considerations-for-the-windowsformshost-element"></a>Überlegungen zum Layout für das WindowsFormsHost-Element
In diesem Thema wird beschrieben, wie das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element mit dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layoutsystem interagiert.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und Windows Forms unterstützen unterschiedliche, aber ähnliche Logik für die Größenanpassung und Positionierung von Elementen in einem Formular oder einer Seite. Wenn Sie eine hybride Benutzeroberfläche (UI) erstellen, die Windows Forms Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]hostet, werden die beiden Layoutschemas vom <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element integriert.  
  
## <a name="differences-in-layout-between-wpf-and-windows-forms"></a>Unterschiede beim Layout zwischen WPF und Windows Forms  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet das auflösungsunabhängige Layout. Alle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layoutdimensionen werden mit *geräteunabhängigen Pixeln*angegeben. Ein Geräte unabhängiges Pixel ist eine 90-sechste Zoll-Größe und auflösungsunabhängig, sodass Sie ähnliche Ergebnisse erhalten, unabhängig davon, ob Sie einen 72-dpi-Monitor oder einen 19.200-dpi-Drucker rendern.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] basiert auch auf *dynamischem Layout*. Dies bedeutet, dass sich ein Benutzeroberflächen Element auf einem Formular oder einer Seite entsprechend seinem Inhalt, dem übergeordneten Layoutcontainer und der verfügbaren Bildschirmgröße anordnet. Dynamisches Layout erleichtert die Lokalisierung durch automatisches Anpassen der Größe und Position von Benutzeroberflächen Elementen, wenn die Zeichen folgen die Länge ändern.  
  
 Das Layout in Windows Forms ist Geräte abhängig und wahrscheinlicher, dass es statisch ist. In der Regel werden Windows Forms-Steuerelemente auf einem Formular mithilfe der in Hardware Pixel angegebenen Dimensionen vollkommen positioniert. Windows Forms unterstützt jedoch einige dynamische Layoutfeatures, wie in der folgenden Tabelle zusammengefasst.  
  
|Layoutfunktion|Beschreibung|  
|--------------------|-----------------|  
|Automatisches Anpassen|Einige Windows Forms Steuerelemente ändern sich an sich selbst, um deren Inhalte ordnungsgemäß anzuzeigen. Weitere Informationen finden Sie unter [Übersicht über die AutoSize-Eigenschaft](../../winforms/controls/autosize-property-overview.md).|  
|Verankern und Andocken|Windows Forms Steuerelemente unterstützen Positionierung und Größenanpassung basierend auf dem übergeordneten Container. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType> und <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>.|  
|Automatische Skalierung|Container Steuerelemente ändern die Größe selbst und ihrer untergeordneten Elemente basierend auf der Auflösung des Ausgabegeräts oder der Größe (in Pixel) der Standardcontainer Schriftart. Weitere Informationen finden Sie unter [Automatische Skalierung in Windows Forms](../../winforms/automatic-scaling-in-windows-forms.md).|  
|Layoutcontainer|Die Steuerelemente <xref:System.Windows.Forms.FlowLayoutPanel> und <xref:System.Windows.Forms.TableLayoutPanel> ordnen ihre untergeordneten Steuerelemente und die Größe selbst entsprechend ihren Inhalten an.|  
  
## <a name="layout-limitations"></a>Layouteinschränkungen  
 Im Allgemeinen können Windows Forms Steuerelemente nicht so skaliert und transformiert werden, wie Sie in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]möglich sind. In der folgenden Liste werden die bekannten Einschränkungen beschrieben, wenn das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element versucht, das gehostete Windows Forms-Steuerelement in das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layoutsystem zu integrieren.  
  
- In einigen Fällen können Windows Forms Steuerelemente nicht geändert werden, oder Sie können nur für bestimmte Dimensionen angepasst werden. Beispielsweise unterstützt ein Windows Forms <xref:System.Windows.Forms.ComboBox>-Steuerelement nur eine einzige Höhe, die durch den Schrift Grad des Steuer Elements definiert wird. In einem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dynamischen Layout, in dem Elemente vertikal gestreckt werden können, wird ein gehostetes <xref:System.Windows.Forms.ComboBox> Steuerelement nicht erwartungsgemäß gestreckt.  
  
- Windows Forms Steuerelemente können nicht gedreht oder verzerrt werden. Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element löst das <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError>-Ereignis aus, wenn Sie eine schiefe-oder Rotations Transformation anwenden. Wenn Sie das <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError>-Ereignis nicht behandeln, wird eine <xref:System.InvalidOperationException> ausgelöst.  
  
- In den meisten Fällen unterstützen Windows Forms Steuerelemente keine proportionale Skalierung. Obwohl die gesamten Dimensionen des Steuerelements skaliert werden, können untergeordnete Steuerelemente und Komponenten des Steuerelements unter Umständen nicht wie erwartet skaliert werden. Diese Einschränkung hängt davon ab, wie gut die einzelnen Windows Forms Steuerelemente die Skalierung unterstützen Darüber hinaus können Sie Windows Forms-Steuerelemente nicht auf eine Größe von 0 Pixeln skalieren.  
  
- Windows Forms Steuerelemente unterstützen die automatische Skalierung, in der das Formular automatisch die Größe selbst und dessen Steuerelemente basierend auf dem Schrift Grad ändert. In einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Benutzeroberfläche bewirkt eine Änderung des Schriftgrads keine Größenänderung des gesamten Layouts; einzelne Elemente können ihre Größe jedoch ggf. dynamisch anpassen.  
  
### <a name="z-order"></a>Z-Reihenfolge  
 In einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Benutzeroberfläche können Sie die Z-Reihenfolge der Elemente ändern, um ihr Verhalten bei Überlappung zu steuern. Ein gehostetes Windows Forms Steuerelement wird in einem separaten HWND gezeichnet, sodass es immer auf [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Elementen gezeichnet wird.  
  
 Ein gehostetes Windows Forms Steuerelement wird auch auf allen <xref:System.Windows.Documents.Adorner> Elementen gezeichnet.  
  
## <a name="layout-behavior"></a>Layoutverhalten  
 In den folgenden Abschnitten werden bestimmte Aspekte des Layoutverhaltens beim Hosting von Windows Forms Steuerelementen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]beschrieben.  
  
### <a name="scaling-unit-conversion-and-device-independence"></a>Skalierung, Einheiten Konvertierung und Geräteunabhängigkeit  
 Wenn das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element Vorgänge mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und Windows Forms Dimensionen ausführt, sind zwei Koordinatensysteme beteiligt: geräteunabhängige Pixel für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und Hardware Pixel für Windows Forms. Daher müssen Sie geeignete Einheiten-und Skalierungs Konvertierungen anwenden, um ein konsistentes Layout zu erzielen.  
  
 Die Konvertierung zwischen den Koordinatensystemen hängt von der aktuellen Geräte Auflösung und allen Layout-oder Renderingtransformationen ab, die auf das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element oder seine Vorgänger angewendet werden.  
  
 Wenn das Ausgabegerät 96 dpi und keine Skalierung auf das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element angewendet wurde, ist ein Geräte unabhängiges Pixel gleich einem Hardware Pixel.  
  
 Für alle anderen Fälle ist eine Koordinatensystem Skalierung erforderlich. Die Größe des gehosteten Steuer Elements wird nicht geändert. Stattdessen versucht das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element, das gehostete Steuerelement und alle untergeordneten Steuerelemente zu skalieren. Da Windows Forms die Skalierung nicht vollständig unterstützt, wird das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element in den von bestimmten Steuerelementen unterstützten Grad skaliert.  
  
 Überschreiben Sie die-<xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A>-Methode, um ein benutzerdefiniertes Skalierungs Verhalten für das gehostete Windows Forms  
  
 Zusätzlich zur Skalierung verarbeitet das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element Rundungs-und Überlauf Fälle, wie in der folgenden Tabelle beschrieben.  
  
|Konvertierungs Problem|Beschreibung|  
|----------------------|-----------------|  
|Rundung (Rounding)|[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] geräteunabhängigen Pixel Dimensionen werden als `double`angegeben, und Windows Forms Hardware Pixel Dimensionen werden als `int`angegeben. In Fällen, in denen `double`-basierte Dimensionen in `int`-basierte Dimensionen konvertiert werden, verwendet das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element Standard Rundungen, sodass Bruchzahlen, die kleiner als 0,5 sind, auf 0 gerundet werden.|  
|Überlauf|Wenn das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element von `double` Werten in `int` Werte konvertiert, ist ein Überlauf möglich. Werte, die größer als <xref:System.Int32.MaxValue> sind, werden auf <xref:System.Int32.MaxValue>festgelegt.|  
  
### <a name="layout-related-properties"></a>Layouteigenschaften  
 Eigenschaften, die das Layoutverhalten in Windows Forms Steuerelementen und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Elementen steuern, werden entsprechend dem <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element zugeordnet. Weitere Informationen finden Sie unter [Eigenschaftenzuordnung von Windows Forms und WPF](windows-forms-and-wpf-property-mapping.md).  
  
### <a name="layout-changes-in-the-hosted-control"></a>Layoutänderungen im gehosteten Steuerelement  
 Layoutänderungen im gehosteten Windows Forms Steuerelement werden an [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] weitergegeben, um layoutaktualisierungen zu initiieren. Die <xref:System.Windows.UIElement.InvalidateMeasure%2A>-Methode auf <xref:System.Windows.Forms.Integration.WindowsFormsHost> stellt sicher, dass Layoutänderungen im gehosteten Steuerelement bewirken, dass die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layout-Engine ausgeführt wird.  
  
### <a name="continuously-sized-windows-forms-controls"></a>Windows Forms Steuerelemente mit kontinuierlicher Größenanpassung  
 Windows Forms Steuerelemente, die kontinuierliche Skalierung unterstützen, interagieren vollständig mit dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layoutsystem Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element verwendet die Methoden <xref:System.Windows.FrameworkElement.MeasureOverride%2A> und <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> wie üblich, um das gehostete Windows Forms Steuerelement zu sortieren und anzuordnen.  
  
### <a name="sizing-algorithm"></a>Größen Änderungs Algorithmus  
 Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element verwendet das folgende Verfahren, um das gehostete Steuerelement zu verkleinern:  
  
1. Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element überschreibt die Methoden <xref:System.Windows.FrameworkElement.MeasureOverride%2A> und <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>.  
  
2. Um die Größe des gehosteten Steuer Elements zu bestimmen, ruft die <xref:System.Windows.FrameworkElement.MeasureOverride%2A>-Methode die <xref:System.Windows.Forms.Control.GetPreferredSize%2A> Methode des gehosteten Steuer Elements mit einer Einschränkung auf, die aus der an die <xref:System.Windows.FrameworkElement.MeasureOverride%2A>-Methode übergebenen Einschränkung übersetzt wurde.  
  
3. Die <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>-Methode versucht, das gehostete Steuerelement auf die angegebene Größen Einschränkung festzulegen.  
  
4. Wenn die <xref:System.Windows.Forms.Control.Size%2A>-Eigenschaft des gehosteten Steuer Elements mit der angegebenen Einschränkung übereinstimmt, wird das gehostete Steuerelement auf die Einschränkung skaliert.  
  
 Wenn die <xref:System.Windows.Forms.Control.Size%2A>-Eigenschaft nicht mit der angegebenen Einschränkung identisch ist, unterstützt das gehostete Steuerelement keine fortlaufende Größenanpassung. Das <xref:System.Windows.Forms.MonthCalendar>-Steuerelement lässt z. b. nur diskrete Größen zu. Die zulässigen Größen für dieses Steuerelement bestehen aus ganzen Zahlen (die die Anzahl der Monate darstellen) für Höhe und Breite. In diesen Fällen verhält sich das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element wie folgt:  
  
- Wenn die <xref:System.Windows.Forms.Control.Size%2A>-Eigenschaft eine größere Größe als die angegebene Einschränkung zurückgibt, schneidet das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element das gehostete Steuerelement ab. Höhe und Breite werden separat behandelt, sodass das gehostete Steuerelement in beide Richtungen abgeschnitten werden kann.  
  
- Wenn die <xref:System.Windows.Forms.Control.Size%2A>-Eigenschaft eine geringere Größe zurückgibt als die angegebene Einschränkung, akzeptiert <xref:System.Windows.Forms.Integration.WindowsFormsHost> diesen Größen Wert und gibt den Wert an das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layoutsystem zurück.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Exemplarische Vorgehensweise: Anordnen von Windows Forms-Steuerelementen in WPF](walkthrough-arranging-windows-forms-controls-in-wpf.md)
- [Anordnen von Windows Forms Steuerelementen in WPF-Beispiel](https://go.microsoft.com/fwlink/?LinkID=159971)
- [Eigenschaftenzuordnung von Windows Forms und WPF](windows-forms-and-wpf-property-mapping.md)
- [Migration und Interoperabilität](migration-and-interoperability.md)

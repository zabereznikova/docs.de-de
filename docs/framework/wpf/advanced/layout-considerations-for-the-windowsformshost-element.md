---
title: "&#220;berlegungen zum Layout f&#252;r das WindowsFormsHost-Element | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Geräteunabhängige Pixel"
  - "Dynamisches Layout [WPF-Interoperabilität]"
  - "Interoperabilität [WPF], Windows Forms"
  - "Windows Forms [WPF], Interoperabilität mit"
  - "Windows Forms, WPF-Interoperation"
  - "Überlegungen zum Layout für das WindowsFormsHost-Element"
ms.assetid: 3c574597-bbde-440f-95cc-01371f1a5d9d
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# &#220;berlegungen zum Layout f&#252;r das WindowsFormsHost-Element
In diesem Thema wird beschrieben, wie das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element mit dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Layoutsystem interagiert.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] unterstützen unterschiedliche, aber ähnliche Logik für die Größenanpassung und Positionierung von Elementen in einem Formular oder auf einer Seite.  Beim Erstellen einer Hybridbenutzeroberfläche, die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hostet, führt das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element die beiden Layoutschemas zusammen.  
  
## Layoutunterschiede zwischen WPF und Windows Forms  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet ein von der Auflösung unabhängiges Layout.  Alle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Layoutdimensionen werden in *geräteunabhängigen Pixeln* angegeben.  Die Größe eines geräteunabhängigen Pixels beträgt ein neunundsechzigstel Zoll, und es ist nicht von der Auflösung abhängig. Unabhängig davon, ob Sie mit 72 DPI \(Dots Per Inch\) auf einem Bildschirm oder mit 19200 DPI auf einem Drucker rendern, erhalten Sie also ähnliche Ergebnisse.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] basiert auch auf *dynamischem Layout*.  Dies bedeutet, dass die Größe eines Benutzeroberflächenelements auf einem Formular oder einer Seite entsprechend dem Inhalt, dem übergeordneten Layoutcontainer und der verfügbaren Bildschirmgröße angepasst wird.  Das dynamische Layout erleichtert die Lokalisierung dadurch, dass die Größe und die Position von Benutzeroberflächenelementen automatisch angepasst werden, wenn sich die Länge der darin enthaltenen Zeichenfolgen ändert.  
  
 Das Layout in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ist geräteabhängig und mit höherer Wahrscheinlichkeit statisch.  Normalerweise werden [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelemente in einem Formular absolut positioniert, wobei in Hardwarepixel angegebene Dimensionen verwendet werden.  [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] unterstützt jedoch einige dynamische Layoutfeatures, die in der folgenden Tabelle zusammengefasst werden.  
  
|Layoutfeature|Description|  
|-------------------|-----------------|  
|Automatische Größenanpassung|Einige [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelemente ändern ihre Größe, damit ihr Inhalt richtig angezeigt wird.  Weitere Informationen finden Sie unter [Übersicht über die AutoSize\-Eigenschaft](../../../../docs/framework/winforms/controls/autosize-property-overview.md).|  
|Verankern und Andocken|[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelemente unterstützen die Positionierung und die Größenanpassung auf Grundlage des übergeordneten Containers.  Weitere Informationen finden Sie unter <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=fullName> und <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=fullName>.|  
|Automatische Skalierung|Container\-Steuerelemente ändern ihre Größe und die Größe ihrer untergeordneten Elemente basierend auf der Auflösung des Ausgabegeräts oder der in Pixeln angegebenen Größe der Standardcontainerschriftart.  Weitere Informationen finden Sie unter [Automatische Skalierung in Windows Forms](../../../../docs/framework/winforms/automatic-scaling-in-windows-forms.md).|  
|Layoutcontainer|Das <xref:System.Windows.Forms.FlowLayoutPanel>\-Steuerelement und das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement ordnen ihre untergeordneten Steuerelemente an und passen ihre Größe dem Inhalt an.|  
  
## Layouteinschränkungen  
 Im Allgemeinen können [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelemente nicht in dem Umfang skaliert und umgewandelt werden, wie es in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] möglich ist.  In der folgenden Liste werden die bekannten Einschränkungen beschrieben, die gelten, wenn das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element versucht, das zugehörige gehostete [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelement in das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Layoutsystem zu integrieren.  
  
-   In einigen Fällen kann die Größe von [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelementen nicht angepasst oder nur auf bestimmte Abmessungen festgelegt werden.  Ein [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.ComboBox>\-Steuerelement unterstützt beispielsweise nur eine einzige Höhe, die durch den Schriftgrad des Steuerelements definiert wird.  In einem dynamischen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Layout, in dem Elemente vertikal gestreckt werden können, wird ein gehostetes <xref:System.Windows.Forms.ComboBox>\-Steuerelement nicht wie erwartet gestreckt.  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelemente können nicht gedreht oder verzerrt werden.  Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element löst das <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError>\-Ereignis aus, wenn Sie eine Neigungs\- oder eine Drehungstransformation anwenden.  Wenn Sie das <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError>\-Ereignis nicht behandeln, wird eine <xref:System.InvalidOperationException>\-Ausnahme ausgelöst.  
  
-   In den meisten Fällen unterstützen [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelemente keine proportionale Skalierung.  Obwohl sich die Gesamtabmessungen des Steuerelements skalieren lassen, wird die Größe von untergeordneten Steuerelementen und Komponentenelementen des Steuerelements möglicherweise nicht wie erwartet angepasst.  Diese Einschränkung hängt davon ab, in welchem Maße jedes [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelement die Skalierung unterstützt.  Außerdem können Sie die Größe von [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelementen nicht auf 0 Pixel verringern.  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelemente unterstützen die automatische Skalierung, bei der die Größe des Formulars und seiner Steuerelemente entsprechend der Schriftart automatisch angepasst werden.  Wenn Sie in einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Benutzeroberfläche den Schriftgrad ändern, wird nicht das gesamte Layout angepasst. Möglicherweise werden jedoch einzelne Elemente dynamisch angepasst.  
  
### Z\-Reihenfolge  
 In einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Benutzeroberfläche können Sie die z\-Reihenfolge von Elementen zur Steuerung des Verhaltens beim Überlappen ändern.  Ein gehostetes [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelement wird in einem separaten HWND gezeichnet, d. h., es wird immer über [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Elementen gezeichnet.  
  
 Ein gehostetes [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelement wird ebenfalls über allen <xref:System.Windows.Documents.Adorner>\-Elementen gezeichnet.  
  
## Layoutverhalten  
 In den folgenden Abschnitten werden bestimmte Aspekte des Layoutverhaltens beim Hosten von [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelementen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] beschrieben.  
  
### Skalieren, Konvertieren von Einheiten und Geräteunabhängigkeit  
 Wenn das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element Operationen ausführt, bei denen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Dimensionen und [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Dimensionen verwendet werden, spielen zwei Koordinatensysteme eine Rolle: geräteunabhängige Pixel für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und Hardwarepixel für [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  Aus diesem Grund müssen Sie die Einheiten und Größen richtig umrechnen, damit ein konsistentes Layout erreicht wird.  
  
 Konvertierungen zwischen den Koordinatensystemen hängen von der aktuellen Geräteauflösung sowie jeglichen Layout\- oder Renderingtransformationen ab, die auf das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element oder seine Vorgängerelemente angewendet werden.  
  
 Wenn ein Ausgabegerät mit 96 DPI verwendet wird und das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element nicht skaliert wurde, entspricht ein geräteunabhängiges Pixel einem Hardwarepixel.  
  
 In allen anderen Fällen ist die Skalierung des Koordinatensystems erforderlich.  Die Größe des gehosteten Steuerelements wird nicht geändert.  Stattdessen versucht das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element, das gehostete Steuerelement und alle untergeordneten Steuerelemente zu skalieren.  Da [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] die Skalierung nicht vollständig unterstützt, skaliert das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element in dem Umfang, der von bestimmten Steuerelementen unterstützt wird.  
  
 Überschreiben Sie die <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A>\-Methode, um ein benutzerdefiniertes Skalierungsverhalten für das gehostete [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)]\-Steuerelement bereitzustellen.  
  
 Neben der Skalierung behandelt das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element Fälle von Rundung und Überlauf, wie in der nachstehenden Tabelle beschrieben.  
  
|Konvertierungsproblem|Description|  
|---------------------------|-----------------|  
|Runden|Die geräteunabhängigen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Pixeldimensionen werden als `double` und die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Hardware\-Pixeldimensionen als `int` angegeben.  In Fällen, in denen `double`\-basierte Dimensionen in `int`\-basierte Dimensionen konvertiert werden, verwendet das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element die Standardrundung, sodass Bruchwerte unter 0,5 auf 0 abgerundet werden.|  
|Overflow|Wenn das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element von `double`\-Werten in `int`\-Werte konvertiert, kann dies zu einem Überlauf führen.  Werte, die größer sind als <xref:System.Int32.MaxValue>, werden auf <xref:System.Int32.MaxValue> festgelegt.|  
  
### Eigenschaften, die sich auf das Layout beziehen  
 Eigenschaften, die das Layoutverhalten in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelementen und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Elementen steuern, werden vom <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element entsprechend zugeordnet.  Weitere Informationen finden Sie unter [Eigenschaftenzuordnung von Windows Forms und WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md).  
  
### Layoutänderungen im gehosteten Steuerelement  
 Layoutänderungen im gehosteten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelement werden an [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] weitergeleitet, um Layoutupdates auszulösen.  Die <xref:System.Windows.UIElement.InvalidateMeasure%2A>\-Methode auf <xref:System.Windows.Forms.Integration.WindowsFormsHost> stellt sicher, dass Änderungen am Layout des gehosteten Steuerelements dazu führen, dass das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Layoutmodul ausgeführt wird.  
  
### Kontinuierlich skalierte Windows Forms\-Steuerelemente  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelemente, die die kontinuierliche Skalierung unterstützen, interagieren vollständig mit dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Layoutsystem.  Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element verwendet die <xref:System.Windows.FrameworkElement.MeasureOverride%2A>\-Methode und die <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>\-Methode wie gewohnt, um die Größe des gehosteten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelements anzupassen und es anzuordnen.  
  
### Größenanpassungsalgorithmus  
 Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element verwendet das folgende Verfahren, um die Größe des gehosteten Steuerelements anzupassen:  
  
1.  Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element überschreibt die <xref:System.Windows.FrameworkElement.MeasureOverride%2A>\-Methode und die <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>\-Methode.  
  
2.  Um die Größe des gehosteten Steuerelements zu bestimmen, ruft die <xref:System.Windows.FrameworkElement.MeasureOverride%2A>\-Methode die <xref:System.Windows.Forms.Control.GetPreferredSize%2A>\-Methode des gehosteten Steuerelements mit einer Einschränkung auf, die aus der an die <xref:System.Windows.FrameworkElement.MeasureOverride%2A>\-Methode weitergegebenen Einschränkung übersetzt wird.  
  
3.  Die <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>\-Methode versucht, das gehostete Steuerelement auf die gegebene Größeneinschränkung festzulegen.  
  
4.  Wenn die <xref:System.Windows.Forms.Control.Size%2A>\-Eigenschaft des gehosteten Steuerelements der angegebenen Einschränkung entspricht, wird die Größe des gehosteten Steuerelements der Einschränkung entsprechend angepasst.  
  
 Wenn die <xref:System.Windows.Forms.Control.Size%2A>\-Eigenschaft nicht mit der angegebenen Einschränkung übereinstimmt, wird die kontinuierliche Größenanpassung von dem gehosteten Steuerelement nicht unterstützt.  Zum Beispiel lässt das <xref:System.Windows.Forms.MonthCalendar>\-Steuerelement nur diskrete Größen zu.  Die zulässigen Größen für dieses Steuerelement bestehen aus Ganzzahlen \(welche die Monatszahl angeben\) für die Höhe und die Breite.  In solchen Fällen verhält sich das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element wie folgt:  
  
-   Wenn die <xref:System.Windows.Forms.Control.Size%2A>\-Eigenschaft eine größere Größe als die angegebene Einschränkung angibt, beschneidet das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element das gehostete Steuerelement.  Höhe und Breite werden getrennt behandelt, sodass das gehostete Steuerelement in beide Richtungen beschnitten werden kann.  
  
-   Wenn die <xref:System.Windows.Forms.Control.Size%2A>\-Eigenschaft eine kleinere Größe als die angegebene Einschränkung angibt, akzeptiert das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element diesen Größenwert und gibt den Wert an das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Layoutsystem zurück.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Exemplarische Vorgehensweise: Anordnen von Windows Forms\-Steuerelementen in WPF](../../../../docs/framework/wpf/advanced/walkthrough-arranging-windows-forms-controls-in-wpf.md)   
 [Anordnen von Windows Forms\-Steuerelementen in WPF\-Beispiel](http://go.microsoft.com/fwlink/?LinkID=159971)   
 [Eigenschaftenzuordnung von Windows Forms und WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)   
 [Migration und Interoperabilität](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)
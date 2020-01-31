---
title: 'Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem WindowsFormsHost-Element'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 74809167-bf8e-48b7-a2e7-b4ea08bc7d8c
ms.openlocfilehash: c076937d6431adf1750793d47ece88dc82edf95c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794101"
---
# <a name="walkthrough-mapping-properties-using-the-windowsformshost-element"></a>Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem WindowsFormsHost-Element

In dieser exemplarischen Vorgehensweise wird gezeigt, wie Sie die <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>-Eigenschaft verwenden, um den entsprechenden Eigenschaften eines gehosteten Windows Forms Steuer Elements [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften zuzuordnen.

In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:

- Erstellen des Projekts

- Definieren des Anwendungslayouts

- Definieren einer neuen Eigenschaftenzuordnung

- Entfernen einer standardmäßigen Eigenschaftenzuordnung

- Ersetzen einer standardmäßigen Eigenschaftenzuordnung

- Erweitern einer standardmäßigen Eigenschaftenzuordnung

Eine komplette Code Auflistung der Aufgaben in dieser exemplarischen Vorgehensweise finden Sie unter [Mapping Properties using the Windows Form shost Element Sample](https://go.microsoft.com/fwlink/?LinkID=160019).

Wenn Sie fertig sind, können Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften den entsprechenden Eigenschaften eines gehosteten Windows Forms Steuer Elements zuordnen.

## <a name="prerequisites"></a>Erforderliche Komponenten

Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:

- Visual Studio 2017

## <a name="create-and-set-up-the-project"></a>Erstellen und Einrichten des Projekts

1. Erstellen Sie ein **WPF-App** -Projekt mit dem Namen `PropertyMappingWithWfhSample`.

2. Fügen Sie in **Projektmappen-Explorer**einen Verweis auf die WindowsFormsIntegration-Assembly mit dem Namen "WindowsFormsIntegration. dll" hinzu.

3. Fügen Sie in **Projektmappen-Explorer**Verweise auf die Assemblys "System. Drawing" und "System. Windows. Forms" hinzu.

## <a name="defining-the-application-layout"></a>Definieren des Anwendungslayouts

Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]basierte Anwendung verwendet das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element, um ein Windows Forms-Steuerelement zu hosten.

### <a name="to-define-the-application-layout"></a>So definieren sie das Anwendungslayout

1. Öffnen Sie Window1. XAML im WPF-Designer.

2. Ersetzen Sie den vorhandenen Code durch folgenden Code:

     [!code-xaml[PropertyMappingWithWfhSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml#1)]

3. Öffnen Sie Window1.xaml.cs im Code-Editor.

4. Importieren Sie am Anfang der Datei die folgenden Namespaces.

     [!code-csharp[PropertyMappingWithWfhSample#20](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#20)]
     [!code-vb[PropertyMappingWithWfhSample#20](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#20)]

## <a name="defining-a-new-property-mapping"></a>Definieren einer neuen Eigenschaftenzuordnung

Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element stellt mehrere Standardeigenschaften Zuordnungen bereit. Sie fügen eine neue Eigenschaften Zuordnung hinzu, indem Sie die <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A>-Methode für die <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>des <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elements aufrufen.

### <a name="to-define-a-new-property-mapping"></a>Definieren einer neuen Eigenschaftenzuordnung

- Kopieren Sie den folgenden Code in die Definition für die `Window1`-Klasse.

     [!code-csharp[PropertyMappingWithWfhSample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#14)]
     [!code-vb[PropertyMappingWithWfhSample#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#14)]

     Mit der `AddClipMapping`-Methode wird eine neue Zuordnung für die <xref:System.Windows.UIElement.Clip%2A>-Eigenschaft hinzugefügt.

     Die `OnClipChange`-Methode übersetzt die <xref:System.Windows.UIElement.Clip%2A>-Eigenschaft in die Windows Forms<xref:System.Windows.Forms.Control.Region%2A>-Eigenschaft.

     Die `Window1_SizeChanged`-Methode behandelt das <xref:System.Windows.FrameworkElement.SizeChanged> Ereignis des Fensters und passt die Größe des Clippingbereichs an das Anwendungsfenster an.

## <a name="removing-a-default-property-mapping"></a>Entfernen einer standardmäßigen Eigenschaftenzuordnung

Entfernen Sie eine standardmäßige Eigenschaften Zuordnung, indem Sie die <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A>-Methode für die <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>des <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elements aufrufen.

### <a name="to-remove-a-default-property-mapping"></a>Entfernen einer standardmäßigen Eigenschaftenzuordnung

- Kopieren Sie den folgenden Code in die Definition für die `Window1`-Klasse.

     [!code-csharp[PropertyMappingWithWfhSample#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#13)]
     [!code-vb[PropertyMappingWithWfhSample#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#13)]

     Die `RemoveCursorMapping`-Methode löscht die Standard Zuordnung für die <xref:System.Windows.FrameworkElement.Cursor%2A>-Eigenschaft.

## <a name="replacing-a-default-property-mapping"></a>Ersetzen einer standardmäßigen Eigenschaftenzuordnung

Ersetzen Sie eine standardmäßige Eigenschaften Zuordnung, indem Sie die Standard Zuordnung entfernen und die <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A>-Methode für die <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>des <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elements aufrufen.

### <a name="to-replace-a-default-property-mapping"></a>So ersetzen Sie eine standardmäßige Eigenschaftenzuordnung

- Kopieren Sie den folgenden Code in die Definition für die `Window1`-Klasse.

     [!code-csharp[PropertyMappingWithWfhSample#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#12)]
     [!code-vb[PropertyMappingWithWfhSample#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#12)]

     Die `ReplaceFlowDirectionMapping`-Methode ersetzt die Standard Zuordnung für die <xref:System.Windows.FrameworkElement.FlowDirection%2A>-Eigenschaft.

     Die `OnFlowDirectionChange`-Methode übersetzt die <xref:System.Windows.FrameworkElement.FlowDirection%2A>-Eigenschaft in die Windows Forms<xref:System.Windows.Forms.Control.RightToLeft%2A>-Eigenschaft.

     Die `cb_CheckedChanged`-Methode behandelt das <xref:System.Windows.Forms.CheckBox.CheckedChanged>-Ereignis auf dem <xref:System.Windows.Forms.CheckBox>-Steuerelement. Die <xref:System.Windows.FrameworkElement.FlowDirection%2A>-Eigenschaft wird basierend auf dem Wert der <xref:System.Windows.Forms.CheckBox.CheckState%2A>-Eigenschaft zugewiesen.

## <a name="extending-a-default-property-mapping"></a>Erweitern einer standardmäßigen Eigenschaftenzuordnung

Sie können auch eine standardmäßige Eigenschaftenzuordnung verwenden und sie um Ihre eigenen Zuordnung erweitern.

### <a name="to-extend-a-default-property-mapping"></a>So erweitern Sie eine standardmäßigen Eigenschaftenzuordnung

- Kopieren Sie den folgenden Code in die Definition für die `Window1`-Klasse.

     [!code-csharp[PropertyMappingWithWfhSample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#15)]
     [!code-vb[PropertyMappingWithWfhSample#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#15)]

     Die `ExtendBackgroundMapping`-Methode fügt der vorhandenen <xref:System.Windows.Controls.Control.Background%2A> Eigenschaften Zuordnung einen benutzerdefinierten Eigenschaften Übersetzer hinzu.

     Die `OnBackgroundChange`-Methode weist ein bestimmtes Bild der <xref:System.Windows.Forms.Control.BackgroundImage%2A>-Eigenschaft des gehosteten Steuer Elements zu. Die `OnBackgroundChange`-Methode wird aufgerufen, nachdem die Standardeigenschaften Zuordnung angewendet wurde.

## <a name="initializing-your-property-mappings"></a>Initialisieren der Eigenschaftenzuordnungen

Richten Sie die Eigenschafts Zuordnungen ein, indem Sie die zuvor beschriebenen Methoden im <xref:System.Windows.FrameworkElement.Loaded>-Ereignishandler aufrufen.

### <a name="to-initialize-your-property-mappings"></a>So initialisieren Sie Ihre Eigenschaftenzuordnungen

1. Kopieren Sie den folgenden Code in die Definition für die `Window1`-Klasse.

     [!code-csharp[PropertyMappingWithWfhSample#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#11)]
     [!code-vb[PropertyMappingWithWfhSample#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#11)]

     Die `WindowLoaded`-Methode behandelt das <xref:System.Windows.FrameworkElement.Loaded>-Ereignis und führt die folgende Initialisierung aus.

    - Erstellt eine Windows Forms<xref:System.Windows.Forms.CheckBox> Steuer Elements.

    - Sie ruft die Methoden, die Sie zuvor in der exemplarischen Vorgehensweise definiert haben, auf, um die Eigenschaftenzuordnungen einzurichten.

    - Sie weist den zugeordneten Eigenschaften Anfangswerte zu.

2. Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen. Aktivieren Sie das Kontrollkästchen, um die Auswirkung der <xref:System.Windows.FrameworkElement.FlowDirection%2A> Zuordnung anzuzeigen. Wenn Sie das Kontrollkästchen klicken, kehrt das Layout seine Links-Rechts-Ausrichtung um.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Eigenschaftenzuordnung von Windows Forms und WPF](windows-forms-and-wpf-property-mapping.md)
- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)

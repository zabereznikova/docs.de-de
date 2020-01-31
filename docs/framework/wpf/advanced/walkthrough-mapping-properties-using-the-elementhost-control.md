---
title: 'Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem ElementHost-Steuerelement'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- ElementHost control [WPF], mapping properties
ms.assetid: bccd6e0d-2272-4924-9107-ff8ed58b88aa
ms.openlocfilehash: 7ff4ff607ab70b55cda1e2c4736ff773d4907a22
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794120"
---
# <a name="walkthrough-mapping-properties-using-the-elementhost-control"></a>Exemplarische Vorgehensweise: Zuordnen von Eigenschaften mit dem ElementHost-Steuerelement

In dieser exemplarischen Vorgehensweise wird gezeigt, wie Sie die <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>-Eigenschaft verwenden, um den entsprechenden Eigenschaften eines gehosteten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Elements Windows Forms Eigenschaften zuzuordnen.

In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:

- Erstellen des Projekts

- Definieren einer neuen Eigenschaftenzuordnung

- Entfernen einer standardmäßigen Eigenschaftenzuordnung

- Erweitern einer standardmäßigen Eigenschaftenzuordnung

Eine komplette Code Auflistung der Aufgaben, die in dieser exemplarischen Vorgehensweise veranschaulicht werden, finden [Sie unter Mapping Properties using the ElementHost Control Sample](https://go.microsoft.com/fwlink/?LinkID=160018).

Wenn Sie fertig sind, können Sie Windows Forms Eigenschaften den entsprechenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Eigenschaften für ein gehosteter Element zuordnen.

## <a name="prerequisites"></a>Erforderliche Komponenten

Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:

- Visual Studio 2017

## <a name="creating-the-project"></a>Erstellen des Projekts

### <a name="to-create-the-project"></a>So erstellen Sie das Projekt

1. Erstellen Sie ein **Windows Forms App** -Projekt mit dem Namen `PropertyMappingWithElementHost`.

2. Fügen Sie in **Projektmappen-Explorer**Verweise auf die folgenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Assemblys hinzu.

    - PresentationCore

    - PresentationFramework

    - WindowsBase

    - WindowsFormsIntegration

3. Kopieren Sie den folgenden Code an den Anfang der Codedatei `Form1`.

     [!code-csharp[PropertyMappingWithElementHost#10](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]

4. Öffnen Sie `Form1` im Windows Forms-Designer. Doppelklicken Sie auf das Formular, um einen Ereignishandler für das <xref:System.Windows.Forms.Form.Load>-Ereignis hinzuzufügen.

5. Kehren Sie zum Windows Forms-Designer zurück, und fügen Sie einen Ereignishandler für das <xref:System.Windows.Forms.Control.Resize>-Ereignis des Formulars hinzu. Weitere Informationen finden Sie unter Gewusst [wie: Erstellen von Ereignis Handlern mithilfe des Designers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).

6. Deklarieren Sie ein <xref:System.Windows.Forms.Integration.ElementHost> Feld in der `Form1`-Klasse.

     [!code-csharp[PropertyMappingWithElementHost#16](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]

## <a name="defining-new-property-mappings"></a>Definieren neuer Eigenschaften Zuordnungen

Das <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement stellt mehrere Standardeigenschaften Zuordnungen bereit. Sie fügen eine neue Eigenschaften Zuordnung hinzu, indem Sie die <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A>-Methode für die <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>des <xref:System.Windows.Forms.Integration.ElementHost> Steuer Elements aufrufen.

### <a name="to-define-new-property-mappings"></a>So definieren Sie neue Eigenschaften Zuordnungen

1. Kopieren Sie den folgenden Code in die Definition für die `Form1`-Klasse.

     [!code-csharp[PropertyMappingWithElementHost#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]

     Mit der `AddMarginMapping`-Methode wird eine neue Zuordnung für die <xref:System.Windows.Forms.Control.Margin%2A>-Eigenschaft hinzugefügt.

     Die `OnMarginChange`-Methode übersetzt die <xref:System.Windows.Forms.Control.Margin%2A>-Eigenschaft in die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A>-Eigenschaft.

2. Kopieren Sie den folgenden Code in die Definition für die `Form1`-Klasse.

     [!code-csharp[PropertyMappingWithElementHost#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]

     Mit der `AddRegionMapping`-Methode wird eine neue Zuordnung für die <xref:System.Windows.Forms.Control.Region%2A>-Eigenschaft hinzugefügt.

     Die `OnRegionChange`-Methode übersetzt die <xref:System.Windows.Forms.Control.Region%2A>-Eigenschaft in die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A>-Eigenschaft.

     Die `Form1_Resize`-Methode behandelt das <xref:System.Windows.Forms.Control.Resize>-Ereignis des Formulars und passt die Größe des Clippingbereichs an das gehostete Element an.

## <a name="removing-a-default-property-mapping"></a>Entfernen einer standardmäßigen Eigenschaftenzuordnung

Entfernen Sie eine standardmäßige Eigenschaften Zuordnung, indem Sie die <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A>-Methode für die <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>des <xref:System.Windows.Forms.Integration.ElementHost> Steuer Elements aufrufen.

### <a name="to-remove-a-default-property-mapping"></a>Entfernen einer standardmäßigen Eigenschaftenzuordnung

- Kopieren Sie den folgenden Code in die Definition für die `Form1`-Klasse.

     [!code-csharp[PropertyMappingWithElementHost#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]

     Die `RemoveCursorMapping`-Methode löscht die Standard Zuordnung für die <xref:System.Windows.Forms.Control.Cursor%2A>-Eigenschaft.

## <a name="extending-a-default-property-mapping"></a>Erweitern einer standardmäßigen Eigenschaftenzuordnung

Sie können auch eine standardmäßige Eigenschaftenzuordnung verwenden und sie um Ihre eigenen Zuordnung erweitern.

### <a name="to-extend-a-default-property-mapping"></a>So erweitern Sie eine standardmäßigen Eigenschaftenzuordnung

- Kopieren Sie den folgenden Code in die Definition für die `Form1`-Klasse.

     [!code-csharp[PropertyMappingWithElementHost#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]

     Die `ExtendBackColorMapping`-Methode fügt der vorhandenen <xref:System.Windows.Forms.Control.BackColor%2A> Eigenschaften Zuordnung einen benutzerdefinierten Eigenschaften Übersetzer hinzu.

     Die `OnBackColorChange`-Methode weist ein bestimmtes Bild der <xref:System.Windows.Controls.Control.Background%2A>-Eigenschaft des gehosteten Steuer Elements zu. Die `OnBackColorChange`-Methode wird aufgerufen, nachdem die Standardeigenschaften Zuordnung angewendet wurde.

## <a name="initialize-your-property-mappings"></a>Eigenschafts Zuordnungen initialisieren

1. Kopieren Sie den folgenden Code in die Definition für die `Form1`-Klasse.

     [!code-csharp[PropertyMappingWithElementHost#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]

     Die `Form1_Load`-Methode behandelt das <xref:System.Windows.Forms.Form.Load>-Ereignis und führt die folgende Initialisierung aus.

    - Erstellt eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button>-Elements.

    - Sie ruft die Methoden, die Sie zuvor in der exemplarischen Vorgehensweise definiert haben, auf, um die Eigenschaftenzuordnungen einzurichten.

    - Sie weist den zugeordneten Eigenschaften Anfangswerte zu.

2. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Eigenschaftenzuordnung von Windows Forms und WPF](windows-forms-and-wpf-property-mapping.md)
- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)

---
title: 'Exemplarische Vorgehensweise: Formatieren von WPF-Inhalt'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
ms.openlocfilehash: b689bb7299d541708db7ae786bff62a1007608e5
ms.sourcegitcommit: 682c64df0322c7bda016f8bfea8954e9b31f1990
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2019
ms.locfileid: "65557888"
---
# <a name="walkthrough-style-wpf-content"></a>Exemplarische Vorgehensweise: Style-WPF-Inhalt

In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie eine Formatvorlage auf ein WPF-Steuerelement (Windows Presentation Foundation) angewendet wird, das in einem Windows Form-Objekt gehostet wird.

 Im Verlauf dieser exemplarischen Vorgehensweise führen Sie die folgenden Aufgaben aus:

- Erstellen eines Projekts

- Erstellen des WPF-Steuerelementtyps

- Anwenden einer Formatvorlage auf die WPF-control.a

## <a name="prerequisites"></a>Vorraussetzungen

Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.

## <a name="create-the-project"></a>Erstellen eines Projekts

Öffnen Sie Visual Studio, und erstellen Sie ein neues Windows Forms-Anwendungsprojekt in Visual Basic oder Visual C# mit dem Namen `StylingWpfContent`.

> [!NOTE]
> Beim Hosten von WPF-Inhalt werden nur C#- und Visual Basic-Projekte unterstützt.

## <a name="create-the-wpf-control-types"></a>Erstellen der WPF-Steuerelementtypen

Nachdem Sie dem Projekt ein WPF-Steuerelement hinzugefügt haben, können Sie dieses in einem <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement hosten.

1. Fügen Sie der Projektmappe ein neues WPF-<xref:System.Windows.Controls.UserControl>-Projekt hinzu. Verwenden Sie den Standardnamen, `UserControl1.xaml`, für den Steuerelementtyp. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen von neuen WPF-Inhalts in Windows Forms zur Entwurfszeit](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).

2. Stellen Sie in der Entwurfsansicht sicher, dass `UserControl1` ausgewählt ist. Weitere Informationen finden Sie unter [Vorgehensweise: Wählen Sie aus, und verschieben Sie Elemente auf der Entwurfsoberfläche](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).

3. In der **Eigenschaften** legen den Wert des der <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften `200`.

4. Hinzufügen einer <xref:System.Windows.Controls.Button?displayProperty=nameWithType> die Steuerung an die <xref:System.Windows.Controls.UserControl> und legen Sie den Wert von der <xref:System.Windows.Controls.ContentControl.Content%2A> Eigenschaft **Abbrechen**.

5. Fügen Sie eine zweite <xref:System.Windows.Controls.Button?displayProperty=nameWithType> die Steuerung an die <xref:System.Windows.Controls.UserControl> und legen Sie den Wert von der <xref:System.Windows.Controls.ContentControl.Content%2A> Eigenschaft **OK**.

6. Erstellen Sie das Projekt.

## <a name="apply-a-style-to-a-wpf-control"></a>Anwenden einer Formatvorlage auf ein WPF-Steuerelement

Sie können verschiedene Formatvorlagen auf ein WPF-Steuerelement anwenden, um seine Darstellung und das Verhalten zu ändern.

1. Öffnen Sie `Form1` im Windows Forms-Designer.

1. In der **Toolbox**, doppelklicken Sie auf `UserControl1` zum Erstellen einer Instanz von `UserControl1` auf dem Formular.

     Eine Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement namens `elementHost1` gehostet.

1. Der Smarttagbereich für `elementHost1`, klicken Sie auf **gehosteten Inhalt bearbeiten** aus der Dropdown-Liste.

     `UserControl1` wird im [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] geöffnet.

1. Fügen Sie den folgenden XAML-Code in der XAML-Ansicht hinter dem `<UserControl>`-Starttag ein.

     Dieser XAML-Code erstellt einen Farbverlauf mit kontrastreichem Farbverlaufsrand. Wenn das Steuerelement angeklickt wird, werden die Farbverläufe geändert, um den Eindruck einer gedrückten Schaltfläche zu generieren. Weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../../wpf/controls/styling-and-templating.md).

   ```xaml
   <UserControl.Resources>
    <LinearGradientBrush x:Key="NormalBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#FFF" Offset="0.0"/>
        <GradientStop Color="#CCC" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="PressedBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#BBB" Offset="0.0"/>
        <GradientStop Color="#EEE" Offset="0.1"/>
        <GradientStop Color="#EEE" Offset="0.9"/>
        <GradientStop Color="#FFF" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="NormalBorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#CCC" Offset="0.0"/>
        <GradientStop Color="#444" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="BorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#CCC" Offset="0.0"/>
        <GradientStop Color="#444" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="PressedBorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#444" Offset="0.0"/>
        <GradientStop Color="#888" Offset="1.0"/>
    </LinearGradientBrush>

    <Style x:Key="SimpleButton" TargetType="{x:Type Button}" BasedOn="{x:Null}">
        <Setter Property="Background" Value="{StaticResource NormalBrush}"/>
        <Setter Property="BorderBrush" Value="{StaticResource NormalBorderBrush}"/>
        <Setter Property="Template">
            <Setter.Value>
                <ControlTemplate TargetType="{x:Type Button}">
                    <Grid x:Name="Grid">
                        <Border x:Name="Border" Background="{TemplateBinding Background}" BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Padding="{TemplateBinding Padding}"/>
                        <ContentPresenter HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}" RecognizesAccessKey="True"/>
                    </Grid>
                    <ControlTemplate.Triggers>
                        <Trigger Property="IsPressed" Value="true">
                            <Setter Property="Background" Value="{StaticResource PressedBrush}" TargetName="Border"/>
                            <Setter Property="BorderBrush" Value="{StaticResource PressedBorderBrush}" TargetName="Border"/>
                        </Trigger>
                    </ControlTemplate.Triggers>
                </ControlTemplate>
            </Setter.Value>
        </Setter>
    </Style>
   </UserControl.Resources>
   ```

1. Wenden Sie die im vorherigen Schritt definierte `SimpleButton`-Formatvorlage auf die „Cancel“-Schaltfläche an, indem Sie den folgenden XAML-Code im `<Button>`-Tag der „Cancel“-Schaltfläche einfügen.

   ```xaml
   Style="{StaticResource SimpleButton}
   ```

   Ihre Schaltflächendeklaration wird der folgende XAML ähneln:

   ```xaml
   <Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"
                Style="{StaticResource SimpleButton}">Cancel</Button>
   ```

1. Erstellen Sie das Projekt.

1. Öffnen Sie `Form1` im Windows Forms-Designer.

1. Die neue Formatvorlage wird auf das Schaltflächensteuerelement angewendet.

1. Von der **Debuggen** , wählen Sie im Menü **Debuggen starten** zum Ausführen der Anwendung.

1. Klicken Sie auf die Schaltflächen "OK" und "Cancel", und beobachten Sie die Unterschiede.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Migration und Interoperabilität](../../wpf/advanced/migration-and-interoperability.md)
- [Verwenden von WPF-Steuerelementen](using-wpf-controls.md)
- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Übersicht über XAML (WPF)](../../wpf/advanced/xaml-overview-wpf.md)
- [Erstellen von Formaten und Vorlagen](../../wpf/controls/styling-and-templating.md)

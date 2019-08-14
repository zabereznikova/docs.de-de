---
title: 'Exemplarische Vorgehensweise: Formatieren von WPF-Inhalt'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
ms.openlocfilehash: 32ca9658ddf4ab6e8690f29797b7ac7b09df2ca7
ms.sourcegitcommit: d98fdb087d9c8aba7d2cb93fe4b4ee35a2308cee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2019
ms.locfileid: "69012958"
---
# <a name="walkthrough-style-wpf-content"></a>Exemplarische Vorgehensweise: Stil von WPF-Inhalt

In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie eine Formatvorlage auf ein WPF-Steuerelement (Windows Presentation Foundation) angewendet wird, das in einem Windows Form-Objekt gehostet wird.

 Im Verlauf dieser exemplarischen Vorgehensweise führen Sie die folgenden Aufgaben aus:

- Erstellen eines Projekts

- Erstellen des WPF-Steuerelementtyps

- Zuweisen einer Formatvorlage zum WPF-Steuerelement

## <a name="prerequisites"></a>Vorraussetzungen

Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.

## <a name="create-the-project"></a>Erstellen eines Projekts

Öffnen Sie Visual Studio, und erstellen Sie ein neues Windows Forms-Anwendungsprojekt C# in `StylingWpfContent`Visual Basic oder Visual mit dem Namen.

> [!NOTE]
> Beim Hosten von WPF-Inhalt werden nur C#- und Visual Basic-Projekte unterstützt.

## <a name="create-the-wpf-control-types"></a>Erstellen der WPF-Steuerelement Typen

Nachdem Sie dem Projekt ein WPF-Steuerelement hinzugefügt haben, können Sie dieses in einem <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement hosten.

1. Fügen Sie der Projektmappe ein neues WPF-<xref:System.Windows.Controls.UserControl>-Projekt hinzu. Verwenden Sie den Standardnamen, `UserControl1.xaml`, für den Steuerelementtyp. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen eines neuen WPF-Inhalts auf Windows Forms zur](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)Entwurfszeit.

2. Stellen Sie in der Entwurfsansicht sicher, dass `UserControl1` ausgewählt ist. Weitere Informationen finden Sie unter [Vorgehensweise: Auswählen und Verschieben von Elementen auf der](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100))Designoberfläche

3. Legen Sie im Fenster **Eigenschaften** den Wert <xref:System.Windows.FrameworkElement.Width%2A> der-Eigenschaft und der- `200` <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaft auf fest.

4. Fügen Sie <xref:System.Windows.Controls.Button?displayProperty=nameWithType> ein <xref:System.Windows.Controls.UserControl> -Steuerelement hinzu, und <xref:System.Windows.Controls.ContentControl.Content%2A> legen Sie den Wert der-Eigenschaft auf **Cancel**fest.

5. Fügen Sie ein <xref:System.Windows.Controls.Button?displayProperty=nameWithType> zweites <xref:System.Windows.Controls.UserControl> -Steuerelement hinzu, und <xref:System.Windows.Controls.ContentControl.Content%2A> legen Sie den Wert der-Eigenschaft auf **OK**fest.

6. Erstellen Sie das Projekt.

## <a name="apply-a-style-to-a-wpf-control"></a>Anwenden eines Stils auf ein WPF-Steuerelement

Sie können verschiedene Formatvorlagen auf ein WPF-Steuerelement anwenden, um seine Darstellung und das Verhalten zu ändern.

1. Öffnen Sie `Form1` im Windows Forms-Designer.

1. DoppelklickenSie `UserControl1` in der Toolbox auf, um eine Instanz von `UserControl1` auf dem Formular zu erstellen.

     Eine Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement namens `elementHost1` gehostet.

1. Klicken Sie im smarttagpanel für `elementHost1`in der Dropdown Liste auf **gehosteten Inhalt bearbeiten** .

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

   Die Schaltflächen Deklaration ähnelt der folgenden XAML:

   ```xaml
   <Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"
                Style="{StaticResource SimpleButton}">Cancel</Button>
   ```

1. Erstellen Sie das Projekt.

1. Öffnen Sie `Form1` im Windows Forms-Designer.

1. Die neue Formatvorlage wird auf das Schaltflächensteuerelement angewendet.

1. Wählen Sie im Menü **Debuggen** die Option **Debuggen starten** , um die Anwendung auszuführen.

1. Klicken Sie auf die Schaltflächen "OK" und "Cancel", und beobachten Sie die Unterschiede.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Migration und Interoperabilität](../../wpf/advanced/migration-and-interoperability.md)
- [Verwenden von WPF-Steuerelementen](using-wpf-controls.md)
- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Übersicht über XAML (WPF)](../../wpf/advanced/xaml-overview-wpf.md)
- [Erstellen von Formaten und Vorlagen](../../wpf/controls/styling-and-templating.md)

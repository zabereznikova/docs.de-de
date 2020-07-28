---
title: 'Exemplarische Vorgehensweise: Erstellen einer Schaltfläche mit XAML'
description: In dieser exemplarischen Vorgehensweise erfahren Sie, wie Sie eine animierte Schaltfläche zur Verwendung in einer Windows Presentation Foundation Anwendung mithilfe von XAML erstellen.
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
ms.openlocfilehash: 136d1ad5d6fefd70f0d977e5287ae75f06c52d36
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164850"
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a>Exemplarische Vorgehensweise: Erstellen einer Schaltfläche mit XAML

In dieser exemplarischen Vorgehensweise erfahren Sie, wie Sie eine animierte Schaltfläche zur Verwendung in einer Windows Presentation Foundation (WPF)-Anwendung erstellen. Diese exemplarische Vorgehensweise verwendet Stile und eine Vorlage, um eine angepasste Schaltflächen Ressource zu erstellen, die die Wiederverwendung von Code und die Trennung der Schaltflächen Logik von der Schaltflächen Deklaration Diese exemplarische Vorgehensweise ist vollständig in geschrieben [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] .

> [!IMPORTANT]
> Diese exemplarische Vorgehensweise führt Sie durch die Schritte zum Erstellen der Anwendung, indem Sie in Visual Studio eingeben oder kopieren und einfügen [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] . Wenn Sie lieber erfahren möchten, wie Sie einen Designer verwenden, um dieselbe Anwendung zu erstellen, finden Sie unter [Erstellen einer Schaltfläche mit Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)Weitere Informationen.

In der folgenden Abbildung sind die Schaltflächen fertig angezeigt.

![Benutzerdefinierte Schaltflächen, die mit XAML erstellt wurden](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")

## <a name="create-basic-buttons"></a>Grundlegende Schaltflächen erstellen

Erstellen Sie zunächst ein neues Projekt, und fügen Sie dem Fenster einige Schaltflächen hinzu.

### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a>So erstellen Sie ein neues WPF-Projekt und fügen dem Fenster Schaltflächen hinzu

1. Starten Sie Visual Studio.

2. **Erstellen Sie ein neues WPF-Projekt:** Zeigen Sie im Menü **Datei** auf **neu**, und klicken Sie dann auf **Projekt**. Suchen Sie die Vorlage **Windows-Anwendung (WPF)** , und benennen Sie das Projekt mit dem Namen "AnimatedButton". Dadurch wird das Gerüst für die Anwendung erstellt.

3. **Einfache Standard Schaltflächen hinzufügen:** Alle Dateien, die Sie für diese exemplarische Vorgehensweise benötigen, werden von der Vorlage bereitgestellt. Öffnen Sie die Datei Window1. XAML, indem Sie in Projektmappen-Explorer auf die Datei doppelklicken. Standardmäßig ist ein- <xref:System.Windows.Controls.Grid> Element in Window1. XAML vorhanden. Entfernen <xref:System.Windows.Controls.Grid> Sie das-Element, und fügen Sie der Seite einige Schaltflächen hinzu, [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] indem Sie den folgenden hervorgehobenen Code in Window1. xaml eingeben oder kopieren und einfügen:

    ```xaml
    <Window x:Class="AnimatedButton.Window1"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      Title="AnimatedButton" Height="300" Width="300"
      Background="Black">
      <!-- Buttons arranged vertically inside a StackPanel. -->
      <StackPanel HorizontalAlignment="Left">
          <Button>Button 1</Button>
          <Button>Button 2</Button>
          <Button>Button 3</Button>
      </StackPanel>
    </Window>
    ```

     Drücken Sie F5, um die Anwendung auszuführen. Es sollte eine Reihe von Schaltflächen angezeigt werden, die wie in der folgenden Abbildung aussehen.

     ![Drei grundlegende Schaltflächen](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")

     Nachdem Sie nun die grundlegenden Schaltflächen erstellt haben, sind Sie mit der Arbeit in der Datei Window1. XAML fertig. Der Rest der exemplarischen Vorgehensweise konzentriert sich auf die Datei app. XAML, in der Stile und eine Vorlage für die Schaltflächen definiert werden.

## <a name="set-basic-properties"></a>Festlegen von grundlegenden Eigenschaften

Als nächstes legen wir einige Eigenschaften für diese Schaltflächen fest, um die Darstellung und das Layout der Schaltfläche zu steuern. Anstatt die Eigenschaften für die Schaltflächen einzeln festzulegen, verwenden Sie Ressourcen, um Schaltflächen Eigenschaften für die gesamte Anwendung zu definieren. Anwendungs Ressourcen sind konzeptionell vergleichbar mit externen Cascading Stylesheets (CSS) für Webseiten. Ressourcen sind jedoch viel leistungsfähiger als Cascading Stylesheets (CSS), wie Sie am Ende dieser exemplarischen Vorgehensweise sehen werden. Weitere Informationen zu Ressourcen finden Sie unter [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md).

### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a>So verwenden Sie Stile zum Festlegen grundlegender Eigenschaften auf den Schaltflächen

1. **Definieren eines "Application. Resources"-Blocks:** Öffnen Sie App. XAML, und fügen Sie das folgende hervorgehobene Markup hinzu, wenn es nicht bereits vorhanden ist:

    ```xaml
    <Application x:Class="AnimatedButton.App"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      StartupUri="Window1.xaml"
      >
      <Application.Resources>
        <!-- Resources for the entire application can be defined here. -->
      </Application.Resources>
    </Application>
    ```

     Der Ressourcenbereich wird bestimmt, wo Sie die Ressource definieren. Durch Definieren von Ressourcen in `Application.Resources` in der Datei "App. XAML" kann die Ressource von überall in der Anwendung verwendet werden. Weitere Informationen zum Definieren des Umfangs ihrer Ressourcen finden Sie unter [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md).

2. **Erstellen Sie einen Stil, und definieren Sie grundlegende Eigenschaftswerte damit:** Fügen Sie dem-Block das folgende Markup hinzu `Application.Resources` . Dieses Markup erstellt eine <xref:System.Windows.Style> , die für alle Schaltflächen in der Anwendung gilt, wobei der <xref:System.Windows.FrameworkElement.Width%2A> der Schaltflächen auf 90 und auf 10 festgelegt wird <xref:System.Windows.FrameworkElement.Margin%2A> :

    ```xaml
    <Application.Resources>
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     Die- <xref:System.Windows.Style.TargetType%2A> Eigenschaft gibt an, dass der Stil für alle Objekte vom Typ gilt <xref:System.Windows.Controls.Button> . Jeder <xref:System.Windows.Setter> legt einen anderen Eigenschafts Wert für fest <xref:System.Windows.Style> . Daher hat an diesem Punkt jede Schaltfläche in der Anwendung eine Breite von 90 und einen Rand von 10.  Wenn Sie F5 drücken, um die Anwendung auszuführen, wird das folgende Fenster angezeigt.

     ![Schaltflächen mit einer Breite von 90 und einem Rand von 10](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")

     Es gibt noch viel mehr Möglichkeiten mit Stilen, einschließlich einer Vielzahl von Möglichkeiten, um zu optimieren, welche Objekte als Ziel verwendet werden, wie komplexe Eigenschaftswerte angegeben werden, und sogar Stile als Eingabe für andere Stile verwendet werden. Weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md).

3. **Legen Sie einen Stil Eigenschafts Wert auf eine Ressource fest:** Ressourcen ermöglichen eine einfache Möglichkeit, häufig definierte Objekte und Werte wiederzuverwenden. Es ist besonders hilfreich, komplexe Werte mithilfe von Ressourcen zu definieren, um den Code modularer zu gestalten. Fügen Sie der Datei "App. XAML" das folgende hervorgehobene Markup hinzu.

    ```xaml
    <Application.Resources>
      <LinearGradientBrush x:Key="GrayBlueGradientBrush" StartPoint="0,0" EndPoint="1,1">
        <GradientStop Color="DarkGray" Offset="0" />
        <GradientStop Color="#CCCCFF" Offset="0.5" />
        <GradientStop Color="DarkGray" Offset="1" />
      </LinearGradientBrush>
      <Style TargetType="{x:Type Button}">
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />
        <Setter Property="Width" Value="80" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     Direkt unter dem- `Application.Resources` Block haben Sie eine Ressource mit dem Namen "GrayBlueGradientBrush" erstellt. Diese Ressource definiert einen horizontalen Farbverlauf. Diese Ressource kann als Eigenschafts Wert von jeder beliebigen Stelle in der Anwendung verwendet werden, einschließlich der Schaltfläche für den Schaltflächen Stil für die <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft. Jetzt haben alle Schaltflächen einen <xref:System.Windows.Controls.Control.Background%2A> Eigenschafts Wert dieses Farbverlaufs.

     Drücken Sie die Taste F5, um die Anwendung auszuführen. Es sollte wie folgt aussehen.

     ![Schaltflächen mit einem Farbverlaufshintergrund](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")

## <a name="create-a-template-that-defines-the-look-of-the-button"></a>Erstellen einer Vorlage, die das Aussehen der Schaltfläche definiert

In diesem Abschnitt erstellen Sie eine Vorlage, mit der die Darstellung (Darstellung) der Schaltfläche angepasst wird. Die Darstellung der Schaltfläche besteht aus mehreren Objekten, einschließlich Rechtecke und anderen Komponenten, um der Schaltfläche ein eindeutiges aussehen zu verschaffen.

Bisher wurde die Steuerung, wie Schaltflächen in der Anwendung aussehen, auf das Ändern der Eigenschaften der Schaltfläche beschränkt. Was geschieht, wenn Sie radikale Änderungen an der Darstellung der Schaltfläche vornehmen möchten? Vorlagen ermöglichen eine leistungsstarke Kontrolle über die Darstellung eines Objekts. Da Vorlagen in Stilen verwendet werden können, können Sie eine Vorlage auf alle Objekte anwenden, auf die sich der Stil bezieht (in dieser exemplarischen Vorgehensweise die Schaltfläche).

### <a name="to-use-the-template-to-define-the-look-of-the-button"></a>So definieren Sie mit der Vorlage das Aussehen der Schaltfläche

1. **Einrichten der Vorlage:** Da Steuerelemente wie <xref:System.Windows.Controls.Button> über eine- <xref:System.Windows.Controls.Control.Template%2A> Eigenschaft verfügen, können Sie den Eigenschafts Wert der Vorlage genau wie die anderen Eigenschaftswerte definieren, die wir in einem mithilfe von festgelegt haben <xref:System.Windows.Style> <xref:System.Windows.Setter> . Fügen Sie dem Schaltflächen Stil das folgende hervorgehobene Markup hinzu.

    ```xaml
    <Application.Resources>
      <LinearGradientBrush x:Key="GrayBlueGradientBrush"
        StartPoint="0,0" EndPoint="1,1">
        <GradientStop Color="DarkGray" Offset="0" />
        <GradientStop Color="#CCCCFF" Offset="0.5" />
        <GradientStop Color="DarkGray" Offset="1" />
      </LinearGradientBrush>
      <Style TargetType="{x:Type Button}">
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />
        <Setter Property="Width" Value="80" />
        <Setter Property="Margin" Value="10" />
        <Setter Property="Template">
          <Setter.Value>
            <!-- The button template is defined here. -->
          </Setter.Value>
        </Setter>
      </Style>
    </Application.Resources>
    ```

2. **Alter Button-Präsentation:** An diesem Punkt müssen Sie die Vorlage definieren. Fügen Sie das folgende hervorgehobene Markup hinzu. Dieses Markup gibt zwei <xref:System.Windows.Shapes.Rectangle> Elemente mit abgerundeten Kanten an, gefolgt von einer <xref:System.Windows.Controls.DockPanel> . Der <xref:System.Windows.Controls.DockPanel> wird zum Hosten des <xref:System.Windows.Controls.ContentPresenter> der Schaltfläche verwendet. Ein <xref:System.Windows.Controls.ContentPresenter> zeigt den Inhalt der Schaltfläche an. In dieser exemplarischen Vorgehensweise ist der Inhalt Text ("Button 1", "Button 2", "Schaltfläche 3"). Alle Vorlagen Komponenten (Rechtecke und <xref:System.Windows.Controls.DockPanel> ) werden in einer angeordnet <xref:System.Windows.Controls.Grid> .

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="Button">
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}" ClipToBounds="True">
          <!-- Outer Rectangle with rounded corners. -->
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}" RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />
          <!-- Inner Rectangle with rounded corners. -->
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20" Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />
          <!-- Present Content (text) of the button. -->
          <DockPanel Name="myContentPresenterDockPanel">
            <ContentPresenter x:Name="myContentPresenter" Margin="20" Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
          </DockPanel>
        </Grid>
      </ControlTemplate>
    </Setter.Value>
    ```

     Drücken Sie die Taste F5, um die Anwendung auszuführen. Es sollte wie folgt aussehen.

     ![Fenster mit drei Schaltflächen](./media/custom-button-animatedbutton-4.gif)

3. **Fügen Sie der Vorlage einen glasseffect hinzu:** Als Nächstes fügen Sie das Glas hinzu. Zuerst erstellen Sie einige Ressourcen, die einen Glas Farbverlaufs Effekt erzeugen. Fügen Sie diese Farbverlaufs Ressourcen an einer beliebigen Stelle innerhalb des `Application.Resources` Blocks

    ```xaml
    <Application.Resources>
      <GradientStopCollection x:Key="MyGlassGradientStopsResource">
        <GradientStop Color="WhiteSmoke" Offset="0.2" />
        <GradientStop Color="Transparent" Offset="0.4" />
        <GradientStop Color="WhiteSmoke" Offset="0.5" />
        <GradientStop Color="Transparent" Offset="0.75" />
        <GradientStop Color="WhiteSmoke" Offset="0.9" />
        <GradientStop Color="Transparent" Offset="1" />
      </GradientStopCollection>
      <LinearGradientBrush x:Key="MyGlassBrushResource"
        StartPoint="0,0" EndPoint="1,1" Opacity="0.75"
        GradientStops="{StaticResource MyGlassGradientStopsResource}" />
    <!-- Styles and other resources below here. -->
    ```

     Diese Ressourcen werden als <xref:System.Windows.Shapes.Shape.Fill%2A> für ein Rechteck verwendet, das in die <xref:System.Windows.Controls.Grid> der Schaltflächen Vorlage eingefügt wird. Fügen Sie der Vorlage das folgende hervorgehobene Markup hinzu.

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="{x:Type Button}">
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}"
          ClipToBounds="True">

        <!-- Outer Rectangle with rounded corners. -->
        <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />

        <!-- Inner Rectangle with rounded corners. -->
        <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20"
          Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />

        <!-- Glass Rectangle -->
        <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch"
          StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"
          Fill="{StaticResource MyGlassBrushResource}"
          RenderTransformOrigin="0.5,0.5">
          <Rectangle.Stroke>
            <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">
              <LinearGradientBrush.GradientStops>
                <GradientStop Offset="0.0" Color="LightBlue" />
                <GradientStop Offset="1.0" Color="Gray" />
              </LinearGradientBrush.GradientStops>
            </LinearGradientBrush>
          </Rectangle.Stroke>
          <!-- These transforms have no effect as they are declared here.
          The reason the transforms are included is to be targets
          for animation (see later). -->
          <Rectangle.RenderTransform>
            <TransformGroup>
              <ScaleTransform />
              <RotateTransform />
            </TransformGroup>
          </Rectangle.RenderTransform>
          <!-- A BevelBitmapEffect is applied to give the button a "Beveled" look. -->
          <Rectangle.BitmapEffect>
            <BevelBitmapEffect />
          </Rectangle.BitmapEffect>
        </Rectangle>

        <!-- Present Text of the button. -->
        <DockPanel Name="myContentPresenterDockPanel">
          <ContentPresenter x:Name="myContentPresenter" Margin="20"
            Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
        </DockPanel>
      </Grid>
    </ControlTemplate>
    </Setter.Value>
    ```

     Beachten Sie, dass der <xref:System.Windows.UIElement.Opacity%2A> des Rechtecks mit der- `x:Name` Eigenschaft von "glassCube" den Wert 0 hat. Wenn Sie das Beispiel ausführen, wird das Glas Rechteck nicht oberhalb der oberen Position angezeigt. Dies liegt daran, dass später der Vorlage Trigger hinzugefügt werden, wenn der Benutzer mit der Schaltfläche interagiert. Sie können jedoch sehen, wie die Schaltfläche jetzt aussieht, indem Sie den <xref:System.Windows.UIElement.Opacity%2A> Wert in 1 ändern und die Anwendung ausführen. Dies wird in der folgenden Abbildung veranschaulicht. Bevor Sie mit dem nächsten Schritt fortfahren, ändern <xref:System.Windows.UIElement.Opacity%2A> Sie zurück in 0.

     ![Benutzerdefinierte Schaltflächen, die mit XAML erstellt wurden](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")

## <a name="create-button-interactivity"></a>Interaktivität zum Erstellen einer Schaltfläche

In diesem Abschnitt erstellen Sie Eigenschafts Trigger und Ereignis Trigger, um Eigenschaftswerte zu ändern und Animationen als Reaktion auf Benutzeraktionen auszuführen, z. b. das Bewegen des Mauszeigers über die Schaltfläche und das Klicken auf.

Eine einfache Möglichkeit, Interaktivität hinzuzufügen (Mouseover, Mouseover, Click usw.), besteht darin, Trigger innerhalb Ihrer Vorlage oder Ihres Stils zu definieren. Um einen zu erstellen <xref:System.Windows.Trigger> , definieren Sie eine Eigenschaft "Bedingung", z. b <xref:System.Windows.UIElement.IsMouseOver%2A> .: der Eigenschafts Wert der Schaltfläche ist gleich `true` . Dann definieren Sie Setter (Aktionen), die stattfinden, wenn die Auslöserbedingung erfüllt ist.

### <a name="to-create-button-interactivity"></a>So erstellen Sie Schaltflächen-Interaktivität

1. **Vorlagen Trigger hinzufügen:** Fügen Sie der Vorlage das hervorgehobene Markup hinzu.

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="{x:Type Button}">
        <Grid Width="{TemplateBinding Width}"
          Height="{TemplateBinding Height}" ClipToBounds="True">

          <!-- Outer Rectangle with rounded corners. -->
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />

          <!-- Inner Rectangle with rounded corners. -->
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"
            VerticalAlignment="Stretch" Stroke="Transparent"
            StrokeThickness="20"
            Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20"
          />

          <!-- Glass Rectangle -->
          <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"
            VerticalAlignment="Stretch"
            StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"
            Fill="{StaticResource MyGlassBrushResource}"
            RenderTransformOrigin="0.5,0.5">
            <Rectangle.Stroke>
              <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">
                <LinearGradientBrush.GradientStops>
                  <GradientStop Offset="0.0" Color="LightBlue" />
                  <GradientStop Offset="1.0" Color="Gray" />
                </LinearGradientBrush.GradientStops>
              </LinearGradientBrush>
            </Rectangle.Stroke>

            <!-- These transforms have no effect as they
                 are declared here.
                 The reason the transforms are included is to be targets
                 for animation (see later). -->
            <Rectangle.RenderTransform>
              <TransformGroup>
                <ScaleTransform />
                <RotateTransform />
              </TransformGroup>
            </Rectangle.RenderTransform>

              <!-- A BevelBitmapEffect is applied to give the button a
                   "Beveled" look. -->
            <Rectangle.BitmapEffect>
              <BevelBitmapEffect />
            </Rectangle.BitmapEffect>
          </Rectangle>

          <!-- Present Text of the button. -->
          <DockPanel Name="myContentPresenterDockPanel">
            <ContentPresenter x:Name="myContentPresenter" Margin="20"
              Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
          </DockPanel>
        </Grid>

        <ControlTemplate.Triggers>       <!-- Set action triggers for the buttons and define            what the button does in response to those triggers. -->     </ControlTemplate.Triggers>
      </ControlTemplate>
    </Setter.Value>
    ```

2. **Eigenschafts Trigger hinzufügen:** Fügen Sie dem Block das hervorgehobene Markup hinzu `ControlTemplate.Triggers` :

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>

    <ControlTemplate.Triggers/>
    ```

     Drücken Sie F5, um die Anwendung auszuführen, und sehen Sie sich den Effekt an, während Sie den Mauszeiger über den Schaltflächen ausführen.

3. **Hinzufügen eines Fokus Auslösers:** Als Nächstes fügen wir einige ähnliche Setter hinzu, um den Fall zu behandeln, dass die Schaltfläche den Fokus besitzt (z. b. Nachdem der Benutzer darauf geklickt hat).

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->
      <Trigger Property="IsMouseOver" Value="True">

        <!-- Below are three property settings that occur when the
             condition is met (user mouses over button).  -->
        <!-- Change the color of the outer rectangle when user          mouses over it. -->
        <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"
          Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />

        <!-- Sets the glass opacity to 1, therefore, the          glass "appears" when user mouses over it. -->
        <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />

        <!-- Makes the text slightly blurry as though you were          looking at it through blurry glass. -->
        <Setter Property="ContentPresenter.BitmapEffect"       TargetName="myContentPresenter">
          <Setter.Value>
            <BlurBitmapEffect Radius="1" />
          </Setter.Value>
        </Setter>
      </Trigger>
      <!-- Set properties when button has focus. -->   <Trigger Property="IsFocused" Value="true">     <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />     <Setter Property="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />   </Trigger>

    </ControlTemplate.Triggers>
    ```

     Drücken Sie F5, um die Anwendung auszuführen, und klicken Sie auf eine der Schaltflächen. Beachten Sie, dass die Schaltfläche hervorgehoben bleibt, nachdem Sie darauf geklickt haben, da Sie noch den Fokus besitzt Wenn Sie auf eine andere Schaltfläche klicken, erhält die neue Schaltfläche den Fokus, während der letzte die Schaltfläche verliert.

4. **Animationen hinzufügen für** <xref:System.Windows.UIElement.MouseEnter> **und** <xref:System.Windows.UIElement.MouseLeave> **:** Als Nächstes fügen wir den Triggern einige Animationen hinzu.   Fügen Sie das folgende Markup an einer beliebigen Stelle innerhalb des- `ControlTemplate.Triggers` Blocks hinzu.

    ```xaml
    <!-- Animations that start when mouse enters and leaves button. -->
    <EventTrigger RoutedEvent="Mouse.MouseEnter">
      <EventTrigger.Actions>
        <BeginStoryboard Name="mouseEnterBeginStoryboard">
          <Storyboard>
          <!-- This animation makes the glass rectangle shrink in the X direction. -->
            <DoubleAnimation Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleX)"
              By="-0.1" Duration="0:0:0.5" />
            <!-- This animation makes the glass rectangle shrink in the Y direction. -->
            <DoubleAnimation
            Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleY)"
              By="-0.1" Duration="0:0:0.5" />
          </Storyboard>
        </BeginStoryboard>
      </EventTrigger.Actions>
    </EventTrigger>
    <EventTrigger RoutedEvent="Mouse.MouseLeave">
      <EventTrigger.Actions>
        <!-- Stopping the storyboard sets all animated properties back to default. -->
        <StopStoryboard BeginStoryboardName="mouseEnterBeginStoryboard" />
      </EventTrigger.Actions>
    </EventTrigger>
    ```

     Das Glas Rechteck verkleinert sich, wenn der Mauszeiger über die Schaltfläche bewegt wird, und kehrt zur normalen Größe zurück, wenn der Zeiger verlässt.

     Zwei Animationen werden ausgelöst, wenn der Mauszeiger über die Schaltfläche bewegt wird (das- <xref:System.Windows.UIElement.MouseEnter> Ereignis wird ausgelöst). Diese Animationen verkleinern das Glas Rechteck entlang der X-und Y-Achse. Beachten Sie die Eigenschaften der <xref:System.Windows.Media.Animation.DoubleAnimation> Elemente – <xref:System.Windows.Media.Animation.Timeline.Duration%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> . Der <xref:System.Windows.Media.Animation.Timeline.Duration%2A> gibt an, dass die Animation über eine halbe Sekunde ausgeführt wird, und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> gibt an, dass das Glas um 10% verkleinert wird.

     Der zweite Ereignis auslöst ( <xref:System.Windows.UIElement.MouseLeave> ) beendet einfach den ersten. Wenn Sie ein Beenden <xref:System.Windows.Media.Animation.Storyboard> , werden alle animierten Eigenschaften auf die Standardwerte zurückgegeben. Wenn der Benutzer den Mauszeiger auf die Schaltfläche verschiebt, wird die Schaltfläche auf die Art und Weise zurückgesetzt, in der sich der Mauszeiger über die Schaltfläche bewegt hat. Weitere Informationen zu Animationen finden Sie unter [Übersicht](../graphics-multimedia/animation-overview.md)über Animationen.

5. **Fügen Sie eine Animation für hinzu, wenn auf die Schaltfläche geklickt wird:** Der letzte Schritt ist das Hinzufügen eines-Auslösers, wenn der Benutzer auf die Schaltfläche klickt. Fügen Sie das folgende Markup an einer beliebigen Stelle innerhalb des- `ControlTemplate.Triggers` Blocks hinzu:

    ```xaml
    <!-- Animation fires when button is clicked, causing glass to spin.  -->
    <EventTrigger RoutedEvent="Button.Click">
      <EventTrigger.Actions>
        <BeginStoryboard>
          <Storyboard>
            <DoubleAnimation Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[1].(RotateTransform.Angle)"
              By="360" Duration="0:0:0.5" />
          </Storyboard>
        </BeginStoryboard>
      </EventTrigger.Actions>
    </EventTrigger>
    ```

     Drücken Sie F5, um die Anwendung auszuführen, und klicken Sie auf eine der Schaltflächen. Wenn Sie auf eine Schaltfläche klicken, dreht sich das Glas Rechteck herum.

## <a name="summary"></a>Zusammenfassung
 In dieser exemplarischen Vorgehensweise haben Sie die folgenden Übungen ausgeführt:

- Als Ziel <xref:System.Windows.Style> für einen Objekttyp ( <xref:System.Windows.Controls.Button> ).

- Die grundlegenden Eigenschaften der Schaltflächen in der gesamten Anwendung werden mithilfe von gesteuert <xref:System.Windows.Style> .

- Es wurden Ressourcen wie Farbverläufe erstellt, die für Eigenschaftswerte der Setter verwendet werden <xref:System.Windows.Style> .

- Sie haben das Aussehen von Schaltflächen in der gesamten Anwendung angepasst, indem Sie eine Vorlage auf die Schaltflächen anwenden.

- Benutzerdefiniertes Verhalten für die Schaltflächen als Reaktion auf Benutzeraktionen (z. b. <xref:System.Windows.UIElement.MouseEnter> , <xref:System.Windows.UIElement.MouseLeave> und <xref:System.Windows.Controls.Primitives.ButtonBase.Click> ), die Animationseffekte enthalten.

## <a name="see-also"></a>Siehe auch

- [Erstellen einer Schaltfläche mit Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)
- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Übersicht über Animationen](../graphics-multimedia/animation-overview.md)
- [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [Übersicht über Bitmapeffekte](../graphics-multimedia/bitmap-effects-overview.md)

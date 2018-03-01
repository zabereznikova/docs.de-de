---
title: "Exemplarische Vorgehensweise: Erstellen einer Schaltfläche mit XAML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5c5efa9f8787e65d59e1b544632e806bf3fbbc81
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a>Exemplarische Vorgehensweise: Erstellen einer Schaltfläche mit XAML
Das Ziel dieser exemplarischen Vorgehensweise ist, Informationen zum Erstellen einer animierten Schaltfläche für die Verwendung in einer [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Anwendung. In dieser exemplarischen Vorgehensweise verwendet und eine Vorlage zum Erstellen einer benutzerdefinierten Schaltflächenressource, die Wiederverwendung von Code und die Trennung von Schaltfläche Logik aus der Schaltflächendeklaration ermöglicht. Diese exemplarische Vorgehensweise ist vollständig in geschrieben [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
> [!IMPORTANT]
>  Diese exemplarische Vorgehensweise führt Sie durch die Schritte zum Erstellen der Anwendung durch eingeben bzw. kopieren und Einfügen von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] in Microsoft [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]. Wenn Sie erfahren lieber, wie einem Entwurfstool (Microsoft Expression Blend) verwenden, um dieselbe Anwendung zu erstellen, finden Sie unter [erstellen Sie eine Schaltfläche mithilfe von Microsoft Expression Blend](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md).  
  
 Die folgende Abbildung zeigt die Schaltflächen fertig.  
  
 ![Benutzerdefinierte Schaltflächen, die erstellt wurden, indem Sie XAML-](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")  
  
## <a name="create-basic-buttons"></a>Erstellen von grundlegenden Schaltflächen  
 Zunächst erstellen ein neues Projekt und das Fenster einige Schaltflächen hinzugefügt.  
  
#### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a>Erstellen eines neuen WPF-Projekts und Hinzufügen von Schaltflächen zum Fenster  
  
1.  Starten Sie[!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].  
  
2.  **Erstellen Sie ein neues WPF-Projekt:** auf die **Datei** Sie im Menü **neu**, und klicken Sie dann auf **Projekt**. Suchen der **Windows-Anwendung (WPF)** Vorlage, und nennen Sie das Projekt "den Namen AnimatedButton". Dadurch wird das Gerüst für die Anwendung erstellt.  
  
3.  **Fügen Sie grundlegende Standardschaltflächen hinzu:** alle Dateien, die in dieser exemplarischen Vorgehensweise Sie müssen von der Vorlage bereitgestellt werden. Öffnen Sie die Datei Window1.xaml, indem Sie auf die sie im Projektmappen-Explorer doppelklicken. Es wird standardmäßig ein <xref:System.Windows.Controls.Grid> Element in der Datei Window1.xaml. Entfernen der <xref:System.Windows.Controls.Grid> Element und einige Schaltflächen zum Hinzufügen der [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Seite, indem Sie eingeben oder kopieren und Einfügen von den folgenden hervorgehobenen Code hinzu Window1.xaml:  
  
    ```xaml  
    <Window x:Class="AnimatedButton.Window1"  
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
      Title="AnimatedButton" Height="300" Width="300"   
      Background="Black">   <!-- Buttons arranged vertically inside a StackPanel. -->   <StackPanel HorizontalAlignment="Left">     <Button>Button 1</Button>     <Button>Button 2</Button>     <Button>Button 3</Button>   </StackPanel>  
  
    </Window>  
    ```  
  
     Drücken Sie F5, um die Anwendung auszuführen. Sie sollten eine Reihe von Schaltflächen angezeigt werden, die wie in der folgenden Abbildung aussieht.  
  
     ![Drei grundlegende Schaltflächen](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")  
  
     Nachdem Sie grundlegenden Schaltflächen erstellt haben, können Sie in der Datei Window1.xaml Arbeit fertig. Der Rest der exemplarischen Vorgehensweise konzentriert sich auf die Datei "app.xaml" Definieren von Formatvorlagen und eine Vorlage für die Schaltflächen.  
  
## <a name="set-basic-properties"></a>Legen Sie grundlegende Eigenschaften  
 Als Nächstes legen Sie einige Eigenschaften auf diese Schaltflächen, um die Darstellung und Layout zu steuern. Statt einzeln festlegen von Eigenschaften auf die Schaltflächen, verwenden Sie die Ressourcen, auf die um Schaltflächeneigenschaften für die gesamte Anwendung zu definieren. Anwendungsressourcen sind konzeptionell identisch mit externen [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)] für Webseiten; allerdings Ressourcen sind viel leistungsstärker als [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)], wie Sie am Ende dieser exemplarischen Vorgehensweise sehen. Weitere Informationen zu Ressourcen finden Sie unter [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
#### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a>Um Formate zu verwenden, um grundlegende Eigenschaften für die Schaltflächen festlegen  
  
1.  **Definieren Sie einen Application.Resources-Block:** app.xaml öffnen, und fügen Sie das folgende hervorgehobene Markup, wenn er noch nicht vorhanden ist:  
  
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
  
     Ressourcenbereich richtet sich nach, wo Sie die Ressource zu definieren. Definieren von Ressourcen in `Application.Resources` in der app.xaml Datei die Ressource aus an einer beliebigen Stelle in der Anwendung verwendet werden kann. Weitere Informationen zum Definieren des Bereichs Ihrer Ressourcen finden Sie unter [XAML-Ressourcen](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
2.  **Erstellen Sie eine Formatvorlage, und definieren Sie grundlegende Eigenschaftswerte:** fügen Sie das folgende Markup zum Rendern der `Application.Resources` Block. Dieses Markup erstellt einen <xref:System.Windows.Style> , die für alle Schaltflächen in der Anwendung, die Einstellung gilt die <xref:System.Windows.FrameworkElement.Width%2A> der Schaltflächen auf 90 und die <xref:System.Windows.FrameworkElement.Margin%2A> auf 10:  
  
    ```xaml  
    <Application.Resources>  
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>  
    </Application.Resources>  
    ```  
  
     Die <xref:System.Windows.Style.TargetType%2A> Eigenschaft gibt an, dass das Format für alle Objekte vom Typ gilt <xref:System.Windows.Controls.Button>. Jede <xref:System.Windows.Setter> legt einen anderen Eigenschaftswert für die <xref:System.Windows.Style>. Deshalb hat jede Schaltfläche in der Anwendung zu diesem Zeitpunkt eine Breite von 90 und einem Rand von 10.  Wenn Sie zum Ausführen der Anwendung F5 drücken, wird das folgende Fenster angezeigt.  
  
     ![Schaltflächen mit einer Breite von 90 und einem Rand von 10](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")  
  
     Es gibt viele weitere Möglichkeiten mit Formatvorlagen, einschließlich eine Vielzahl von Möglichkeiten zum Optimieren, welche Objekte gelten, komplexe Eigenschaftswerte angeben und sogar mit der Formatvorlagen als Eingabe für andere Formate. Weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
3.  **Legen Sie einen Stil-Eigenschaftswert auf eine Ressource:** Ressourcen bieten eine einfache Möglichkeit, die die Wiederverwendung von häufig definierten Objekte und Werte. Er ist besonders nützlich zum Definieren von komplexen Werten mithilfe von Ressourcen, die um den Code modularer zu gestalten. App.xaml das folgende hervorgehobene Markup hinzugefügt.  
  
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
  
     Direkt unterhalb der `Application.Resources` Block, haben Sie eine Ressource namens "GrayBlueGradientBrush erstellt". Diese Ressource definiert einen horizontalen Farbverlauf. Diese Ressource kann verwendet werden, als einen Eigenschaftswert von jedem beliebigen Standort in der Anwendung, einschließlich innerhalb des Schaltfläche Style Setters für die <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft. Jetzt alle Schaltflächen haben eine <xref:System.Windows.Controls.Control.Background%2A> Eigenschaftswert von diesem Farbverlauf.  
  
     Drücken Sie F5, um die Anwendung auszuführen. Es sollte wie folgt aussehen.  
  
     ![Schaltflächen mit einem Farbverlaufshintergrund](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")  
  
## <a name="create-a-template-that-defines-the-look-of-the-button"></a>Erstellen Sie eine Vorlage, die das Aussehen der Schaltfläche definiert.  
 In diesem Abschnitt erstellen Sie eine Vorlage, die die Darstellung (Presentation) neben der Schaltfläche passt. Die Schaltfläche Präsentation mehrere Objekte, z. B. Rechtecke und andere Komponenten besteht auf der Schaltfläche "" ein eindeutige Erscheinungsbild zu verleihen.  
  
 Bisher wurde die Steuerung der Darstellung von Schaltflächen in der Anwendung beschränkt wurde, zum Ändern der Eigenschaften der Schaltfläche. Was geschieht, wenn Sie die Darstellung der Schaltfläche mehr radikal ändern möchten? Vorlagen können leistungsstarke Steuerung der Darstellung eines Objekts. Da Vorlagen in Formate verwendet werden können, können Sie eine Vorlage für alle Objekte anwenden, denen der Stil für (in dieser exemplarischen Vorgehensweise, die Schaltfläche "") gilt.  
  
#### <a name="to-use-the-template-to-define-the-look-of-the-button"></a>Die Vorlage verwenden, um das Aussehen der Schaltfläche zu definieren.  
  
1.  **Richten Sie die Vorlage:** da Steuerelemente wie <xref:System.Windows.Controls.Button> haben eine <xref:System.Windows.Controls.Control.Template%2A> -Eigenschaft, können Sie den Wert der Vorlage genau wie die anderen Eigenschaftswerte wir in legen haben definieren eine <xref:System.Windows.Style> mithilfe einer <xref:System.Windows.Setter>. Fügen Sie die folgende hervorgehobene Markup, auf die Schaltflächenformat.  
  
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
  
2.  **Ändern Sie die Schaltfläche Präsentation:** an diesem Punkt müssen Sie die Vorlage definieren. Fügen Sie das folgende hervorgehobene Markup hinzu. Dieses Markup gibt zwei <xref:System.Windows.Shapes.Rectangle> Elemente mit abgerundeten Ecken an, gefolgt von einem <xref:System.Windows.Controls.DockPanel>. Die <xref:System.Windows.Controls.DockPanel> wird verwendet, auf dem Host die <xref:System.Windows.Controls.ContentPresenter> der Schaltfläche. Ein <xref:System.Windows.Controls.ContentPresenter> zeigt den Inhalt der Schaltfläche. In dieser exemplarischen Vorgehensweise befindet sich der Inhalt Text ("Schaltfläche 1", "Button 2", "Button 3"). Alle Vorlagenkomponenten (Rechtecke und die <xref:System.Windows.Controls.DockPanel>) werden innerhalb eines angeordnet eine <xref:System.Windows.Controls.Grid>.  
  
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
  
     Drücken Sie F5, um die Anwendung auszuführen. Es sollte wie folgt aussehen.  
  
     ![](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-4.gif "custom_button_AnimatedButton_4")  
  
3.  **Fügen Sie der Vorlage einen Glaseffekt:** als Nächstes fügen Sie das Glas. Erstellen Sie zunächst einige Ressourcen, die einen Farbverlauf Glaseffekt zu erstellen. Fügen Sie diese Farbverlauf Ressourcen an einer beliebigen Stelle innerhalb der `Application.Resources` blockieren:  
  
    ```xaml  
    <Application.Resources>  
      <GradientStopCollection x:Key="MyGlassGradientStopsResource">     <GradientStop Color="WhiteSmoke" Offset="0.2" />     <GradientStop Color="Transparent" Offset="0.4" />     <GradientStop Color="WhiteSmoke" Offset="0.5" />     <GradientStop Color="Transparent" Offset="0.75" />     <GradientStop Color="WhiteSmoke" Offset="0.9" />     <GradientStop Color="Transparent" Offset="1" />   </GradientStopCollection>   <LinearGradientBrush x:Key="MyGlassBrushResource"     StartPoint="0,0" EndPoint="1,1" Opacity="0.75"     GradientStops="{StaticResource MyGlassGradientStopsResource}" />  
    <!-- Styles and other resources below here. -->  
    ```  
  
     Diese Ressourcen dienen als die <xref:System.Windows.Shapes.Shape.Fill%2A> für ein Rechteck, das wir fügen Sie der <xref:System.Windows.Controls.Grid> der Schaltflächenvorlage. Fügen Sie das folgende hervorgehobene Markup der Vorlage.  
  
    ```  
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
  
        <!-- Glass Rectangle -->     <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"       VerticalAlignment="Stretch"       StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"       Fill="{StaticResource MyGlassBrushResource}"       RenderTransformOrigin="0.5,0.5">       <Rectangle.Stroke>         <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">           <LinearGradientBrush.GradientStops>             <GradientStop Offset="0.0" Color="LightBlue" />             <GradientStop Offset="1.0" Color="Gray" />           </LinearGradientBrush.GradientStops>         </LinearGradientBrush>       </Rectangle.Stroke>       <!-- These transforms have no effect as they are declared here.             The reason the transforms are included is to be targets             for animation (see later). -->       <Rectangle.RenderTransform>         <TransformGroup>           <ScaleTransform />           <RotateTransform />         </TransformGroup>       </Rectangle.RenderTransform>       <!-- A BevelBitmapEffect is applied to give the button a             "Beveled" look. -->       <Rectangle.BitmapEffect>         <BevelBitmapEffect />       </Rectangle.BitmapEffect>     </Rectangle>  
  
        <!-- Present Text of the button. -->  
        <DockPanel Name="myContentPresenterDockPanel">  
          <ContentPresenter x:Name="myContentPresenter" Margin="20"   
            Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />  
        </DockPanel>  
      </Grid>  
    </ControlTemplate>  
    </Setter.Value>  
    ```  
  
     Beachten Sie, dass die <xref:System.Windows.UIElement.Opacity%2A> des Rechtecks mit der `x:Name` "GlassCube"-Eigenschaft ist 0 (null), wenn Sie das Beispiel ausführen, nicht das Glasrechteck Überlagerung im Vordergrund angezeigt wird. Dies ist, da wir später Trigger auf die Vorlage für hinzufügen, wenn der Benutzer mit der Schaltfläche interagiert. Allerdings sehen Sie die Schaltfläche jetzt durch Ändern illustriert die <xref:System.Windows.UIElement.Opacity%2A> Wert auf 1 und Ausführen der Anwendung. Das Ergebnis wird in der folgende Abbildung gezeigt. Bevor Sie mit dem nächsten Schritt fortfahren, ändern Sie die <xref:System.Windows.UIElement.Opacity%2A> auf 0 zurück.  
  
     ![Benutzerdefinierte Schaltflächen, die erstellt wurden, indem Sie XAML-](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")  
  
## <a name="create-button-interactivity"></a>Erstellen Sie Interaktivitätsfunktionen für die Schaltfläche  
 In diesem Abschnitt erstellen Sie die Eigenschaftentrigger und Ereignistriggern Eigenschaftswerte ändern und Ausführen von Animationen in Reaktion auf Benutzeraktionen, wie z. B. den Mauszeiger über der Schaltfläche und dann auf.  
  
 Eine einfache Möglichkeit zum Hinzufügen von Interaktivität (Mouseover, MouseLeave-, klicken Sie hier, usw.) werden Trigger in der Vorlage oder einem Stil zu definieren. Zum Erstellen einer <xref:System.Windows.Trigger>, definieren Sie z. B. eine Eigenschaft "Bedingung": die Schaltfläche "" <xref:System.Windows.UIElement.IsMouseOver%2A> Eigenschaftswert gleich `true`. Anschließend definieren Sie den Setter (Aktionen), die stattfinden, wenn die auslöserbedingung "true" ist.  
  
#### <a name="to-create-button-interactivity"></a>So erstellen Interaktivitätsfunktionen für die Schaltfläche  
  
1.  **Hinzufügen von Vorlagentriggern:** Ihre Vorlage das hervorgehobene Markup hinzugefügt.  
  
    ```  
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
  
2.  **Eigenschaftentrigger hinzufügen:** hinzufügen das hervorgehobene Markup zum Rendern der `ControlTemplate.Triggers` blockieren:  
  
    ```  
    <ControlTemplate.Triggers>  
  
      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>  
  
    <ControlTemplate.Triggers/>  
    ```  
  
     Drücken Sie F5, um die Anwendung auszuführen und die Auswirkung dieser feststellen, wie Sie den Mauszeiger über die Schaltflächen ausführen.  
  
3.  **Hinzufügen eines Triggers Fokus:** als Nächstes fügen wir einige ähnliche Setter, um Fälle zu behandeln, wenn die Schaltfläche "" den Fokus (z. B. hat, nachdem der Benutzer darauf klickt).  
  
    ```  
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
  
     Drücken Sie F5, um die Anwendung auszuführen, und klicken auf eine der Schaltflächen. Beachten Sie, dass die Schaltfläche "" markierten bleibt, nachdem Sie darauf klicken, da er weiterhin den Fokus besitzt. Wenn Sie eine weitere Schaltfläche klicken, im die Schaltfläche "Neu" den Fokus erhält, während das letzte Lesezeichen geht verloren.  
  
4.  **Hinzufügen von Animationen für** <xref:System.Windows.UIElement.MouseEnter> **und** <xref:System.Windows.UIElement.MouseLeave> **:** als Nächstes fügen wir einige Animationen, die Trigger hinzu. Fügen Sie das folgende Markup an einer beliebigen Stelle in der die `ControlTemplate.Triggers` Block.  
  
    ```  
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
  
     Das Glasrechteck verkleinert wird, wenn der Mauszeiger über die Schaltfläche bewegt und gibt an Normalgröße zurück, wenn der Mauszeiger den Bereich verlässt.  
  
     Es gibt zwei Animationen, die ausgelöst werden, wenn der Zeiger auf die Schaltfläche befindet (<xref:System.Windows.UIElement.MouseEnter> Ereignis wird ausgelöst). Diese Animationen verkleinern das Glasrechteck entlang der X- und Y-Achse. Beachten Sie die Eigenschaften auf der <xref:System.Windows.Media.Animation.DoubleAnimation> Elemente – <xref:System.Windows.Media.Animation.Timeline.Duration%2A> und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>. Die <xref:System.Windows.Media.Animation.Timeline.Duration%2A> gibt an, dass die Animation mehr als eine halbe Sekunde auftritt und <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> gibt an, dass das Glas um 10 % verkleinert wird.  
  
     Die zweite Ereignisauslöser (<xref:System.Windows.UIElement.MouseLeave>) einfach den ersten beendet. Wenn Sie beenden eine <xref:System.Windows.Media.Animation.Storyboard>, alle animierten Eigenschaften auf ihre Standardwerte zurück. Deshalb, wenn der Benutzer den Zeiger deaktiviert die Schaltfläche richtet, wechselt die Schaltfläche "" die Art und Weise, die vor der Mauszeiger über die Schaltfläche bewegt. Weitere Informationen zu Animationen finden Sie unter [Übersicht über Animation](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
5.  **Hinzufügen einer Animation für die beim Klicken auf die Schaltfläche:** der letzte Schritt besteht, einen Trigger für klickt der Benutzer auf die Schaltfläche hinzufügen. Fügen Sie das folgende Markup an einer beliebigen Stelle in der die `ControlTemplate.Triggers` blockieren:  
  
    ```  
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
  
     Drücken Sie F5, um die Anwendung auszuführen, und klicken Sie auf eine der Schaltflächen. Wenn Sie eine Schaltfläche klicken, dreht sich um das Glasrechteck.  
  
## <a name="summary"></a>Zusammenfassung  
 In dieser exemplarischen Vorgehensweise ausgeführt Sie den folgenden Übungen:  
  
-   Ziel eine <xref:System.Windows.Style> auf einen Objekttyp (<xref:System.Windows.Controls.Button>).  
  
-   Kontrolliert die grundlegende Eigenschaften von den Schaltflächen in der gesamten Anwendung mithilfe der <xref:System.Windows.Style>.  
  
-   Ressourcen wie Farbverläufe, für Eigenschaftenwerte des erstellt die <xref:System.Windows.Style> Settern für Eigenschaften.  
  
-   Die Darstellung der Schaltflächen in der gesamten Anwendung durch Anwenden einer Vorlage auf die Schaltflächen angepasst.  
  
-   Anpassen des Verhaltens für die Schaltflächen in Reaktion auf Benutzeraktionen (z. B. <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave>, und <xref:System.Windows.Controls.Primitives.ButtonBase.Click>), die Animationseffekte enthalten.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen einer Schaltfläche mit Microsoft Expression Blend](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md)  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [Übersicht über Bitmapeffekte](../../../../docs/framework/wpf/graphics-multimedia/bitmap-effects-overview.md)

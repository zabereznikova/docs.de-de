---
title: Fokusstile in Steuerelementen und FocusVisualStyle
ms.date: 03/30/2017
helpviewer_keywords:
- keyboard focus [WPF]
- focus [WPF], visual styling
- styles [WPF], focus visual style
ms.assetid: 786ac576-011b-4d72-913b-558deccb9b35
ms.openlocfilehash: 07dd5f015624e934ceb4fd38f23f7e780d185dfc
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43672630"
---
# <a name="styling-for-focus-in-controls-and-focusvisualstyle"></a>Fokusstile in Steuerelementen und FocusVisualStyle
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt zwei parallele Mechanismen zum Ändern der Darstellung eines Steuerelements bereit, wenn es den Tastaturfokus erhält. Der erste Mechanismus besteht im Eigenschaften-Settern für Eigenschaften verwenden, z. B. <xref:System.Windows.UIElement.IsKeyboardFocused%2A> innerhalb der Stil oder Vorlage, die auf das Steuerelement angewendet wird. Der zweite Mechanismus besteht in der Bereitstellung eines gesonderten Stils als Wert für die <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> Eigenschaft der "visuelle Fokusstil" erstellt Sie eine separate visuelle Struktur für einen Adorner, auf das Steuerelement, anstatt die visuelle Struktur des Steuerelements oder eine andere Benutzeroberfläche zu ändern Element, indem Sie ersetzt wird. In diesem Thema werden die Szenarios erläutert, für die sich die jeweiligen Mechanismen eignen.  
   
  
<a name="Purpose"></a>   
## <a name="the-purpose-of-focus-visual-style"></a>Zweck des Visuellen Fokusstils  
 Der visuelle Fokusstils stellt ein gemeinsames „Objektmodell“ bereit, mit dem ein visuelles Benutzerfeedback auf der Basis der Tastaturnavigation zu einem beliebigen Element der Benutzeroberfläche eingeführt wird. Dazu muss keine neue Vorlage für das Steuerelement angewendet werden und die spezifische Vorlagenzusammensetzung muss nicht bekannt sein.  
  
 Da jedoch die Funktion des visuellen Fokusstils ohne Kenntnis der Steuerungsvorlagen funktioniert, ist das visuelle Feedback, das für ein Steuerelement unter Verwendung eines visuellen Fokusstils angezeigt werden kann, beschränkt. Das Feature überlagert die visuelle Struktur nämlich einfach durch eine andere visuelle Struktur (einen Adorner), die durch das Rendern eines Steuerelements über seine Vorlage erstellt wird. Sie definieren diese separate visuelle Struktur, die mit einem Stil, der füllt die <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> Eigenschaft.  
  
<a name="Default"></a>   
## <a name="default-focus-visual-style-behavior"></a>Standardverhalten des visuellen Fokusstils  
 Visuelle Fokusstile werden nur dann wirksam, wenn die Fokusaktion über die Tastatur gestartet wurde. Eine Mausaktion oder eine programmatische Fokusänderung deaktivieren den Modus für visuelle Fokusstile. Weitere Informationen über die Unterschiede zwischen den Fokusmodi finden Sie unter [Fokus-Übersicht](../../../../docs/framework/wpf/advanced/focus-overview.md).  
  
 Die Designs für Steuerelemente umfassen ein Standardverhalten für den visuellen Fokusstil, das zum visuellen Fokusstil für alle Steuerelemente in diesem Design wird. Dieser Designstil wird durch den Wert des statischen Schlüssels <xref:System.Windows.SystemParameters.FocusVisualStyleKey%2A>. Wenn Sie einen eigenen visuellen Fokusstil auf der Anwendungsebene deklarieren, ersetzen Sie das Standardverhalten des Stils in den Designs. Wenn Sie hingegen das gesamte Design definieren, sollten Sie diesen Schlüssel auch verwenden, um den Stil für das Standardverhalten des gesamten Designs zu definieren.  
  
 In den Designs ist der Standardstil für den visuellen Fokus im Allgemeinen sehr einfach. Im Folgenden finden Sie eine grobe Übersicht:  
  
```xaml  
<Style x:Key="{x:Static SystemParameters.FocusVisualStyleKey}">  
  <Setter Property="Control.Template">  
    <Setter.Value>  
      <ControlTemplate>  
        <Rectangle StrokeThickness="1"  
          Stroke="Black"  
          StrokeDashArray="1 2"  
          SnapsToDevicePixels="true"/>  
      </ControlTemplate>  
    </Setter.Value>  
  </Setter>  
</Style>  
```  
  
<a name="When"></a>   
## <a name="when-to-use-focus-visual-styles"></a>Verwendung von visuellen Fokusstilen  
 Im Prinzip sollte die Darstellung der visuellen Fokusstile, die für die Steuerelemente übernommen werden, kohärent sein. Eine Methode zur Sicherstellung der Kohärenz besteht darin, den visuellen Fokusstil nur dann zu ändern, wenn Sie ein vollständiges Design erstellen, in dem für jedes definierte Steuerelement, das in dem Design definiert wird, derselbe visuelle Fokusstil oder eine Variation eines Stils festgelegt wird, der von Steuerelement zu Steuerelement verknüpft ist. Alternativ können Sie denselben Stil (oder ähnliche Stile) zur Formatierung aller Elemente auf einer Seite oder in einer Benutzeroberfläche verwenden, die den Tastaturfokus erhalten können.  
  
 Festlegen von <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> für einzelne Steuerelementstile, die nicht Teil eines Designs sind ist nicht die beabsichtigte Verwendung des Fokus visuellen Stilen. Dieses inkonsistente visuelle Verhalten zwischen Steuerelementen könnte zu einer verwirrenden Nutzererfahrung hinsichtlich des Tastaturfokus führen. Wenn Sie steuerelementspezifische Verhaltensweisen für den Tastaturfokus, die designübergreifend bewusst nicht kohärent sind festlegen möchten, ist viel besser in Stilen für einzelne Eingabezustandseigenschaften wie z. B. Verwenden von Triggern <xref:System.Windows.UIElement.IsFocused%2A> oder <xref:System.Windows.UIElement.IsKeyboardFocused%2A>.  
  
 Visuelle Fokusstile sind ausschließlich für den Tastaturfokus wirksam. Visuelle Fokusstile sind somit eine Art Barrierefreiheitsfunktion. Wenn Sie eine Änderung der Benutzeroberfläche für jeden Fokustyp erreichen möchten, egal ob über Mausklick, Tastatureingabe oder programmgesteuert, sollten Sie keine visuellen Fokusstile verwenden. Stattdessen sollten Sie Setter und Trigger in Stilen oder Vorlagen einsetzen, die auf der Basis des Werts allgemeiner Fokuseigenschaften arbeiten, wie z.B. <xref:System.Windows.UIElement.IsFocused%2A> oder <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A>.  
  
<a name="How"></a>   
## <a name="how-to-create-a-focus-visual-style"></a>Erstellen eines visuellen Fokusstils  
 Das Format für ein visuellen Fokusstils immer müssen Sie erstellen die <xref:System.Windows.Style.TargetType%2A> von <xref:System.Windows.Controls.Control>. Das Format sollte bestehen hauptsächlich aus einer <xref:System.Windows.Controls.ControlTemplate>. Sie geben nicht den Zieltyp der Typ sein, in dem der visuelle Fokusstil zugewiesen wird, die <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>.  
  
 Da der Zieltyp immer <xref:System.Windows.Controls.Control>, müssen Sie mithilfe von Eigenschaften, die allen Steuerelementen gemeinsam sind Stils (mit den Eigenschaften des der <xref:System.Windows.Controls.Control> -Klasse und deren Basisklassen). Sie sollten eine Vorlage erstellen, die ordnungsgemäß als Überlagerung für ein Benutzeroberflächenelement dient und keine funktionalen Bereiche des Steuerelements verdeckt. Im Allgemeinen bedeutet das, dass das visuelle Feedback außerhalb der Ränder eines Steuerelements oder als temporärer oder unaufdringlicher Effekt dargestellt werden sollte, sodass der Treffertest für das Steuerelement bei übernommenem visuellem Fokusstil nicht blockiert wird. Eigenschaften, die Sie bei der vorlagenbindung verwenden können, die zur Bestimmung von Größe und Position der überlagerungsvorlage hilfreich sind, gehören <xref:System.Windows.FrameworkElement.ActualHeight%2A>, <xref:System.Windows.FrameworkElement.ActualWidth%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, und <xref:System.Windows.Controls.Control.Padding%2A>.  
  
<a name="Alternatives"></a>   
## <a name="alternatives-to-using-a-focus-visual-style"></a>Alternativen zur Verwendung eines visuellen Fokusstils  
 In Situationen, in denen die Verwendung eine visuellen Fokusstils nicht angemessen ist, weil Sie beispielsweise einzelne Steuerelemente formatieren oder die Steuerelementvorlage noch weitreichender steuern möchten, stehen viele andere Eigenschaften und Techniken zur Verfügung, mit denen Sie ein visuelles Verhalten als Reaktion auf eine Fokusänderung erstellen können.  
  
 Trigger, Setter und Ereignissetter werden ausführlich unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md) erläutert. Die Routingereignisbehandlung wird unter [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md) erläutert.  
  
### <a name="iskeyboardfocused"></a>IsKeyboardFocused  
 Wenn Sie besonders am Tastaturfokus interessiert sind die <xref:System.Windows.UIElement.IsKeyboardFocused%2A> Abhängigkeitseigenschaft kann verwendet werden, für eine Eigenschaft <xref:System.Windows.Trigger>. Ein Eigenschaftentrigger in einem Stil oder einer Vorlage ist eine gut geeignete Technik, um ein Tastaturfokusverhalten zu definieren, das speziell für ein einziges Steuerelement gilt und das visuell nicht dem Tastaturfokusverhalten anderer Steuerelemente entspricht.  
  
 Eine weitere ähnliche Abhängigkeitseigenschaft ist <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A>, die möglicherweise zu verwenden, sollten Sie visuell aufzurufen, über den Tastaturfokus an einer beliebigen Stelle innerhalb der Zusammensetzung oder innerhalb des funktionalen Bereichs des Steuerelements ist. Beispielsweise kann man eine <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> Trigger so, dass ein Bereich, der mehrere Steuerelemente gruppiert, anders dargestellt wird, obwohl Sie über den Tastaturfokus genauer gesagt kann sein, auf ein einzelnes Element innerhalb dieses Bereichs.  
  
 Sie können auch die Ereignisse <xref:System.Windows.UIElement.GotKeyboardFocus> und <xref:System.Windows.UIElement.LostKeyboardFocus> (sowie deren vorschauentsprechungen). Sie können diese Ereignisse verwenden, als Grundlage für eine <xref:System.Windows.EventSetter>, oder Sie können auch Handler für die Ereignisse in CodeBehind schreiben.  
  
### <a name="other-focus-properties"></a>Andere Fokuseigenschaften  
 Wenn Sie möchten, dass alle mögliche Ursachen der Änderung des Fokus auf das visuelle Verhalten zu erstellen, sollten Sie Basis für einen Setter oder trigger für die <xref:System.Windows.UIElement.IsFocused%2A> Abhängigkeitseigenschaft fest, oder Sie können auch auf die <xref:System.Windows.UIElement.GotFocus> oder <xref:System.Windows.UIElement.LostFocus> Ereignissen für ein <xref:System.Windows.EventSetter>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Fokus - Übersicht](../../../../docs/framework/wpf/advanced/focus-overview.md)  
 [Übersicht über die Eingabe](../../../../docs/framework/wpf/advanced/input-overview.md)

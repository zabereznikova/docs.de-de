---
title: Fokusstile in Steuerelementen und FocusVisualStyle
ms.date: 03/30/2017
helpviewer_keywords:
- keyboard focus [WPF]
- focus [WPF], visual styling
- styles [WPF], focus visual style
ms.assetid: 786ac576-011b-4d72-913b-558deccb9b35
ms.openlocfilehash: 988b084144532df6f7a6073184fcf035b0813bfd
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458678"
---
# <a name="styling-for-focus-in-controls-and-focusvisualstyle"></a>Fokusstile in Steuerelementen und FocusVisualStyle
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt zwei parallele Mechanismen zum Ändern der Darstellung eines Steuerelements bereit, wenn es den Tastaturfokus erhält. Der erste Mechanismus besteht darin, Eigenschaften Setter für Eigenschaften wie <xref:System.Windows.UIElement.IsKeyboardFocused%2A> innerhalb des Stils oder der Vorlage zu verwenden, die auf das Steuerelement angewendet wird. Der zweite Mechanismus besteht darin, einen separaten Stil als Wert der <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>-Eigenschaft anzugeben. der "Fokus visueller Stil" erstellt eine separate visuelle Struktur für einen Funktions Indikator, der auf das Steuerelement verweist, anstatt die visuelle Struktur des Steuer Elements oder eines anderen Benutzeroberflächen Elements durch ersetzen zu ändern. In diesem Thema werden die Szenarios erläutert, für die sich die jeweiligen Mechanismen eignen.  

<a name="Purpose"></a>   
## <a name="the-purpose-of-focus-visual-style"></a>Zweck des Visuellen Fokusstils  
 Der visuelle Fokusstils stellt ein gemeinsames „Objektmodell“ bereit, mit dem ein visuelles Benutzerfeedback auf der Basis der Tastaturnavigation zu einem beliebigen Element der Benutzeroberfläche eingeführt wird. Dazu muss keine neue Vorlage für das Steuerelement angewendet werden und die spezifische Vorlagenzusammensetzung muss nicht bekannt sein.  
  
 Da jedoch die Funktion des visuellen Fokusstils ohne Kenntnis der Steuerungsvorlagen funktioniert, ist das visuelle Feedback, das für ein Steuerelement unter Verwendung eines visuellen Fokusstils angezeigt werden kann, beschränkt. Das Feature überlagert die visuelle Struktur nämlich einfach durch eine andere visuelle Struktur (einen Adorner), die durch das Rendern eines Steuerelements über seine Vorlage erstellt wird. Sie definieren diese separate visuelle Struktur mithilfe eines Stils, der die <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>-Eigenschaft füllt.  
  
<a name="Default"></a>   
## <a name="default-focus-visual-style-behavior"></a>Standardverhalten des visuellen Fokusstils  
 Visuelle Fokusstile werden nur dann wirksam, wenn die Fokusaktion über die Tastatur gestartet wurde. Eine Mausaktion oder eine programmatische Fokusänderung deaktivieren den Modus für visuelle Fokusstile. Weitere Informationen über die Unterschiede zwischen den Fokusmodi finden Sie unter [Fokus-Übersicht](focus-overview.md).  
  
 Die Designs für Steuerelemente umfassen ein Standardverhalten für den visuellen Fokusstil, das zum visuellen Fokusstil für alle Steuerelemente in diesem Design wird. Dieser Design Stil wird durch den Wert des <xref:System.Windows.SystemParameters.FocusVisualStyleKey%2A>statischer Schlüssel identifiziert. Wenn Sie einen eigenen visuellen Fokusstil auf der Anwendungsebene deklarieren, ersetzen Sie das Standardverhalten des Stils in den Designs. Wenn Sie hingegen das gesamte Design definieren, sollten Sie diesen Schlüssel auch verwenden, um den Stil für das Standardverhalten des gesamten Designs zu definieren.  
  
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
  
 Das Festlegen von <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> für einzelne Steuerelement Stile, die nicht Teil eines Designs sind, ist nicht die beabsichtigte Verwendung von visuellen Fokus Stilen. Dieses inkonsistente visuelle Verhalten zwischen Steuerelementen könnte zu einer verwirrenden Nutzererfahrung hinsichtlich des Tastaturfokus führen. Wenn Sie ein Steuerelement spezifisches Verhalten für den Tastaturfokus haben, das nicht über ein Design hinweg nicht kohärent ist, ist es viel besser, Trigger in Stilen für einzelne Eingabe Zustands Eigenschaften zu verwenden, wie z. b. <xref:System.Windows.UIElement.IsFocused%2A> oder <xref:System.Windows.UIElement.IsKeyboardFocused%2A>.  
  
 Visuelle Fokusstile sind ausschließlich für den Tastaturfokus wirksam. Visuelle Fokusstile sind somit eine Art Barrierefreiheitsfunktion. Wenn Sie eine Änderung der Benutzeroberfläche für jeden Fokustyp erreichen möchten, egal ob über Mausklick, Tastatureingabe oder programmgesteuert, sollten Sie keine visuellen Fokusstile verwenden. Stattdessen sollten Sie Setter und Trigger in Stilen oder Vorlagen einsetzen, die auf der Basis des Werts allgemeiner Fokuseigenschaften arbeiten, wie z.B. <xref:System.Windows.UIElement.IsFocused%2A> oder <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A>.  
  
<a name="How"></a>   
## <a name="how-to-create-a-focus-visual-style"></a>Erstellen eines visuellen Fokusstils  
 Der Stil, den Sie für einen visuellen Fokus Stil erstellen, sollte immer die <xref:System.Windows.Style.TargetType%2A> von <xref:System.Windows.Controls.Control>haben. Der Stil sollte hauptsächlich aus einer <xref:System.Windows.Controls.ControlTemplate>bestehen. Sie geben den Zieltyp nicht als Typ an, dem der <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>den visuellen Fokus Stil zugewiesen ist.  
  
 Da der Zieltyp immer <xref:System.Windows.Controls.Control>ist, müssen Sie mithilfe von Eigenschaften formatieren, die allen Steuerelementen gemeinsam sind (mithilfe der Eigenschaften der <xref:System.Windows.Controls.Control>-Klasse und ihrer Basisklassen). Sie sollten eine Vorlage erstellen, die ordnungsgemäß als Überlagerung für ein Benutzeroberflächenelement dient und keine funktionalen Bereiche des Steuerelements verdeckt. Im Allgemeinen bedeutet das, dass das visuelle Feedback außerhalb der Ränder eines Steuerelements oder als temporärer oder unaufdringlicher Effekt dargestellt werden sollte, sodass der Treffertest für das Steuerelement bei übernommenem visuellem Fokusstil nicht blockiert wird. Eigenschaften, die Sie in der Vorlagen Bindung verwenden können, die zum Bestimmen der Größe und Positionierung Ihrer Überlagerungs Vorlage nützlich sind, sind <xref:System.Windows.FrameworkElement.ActualHeight%2A>, <xref:System.Windows.FrameworkElement.ActualWidth%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>und <xref:System.Windows.Controls.Control.Padding%2A>.  
  
<a name="Alternatives"></a>   
## <a name="alternatives-to-using-a-focus-visual-style"></a>Alternativen zur Verwendung eines visuellen Fokusstils  
 In Situationen, in denen die Verwendung eine visuellen Fokusstils nicht angemessen ist, weil Sie beispielsweise einzelne Steuerelemente formatieren oder die Steuerelementvorlage noch weitreichender steuern möchten, stehen viele andere Eigenschaften und Techniken zur Verfügung, mit denen Sie ein visuelles Verhalten als Reaktion auf eine Fokusänderung erstellen können.  
  
 Trigger, Setter und Ereignissetter werden ausführlich unter [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md) erläutert. Die Routingereignisbehandlung wird unter [Übersicht über Routingereignisse](routed-events-overview.md) erläutert.  
  
### <a name="iskeyboardfocused"></a>IsKeyboardFocused  
 Wenn Sie für den Tastaturfokus besonders interessiert sind, kann die <xref:System.Windows.UIElement.IsKeyboardFocused%2A>-Abhängigkeits Eigenschaft für eine Eigenschaft <xref:System.Windows.Trigger>verwendet werden. Ein Eigenschaftentrigger in einem Stil oder einer Vorlage ist eine gut geeignete Technik, um ein Tastaturfokusverhalten zu definieren, das speziell für ein einziges Steuerelement gilt und das visuell nicht dem Tastaturfokusverhalten anderer Steuerelemente entspricht.  
  
 Eine weitere ähnliche Abhängigkeits Eigenschaft ist <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A>. diese kann verwendet werden, wenn Sie visuell herausfinden möchten, dass sich der Tastaturfokus irgendwo innerhalb der Zusammensetzung oder innerhalb des Funktions Bereichs des Steuer Elements befindet. Beispielsweise können Sie einen <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A>-Triggern so platzieren, dass ein Bereich, in dem mehrere Steuerelemente gruppiert werden, anders aussieht, obwohl der Tastaturfokus auf einem einzelnen Element in diesem Bereich genauer sein könnte.  
  
 Sie können auch die Ereignisse <xref:System.Windows.UIElement.GotKeyboardFocus> und <xref:System.Windows.UIElement.LostKeyboardFocus> (sowie ihre Vorschau Entsprechungen) verwenden. Diese Ereignisse können als Grundlage für eine <xref:System.Windows.EventSetter>verwendet werden, oder Sie können Handler für die Ereignisse im Code Behind schreiben.  
  
### <a name="other-focus-properties"></a>Andere Fokuseigenschaften  
 Wenn Sie alle möglichen Ursachen für das Ändern des Fokus auf die Generierung eines visuellen Verhaltens festlegen möchten, sollten Sie einen Setter oder einen Triggerwert auf der <xref:System.Windows.UIElement.IsFocused%2A>-Abhängigkeits Eigenschaft oder alternativ auf den <xref:System.Windows.UIElement.GotFocus>-oder <xref:System.Windows.UIElement.LostFocus>-Ereignissen, die für eine <xref:System.Windows.EventSetter>verwendet werden, basieren  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>
- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Fokus - Übersicht](focus-overview.md)
- [Übersicht über die Eingabe](input-overview.md)

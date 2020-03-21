---
title: Fokusstile in Steuerelementen und FocusVisualStyle
ms.date: 03/30/2017
helpviewer_keywords:
- keyboard focus [WPF]
- focus [WPF], visual styling
- styles [WPF], focus visual style
ms.assetid: 786ac576-011b-4d72-913b-558deccb9b35
ms.openlocfilehash: fda7ed12d232af5a7cfb8eb43cbb09eb793da171
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141198"
---
# <a name="styling-for-focus-in-controls-and-focusvisualstyle"></a>Fokusstile in Steuerelementen und FocusVisualStyle
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt zwei parallele Mechanismen zum Ändern der Darstellung eines Steuerelements bereit, wenn es den Tastaturfokus erhält. Der erste Mechanismus besteht darin, Eigenschaftssetzer für Eigenschaften zu verwenden, z. <xref:System.Windows.UIElement.IsKeyboardFocused%2A> B. innerhalb der Formatvorlage oder Vorlage, die auf das Steuerelement angewendet wird. Der zweite Mechanismus besteht darin, einen separaten <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> Stil als Wert der Eigenschaft bereitzustellen. Der "visuelle Fokusstil" erstellt eine separate visuelle Struktur für einen Adorner, der auf dem Steuerelement gezeichnet wird, anstatt die visuelle Struktur des Steuerelements oder eines anderen UI-Elements zu ändern, indem er ersetzt wird. In diesem Thema werden die Szenarios erläutert, für die sich die jeweiligen Mechanismen eignen.  

<a name="Purpose"></a>
## <a name="the-purpose-of-focus-visual-style"></a>Zweck des Visuellen Fokusstils  
 Der visuelle Fokusstils stellt ein gemeinsames „Objektmodell“ bereit, mit dem ein visuelles Benutzerfeedback auf der Basis der Tastaturnavigation zu einem beliebigen Element der Benutzeroberfläche eingeführt wird. Dazu muss keine neue Vorlage für das Steuerelement angewendet werden und die spezifische Vorlagenzusammensetzung muss nicht bekannt sein.  
  
 Da jedoch die Funktion des visuellen Fokusstils ohne Kenntnis der Steuerungsvorlagen funktioniert, ist das visuelle Feedback, das für ein Steuerelement unter Verwendung eines visuellen Fokusstils angezeigt werden kann, beschränkt. Das Feature überlagert die visuelle Struktur nämlich einfach durch eine andere visuelle Struktur (einen Adorner), die durch das Rendern eines Steuerelements über seine Vorlage erstellt wird. Sie definieren diese separate visuelle Struktur mithilfe <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> eines Stils, der die Eigenschaft ausfüllt.  
  
<a name="Default"></a>
## <a name="default-focus-visual-style-behavior"></a>Standardverhalten des visuellen Fokusstils  
 Visuelle Fokusstile werden nur dann wirksam, wenn die Fokusaktion über die Tastatur gestartet wurde. Eine Mausaktion oder eine programmatische Fokusänderung deaktivieren den Modus für visuelle Fokusstile. Weitere Informationen über die Unterschiede zwischen den Fokusmodi finden Sie unter [Fokus-Übersicht](focus-overview.md).  
  
 Die Designs für Steuerelemente umfassen ein Standardverhalten für den visuellen Fokusstil, das zum visuellen Fokusstil für alle Steuerelemente in diesem Design wird. Dieser Designstil wird durch den Wert <xref:System.Windows.SystemParameters.FocusVisualStyleKey%2A>des statischen Schlüssels identifiziert. Wenn Sie einen eigenen visuellen Fokusstil auf der Anwendungsebene deklarieren, ersetzen Sie das Standardverhalten des Stils in den Designs. Wenn Sie hingegen das gesamte Design definieren, sollten Sie diesen Schlüssel auch verwenden, um den Stil für das Standardverhalten des gesamten Designs zu definieren.  
  
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
  
 Das <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> Festlegen einzelner Steuerelementstile, die nicht Teil eines Designs sind, ist nicht die beabsichtigte Verwendung visueller Fokusstile. Dieses inkonsistente visuelle Verhalten zwischen Steuerelementen könnte zu einer verwirrenden Nutzererfahrung hinsichtlich des Tastaturfokus führen. Wenn Sie steuerungsspezifische Verhaltensweisen für den Tastaturfokus beabsichtigen, die absichtlich nicht über ein Design hinweg kohärent sind, ist es <xref:System.Windows.UIElement.IsFocused%2A> ein <xref:System.Windows.UIElement.IsKeyboardFocused%2A>viel besserer Ansatz, Trigger in Stilen für einzelne Eingabezustandseigenschaften zu verwenden, z. B. oder .  
  
 Visuelle Fokusstile sind ausschließlich für den Tastaturfokus wirksam. Visuelle Fokusstile sind somit eine Art Barrierefreiheitsfunktion. Wenn Sie eine Änderung der Benutzeroberfläche für jeden Fokustyp erreichen möchten, egal ob über Mausklick, Tastatureingabe oder programmgesteuert, sollten Sie keine visuellen Fokusstile verwenden. Stattdessen sollten Sie Setter und Trigger in Stilen oder Vorlagen einsetzen, die auf der Basis des Werts allgemeiner Fokuseigenschaften arbeiten, wie z.B. <xref:System.Windows.UIElement.IsFocused%2A> oder <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A>.  
  
<a name="How"></a>
## <a name="how-to-create-a-focus-visual-style"></a>Erstellen eines visuellen Fokusstils  
 Der Stil, den Sie für einen <xref:System.Windows.Style.TargetType%2A> visuellen Fokusstil erstellen, sollte immer die von <xref:System.Windows.Controls.Control>haben. Der Stil sollte hauptsächlich <xref:System.Windows.Controls.ControlTemplate>aus einem bestehen. Sie geben nicht den Zieltyp als Typ an, für <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>den der visuelle Fokusstil der zugewiesen ist.  
  
 Da der Zieltyp <xref:System.Windows.Controls.Control>immer ist, müssen Sie die Formatvorlage mithilfe von <xref:System.Windows.Controls.Control> Eigenschaften verwenden, die allen Steuerelementen gemeinsam sind (unter Verwendung von Eigenschaften der Klasse und ihrer Basisklassen). Sie sollten eine Vorlage erstellen, die ordnungsgemäß als Überlagerung für ein Benutzeroberflächenelement dient und keine funktionalen Bereiche des Steuerelements verdeckt. Im Allgemeinen bedeutet das, dass das visuelle Feedback außerhalb der Ränder eines Steuerelements oder als temporärer oder unaufdringlicher Effekt dargestellt werden sollte, sodass der Treffertest für das Steuerelement bei übernommenem visuellem Fokusstil nicht blockiert wird. Eigenschaften, die Sie in der Vorlagenbindung verwenden können und die zum <xref:System.Windows.FrameworkElement.ActualHeight%2A> <xref:System.Windows.FrameworkElement.ActualWidth%2A>Bestimmen <xref:System.Windows.FrameworkElement.Margin%2A>der <xref:System.Windows.Controls.Control.Padding%2A>Größe und Positionierung der Überlagerungsvorlage nützlich sind, sind , , und .  
  
<a name="Alternatives"></a>
## <a name="alternatives-to-using-a-focus-visual-style"></a>Alternativen zur Verwendung eines visuellen Fokusstils  
 In Situationen, in denen die Verwendung eine visuellen Fokusstils nicht angemessen ist, weil Sie beispielsweise einzelne Steuerelemente formatieren oder die Steuerelementvorlage noch weitreichender steuern möchten, stehen viele andere Eigenschaften und Techniken zur Verfügung, mit denen Sie ein visuelles Verhalten als Reaktion auf eine Fokusänderung erstellen können.  
  
 Trigger, Setter und Ereignissetter werden ausführlich unter [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md) erläutert. Die Routingereignisbehandlung wird unter [Übersicht über Routingereignisse](routed-events-overview.md) erläutert.  
  
### <a name="iskeyboardfocused"></a>IsKeyboardFocused  
 Wenn Sie sich speziell für <xref:System.Windows.UIElement.IsKeyboardFocused%2A> den Tastaturfokus interessieren, <xref:System.Windows.Trigger>kann die Abhängigkeitseigenschaft für eine Eigenschaft verwendet werden. Ein Eigenschaftentrigger in einem Stil oder einer Vorlage ist eine gut geeignete Technik, um ein Tastaturfokusverhalten zu definieren, das speziell für ein einziges Steuerelement gilt und das visuell nicht dem Tastaturfokusverhalten anderer Steuerelemente entspricht.  
  
 Eine weitere ähnliche <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A>Abhängigkeitseigenschaft ist , die möglicherweise verwendet werden kann, wenn Sie visuell aufrufen möchten, dass sich der Tastaturfokus irgendwo innerhalb des Compositings oder innerhalb des Funktionsbereichs des Steuerelements befindet. Sie können z. <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> B. einen Trigger so platzieren, dass ein Bedienfeld, das mehrere Steuerelemente gruppiert, anders angezeigt wird, obwohl sich der Tastaturfokus möglicherweise genauer auf ein einzelnes Element in diesem Bereich befindet.  
  
 Sie können auch <xref:System.Windows.UIElement.GotKeyboardFocus> die <xref:System.Windows.UIElement.LostKeyboardFocus> Ereignisse und (sowie deren Vorschauäquivalente) verwenden. Sie können diese Ereignisse als <xref:System.Windows.EventSetter>Grundlage für eine verwenden oder Handler für die Ereignisse in CodeBehind schreiben.  
  
### <a name="other-focus-properties"></a>Andere Fokuseigenschaften  
 Wenn Sie möchten, dass alle möglichen Ursachen für eine Änderung des Fokus <xref:System.Windows.UIElement.IsFocused%2A> ein visuelles Verhalten erzeugen, <xref:System.Windows.UIElement.LostFocus> sollten Sie <xref:System.Windows.EventSetter>einen Setter oder Trigger auf der Abhängigkeitseigenschaft oder alternativ auf dem oder auf ereignissen, die <xref:System.Windows.UIElement.GotFocus> für eine verwendet werden, basieren.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>
- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Fokus - Übersicht](focus-overview.md)
- [Übersicht über die Eingabe](input-overview.md)

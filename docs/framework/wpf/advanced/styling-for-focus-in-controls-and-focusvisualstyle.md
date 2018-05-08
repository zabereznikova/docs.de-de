---
title: Fokusstile in Steuerelementen und FocusVisualStyle
ms.date: 03/30/2017
helpviewer_keywords:
- keyboard focus [WPF]
- focus [WPF], visual styling
- styles [WPF], focus visual style
ms.assetid: 786ac576-011b-4d72-913b-558deccb9b35
ms.openlocfilehash: 6c73c8bbfcf7631094ddf89641de9af38f86f88e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="styling-for-focus-in-controls-and-focusvisualstyle"></a>Fokusstile in Steuerelementen und FocusVisualStyle
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt zwei parallele Mechanismen zum Ändern der Darstellung eines Steuerelements bereit, wenn es den Tastaturfokus erhält. Der erste Mechanismus besteht im Eigenschaften-Settern für Eigenschaften verwenden, z. B. <xref:System.Windows.UIElement.IsKeyboardFocused%2A> innerhalb der Stil oder eine Vorlage, die auf das Steuerelement angewendet wird. Der zweite Mechanismus besteht, einen separaten Stil als Wert des an die <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> Eigenschafts-"konzentrieren visuellen Stil" erstellt Sie eine separate visuelle Struktur für einen Adorner, auf das Steuerelement, anstatt die visuelle Struktur des Steuerelements oder eine andere Benutzeroberfläche zu ändern Element, indem Sie sie ersetzen. In diesem Thema werden die Szenarios erläutert, für die sich die jeweiligen Mechanismen eignen.  
   
  
<a name="Purpose"></a>   
## <a name="the-purpose-of-focus-visual-style"></a>Zweck des Visuellen Fokusstils  
 Der visuelle Fokusstils stellt ein gemeinsames „Objektmodell“ bereit, mit dem ein visuelles Benutzerfeedback auf der Basis der Tastaturnavigation zu einem beliebigen Element der Benutzeroberfläche eingeführt wird. Dazu muss keine neue Vorlage für das Steuerelement angewendet werden und die spezifische Vorlagenzusammensetzung muss nicht bekannt sein.  
  
 Da jedoch die Funktion des visuellen Fokusstils ohne Kenntnis der Steuerungsvorlagen funktioniert, ist das visuelle Feedback, das für ein Steuerelement unter Verwendung eines visuellen Fokusstils angezeigt werden kann, beschränkt. Das Feature überlagert die visuelle Struktur nämlich einfach durch eine andere visuelle Struktur (einen Adorner), die durch das Rendern eines Steuerelements über seine Vorlage erstellt wird. Sie definieren diese separaten visuellen Struktur über ein Format, das füllt die <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> Eigenschaft.  
  
<a name="Default"></a>   
## <a name="default-focus-visual-style-behavior"></a>Standardverhalten des visuellen Fokusstils  
 Visuelle Fokusstile werden nur dann wirksam, wenn die Fokusaktion über die Tastatur gestartet wurde. Eine Mausaktion oder eine programmatische Fokusänderung deaktivieren den Modus für visuelle Fokusstile. Weitere Informationen über die Unterschiede zwischen den Fokusmodi finden Sie unter [Fokus-Übersicht](../../../../docs/framework/wpf/advanced/focus-overview.md).  
  
 Die Designs für Steuerelemente umfassen ein Standardverhalten für den visuellen Fokusstil, das zum visuellen Fokusstil für alle Steuerelemente in diesem Design wird. Dieser Designstil wird durch den Wert des statischen Schlüssels <xref:System.Windows.SystemParameters.FocusVisualStyleKey%2A>. Wenn Sie einen eigenen visuellen Fokusstil auf der Anwendungsebene deklarieren, ersetzen Sie das Standardverhalten des Stils in den Designs. Wenn Sie hingegen das gesamte Design definieren, sollten Sie diesen Schlüssel auch verwenden, um den Stil für das Standardverhalten des gesamten Designs zu definieren.  
  
 In den Designs ist der Standardstil für den visuellen Fokus im Allgemeinen sehr einfach. Im Folgenden finden Sie eine grobe Übersicht:  
  
```  
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
  
 Festlegen von <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> auf einzelne Steuerelementtypen, die nicht Teil eines Designs sind ist nicht für die vorgesehene Nutzung des Fokus visuelle Stile. Dieses inkonsistente visuelle Verhalten zwischen Steuerelementen könnte zu einer verwirrenden Nutzererfahrung hinsichtlich des Tastaturfokus führen. Wenn Sie für das Steuerelement spezifische Verhalten für den Tastaturfokus, die nicht absichtlich kohärente sind festlegen, wird ein viel besserer Ansatz im Stile für einzelne Eingabestatus-Eigenschaften, z. B. Verwenden von Triggern <xref:System.Windows.UIElement.IsFocused%2A> oder <xref:System.Windows.UIElement.IsKeyboardFocused%2A>.  
  
 Visuelle Fokusstile sind ausschließlich für den Tastaturfokus wirksam. Visuelle Fokusstile sind somit eine Art Barrierefreiheitsfunktion. Wenn Sie eine Änderung der Benutzeroberfläche für jeden Fokustyp erreichen möchten, egal ob über Mausklick, Tastatureingabe oder programmgesteuert, sollten Sie keine visuellen Fokusstile verwenden. Stattdessen sollten Sie Setter und Trigger in Stilen oder Vorlagen einsetzen, die auf der Basis des Werts allgemeiner Fokuseigenschaften arbeiten, wie z.B. `IsFocused` oder `IsFocusWithin`.  
  
<a name="How"></a>   
## <a name="how-to-create-a-focus-visual-style"></a>Erstellen eines visuellen Fokusstils  
 Das Format für ein visuellen Stil der Fokus immer haben sollen, Sie erstellen die <xref:System.Windows.Style.TargetType%2A> von <xref:System.Windows.Controls.Control>. Das Format sollte bestehen hauptsächlich aus einem <xref:System.Windows.Controls.ControlTemplate>. Sie geben Sie den Zieltyp aus, um den Typ sein, auf dem visuellen Stil des Fokus zugewiesen ist, keine der <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>.  
  
 Da der Zieltyp immer ist <xref:System.Windows.Controls.Control>, Sie müssen mit den Eigenschaften, die allen Steuerelementen gemeinsam sind formatieren (mit den Eigenschaften des der <xref:System.Windows.Controls.Control> Klasse und deren Basisklassen). Sie sollten eine Vorlage erstellen, die ordnungsgemäß als Überlagerung für ein Benutzeroberflächenelement dient und keine funktionalen Bereiche des Steuerelements verdeckt. Im Allgemeinen bedeutet das, dass das visuelle Feedback außerhalb der Ränder eines Steuerelements oder als temporärer oder unaufdringlicher Effekt dargestellt werden sollte, sodass der Treffertest für das Steuerelement bei übernommenem visuellem Fokusstil nicht blockiert wird. Eigenschaften, die in der vorlagenbindung verwendet werden können, die zur Bestimmung der Größe und Positionierung der Ihre Vorlage Overlay eignen <xref:System.Windows.FrameworkElement.ActualHeight%2A>, <xref:System.Windows.FrameworkElement.ActualWidth%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, und <xref:System.Windows.Controls.Control.Padding%2A>.  
  
<a name="Alternatives"></a>   
## <a name="alternatives-to-using-a-focus-visual-style"></a>Alternativen zur Verwendung eines visuellen Fokusstils  
 In Situationen, in denen die Verwendung eine visuellen Fokusstils nicht angemessen ist, weil Sie beispielsweise einzelne Steuerelemente formatieren oder die Steuerelementvorlage noch weitreichender steuern möchten, stehen viele andere Eigenschaften und Techniken zur Verfügung, mit denen Sie ein visuelles Verhalten als Reaktion auf eine Fokusänderung erstellen können.  
  
 Trigger, Setter und Ereignissetter werden ausführlich unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md) erläutert. Die Routingereignisbehandlung wird unter [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md) erläutert.  
  
### <a name="iskeyboardfocused"></a>IsKeyboardFocused  
 Wenn Sie über den Tastaturfokus, insbesondere interessiert sind die <xref:System.Windows.UIElement.IsKeyboardFocused%2A> Abhängigkeitseigenschaft kann verwendet werden, für eine Eigenschaft <xref:System.Windows.Trigger>. Ein Eigenschaftentrigger in einem Stil oder einer Vorlage ist eine gut geeignete Technik, um ein Tastaturfokusverhalten zu definieren, das speziell für ein einziges Steuerelement gilt und das visuell nicht dem Tastaturfokusverhalten anderer Steuerelemente entspricht.  
  
 Eine weitere ähnliche Abhängigkeitseigenschaft ist <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A>, die möglicherweise zu verwenden, wenn Sie, den Tastaturfokus visuell aufzurufen möchten an einer beliebigen Stelle innerhalb der Zusammensetzung oder in den Funktionsbereich "des Steuerelements" ist. Sie können z. B. Platzieren einer <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> Trigger, ein Bereich, der mehrere Steuerelemente gruppiert unterschiedlich ist, wird angezeigt, obwohl genauer über den Tastaturfokus möglicherweise auf ein einzelnes Element in diesem Bereich werden.  
  
 Sie können auch die Ereignisse <xref:System.Windows.UIElement.GotKeyboardFocus> und <xref:System.Windows.UIElement.LostKeyboardFocus> (sowie ihre Entsprechungen Preview). Sie können diese Ereignisse verwenden, als Grundlage für eine <xref:System.Windows.EventSetter>, oder Sie können Handler für die Ereignisse im Code-Behind schreiben.  
  
### <a name="other-focus-properties"></a>Andere Fokuseigenschaften  
 Wenn Sie alle mögliche Ursachen ändern den Fokus auf ein visuelles Verhalten erzeugen möchten, sollten Sie Basis für einen Setter oder trigger für die <xref:System.Windows.UIElement.IsFocused%2A> Abhängigkeitseigenschaft oder alternativ auf die <xref:System.Windows.UIElement.GotFocus> oder <xref:System.Windows.UIElement.LostFocus> Ereignissen für eine <xref:System.Windows.EventSetter>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Fokus - Übersicht](../../../../docs/framework/wpf/advanced/focus-overview.md)  
 [Übersicht über die Eingabe](../../../../docs/framework/wpf/advanced/input-overview.md)

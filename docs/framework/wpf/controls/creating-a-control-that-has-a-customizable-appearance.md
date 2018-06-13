---
title: Erstellen eines Steuerelements mit einer anpassbaren Darstellung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], customizing
- VisualStateManager [WPF], managing the state of a control
- ControlTemplate [WPF], customizing appearance
- controls [WPF], defining the visual structure and behavior of
- customizing appearance [WPF], ControlTemplate
- managing control states [WPF], VisualStateManager
- VisualStateManager [WPF], best practice
ms.assetid: 9e356d3d-a3d0-4b01-a25f-2d43e4d53fe5
ms.openlocfilehash: 9f539e7dbb105591375857122d738fddd87f6776
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558277"
---
# <a name="creating-a-control-that-has-a-customizable-appearance"></a>Erstellen eines Steuerelements mit einer anpassbaren Darstellung
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet Ihnen die Möglichkeit, ein Steuerelement erstellen, dessen Darstellung angepasst werden kann. Sie können z. B. Ändern der Darstellung von einer <xref:System.Windows.Controls.CheckBox> über welche Einstellung Eigenschaften möglich ist, durch Erstellen eines neuen <xref:System.Windows.Controls.ControlTemplate>. Die folgende Abbildung zeigt eine <xref:System.Windows.Controls.CheckBox> , verwendet den Standardwert <xref:System.Windows.Controls.ControlTemplate> und ein <xref:System.Windows.Controls.CheckBox> , verwendet eine benutzerdefinierte <xref:System.Windows.Controls.ControlTemplate>.  
  
 ![Kontrollkästchen mit der Standardsteuerelementvorlage. ] (../../../../docs/framework/wpf/controls/media/ndp-checkboxdefault.png "NDP_CheckBoxDefault")  
Ein Kontrollkästchen, das die Standardsteuerelementvorlage verwendet  
  
 ![Kontrollkästchen mit einer benutzerdefinierten Steuerelementvorlage. ] (../../../../docs/framework/wpf/controls/media/ndp-checkboxcustom.png "NDP_CheckBoxCustom")  
Ein Kontrollkästchen, das eine benutzerdefinierte Steuerelementvorlage verwendet  
  
 Wenn Sie das Modell Teile und Zustände bei der Erstellung eines Steuerelements folgen, wird die Darstellung des Steuerelements anpassbar sein. Designer Tools wie Microsoft Expression Blend unterstützen das Modell Teile und Zustände, damit, wenn Sie dieses Modell führen Sie das Steuerelement in diese Anwendungstypen anpassbare werden.  In diesem Thema erläutert das Modell Teile und Zustände und wie, ihm zu folgen, wenn Sie ein eigenes Steuerelement erstellen. In diesem Thema wird ein Beispiel für ein benutzerdefiniertes Steuerelement `NumericUpDown`, um die Philosophie dieses Modells zu veranschaulichen.  Die `NumericUpDown` -Steuerelement zeigt einen numerischen Wert, der ein Benutzer kann zu erhöhen oder verringern, indem Sie durch Klicken auf die Schaltflächen des Steuerelements.  Die folgende Abbildung zeigt die `NumericUpDown` Steuerelement, das in diesem Thema erläutert wird.  
  
 ![Benutzerdefiniertes NumericUpDown-Steuerelement. ] (../../../../docs/framework/wpf/controls/media/ndp-numericupdown.png "NDP_NumericUPDown")  
Ein benutzerdefiniertes NumericUpDown-Steuerelement  
  
 Dieses Thema enthält folgende Abschnitte:  
  
-   [Erforderliche Komponenten](#prerequisites)  
  
-   [Teile und Zustände-Modell](#parts_and_states_model)  
  
-   [Definieren die visuelle Struktur und das visuelle Verhalten eines Steuerelements in einer ControlTemplate](#defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate)  
  
-   [Verwenden von Teilen der ControlTemplate in Code](#using_parts_of_the_controltemplate_in_code)  
  
-   [Bereitstellen des Steuerelementvertrags](#providing_the_control_contract)  
  
-   [Vollständiges Beispiel](#complete_example)  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 In diesem Thema wird davon ausgegangen, dass Sie wissen, wie zum Erstellen eines neuen <xref:System.Windows.Controls.ControlTemplate> für ein vorhandenes Steuerelement mit, was die Elemente auf einem Steuerelementvertrag sind, vertraut sind und zu verstehen, die in erörterten Konzepte [Anpassen der Darstellung von einem vorhandenen Steuerelement durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
> [!NOTE]
>  Um ein Steuerelement erstellen, dessen Darstellung angepasst werden kann, müssen Sie ein Steuerelement, das von erbt erstellen die <xref:System.Windows.Controls.Control> Klasse oder eine ihrer Unterklassen außer <xref:System.Windows.Controls.UserControl>.  Ein Steuerelement, das von erbt <xref:System.Windows.Controls.UserControl> ist ein Steuerelement, die schnell erstellt werden können, aber es werden keine verwendet eine <xref:System.Windows.Controls.ControlTemplate> und seine Darstellung nicht anpassen.  
  
<a name="parts_and_states_model"></a>   
## <a name="parts-and-states-model"></a>Teile und Zustände-Modell  
 Das Modell Teile und Zustände gibt an, wie die visuelle Struktur und das visuelle Verhalten eines Steuerelements zu definieren. Um die Teile und Zustände Modell folgen zu können, sollten Sie Folgendes tun:  
  
-   Definieren Sie die visuelle Struktur und das visuelle Verhalten in der <xref:System.Windows.Controls.ControlTemplate> eines Steuerelements.  
  
-   Führen Sie bestimmte bewährten Methoden aus, wenn die Logik des Steuerelements mit Teilen der Steuerelementvorlage interagiert.  
  
-   Geben Sie einen Steuerelementvertrag angeben, was in enthalten sein sollen die <xref:System.Windows.Controls.ControlTemplate>.  
  
 Beim Definieren der visuellen Struktur und das visuelle Verhalten in der <xref:System.Windows.Controls.ControlTemplate> eines Steuerelements Anwendungsentwickler können ändern, die visuelle Struktur und das visuelle Verhalten des Steuerelements durch Erstellen eines neuen <xref:System.Windows.Controls.ControlTemplate> keinen Code schreiben.   Geben Sie ein Steuerelementvertrag, der Anwendung weist Autoren die <xref:System.Windows.FrameworkElement> Objekte und Zustände in definiert werden die <xref:System.Windows.Controls.ControlTemplate>. Befolgen Sie einige bewährten Methoden beim Interagieren mit den Teilen in der <xref:System.Windows.Controls.ControlTemplate> , damit das Steuerelement ordnungsgemäß ein unvollständiges behandelt <xref:System.Windows.Controls.ControlTemplate>.  Wenn Sie diese drei Grundsätze folgen, Anwendungsentwickler zeilenfilterausdruck zum Erstellen einer <xref:System.Windows.Controls.ControlTemplate> für Ihr Steuerelement ebenso leicht wie können für die Steuerelemente, die im Lieferumfang [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Im folgende Abschnitt werden alle diese Empfehlungen im Detail beschrieben.  
  
<a name="defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate"></a>   
## <a name="defining-the-visual-structure-and-visual-behavior-of-a-control-in-a-controltemplate"></a>Definieren die visuelle Struktur und das visuelle Verhalten eines Steuerelements in einer ControlTemplate  
 Wenn Sie Ihr benutzerdefinierte Steuerelement erstellen, mit dem Modell Teile und Zustände, definieren Sie visuelle Struktur und das visuelle Verhalten in des Steuerelements seine <xref:System.Windows.Controls.ControlTemplate> statt in ihrer Logik.  Die visuelle Struktur eines Steuerelements ist die Zusammensetzung der <xref:System.Windows.FrameworkElement> Objekte, aus denen das Steuerelement besteht.  Das visuelle Verhalten ist die Möglichkeit, die das Steuerelement angezeigt wird, wenn es in einem bestimmten Zustand befindet.   Weitere Informationen zum Erstellen einer <xref:System.Windows.Controls.ControlTemplate> , die die visuelle Struktur und das visuelle Verhalten eines Steuerelements angibt, finden Sie unter [Anpassen der Darstellung von einem vorhandenen Steuerelement durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
 Im Beispiel für die `NumericUpDown` -Steuerelement, die visuelle Struktur enthält zwei <xref:System.Windows.Controls.Primitives.RepeatButton> Steuerelemente und ein <xref:System.Windows.Controls.TextBlock>.  Wenn Sie diese Steuerelemente im Code des Hinzufügen der `NumericUpDown` Steuerelement--in seinem Konstruktor, z. B. die Positionen von diesen Steuerelementen wäre unveränderbar.  Anstelle von definieren die visuelle Struktur und das visuelle Verhalten des Steuerelements in seinem Code, sollten Sie definieren ihn in die <xref:System.Windows.Controls.ControlTemplate>.  Klicken Sie dann ein Anwendungsentwickler die Position der Schaltflächen anzupassen und <xref:System.Windows.Controls.TextBlock> und angeben, welches Verhalten tritt auf, wenn `Value` ist ein negativer Wert da die <xref:System.Windows.Controls.ControlTemplate> ersetzt werden.  
  
 Das folgende Beispiel zeigt die visuelle Struktur eines der `NumericUpDown` -Steuerelement, das enthält eine <xref:System.Windows.Controls.Primitives.RepeatButton> erhöhen `Value`, <xref:System.Windows.Controls.Primitives.RepeatButton> verringern `Value`, und ein <xref:System.Windows.Controls.TextBlock> anzuzeigende `Value`.  
  
 [!code-xaml[VSMCustomControl#VisualStructure](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#visualstructure)]  
  
 Ein visuelles Verhalten von der `NumericUpDown` Steuerelement ist, dass der Wert in roter Schrift ist, wenn sie negativ ist.  Wenn Sie ändern die <xref:System.Windows.Controls.TextBlock.Foreground%2A> von der <xref:System.Windows.Controls.TextBlock> im code, wenn die `Value` negativ ist, die `NumericUpDown` einen roten negativen Wert wird immer angezeigt. Geben Sie das visuelle Verhalten des Steuerelements in der <xref:System.Windows.Controls.ControlTemplate> durch Hinzufügen von <xref:System.Windows.VisualState> -Objekte und die <xref:System.Windows.Controls.ControlTemplate>.  Das folgende Beispiel zeigt die <xref:System.Windows.VisualState> von Objekten für die `Positive` und `Negative` Status.  `Positive` und `Negative` sind sich gegenseitig ausschließende (das Steuerelement ist stets in genau einem der beiden), damit das Beispiel setzt die <xref:System.Windows.VisualState> Objekte in einem einzelnen <xref:System.Windows.VisualStateGroup>.  Eintritt des Steuerelements in der `Negative` Zustand, der <xref:System.Windows.Controls.TextBlock.Foreground%2A> von der <xref:System.Windows.Controls.TextBlock> Rot.  Wenn das Steuerelement ist der `Positive` Zustand, der <xref:System.Windows.Controls.TextBlock.Foreground%2A> zurückgibt, ursprünglichen Wert.  Definieren von <xref:System.Windows.VisualState> Objekte in einer <xref:System.Windows.Controls.ControlTemplate> wird weiter erläutert [Anpassen der Darstellung von einem vorhandenen Steuerelement durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
> [!NOTE]
>  Achten Sie darauf, dass Sie festlegen der <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> -Eigenschaft auf den Stamm <xref:System.Windows.FrameworkElement> von der <xref:System.Windows.Controls.ControlTemplate>.  
  
 [!code-xaml[VSMCustomControl#ValueStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]  
  
<a name="using_parts_of_the_controltemplate_in_code"></a>   
## <a name="using-parts-of-the-controltemplate-in-code"></a>Verwenden von Teilen der ControlTemplate in Code  
 Ein <xref:System.Windows.Controls.ControlTemplate> Autor kann ausgelassen <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.VisualState> Objekte, absichtlich oder versehentlich, aber die Logik des Steuerelements möglicherweise die Teile ordnungsgemäß funktioniert. Modell für Teile und Zustände gibt an, dass das Steuerelement flexibel auf eine <xref:System.Windows.Controls.ControlTemplate> , die fehlt <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.VisualState> Objekte.  Das Steuerelement sollte keine Auslösen einer Ausnahme oder einem Bericht einen Fehler Wenn eine <xref:System.Windows.FrameworkElement>, <xref:System.Windows.VisualState>, oder <xref:System.Windows.VisualStateGroup> fehlt in der <xref:System.Windows.Controls.ControlTemplate>. In diesem Abschnitt wird beschrieben, die empfohlenen Vorgehensweisen für die Interaktion mit <xref:System.Windows.FrameworkElement> Objekte und Verwalten von Zuständen.  
  
### <a name="anticipate-missing-frameworkelement-objects"></a>Erwarten Sie fehlende Objekte des Typs "FrameworkElement"  
 Beim definieren <xref:System.Windows.FrameworkElement> Objekte in der <xref:System.Windows.Controls.ControlTemplate>, die Logik des Steuerelements müssen möglicherweise einige von ihnen interagieren.  Z. B. die `NumericUpDown` Steuerelement abonniert der Schaltflächen <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis vergrößern oder verkleinern `Value` und legt sie fest der <xref:System.Windows.Controls.TextBlock.Text%2A> Eigenschaft von der <xref:System.Windows.Controls.TextBlock> zu `Value`. Wenn ein benutzerdefinierter <xref:System.Windows.Controls.ControlTemplate> lässt die <xref:System.Windows.Controls.TextBlock> oder Schaltflächen, es ist akzeptabel, dass das Steuerelement einige ihrer Funktionen verliert, aber Sie achten darauf sollten, dass das Steuerelement keine Fehler verursacht. Z. B. wenn ein <xref:System.Windows.Controls.ControlTemplate> enthält nicht die Schaltflächen zum Ändern `Value`, die `NumericUpDown` verliert diese Funktionalität jedoch eine Anwendung, verwendet der <xref:System.Windows.Controls.ControlTemplate> wird weiterhin ausgeführt.  
  
 Die folgenden Methoden werden sichergestellt, dass das Steuerelement ordnungsgemäß mit fehlendem antwortet <xref:System.Windows.FrameworkElement> Objekte:  
  
1.  Legen Sie die `x:Name` Attribut für jede <xref:System.Windows.FrameworkElement> , die Sie im Code verweisen müssen.  
  
2.  Definieren Sie die private Eigenschaften für jede <xref:System.Windows.FrameworkElement> , die Sie für die Interaktion mit benötigen.  
  
3.  Abonnieren und kündigen Sie alle Ereignisse, die das Steuerelement behandelt die <xref:System.Windows.FrameworkElement> Eigenschaft des set-Zugriffsmethode.  
  
4.  Legen Sie die <xref:System.Windows.FrameworkElement> in definierten Eigenschaften in Schritt 2 der <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> Methode. Dies ist möglich, die <xref:System.Windows.FrameworkElement> in der <xref:System.Windows.Controls.ControlTemplate> für das Steuerelement verfügbar ist. Verwenden der `x:Name` von der <xref:System.Windows.FrameworkElement> Bezugsquelle aus der <xref:System.Windows.Controls.ControlTemplate>.  
  
5.  Überprüfen Sie, ob die <xref:System.Windows.FrameworkElement> nicht `null` vor dem Zugriff auf ihre Member.  Ist er `null`, aber keine Fehler gemeldet.  
  
 Das folgende Beispiel zeigt wie die `NumericUpDown` Steuerelement interagiert mit <xref:System.Windows.FrameworkElement> Objekte gemäß den Empfehlungen in der vorangehenden Liste aufgeführt.  
  
 In dem Beispiel die visuelle Struktur eines definiert der `NumericUpDown` steuern, der <xref:System.Windows.Controls.ControlTemplate>, die <xref:System.Windows.Controls.Primitives.RepeatButton> erhöht sich dadurch `Value` hat seine `x:Name` -Attributsatz zur `UpButton`.  Das folgende Beispiel deklariert eine Eigenschaft mit dem Namen `UpButtonElement` darstellt, die die <xref:System.Windows.Controls.Primitives.RepeatButton> , deklariert ist, der <xref:System.Windows.Controls.ControlTemplate>. Die `set` Accessor abonnementkündigungen zuerst auf der Schaltfläche <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis wenn `UpDownElement` nicht `null`, dann legt die Eigenschaft fest, und klicken Sie dann abonniert die <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis. Es gibt auch eine Eigenschaft definiert, aber nicht hier gezeigt werden, für die anderen <xref:System.Windows.Controls.Primitives.RepeatButton>namens `DownButtonElement`.  
  
 [!code-csharp[VSMCustomControl#UpButtonProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#upbuttonproperty)]
 [!code-vb[VSMCustomControl#UpButtonProperty](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#upbuttonproperty)]  
  
 Das folgende Beispiel zeigt die <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> für die `NumericUpDown` Steuerelement.  Im Beispiel wird die <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> Methode zum Abrufen der <xref:System.Windows.FrameworkElement> Objekte aus der <xref:System.Windows.Controls.ControlTemplate>.  Beachten Sie, die im Beispiel für schützt Fälle, in denen <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> sucht nach einem <xref:System.Windows.FrameworkElement> mit dem angegebenen Namen, der nicht dem erwarteten Typ ist. Es ist auch eine bewährte Methode, um Elemente zu ignorieren, die dem angegebenen `x:Name` jedoch den falschen Typ.  
  
 [!code-csharp[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
 [!code-vb[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]  
  
 Mit den Methoden, die in den vorherigen Beispielen gezeigt werden, Sie stellen Sie sicher, dass das Steuerelement weiterhin ausgeführt werden, wenn die <xref:System.Windows.Controls.ControlTemplate> fehlt ein <xref:System.Windows.FrameworkElement>.  
  
### <a name="use-the-visualstatemanager-to-manage-states"></a>Verwenden von VisualStateManager Zustände verwalten  
 Die <xref:System.Windows.VisualStateManager> verfolgt den Status eines Steuerelements und führt die Logik für den Übergang zwischen Zuständen erforderlich. Beim Hinzufügen <xref:System.Windows.VisualState> -Objekte der <xref:System.Windows.Controls.ControlTemplate>, fügen Sie die Objekte einer <xref:System.Windows.VisualStateGroup> und Hinzufügen der <xref:System.Windows.VisualStateGroup> auf die <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> angefügte Eigenschaft, damit die <xref:System.Windows.VisualStateManager> hat Zugriff auf diese.  
  
 Im folgende Beispiel wird das vorherige Beispiel, das zeigt wiederholt die <xref:System.Windows.VisualState> Objekte, die entspricht der `Positive` und `Negative` Status des Steuerelements. Die <xref:System.Windows.Media.Animation.Storyboard> in der `Negative` <xref:System.Windows.VisualState> aktiviert die <xref:System.Windows.Controls.TextBlock.Foreground%2A> von der <xref:System.Windows.Controls.TextBlock> Rot.   Wenn die `NumericUpDown` -Steuerelement befindet sich im die `Negative` Zustand befindet, dann ist das Storyboard in der `Negative` Zustand beginnt.  Die <xref:System.Windows.Media.Animation.Storyboard> in der `Negative` Status beendet gibt das Steuerelement an die `Positive` Zustand.  Die `Positive` <xref:System.Windows.VisualState> muss nicht enthalten eine <xref:System.Windows.Media.Animation.Storyboard> da bei der <xref:System.Windows.Media.Animation.Storyboard> für die `Negative` beendet wird, die <xref:System.Windows.Controls.TextBlock.Foreground%2A> an seine ursprüngliche Farbe zurückgegeben.  
  
 [!code-xaml[VSMCustomControl#ValueStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]  
  
 Beachten Sie, dass die <xref:System.Windows.Controls.TextBlock> erhält einen Namen, aber die <xref:System.Windows.Controls.TextBlock> ist nicht im Steuerelementvertrag `NumericUpDown` , da die Logik des Steuerelements nie verweist auf die <xref:System.Windows.Controls.TextBlock>.  Elemente, auf die verweist, die <xref:System.Windows.Controls.ControlTemplate> Namen haben, müssen jedoch nicht Teil des Steuerelementvertrags sein, da ein neues <xref:System.Windows.Controls.ControlTemplate> für das Steuerelement möglicherweise nicht auf dieses Element verweisen muss.  Z. B. eine Person, die eine neue erstellt <xref:System.Windows.Controls.ControlTemplate> für `NumericUpDown` ggf. nicht angeben, dass `Value` ist ein negativer Wert durch Ändern der <xref:System.Windows.Controls.Control.Foreground%2A>.  In diesem Fall wird weder der Code noch die <xref:System.Windows.Controls.ControlTemplate> Verweise der <xref:System.Windows.Controls.TextBlock> anhand des Namens.  
  
 Die Logik des Steuerelements ist verantwortlich für das Ändern der Zustand des Steuerelements. Im folgenden Beispiel wird gezeigt, die die `NumericUpDown` Aufrufe steuern die <xref:System.Windows.VisualStateManager.GoToState%2A> Methode in Wechseln der `Positive` Zustand über, wenn `Value` ist 0 oder größer ist, und die `Negative` Zustand über, wenn `Value` ist kleiner als 0.  
  
 [!code-csharp[VSMCustomControl#ValueStateChange](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#valuestatechange)]
 [!code-vb[VSMCustomControl#ValueStateChange](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#valuestatechange)]  
  
 Die <xref:System.Windows.VisualStateManager.GoToState%2A> -Methode führt die Logik zum Starten und Beenden des Storyboards erforderlich. Wenn ein Steuerelement ruft <xref:System.Windows.VisualStateManager.GoToState%2A> so ändern Sie den Zustand der <xref:System.Windows.VisualStateManager> bewirkt Folgendes:  
  
-   Wenn die <xref:System.Windows.VisualState> hat, dass das Steuerelement, also eine <xref:System.Windows.Media.Animation.Storyboard>, beginnt das Storyboard. Wenn danach die <xref:System.Windows.VisualState> hat, dass das Steuerelement von stammt eine <xref:System.Windows.Media.Animation.Storyboard>, das Storyboard beendet.  
  
-   Wenn das Steuerelement bereits in den Zustand, der angegeben wird, <xref:System.Windows.VisualStateManager.GoToState%2A> führt keine Aktion aus, und gibt `true`.  
  
-   Wenn Zustand, der angegeben wird, ist nicht ist in vorhanden der <xref:System.Windows.Controls.ControlTemplate> von `control`, <xref:System.Windows.VisualStateManager.GoToState%2A> führt keine Aktion aus, und gibt `false`.  
  
#### <a name="best-practices-for-working-with-the-visualstatemanager"></a>Bewährte Methoden für die Arbeit mit VisualStateManager  
 Es wird empfohlen, dass Sie Folgendes ein, um das Steuerelement Zustände aufrechtzuerhalten ausführen:  
  
-   Verwenden Sie Eigenschaften, um den Status zu verfolgen.  
  
-   Erstellen Sie eine Hilfsmethode, den Übergang zwischen Zuständen.  
  
 Die `NumericUpDown` -Steuerelement verwendet seine `Value` Eigenschaft zum Nachverfolgen, ob es in der `Positive` oder `Negative` Zustand.  Die `NumericUpDown` Steuerelement definiert außerdem die `Focused` und `UnFocused` angibt, welche verfolgt die <xref:System.Windows.UIElement.IsFocused%2A> Eigenschaft. Wenn Sie Zustände, die natürliche Weise an eine Eigenschaft des Steuerelements nicht entsprechen verwenden, können Sie eine private Eigenschaft zum Nachverfolgen des Status definieren.  
  
 Eine einzelne Methode, die alle Status aktualisiert zentralisiert Aufrufe an die <xref:System.Windows.VisualStateManager> und hält den Code überschaubar. Das folgende Beispiel zeigt die `NumericUpDown` des Steuerelements Hilfsmethode `UpdateStates`. Wenn `Value` ist größer als oder gleich 0, die <xref:System.Windows.Controls.Control> befindet sich in der `Positive` Zustand.  Wenn `Value` ist kleiner als 0 ist, befindet sich das Steuerelement in der `Negative` Zustand.  Wenn <xref:System.Windows.UIElement.IsFocused%2A> ist `true`, das Steuerelement ist der `Focused` State; andernfalls ist Sie der `Unfocused` Zustand.  Das Steuerelement kann Aufrufen `UpdateStates` muss bei jedem ändert seinen Status, unabhängig davon, welcher Zustand sich ändert.  
  
 [!code-csharp[VSMCustomControl#UpdateStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#updatestates)]
 [!code-vb[VSMCustomControl#UpdateStates](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#updatestates)]  
  
 Wenn Sie einen Status ein, um übergeben <xref:System.Windows.VisualStateManager.GoToState%2A> Wenn das Steuerelement bereits in diesem Zustand wird <xref:System.Windows.VisualStateManager.GoToState%2A> nichts, daher brauchen Sie für den aktuellen Zustand des Serversteuerelements überprüfen.  Z. B. wenn `Value` ändert von eine negative Zahl in eine andere negative Zahl ist, das Storyboard für die `Negative` Zustand nicht unterbrochen wird und dem Benutzer eine Änderung im Steuerelement nicht angezeigt.  
  
 Die <xref:System.Windows.VisualStateManager> verwendet <xref:System.Windows.VisualStateGroup> Objekte, um zu bestimmen, welcher Zustand beendet wird, wenn Sie aufrufen <xref:System.Windows.VisualStateManager.GoToState%2A>. Das Steuerelement ist stets in einem Status für jeden <xref:System.Windows.VisualStateGroup> in definierten seine <xref:System.Windows.Controls.ControlTemplate> und verlässt nur einen Status aus, wenn er in einen anderen Zustand, aus der gleichen wechselt <xref:System.Windows.VisualStateGroup>. Z. B. die <xref:System.Windows.Controls.ControlTemplate> von der `NumericUpDown` -Steuerelement definiert die `Positive` und `Negative` <xref:System.Windows.VisualState> Objekte in einem <xref:System.Windows.VisualStateGroup> und `Focused` und `Unfocused` <xref:System.Windows.VisualState> Objekte in einer anderen. (Sehen Sie die `Focused` und `Unfocused` <xref:System.Windows.VisualState> definiert, der [vollständiges Beispiel](#complete_example) Abschnitt in diesem Thema wird das Steuerelement aus der `Positive` Zustands, in der `Negative` Zustand, oder umgekehrt, die Steuerung bleibt, entweder in der `Focused` oder `Unfocused` Zustand.  
  
 Es gibt drei typische stellen, in denen der Zustand eines Steuerelements ändern können:  
  
-   Wenn die <xref:System.Windows.Controls.ControlTemplate> wird angewendet, um die <xref:System.Windows.Controls.Control>.  
  
-   Wenn eine Eigenschaft geändert wird.  
  
-   Wenn ein Ereignis auftritt.  
  
 Die folgenden Beispiele veranschaulichen den Zustand Aktualisieren der `NumericUpDown` Steuerelement in diesen Fällen.  
  
 Sollten Sie den Zustand des Steuerelements in acht Aktualisieren der <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> Methode, damit das Steuerelement angezeigt wird, in den richtigen Zustand über, wenn die <xref:System.Windows.Controls.ControlTemplate> angewendet wird. Im folgenden Beispiel wird `UpdateStates` in <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> um sicherzustellen, dass das Steuerelement im entsprechenden Zustand ist.  Nehmen wir beispielsweise an, dass Sie erstellen eine `NumericUpDown` steuern, und legen Sie dessen <xref:System.Windows.Controls.Control.Foreground%2A> in Grün und `Value` -5.  Wenn Sie nicht aufrufen `UpdateStates` bei der <xref:System.Windows.Controls.ControlTemplate> wird angewendet, um die `NumericUpDown` -Steuerelement, das Steuerelement ist nicht in der `Negative` Status und der Wert ist Grün statt Rot.  Rufen Sie `UpdateStates` zum Platzieren des Steuerelements der `Negative` Zustand.  
  
 [!code-csharp[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
 [!code-vb[VSMCustomControl#ApplyTemplate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]  
  
 Sie müssen häufig aktualisieren Sie den Status eines Steuerelements, wenn eine Eigenschaft ändert. Das folgende Beispiel zeigt die gesamte `ValueChangedCallback` Methode. Da `ValueChangedCallback` wird aufgerufen, wenn `Value` geändert wird, ruft die Methode `UpdateStates` Falls `Value` positiv, negativ oder umgekehrt geändert. Es ist zulässig, rufen Sie `UpdateStates` Wenn `Value` ändert sich jedoch bleibt positiv oder negativ sein, da in diesem Fall der Status des Steuerelements nicht ändern.  
  
 [!code-csharp[VSMCustomControl#EntireValueChangedCallback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#entirevaluechangedcallback)]
 [!code-vb[VSMCustomControl#EntireValueChangedCallback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#entirevaluechangedcallback)]  
  
 Möglicherweise müssen auch die Status zu aktualisieren, wenn ein Ereignis auftritt. Das folgende Beispiel zeigt, dass die `NumericUpDown` Aufrufe `UpdateStates` auf die <xref:System.Windows.Controls.Control> behandelt die <xref:System.Windows.UIElement.GotFocus> Ereignis.  
  
 [!code-csharp[VSMCustomControl#OnGotFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#ongotfocus)]
 [!code-vb[VSMCustomControl#OnGotFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#ongotfocus)]  
  
 Die <xref:System.Windows.VisualStateManager> können Sie die Zustände des Steuerelements zu verwalten. Mithilfe der <xref:System.Windows.VisualStateManager>, Sie stellen Sie sicher, dass das Steuerelement ordnungsgemäß zwischen Zuständen wechselt.  Wenn Sie die Empfehlungen in diesem Abschnitt für die Arbeit mit beschriebenen befolgen Sie die <xref:System.Windows.VisualStateManager>, lesbaren und verwaltbaren Code des Steuerelements bleibt.  
  
<a name="providing_the_control_contract"></a>   
## <a name="providing-the-control-contract"></a>Bereitstellen des Steuerelementvertrags  
 Geben Sie einen Steuerelementvertrag, damit <xref:System.Windows.Controls.ControlTemplate> Autoren wissen, was in die Vorlage eingefügt. Ein Steuerelementvertrag besteht aus drei Elementen:  
  
-   Den visuellen Elementen, die die Logik des Steuerelements verwenden.  
  
-   Den Zuständen des Steuerelements und den Gruppen, zu denen die einzelnen Zustände gehören.  
  
-   Den öffentlichen Eigenschaften, die die visuelle Darstellung des Steuerelements beeinflussen.  
  
 Eine Person, die eine neue erstellt <xref:System.Windows.Controls.ControlTemplate> muss wissen, was <xref:System.Windows.FrameworkElement> Objekte, die die Logik des Steuerelements verwendet werden, was jedes Objekt "" ist, und welche ihr Name ist. Ein <xref:System.Windows.Controls.ControlTemplate> Autor muss außerdem den Namen der jedem möglichen Status des Steuerelements in werden kann und welche kennen <xref:System.Windows.VisualStateGroup> der Zustand befindet.  
  
 Zum Zurückgeben der `NumericUpDown` beispielsweise erwartet, dass das Steuerelement die <xref:System.Windows.Controls.ControlTemplate> über die folgenden <xref:System.Windows.FrameworkElement> Objekte:  
  
-   Ein <xref:System.Windows.Controls.Primitives.RepeatButton> aufgerufen `UpButton`.  
  
-   Ein <xref:System.Windows.Controls.Primitives.RepeatButton> aufgerufen `DownButton.`  
  
 Das Steuerelement kann die folgenden Zustände aufweisen:  
  
-   In der `ValueStates`<xref:System.Windows.VisualStateGroup>  
  
    -   `Positive`  
  
    -   `Negative`  
  
-   In der `FocusStates`<xref:System.Windows.VisualStateGroup>  
  
    -   `Focused`  
  
    -   `Unfocused`  
  
 Um anzugeben, was <xref:System.Windows.FrameworkElement> Objekte erwartet, dass das Steuerelement, das Sie verwenden die <xref:System.Windows.TemplatePartAttribute>, gibt den Namen und Typ der erwarteten Elemente.  Um die möglichen Zustände eines Steuerelements anzugeben, verwenden Sie die <xref:System.Windows.TemplateVisualStateAttribute>, gibt den Namen des Zustands und der <xref:System.Windows.VisualStateGroup> zur gehört.  Versetzen der <xref:System.Windows.TemplatePartAttribute> und <xref:System.Windows.TemplateVisualStateAttribute> auf die Klassendefinition des Steuerelements.  
  
 Jede öffentliche Eigenschaft, die die Darstellung des Steuerelements wirkt sich auf ist ebenfalls ein Teil des Steuerelementvertrags.  
  
 Im folgenden Beispiel wird die <xref:System.Windows.FrameworkElement> Objekt und die Zustände für die `NumericUpDown` Steuerelement.  
  
 [!code-csharp[VSMCustomControl#ControlContract](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controlcontract)]
 [!code-vb[VSMCustomControl#ControlContract](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controlcontract)]  
  
<a name="complete_example"></a>   
## <a name="complete-example"></a>Vollständiges Beispiel  
 Im folgende Beispiel wird die gesamte <xref:System.Windows.Controls.ControlTemplate> für die `NumericUpDown` Steuerelement.  
  
 [!code-xaml[VSMCustomControl#NUDTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/themes/generic.xaml#nudtemplate)]  
  
 Das folgende Beispiel zeigt die Logik für die `NumericUpDown`.  
  
 [!code-csharp[VSMCustomControl#ControlLogic](../../../../samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controllogic)]
 [!code-vb[VSMCustomControl#ControlLogic](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controllogic)]  
  
## <a name="see-also"></a>Siehe auch  
 [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)  
 [Anpassung von Steuerelementen](../../../../docs/framework/wpf/controls/control-customization.md)

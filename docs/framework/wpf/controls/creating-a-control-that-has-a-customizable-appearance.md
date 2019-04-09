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
ms.openlocfilehash: 17b6fd604b5eca54d6323701dafdd38f9f6e7328
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59131018"
---
# <a name="creating-a-control-that-has-a-customizable-appearance"></a>Erstellen eines Steuerelements mit einer anpassbaren Darstellung
<a name="introduction"></a>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet Ihnen die Möglichkeit zum Erstellen eines Steuerelements, dessen Darstellung angepasst werden kann. Sie können z. B. Ändern der Darstellung von einem <xref:System.Windows.Controls.CheckBox> über welche Einstellung tun, als Eigenschaften werden durch Erstellen eines neuen <xref:System.Windows.Controls.ControlTemplate>. Die folgende Abbildung zeigt eine <xref:System.Windows.Controls.CheckBox> , verwendet den Standardwert <xref:System.Windows.Controls.ControlTemplate> und <xref:System.Windows.Controls.CheckBox> , verwendet eine benutzerdefinierte <xref:System.Windows.Controls.ControlTemplate>.  
  
 ![Kontrollkästchen mit der Standardsteuerelementvorlage. ](./media/ndp-checkboxdefault.png "NDP_CheckBoxDefault")  
Ein Kontrollkästchen, das die Standardsteuerelementvorlage verwendet  
  
 ![Kontrollkästchen mit einer benutzerdefinierten Steuerelementvorlage. ](./media/ndp-checkboxcustom.png "NDP_CheckBoxCustom")  
Ein Kontrollkästchen, das eine benutzerdefinierte Steuerelementvorlage verwendet  
  
 Befolgen Sie das Modell Teile und Zustände, wenn Sie ein Steuerelement erstellen, wird die Darstellung des Steuerelements angepasst werden. Designer-Tools wie Microsoft Expression Blend unterstützt das Modell Teile und Zustände aus, damit bei diesem Modell folgen, können Sie das Steuerelement kann in diese Arten von Anwendungen angepasst werden.  In diesem Thema wird erläutert, das Modell Teile und Zustände und es führen bei der Erstellung eigener Steuerelemente. In diesem Thema wird ein Beispiel für ein benutzerdefiniertes Steuerelement `NumericUpDown`, um die Philosophie dieses Modells zu veranschaulichen.  Die `NumericUpDown` Steuerelement zeigt einen numerischen Wert, der ein Benutzer kann zu erhöhen oder verringern, indem Sie durch Klicken auf die Schaltflächen des Steuerelements.  Die folgende Abbildung zeigt die `NumericUpDown` -Steuerelement, das in diesem Thema erläutert wird.  
  
 ![Benutzerdefiniertes NumericUpDown-Steuerelement. ](./media/ndp-numericupdown.png "NDP_NumericUPDown")  
Ein benutzerdefiniertes NumericUpDown-Steuerelement  
  
 Dieses Thema enthält folgende Abschnitte:  
  
-   [Vorraussetzungen](#prerequisites)  
  
-   [Teile und Zustände-Modell](#parts_and_states_model)  
  
-   [Definieren die visuelle Struktur und das visuelle Verhalten eines Steuerelements in einer ControlTemplate](#defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate)  
  
-   [Verwendung von Teilen der ControlTemplate in Code](#using_parts_of_the_controltemplate_in_code)  
  
-   [Bereitstellen des Steuerelementvertrags](#providing_the_control_contract)  
  
-   [Vollständiges Beispiel](#complete_example)  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Vorraussetzungen  
 In diesem Thema wird davon ausgegangen, dass Sie wissen, wie zum Erstellen eines neuen <xref:System.Windows.Controls.ControlTemplate> für ein vorhandenes Steuerelement an, wie die Elemente in einem Steuerelementvertrag sind, vertraut sind und Verstehen der Konzepte, die in beschriebenen [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).  
  
> [!NOTE]
>  Um ein Steuerelement zu erstellen, die dessen Darstellung angepasst werden können, müssen Sie ein Steuerelement, das von erbt erstellen die <xref:System.Windows.Controls.Control> Klasse oder eine ihrer Unterklassen außer <xref:System.Windows.Controls.UserControl>.  Ein Steuerelement, das von erbt <xref:System.Windows.Controls.UserControl> ist ein Steuerelement, das schnell erstellt werden kann, aber es verwendet keine <xref:System.Windows.Controls.ControlTemplate> und seine Darstellung nicht anpassen.  
  
<a name="parts_and_states_model"></a>   
## <a name="parts-and-states-model"></a>Teile und Zustände-Modell  
 Das Modell Teile und Zustände gibt an, wie die visuelle Struktur und das visuelle Verhalten eines Steuerelements zu definieren. Um das Modell Teile und Zustände zu folgen, sollten Sie Folgendes tun:  
  
-   Definieren Sie die visuelle Struktur und das visuelle Verhalten in der <xref:System.Windows.Controls.ControlTemplate> eines Steuerelements.  
  
-   Führen Sie die bestimmte best Practices, wenn die Logik des Steuerelements mit Teilen der Steuerelementvorlage interagiert.  
  
-   Geben Sie einen Steuerelementvertrag angeben, was in enthalten sein sollen die <xref:System.Windows.Controls.ControlTemplate>.  
  
 Wenn Sie definieren die visuelle Struktur und das visuelle Verhalten in der <xref:System.Windows.Controls.ControlTemplate> eines Steuerelements, Anwendungsentwickler können ändern, die visuelle Struktur und das visuelle Verhalten des Steuerelements durch Erstellen eines neuen <xref:System.Windows.Controls.ControlTemplate> statt Code zu schreiben.   Müssen Sie angeben, ein Steuerelementvertrag, der Anwendung weist Autoren die <xref:System.Windows.FrameworkElement> Objekte und Zustände in definiert werden die <xref:System.Windows.Controls.ControlTemplate>. Befolgen Sie einige bewährten Methoden beim Interagieren mit den Teilen in die <xref:System.Windows.Controls.ControlTemplate> , damit das Steuerelement ordnungsgemäß ein unvollständiges behandelt <xref:System.Windows.Controls.ControlTemplate>.  Wenn Sie diese drei Grundsätzen folgen, Anwendungsentwickler werden zum Erstellen einer <xref:System.Windows.Controls.ControlTemplate> für Ihr Steuerelement ebenso leicht wie können für die Steuerelemente, die im Lieferumfang [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Im folgende Abschnitt werden alle diese Empfehlungen im Detail beschrieben.  
  
<a name="defining_the_visual_structure_and_visual_behavior_of_a_control_in_a_controltemplate"></a>   
## <a name="defining-the-visual-structure-and-visual-behavior-of-a-control-in-a-controltemplate"></a>Definieren die visuelle Struktur und das visuelle Verhalten eines Steuerelements in einer ControlTemplate  
 Wenn Sie Ihr benutzerdefinierte Steuerelement erstellen, mit dem Modell Teile und Zustände, definieren Sie visuelle Struktur des Steuerelements und das visuelle Verhalten in seiner <xref:System.Windows.Controls.ControlTemplate> anstelle von in ihrer Logik.  Die visuelle Struktur eines Steuerelements ist die Zusammensetzung der <xref:System.Windows.FrameworkElement> Objekte, die das Steuerelement bilden.  Das visuelle Verhalten ist die Möglichkeit, die das Steuerelement, das angezeigt wird, wenn es in einem bestimmten Zustand befindet.   Weitere Informationen zum Erstellen einer <xref:System.Windows.Controls.ControlTemplate> die visuelle Struktur und das visuelle Verhalten eines Steuerelements, der angibt, finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).  
  
 Im Beispiel für die `NumericUpDown` -Steuerelement, die visuelle Struktur enthält zwei <xref:System.Windows.Controls.Primitives.RepeatButton> Steuerelemente und ein <xref:System.Windows.Controls.TextBlock>.  Wenn Sie diese Steuerelemente im Code hinzufügen, die `NumericUpDown` Steuerelement – in seinem Konstruktor, z. B. – die Positionen der diese Steuerelemente unveränderbar sein würde.  Anstatt die visuelle Struktur und visuelle Verhalten des Steuerelements in seinem Code, definieren Sie ihn in das <xref:System.Windows.Controls.ControlTemplate>.  Klicken Sie dann ein Anwendungsentwickler, um die Position der Schaltflächen anzupassen und <xref:System.Windows.Controls.TextBlock> , und geben Sie das Verhalten tritt auf, wenn `Value` negativ ist da die <xref:System.Windows.Controls.ControlTemplate> ersetzt werden.  
  
 Das folgende Beispiel zeigt die visuelle Struktur des der `NumericUpDown` -Steuerelement, das enthält eine <xref:System.Windows.Controls.Primitives.RepeatButton> erhöhen `Value`, <xref:System.Windows.Controls.Primitives.RepeatButton> verringern `Value`, und ein <xref:System.Windows.Controls.TextBlock> anzuzeigende `Value`.  
  
 [!code-xaml[VSMCustomControl#VisualStructure](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#visualstructure)]  
  
 Das visuelle Verhalten von der `NumericUpDown` Steuerelement ist, dass der Wert in roter Schrift ist, wenn sie negativ ist.  Wenn Sie ändern die <xref:System.Windows.Controls.TextBlock.Foreground%2A> von der <xref:System.Windows.Controls.TextBlock> in code die `Value` negativ ist, die `NumericUpDown` zeigen daraufhin immer einen roten negativen Wert. Geben Sie das visuelle Verhalten des Steuerelements in der <xref:System.Windows.Controls.ControlTemplate> durch Hinzufügen von <xref:System.Windows.VisualState> Objekte die <xref:System.Windows.Controls.ControlTemplate>.  Das folgende Beispiel zeigt die <xref:System.Windows.VisualState> von Objekten für die `Positive` und `Negative` Zustände.  `Positive` und `Negative` sind sich gegenseitig ausschließende (das Steuerelement ist stets in genau einem der beiden), damit das Beispiel setzt die <xref:System.Windows.VisualState> Objekte in einem einzelnen <xref:System.Windows.VisualStateGroup>.  Wenn das Steuerelement wechselt in die `Negative` Zustand der <xref:System.Windows.Controls.TextBlock.Foreground%2A> von der <xref:System.Windows.Controls.TextBlock> Rot.  Wenn das Steuerelement ist der `Positive` Zustand der <xref:System.Windows.Controls.TextBlock.Foreground%2A> zu ihr zurückkehrt ursprünglichen Wert.  Definieren von <xref:System.Windows.VisualState> Objekte in einem <xref:System.Windows.Controls.ControlTemplate> Weitere Informationen finden Sie unter [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md).  
  
> [!NOTE]
>  Werden Sie sicher, dass die <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> angefügte Eigenschaft im Stammelement <xref:System.Windows.FrameworkElement> von der <xref:System.Windows.Controls.ControlTemplate>.  
  
 [!code-xaml[VSMCustomControl#ValueStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]  
  
<a name="using_parts_of_the_controltemplate_in_code"></a>   
## <a name="using-parts-of-the-controltemplate-in-code"></a>Verwendung von Teilen der ControlTemplate in Code  
 Ein <xref:System.Windows.Controls.ControlTemplate> Autor kann weglassen <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.VisualState> Objekte, die absichtlich oder versehentlich, aber die Logik des Steuerelements möglicherweise die Teile ordnungsgemäß funktioniert. Teile und Zustände Modell gibt an, dass das Steuerelement gegen sollte eine <xref:System.Windows.Controls.ControlTemplate> , die fehlt <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.VisualState> Objekte.  Das Steuerelement sollte keine Ausnahme oder ein Bericht einen Fehler auslösen Wenn eine <xref:System.Windows.FrameworkElement>, <xref:System.Windows.VisualState>, oder <xref:System.Windows.VisualStateGroup> fehlt in der <xref:System.Windows.Controls.ControlTemplate>. In diesem Abschnitt wird beschrieben, die empfohlenen Methoden für die Interaktion mit <xref:System.Windows.FrameworkElement> Objekte und Verwalten von Zuständen.  
  
### <a name="anticipate-missing-frameworkelement-objects"></a>Erwarten Sie fehlende FrameworkElement-Objekte  
 Beim Definieren von <xref:System.Windows.FrameworkElement> Objekte in der <xref:System.Windows.Controls.ControlTemplate>, die Logik des Steuerelements muss möglicherweise mit einigen von ihnen zu interagieren.  Z. B. die `NumericUpDown` Steuerelement abonniert der Schaltflächen <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis vergrößern oder verkleinern `Value` und legt sie fest der <xref:System.Windows.Controls.TextBlock.Text%2A> Eigenschaft der <xref:System.Windows.Controls.TextBlock> zu `Value`. Wenn eine benutzerdefinierte <xref:System.Windows.Controls.ControlTemplate> lässt die <xref:System.Windows.Controls.TextBlock> oder Schaltflächen, es ist akzeptabel, dass das Steuerelement verloren, einen Teil der Funktionen hat, aber Sie achten darauf sollten, dass das Steuerelement keinen Fehler verursacht. Z. B. wenn ein <xref:System.Windows.Controls.ControlTemplate> enthält nicht die Schaltflächen zum Ändern `Value`, `NumericUpDown` verliert, Funktionalität, aber eine Anwendung, verwendet der <xref:System.Windows.Controls.ControlTemplate> wird weiterhin ausgeführt.  
  
 Die folgenden Methoden werden sichergestellt, dass das Steuerelement ordnungsgemäß mit fehlendem reagiert <xref:System.Windows.FrameworkElement> Objekte:  
  
1.  Legen Sie die `x:Name` Attribut für die einzelnen <xref:System.Windows.FrameworkElement> , die Sie im Code verweisen müssen.  
  
2.  Definieren Sie für jede private Eigenschaften <xref:System.Windows.FrameworkElement> , die Sie benötigen für die Interaktion mit.  
  
3.  Abonnieren und abbestellen von Ereignisse, die das Steuerelement behandelt den <xref:System.Windows.FrameworkElement> Eigenschaft des set-Accessor.  
  
4.  Legen Sie die <xref:System.Windows.FrameworkElement> Eigenschaften, die Sie definiert haben, in Schritt 2 in der <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> Methode. Dies ist der früheste Zeitpunkt, die die <xref:System.Windows.FrameworkElement> in die <xref:System.Windows.Controls.ControlTemplate> für das Steuerelement verfügbar ist. Verwenden der `x:Name` von der <xref:System.Windows.FrameworkElement> zum Abrufen von der <xref:System.Windows.Controls.ControlTemplate>.  
  
5.  Überprüfen Sie, ob die <xref:System.Windows.FrameworkElement> nicht `null` vor dem Zugriff auf ihre Mitglieder.  Ist dies `null`, keinen Fehler melden.  
  
 Die folgenden Beispiele zeigen die `NumericUpDown` Steuerelement interagiert mit <xref:System.Windows.FrameworkElement> Objekte gemäß den Empfehlungen in der vorangehenden Liste aufgeführt.  
  
 Im Beispiel, das die visuelle Struktur des definiert die `NumericUpDown` steuern, der <xref:System.Windows.Controls.ControlTemplate>, <xref:System.Windows.Controls.Primitives.RepeatButton> erhöht sich dadurch `Value` hat seine `x:Name` -Attributsatz auf `UpButton`.  Das folgende Beispiel deklariert eine Eigenschaft namens `UpButtonElement` darstellt, die die <xref:System.Windows.Controls.Primitives.RepeatButton> , deklariert ist, der <xref:System.Windows.Controls.ControlTemplate>. Die `set` Accessor zuerst kündigt das Abonnement auf der Schaltfläche <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis wenn `UpDownElement` nicht `null`, dann legt die Eigenschaft fest, und klicken Sie dann abonniert die <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis. Es gibt auch eine Eigenschaft definiert, aber hier nicht angezeigt, für die anderen <xref:System.Windows.Controls.Primitives.RepeatButton>namens `DownButtonElement`.  
  
 [!code-csharp[VSMCustomControl#UpButtonProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#upbuttonproperty)]
 [!code-vb[VSMCustomControl#UpButtonProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#upbuttonproperty)]  
  
 Das folgende Beispiel zeigt die <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> für die `NumericUpDown` Steuerelement.  Im Beispiel wird die <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> -Methode zum Abrufen der <xref:System.Windows.FrameworkElement> Objekte aus der <xref:System.Windows.Controls.ControlTemplate>.  Beachten Sie, die im Beispiel für schützt Fälle, in denen <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> sucht nach einem <xref:System.Windows.FrameworkElement> mit dem angegebenen Namen, die nicht den erwarteten Typ ist. Es ist auch eine bewährte Methode, die Elemente zu ignorieren, die dem angegebenen `x:Name` jedoch den falschen Typ.  
  
 [!code-csharp[VSMCustomControl#ApplyTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
 [!code-vb[VSMCustomControl#ApplyTemplate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]  
  
 Befolgen Sie die Methoden, die in den vorherigen Beispielen angezeigt werden, Sie stellen Sie sicher, dass das Steuerelement weiter ausgeführt werden, wenn die <xref:System.Windows.Controls.ControlTemplate> fehlt eine <xref:System.Windows.FrameworkElement>.  
  
### <a name="use-the-visualstatemanager-to-manage-states"></a>Verwenden der VisualStateManager Zustände verwalten  
 Die <xref:System.Windows.VisualStateManager> verfolgt den Zuständen eines Steuerelements und führt die erforderliche Logik zum Übergang zwischen Zuständen. Beim Hinzufügen <xref:System.Windows.VisualState> Objekte die <xref:System.Windows.Controls.ControlTemplate>, fügen Sie die Objekte einer <xref:System.Windows.VisualStateGroup> und Hinzufügen der <xref:System.Windows.VisualStateGroup> auf die <xref:System.Windows.VisualStateManager.VisualStateGroups%2A?displayProperty=nameWithType> angefügte Eigenschaft, damit die <xref:System.Windows.VisualStateManager> hat Zugriff auf diese.  
  
 Im folgende Beispiel wird im vorherige Beispiel, das zeigt, wiederholt der <xref:System.Windows.VisualState> Objekte, die entspricht, der `Positive` und `Negative` Zustände des Steuerelements. Die <xref:System.Windows.Media.Animation.Storyboard> in die `Negative`<xref:System.Windows.VisualState> aktiviert die <xref:System.Windows.Controls.TextBlock.Foreground%2A> von der <xref:System.Windows.Controls.TextBlock> Rot.   Wenn die `NumericUpDown` Steuerelement befindet sich in der `Negative` -Status befindet, handelt es sich bei das Storyboard in der `Negative` Zustand beginnt.  Die <xref:System.Windows.Media.Animation.Storyboard> in die `Negative` Zustand beendet wird, wenn das Steuerelement zurückgegeben der `Positive` Zustand.  Die `Positive`<xref:System.Windows.VisualState> muss nicht enthalten eine <xref:System.Windows.Media.Animation.Storyboard> da bei der <xref:System.Windows.Media.Animation.Storyboard> für die `Negative` beendet wird, die <xref:System.Windows.Controls.TextBlock.Foreground%2A> an seine ursprüngliche Farbe zurückgegeben.  
  
 [!code-xaml[VSMCustomControl#ValueStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/window1.xaml#valuestates)]  
  
 Beachten Sie, dass die <xref:System.Windows.Controls.TextBlock> erhält einen Namen, aber die <xref:System.Windows.Controls.TextBlock> befindet sich nicht in den Steuerelementvertrag für `NumericUpDown` , da die Logik des Steuerelements niemals verweist auf die <xref:System.Windows.Controls.TextBlock>.  Elemente, auf die verweist, die <xref:System.Windows.Controls.ControlTemplate> Namen haben, müssen jedoch nicht Teil des Steuerelementvertrags sein, da eine neue <xref:System.Windows.Controls.ControlTemplate> für das Steuerelement möglicherweise nicht auf dieses Element verweisen muss.  Z. B. eine Person, ein neues erstellt <xref:System.Windows.Controls.ControlTemplate> für `NumericUpDown` ggf. nicht angeben, dass `Value` negativ ist, durch Ändern der <xref:System.Windows.Controls.Control.Foreground%2A>.  In diesem Fall weder den Code noch die <xref:System.Windows.Controls.ControlTemplate> Verweise der <xref:System.Windows.Controls.TextBlock> anhand des Namens.  
  
 Die Logik des Steuerelements ist verantwortlich für den Zustand des Steuerelements zu ändern. Das folgende Beispiel zeigt, dass die `NumericUpDown` kontrollaufrufe der <xref:System.Windows.VisualStateManager.GoToState%2A> Methode näher betrachten die `Positive` Zustand über, wenn `Value` ist 0 oder größer ist, und die `Negative` Zustand über, wenn `Value` ist kleiner als 0.  
  
 [!code-csharp[VSMCustomControl#ValueStateChange](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#valuestatechange)]
 [!code-vb[VSMCustomControl#ValueStateChange](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#valuestatechange)]  
  
 Die <xref:System.Windows.VisualStateManager.GoToState%2A> Methode führt die erforderliche Logik zum Starten und Beenden des Storyboards. Wenn ein Steuerelement ruft <xref:System.Windows.VisualStateManager.GoToState%2A> so ändern Sie seinen Status, der die <xref:System.Windows.VisualStateManager> bewirkt Folgendes:  
  
-   Wenn die <xref:System.Windows.VisualState> hat, dass das Steuerelement, wird eine <xref:System.Windows.Media.Animation.Storyboard>, beginnt das Storyboard. Wenn danach die <xref:System.Windows.VisualState> , das Steuerelement stammt verfügt über eine <xref:System.Windows.Media.Animation.Storyboard>, das Storyboard beendet.  
  
-   Wenn das Steuerelement bereits im Zustand, die angegeben wird ist, <xref:System.Windows.VisualStateManager.GoToState%2A> führt keine Aktion aus und gibt `true`.  
  
-   Wenn angegebene Zustand im nicht vorhanden. die <xref:System.Windows.Controls.ControlTemplate> von `control`, <xref:System.Windows.VisualStateManager.GoToState%2A> führt keine Aktion aus und gibt `false`.  
  
#### <a name="best-practices-for-working-with-the-visualstatemanager"></a>Bewährte Methoden für die Arbeit mit der VisualStateManager  
 Es wird empfohlen, dass Sie Folgendes ein, um die Verwaltung der Zustände Ihres Steuerelements ausführen:  
  
-   Verwenden Sie Eigenschaften, um seinen Status zu nachzuverfolgen.  
  
-   Erstellen Sie eine Hilfsmethode zum Wechseln zwischen Zuständen.  
  
 Die `NumericUpDown` -Steuerelement verwendet die `Value` Eigenschaft, um nachzuverfolgen, ob es in der `Positive` oder `Negative` Zustand.  Die `NumericUpDown` Steuerelement definiert auch die `Focused` und `UnFocused` angibt, welche verfolgt die <xref:System.Windows.UIElement.IsFocused%2A> Eigenschaft. Wenn Sie Zustände, die nicht auf natürliche Weise an eine Eigenschaft des Steuerelements entsprechen verwenden, können Sie eine private Eigenschaft zum Nachverfolgen des Status definieren.  
  
 Eine einzelne Methode, die alle Status aktualisiert zentralisiert die Aufrufe an die <xref:System.Windows.VisualStateManager> und hält Sie Ihren Code überschaubar. Das folgende Beispiel zeigt die `NumericUpDown` Hilfsprogramm-Methode des Steuerelements `UpdateStates`. Wenn `Value` ist größer als oder gleich 0 (null) der <xref:System.Windows.Controls.Control> befindet sich in der `Positive` Zustand.  Wenn `Value` ist kleiner als 0 ist, das Steuerelement ist der `Negative` Zustand.  Bei <xref:System.Windows.UIElement.IsFocused%2A> ist `true`, das Steuerelement befindet sich in der `Focused` Status; andernfalls ist es der `Unfocused` Zustand.  Rufen Sie das Steuerelement kann `UpdateStates` muss jedes Mal, wenn ändert seinen Status, unabhängig davon, welcher Zustand sich ändert.  
  
 [!code-csharp[VSMCustomControl#UpdateStates](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#updatestates)]
 [!code-vb[VSMCustomControl#UpdateStates](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#updatestates)]  
  
 Wenn Sie einen Statusnamen übergeben <xref:System.Windows.VisualStateManager.GoToState%2A> Wenn das Steuerelement bereits in diesem Status wird <xref:System.Windows.VisualStateManager.GoToState%2A> nichts, weshalb Sie nicht für den aktuellen Zustand des Steuerelements zu überprüfen.  Z. B. wenn `Value` ändert sich von der eine negative Zahl in eine andere negative Zahl ist, das Storyboard für die `Negative` Zustand nicht unterbrochen, und dem Benutzer eine Änderung im Steuerelement nicht angezeigt.  
  
 Die <xref:System.Windows.VisualStateManager> verwendet <xref:System.Windows.VisualStateGroup> Objekte, um zu bestimmen, welcher Zustand beendet wird, wenn Sie aufrufen <xref:System.Windows.VisualStateManager.GoToState%2A>. Das Steuerelement ist immer in einem Status für jeden <xref:System.Windows.VisualStateGroup> , definiert ist, dessen <xref:System.Windows.Controls.ControlTemplate> und lässt nur einen Status aus, wenn er in einen anderen Zustand, aus der gleichen wechselt <xref:System.Windows.VisualStateGroup>. Z. B. die <xref:System.Windows.Controls.ControlTemplate> von der `NumericUpDown` -Steuerelement definiert die `Positive` und `Negative`<xref:System.Windows.VisualState> Objekte in einem <xref:System.Windows.VisualStateGroup> und `Focused` und `Unfocused`<xref:System.Windows.VisualState> Objekte in einer anderen. (Sehen Sie die `Focused` und `Unfocused`<xref:System.Windows.VisualState> definiert, der [vollständiges Beispiel](#complete_example) in diesem Thema, wenn das Steuerelement aus wechselt die `Positive` Zustand der `Negative` Zustand, oder umgekehrt, bleibt das Steuerelement entweder die `Focused` oder `Unfocused` Zustand.  
  
 Es gibt drei typische stellen, in denen der Zustand eines Steuerelements ändern können:  
  
-   Wenn die <xref:System.Windows.Controls.ControlTemplate> gilt, an die <xref:System.Windows.Controls.Control>.  
  
-   Wenn sich eine Eigenschaft ändert.  
  
-   Wenn ein Ereignis eintritt.  
  
 Die folgenden Beispiele veranschaulichen, aktualisieren den Status der `NumericUpDown` -Steuerelement in diesen Fällen.  
  
 Aktualisieren Sie den Zustand des Steuerelements in der <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> Methode, damit das Steuerelement angezeigt wird, den richtigen Zustand über, wenn die <xref:System.Windows.Controls.ControlTemplate> angewendet wird. Im folgenden Beispiel wird `UpdateStates` in <xref:System.Windows.FrameworkElement.OnApplyTemplate%2A> um sicherzustellen, dass das Steuerelement im entsprechenden Zustand befindet.  Nehmen wir beispielsweise an, dass Sie erstellen eine `NumericUpDown` steuern, und legen Sie dessen <xref:System.Windows.Controls.Control.Foreground%2A> in Grün und `Value` -5.  Wenn Sie nicht aufrufen `UpdateStates` bei der <xref:System.Windows.Controls.ControlTemplate> gilt für die `NumericUpDown` -Steuerelement, das Steuerelement ist nicht in der `Negative` Status und der Wert ist Grün anstatt Rot.  Rufen Sie `UpdateStates` zum Platzieren des Steuerelements der `Negative` Zustand.  
  
 [!code-csharp[VSMCustomControl#ApplyTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#applytemplate)]
 [!code-vb[VSMCustomControl#ApplyTemplate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#applytemplate)]  
  
 Häufig müssen Sie den Zuständen eines Steuerelements bei Änderung einer Eigenschaft zu aktualisieren. Das folgende Beispiel zeigt die gesamte `ValueChangedCallback` Methode. Da `ValueChangedCallback` wird aufgerufen, wenn `Value` geändert wird, ruft die Methode `UpdateStates` bei `Value` positiv, negativ oder umgekehrt geändert. Es ist akzeptabel, rufen Sie `UpdateStates` beim `Value` geändert, jedoch bleibt positiv oder negativ sein, da in diesem Fall das Steuerelement den Zustand nicht verändert wird.  
  
 [!code-csharp[VSMCustomControl#EntireValueChangedCallback](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#entirevaluechangedcallback)]
 [!code-vb[VSMCustomControl#EntireValueChangedCallback](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#entirevaluechangedcallback)]  
  
 Sie sollten auch die Status zu aktualisieren, wenn ein Ereignis auftritt. Das folgende Beispiel zeigt, dass die `NumericUpDown` Aufrufe `UpdateStates` auf die <xref:System.Windows.Controls.Control> , behandeln die <xref:System.Windows.UIElement.GotFocus> Ereignis.  
  
 [!code-csharp[VSMCustomControl#OnGotFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#ongotfocus)]
 [!code-vb[VSMCustomControl#OnGotFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#ongotfocus)]  
  
 Die <xref:System.Windows.VisualStateManager> hilft Ihnen beim Verwalten Ihres Steuerelements Zustände. Mithilfe der <xref:System.Windows.VisualStateManager>, Sie stellen Sie sicher, dass das Steuerelement ordnungsgemäß zwischen den Zuständen wechselt.  Wenn Sie in den Empfehlungen in diesem Abschnitt für die Arbeit mit folgen der <xref:System.Windows.VisualStateManager>, Ihres Steuerelements Code lesbarer und leichter verwaltbar bleiben.  
  
<a name="providing_the_control_contract"></a>   
## <a name="providing-the-control-contract"></a>Bereitstellen des Steuerelementvertrags  
 Sie stellen einen Steuerelementvertrag bereit, damit <xref:System.Windows.Controls.ControlTemplate> Autoren weiß, was in der Vorlage eingefügt. Ein Steuerelementvertrag besteht aus drei Elementen:  
  
-   Den visuellen Elementen, die die Logik des Steuerelements verwenden.  
  
-   Den Zuständen des Steuerelements und den Gruppen, zu denen die einzelnen Zustände gehören.  
  
-   Den öffentlichen Eigenschaften, die die visuelle Darstellung des Steuerelements beeinflussen.  
  
 Eine Person, die eine neue erstellt <xref:System.Windows.Controls.ControlTemplate> muss wissen, was <xref:System.Windows.FrameworkElement> Objekte, die die Logik des Steuerelements verwendet werden, was jeder Objekttyp werden und was ihr Name ist. Ein <xref:System.Windows.Controls.ControlTemplate> Autor muss auch wissen, den Namen der jedem möglichen Status, die das Steuerelement in sein kann und welche <xref:System.Windows.VisualStateGroup> der Zustand befindet.  
  
 Zum Zurückgeben der `NumericUpDown` beispielsweise erwartet, dass das Steuerelement die <xref:System.Windows.Controls.ControlTemplate> über die folgenden <xref:System.Windows.FrameworkElement> Objekte:  
  
-   Ein <xref:System.Windows.Controls.Primitives.RepeatButton> namens `UpButton`.  
  
-   Ein <xref:System.Windows.Controls.Primitives.RepeatButton> aufgerufen `DownButton.`  
  
 Das Steuerelement kann die folgenden Zustände aufweisen:  
  
-   Geben Sie Feld `ValueStates`<xref:System.Windows.VisualStateGroup>  
  
    -   `Positive`  
  
    -   `Negative`  
  
-   Geben Sie Feld `FocusStates`<xref:System.Windows.VisualStateGroup>  
  
    -   `Focused`  
  
    -   `Unfocused`  
  
 Um anzugeben, welcher <xref:System.Windows.FrameworkElement> Objekte erwartet, dass das Steuerelement, das Sie verwenden die <xref:System.Windows.TemplatePartAttribute>, die angibt, den Namen und Typ der erwarteten Elemente.  Um die möglichen Zustände eines Steuerelements anzugeben, verwenden Sie die <xref:System.Windows.TemplateVisualStateAttribute>, der angibt, der den Namen des Zustands und der <xref:System.Windows.VisualStateGroup> es gehört.  Platzieren der <xref:System.Windows.TemplatePartAttribute> und <xref:System.Windows.TemplateVisualStateAttribute> auf die Definition der Klasse des Steuerelements.  
  
 Eine beliebige öffentliche Eigenschaft, die die Darstellung Ihres Steuerelements wirkt sich auf ist auch ein Teil des Steuerelementvertrags.  
  
 Im folgenden Beispiel wird die <xref:System.Windows.FrameworkElement> Objekt und die Zustände für die `NumericUpDown` Steuerelement.  
  
 [!code-csharp[VSMCustomControl#ControlContract](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controlcontract)]
 [!code-vb[VSMCustomControl#ControlContract](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controlcontract)]  
  
<a name="complete_example"></a>   
## <a name="complete-example"></a>Vollständiges Beispiel  
 Im folgende Beispiel wird die gesamte <xref:System.Windows.Controls.ControlTemplate> für die `NumericUpDown` Steuerelement.  
  
 [!code-xaml[VSMCustomControl#NUDTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/themes/generic.xaml#nudtemplate)]  
  
 Das folgende Beispiel zeigt die Logik für die `NumericUpDown`.  
  
 [!code-csharp[VSMCustomControl#ControlLogic](~/samples/snippets/csharp/VS_Snippets_Wpf/vsmcustomcontrol/csharp/numericupdown.cs#controllogic)]
 [!code-vb[VSMCustomControl#ControlLogic](~/samples/snippets/visualbasic/VS_Snippets_Wpf/vsmcustomcontrol/visualbasic/numericupdown.vb#controllogic)]  
  
## <a name="see-also"></a>Siehe auch

- [Anpassen der Darstellung eines vorhandenen Steuerelements durch Erstellen einer ControlTemplate](customizing-the-appearance-of-an-existing-control.md)
- [Anpassung von Steuerelementen](control-customization.md)

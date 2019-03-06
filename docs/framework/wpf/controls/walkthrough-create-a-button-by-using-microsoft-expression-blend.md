---
title: 'Exemplarische Vorgehensweise: Erstellen einer Schaltfläche mit Microsoft Expression Blend'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
- converting [WPF], shape to button
- Expression Blend [WPF Designer]
ms.assetid: ff5037c2-bba7-4cae-8abb-6475b686c48e
ms.openlocfilehash: cd143b55190ce398cc33e57a832ae85aabc36c41
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352697"
---
# <a name="walkthrough-create-a-button-by-using-microsoft-expression-blend"></a>Exemplarische Vorgehensweise: Erstellen einer Schaltfläche mit Microsoft Expression Blend
Diese exemplarische Vorgehensweise führt Sie durch den Prozess der Erstellung einer [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] benutzerdefinierte Schaltfläche mit Microsoft Expression Blend.  
  
> [!IMPORTANT]
>  Microsoft Expression Blend funktioniert durch die Erstellung [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , kompiliert um das ausführbare Programm zu erstellen. Wenn Sie lieber mit arbeiten [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] direkt, besteht eine weitere exemplarische Vorgehensweise, die die gleiche Anwendung wie diese erstellt [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] mit Visual Studio anstelle von Blend. Finden Sie unter [Erstellen einer Schaltfläche durch Verwenden von XAML](walkthrough-create-a-button-by-using-xaml.md) für Weitere Informationen.  
  
 Die folgende Abbildung zeigt der benutzerdefinierten Schaltfläche, die Sie erstellen.  
  
 ![Die benutzerdefinierte Schaltfläche, die Sie erstellen](./media/custom-button-blend-intro.jpg "Custom_button_blend_Intro")  
  
## <a name="convert-a-shape-to-a-button"></a>Konvertieren von Formen in einer Schaltfläche  
 Im ersten Teil dieser exemplarischen Vorgehensweise erstellen Sie die benutzerdefinierte Darstellung der benutzerdefinierten Schaltfläche. Hierzu konvertieren Sie zuerst ein Rechteck auf eine Schaltfläche. Fügen Sie dann zusätzliche Formen hinzu die Vorlage für die Schaltfläche, erstellen eine komplexere Schaltfläche. Warum nicht beginnen Sie mit der eine normale Schaltfläche aus, und passen sie an? Da eine Schaltfläche verfügt über integrierte Funktionen, die Sie nicht benötigen, für benutzerdefinierte Schaltflächen ist es einfacher, mit einem Rechteck zu beginnen.  
  
#### <a name="to-create-a-new-project-in-expression-blend"></a>Zum Erstellen eines neuen Projekts in Expression Blend  
  
1.  Starten Sie Expression Blend. (Klicken Sie auf **starten**, zeigen Sie auf **Programme**, zeigen Sie auf **Microsoft Expression**, und klicken Sie dann auf **Microsoft Expression Blend**.)  
  
2.  Maximieren Sie die Anwendung bei Bedarf.  
  
3.  Klicken Sie im Menü **Datei** auf **Neues Projekt**.  
  
4.  Wählen Sie **Standardanwendungen (.exe)**.  
  
5.  Nennen Sie das Projekt `CustomButton` , und drücken Sie **OK**.  
  
 An diesem Punkt haben Sie ein leeres [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Projekt. Sie können zum Ausführen der Anwendung F5 drücken. Wie zu erwarten, besteht die Anwendung nur ein leeres Fenster aus. Als Nächstes Sie ein abgerundetes Rechteck erstellen und in eine Schaltfläche zu konvertieren.  
  
#### <a name="to-convert-a-rectangle-to-a-button"></a>Um ein Rechteck auf eine Schaltfläche zu konvertieren.  
  
1.  **Legen Sie die Fenster Background-Eigenschaft auf Schwarz fest:** Wählen Sie das Fenster aus, klicken Sie auf die **Registerkarte "Eigenschaften"**, und legen Sie die <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft `Black`.  
  
     ![Wie Sie den Hintergrund einer Schaltfläche auf Schwarz festgelegt](./media/custom-button-blend-changebackground.png "Custom_button_blend_ChangeBackground")  
  
2.  **Zeichnen Sie ein Rechteck ungefähr der Größe einer Schaltfläche im Fenster ein:** Wählen Sie das Rechteck auf der linken Seite Tool Bereich, und ziehen Sie das Rechteck in das Fenster.  
  
     ![Gewusst wie: Zeichnen eines Rechtecks](./media/custom-button-blend-drawrect.png "Custom_button_blend_DrawRect")  
  
3.  **Runden Sie die Ecken des Rechtecks:** Ziehen Sie die Steuerpunkte des Rechtecks, oder legen Sie direkt die <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> und <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> Eigenschaften. Legen Sie die Werte der <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> und <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> auf 20.  
  
     ![Wie Sie die Ecken eines Rechtecks round](./media/custom-button-blend-roundcorners.png "Custom_button_blend_RoundCorners")  
  
4.  **Ändern Sie das Rechteck, in eine Schaltfläche:** Wählen Sie das Rechteck. Auf der **Tools** Menü klicken Sie auf **stellen Schaltfläche**.  
  
     ![Wie Sie eine Form in eine Schaltfläche](./media/custom-button-blend-makebutton.png "Custom_button_blend_MakeButton")  
  
5.  **Geben Sie den Geltungsbereich der Stilvorlage:** Es wird ein Dialogfeld wie folgt angezeigt.  
  
     ![Das Dialogfeld "Stilressource erstellen"](./media/custom-button-blend-makebutton2.gif "custom_button_blend_MakeButton2")  
  
     Für **Ressourcenname (Schlüssel)** Option **auf alle anwenden**.  Dies veranlasst den resultierenden Stil und eine Schaltflächenvorlage auf alle Objekte angewendet, die Schaltflächen sind. Für **definieren in**Option **Anwendung**. Dies veranlasst den resultierenden Stil und eine Schaltflächenvorlage Bereich über die gesamte Anwendung haben. Wenn Sie die Werte in diesen beiden Felder festlegen, die Schaltflächen-Formatvorlage und die Vorlage gelten für alle Schaltflächen innerhalb der gesamten Anwendung und eine beliebige Schaltfläche, die Sie in der Anwendung zu erstellen, in der Standardeinstellung verwenden diese Vorlage.  
  
## <a name="edit-the-button-template"></a>Bearbeiten Sie die Schaltflächenvorlage  
 Sie haben jetzt ein Rechteck, das auf eine Schaltfläche geändert wurde. In diesem Abschnitt Sie die Vorlage der Schaltfläche ändern, und weiter anpassen, wie er aussieht.  
  
#### <a name="to-edit-the-button-template-to-change-the-button-appearance"></a>So bearbeiten Sie die Schaltflächenvorlage, um die Darstellung der Schaltfläche ändern  
  
1.  **Wechseln Sie in der Vorlage-Bearbeitungsansicht:** Um das Aussehen der Schaltfläche weiter anpassen zu können, müssen wir die Schaltflächenvorlage zu bearbeiten. Mit dieser Vorlage erstellt wurde, wenn wir das Rechteck in eine Schaltfläche konvertiert. Um die Schaltflächenvorlage zu bearbeiten, der rechten Maustaste, und wählen Sie **Steuerelementteile (Vorlage)** und dann **Vorlage bearbeiten**.  
  
     ![Gewusst wie: Bearbeiten Sie eine Vorlage](./media/custom-button-blend-edittemplate.jpg "Custom_button_blend_EditTemplate")  
  
     Die Vorlagen-Editor, beachten Sie, dass die Schaltfläche mit der jetzt in aufgeteilt wird eine <xref:System.Windows.Shapes.Rectangle> und <xref:System.Windows.Controls.ContentPresenter>. Die <xref:System.Windows.Controls.ContentPresenter> wird verwendet, um Inhalt innerhalb der Schaltfläche (z. B. die Zeichenfolge "Button"). Sowohl das Rechteck und <xref:System.Windows.Controls.ContentPresenter> angeordnet wird innerhalb von einer <xref:System.Windows.Controls.Grid>.  
  
     ![Komponenten in der Darstellung eines Rechtecks](./media/custom-button-blend-templatepanel.png "Custom_button_blend_TemplatePanel")  
  
2.  **Ändern Sie die Namen der Komponenten der Dienstvorlage:** Mit der rechten Maustaste in des Rechtecks in der Vorlage Inventar Änderung der <xref:System.Windows.Shapes.Rectangle> in "Rechteck" in "OuterRectangle", und Ändern von "[ContentPresenter]" in "MyContentPresenter".  
  
     ![Vorgehensweise beim Umbenennen einer Komponente einer Vorlage](./media/custom-button-blend-renamecomponents.png "Custom_button_blend_RenameComponents")  
  
3.  **Ändern Sie das Rechteck aus, sodass sie innerhalb von (z. B. ein Rad) leer ist:** Wählen Sie **OuterRectangle** und <xref:System.Windows.Shapes.Shape.Fill%2A> auf "Transparent" und <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> auf 5.  
  
     ![Wie Sie ein Rechteck leer](./media/custom-button-blend-changerectproperties.png "Custom_button_blend_ChangeRectProperties")  
  
     Legen Sie dann die <xref:System.Windows.Shapes.Shape.Stroke%2A> die Farbe von der Vorlage verwendet werden wird. Zu diesem Zweck klicken Sie auf das kleine weiße Feld neben **Stroke**Option **CustomExpression**, und geben Sie im Dialogfeld "{TemplateBinding Background}".  
  
     ![Gewusst wie: Festlegen der Farbe der Vorlage durch der Verwendung](./media/custom-button-blend-templatestroke.png "Custom_button_blend_TemplateStroke")  
  
4.  **Erstellen Sie ein inneres Rechteck:** Erstellen Sie nun ein weiteres Rechteck (nennen es "InnerRectangle"), und positionieren Sie es symmetrisch auf der Innenseite der **OuterRectangle** . Für diese Art der Arbeit empfiehlt es sich zum Zoomen, um die Schaltfläche mit den in den Arbeitsbereich zu vergrößern.  
  
    > [!NOTE]
    >  Das Rechteck kann nicht in der Abbildung aussehen (z. B. es möglicherweise abgerundete Ecken haben).  
  
     ![Vorgehensweise: Erstellen Sie ein Rechteck in einem anderen Rechteck](./media/custom-button-blend-innerrectangleproperties.png "Custom_button_blend_innerRectangleProperties")  
  
5.  **Verschoben Sie ContentPresenter-Element nach oben:** An diesem Punkt ist es möglich, dass der Text "Button" nicht mehr sichtbar sind. Wenn dies der Fall ist, ist dies, da **InnerRectangle** wird auf der die **MyContentPresenter**. Um dieses Problem zu beheben, ziehen Sie **MyContentPresenter** unten **InnerRectangle**. Verschieben von Rechtecken und **MyContentPresenter** sieht etwa folgendermaßen aussehen.  
  
    > [!NOTE]
    >  Alternativ können Sie auch platzieren **MyContentPresenter** oben, indem sie durch Drücken auf **vorwärts senden**.  
  
     ![Gewusst wie: Verschieben Sie eine Schaltfläche über eine andere Schaltfläche](./media/custom-button-blend-innerrectangle2.png "custom_button_blend_innerRectangle2")  
  
6.  **Ändern Sie die Darstellung von InnerRectangle:** Legen Sie die <xref:System.Windows.Shapes.Rectangle.RadiusX%2A>, <xref:System.Windows.Shapes.Rectangle.RadiusY%2A>, und <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> Werte auf 20. In Addition, legen Sie die <xref:System.Windows.Shapes.Shape.Fill%2A> in den Hintergrund der Vorlage mithilfe des benutzerdefinierten Ausdrucks "{TemplateBinding Background}") und legen Sie <xref:System.Windows.Shapes.Shape.Stroke%2A> "transparent". Beachten Sie, dass die Einstellungen für die <xref:System.Windows.Shapes.Shape.Fill%2A> und <xref:System.Windows.Shapes.Shape.Stroke%2A> von **InnerRectangle** sind das Gegenteil davon für **OuterRectangle**.  
  
     ![Gewusst wie: Ändern Sie die Darstellung eines Rechtecks](./media/custom-button-blend-glassrectangleproperties1.png "custom_button_blend_glassRectangleProperties1")  
  
7.  **Fügen Sie oben auf einer Glasebene hinzu:** Das letzte Stück des Anpassen des Aussehens der Schaltfläche ist zum Hinzufügen einer Glass-Ebene im Vordergrund. Diese Glass-Ebene besteht aus einem dritten Rechteck. Da die ganz auf die Schaltfläche mit den gesamten beschrieben wird, ähnelt das Glasrechteck in Dimensionen aus, die die **OuterRectangle**. Aus diesem Grund erstellen Sie das Rechteck einfach, indem Sie das eine Kopie der **OuterRectangle**. Markieren Sie **OuterRectangle** und verwenden Sie STRG + C und STRG + V, um eine Kopie zu erstellen. Benennen Sie diese neue Rechteck "GlassCube".  
  
8.  **Verschieben Sie bei Bedarf GlassCube:** Wenn **GlassCube** ist noch nicht positioniert, sodass es die gesamte Schaltfläche einnimmt, ziehen Sie es in Position.  
  
9. **Geben Sie eine etwas andere Form als OuterRectangle GlassCube:** Ändern der Eigenschaften eines **GlassCube**. Beginnen Sie damit, Ändern der <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> und <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> Eigenschaften auf 10 und der <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> auf 2.  
  
     ![Die darstellungseinstellungen für GlassCube](./media/custom-button-blend-glasscubeappearance.gif "Custom_button_blend_GlassCubeAppearance")  
  
10. **Stellen Sie GlassCube Glas aussehen:** Legen Sie die <xref:System.Windows.Shapes.Shape.Fill%2A> so einen Glaseffekt mit ein linearer Farbverlauf, die 75 % deckend und wechselt zwischen den Farbe Weiß und Transparent über 6 ungefähr gleichmäßig Intervallen Abstand. Hierfür gibt es die Farbverlaufsstopps festgelegt werden soll:  
  
    -   Farbverlaufsstopp 1: Weiß mit einem Alphawert von 75 %  
  
    -   Farbverlaufsstopp 2: Transparent  
  
    -   Farbverlaufsstopp 3: Weiß mit einem Alphawert von 75 %  
  
    -   Farbverlaufsstopp 4: Transparent  
  
    -   Farbverlaufsstopp 5: Weiß mit einem Alphawert von 75 %  
  
    -   Farbverlaufsstopp 6: Transparent  
  
     Dies erstellt einen Blick "wellenförmige" klicken.  
  
     ![Ein Rechteck, das wie aus Glas dargestellt](./media/custom-button-blend-glassrectangleproperties2.png "custom_button_blend_glassRectangleProperties2")  
  
11. **Blenden Sie die Ebene klicken:** Nun, Sie sehen, wie die Glasebene Ebene aussieht, wechseln Sie in der **Darstellungsbereich** von der **Eigenschaftenpanel** und legen Sie die Deckkraft 0 %, um es auszublenden. In den Abschnitten nun verwenden wir Eigenschaftstrigger und Ereignisse zum Anzeigen und bearbeiten die Ebene klicken.  
  
     ![Wie Sie das Glasrechteck ausblenden](./media/custom-button-glassrectangleproperties3.gif "custom_button_glassRectangleProperties3")  
  
## <a name="customize-the-button-behavior"></a>Passen Sie das Schaltflächenverhalten  
 An diesem Punkt haben Sie die Darstellung der Schaltfläche durch Bearbeiten der Vorlage angepasst, aber die Schaltfläche nicht auf Benutzeraktionen reagieren, haben (z. B. Ändern der Darstellung auf die Mouseovereffekte, den Fokus erhält, und klicken.) Die folgenden beiden Verfahren wird das Verhalten, wie diese in die benutzerdefinierte Schaltfläche erstellen, veranschaulicht. Wir beginnen mit einfachen Eigenschaftstrigger und dann Ereignistriggern und Animationen hinzufügen.  
  
#### <a name="to-set-property-triggers"></a>Festlegen von Eigenschaftstriggern  
  
1.  **Erstellen Sie einen neuen Eigenschaftentrigger ein:** Mit **GlassCube** ausgewählt ist, klicken Sie auf **+ Eigenschaft** in die **Trigger** Bereich (siehe die Abbildung im nächsten Schritt). Dadurch wird einen Eigenschaftsauslöser mit ein standardeigenschaftstrigger erstellt.  
  
2.  **Stellen Sie IsMouseOver den Eigenschaft, die vom Trigger verwendet:** Ändern Sie die Eigenschaft in <xref:System.Windows.UIElement.IsMouseOver%2A>. Dadurch wird der Eigenschaftsauslöser aktiviert, wenn die <xref:System.Windows.UIElement.IsMouseOver%2A> Eigenschaft `true` (wenn der Benutzer mit der Maus auf die Schaltfläche zeigt).  
  
     ![Gewusst wie: Festlegen ein Triggers für eine Eigenschaft](./media/custom-button-blend-ismousedoverpropertytrigger.png "Custom_button_blend_IsMousedOverPropertyTrigger")  
  
3.  **IsMouseOver löst die Deckkraft von 100 % für GlassCube:** Beachten Sie, dass die **triggeraufzeichnung ist** (siehe Abbildung oben). Dies bedeutet, dass alle Änderungen, die Sie, um die Eigenschaftswerte vornehmen **GlassCube** werden während der Aufzeichnung auf ist eine Aktion, wenn findet <xref:System.Windows.UIElement.IsMouseOver%2A> ist `true`. Ändern Sie während der Aufzeichnung der <xref:System.Windows.UIElement.Opacity%2A> von **GlassCube** auf 100 %.  
  
     ![Gewusst wie: Festlegen der Deckkraft einer Schaltfläche](./media/custom-button-blend-ismousedoverpropertytrigger2.gif "custom_button_blend_IsMousedOverPropertyTrigger2")  
  
     Sie haben nun Ihre erste Eigenschaftstrigger erstellt. Beachten Sie, dass die **triggerpanel** des Editors aufgezeichnet hat die <xref:System.Windows.UIElement.Opacity%2A> auf 100 % geändert wird.  
  
     ![Der Bereich „Trigger“](./media/custom-button-blend-propertytriggerinfo.png "custom_button_blend_PropertyTriggerInfo")  
  
     Drücken Sie F5, um die Anwendung auszuführen, und bewegen den Mauszeiger über und der Schaltfläche weg. Daraufhin sollte die Glass-Ebene angezeigt, wenn Sie Maus über die Schaltfläche, und nicht mehr angezeigt, wenn der Mauszeiger verlässt.  
  
4.  **Änderung eines Werts zu IsMouseOver-Trigger Zeichnen:** So ordnen Sie einige andere Aktionen mit der <xref:System.Windows.UIElement.IsMouseOver%2A> Trigger. Während der Aufzeichnung fortgesetzt wird, wechseln Sie die Auswahl von **GlassCube** zu **OuterRectangle**. Legen Sie dann die <xref:System.Windows.Shapes.Shape.Stroke%2A> von **OuterRectangle** auf den benutzerdefinierten Ausdruck von "{DynamicResource {X: Static SystemColors.HighlightBrushKey}}". Hiermit wird die <xref:System.Windows.Shapes.Shape.Stroke%2A> markieren Sie die typischen Schaltflächen Tabellentitelleisten-Farbe. Drücken Sie F5, um die Auswirkungen angezeigt werden soll, wenn Sie den Mauszeiger über der Schaltfläche.  
  
     ![Zum Festlegen den Strich auf die Hervorhebungsfarbe](./media/custom-button-blend-ismousedoverpropertytrigger3.png "custom_button_blend_IsMousedOverPropertyTrigger3")  
  
5.  **IsMouseOver löst verschwommenen Text:** So ordnen Sie eine weitere Aktion zu den <xref:System.Windows.UIElement.IsMouseOver%2A> Eigenschaftstrigger. Stellen Sie den Inhalt der Schaltfläche ein wenig verschwommen angezeigt werden, wenn das Glas darüber angezeigt wird. Zu diesem Zweck können wir einen Weichzeichnungseffekt anwenden <xref:System.Windows.Media.Effects.BitmapEffect> auf die <xref:System.Windows.Controls.ContentPresenter> (**MyContentPresenter**).  
  
     ![Wie Sie den Inhalt einer Schaltfläche blur](./media/custom-button-blend-propertytriggerwithbitmapeffect.png "Custom_button_blend_PropertyTriggerWithBitMapEffect")  
  
    > [!NOTE]
    >  Zurückgeben der **Eigenschaftenpanel** an It-Administrator war, bevor haben Sie die Suche nach <xref:System.Windows.Media.Effects.BitmapEffect>, löschen Sie den Text aus der **Suchfeld**.  
  
     An diesem Punkt haben wir einen Eigenschaftsauslöser mit mehreren zugeordneten Aktionen verwendet, um Hervorhebungen Verhalten für zu erstellen, wenn der Mauszeiger in den und den unteren Bereich verlässt. Eine andere normale Verhalten für eine Schaltfläche ist, um hervorzuheben, wenn es den Fokus besitzt (wie nachdem darauf geklickt wurde). Wir können ein solches Verhalten hinzufügen, durch das Hinzufügen einer anderen Eigenschaftsauslöser für die <xref:System.Windows.UIElement.IsFocused%2A> Eigenschaft.  
  
6.  **Erstellen Sie Eigenschaftstrigger für IsFocused:** Mit dem gleichen Verfahren wie für <xref:System.Windows.UIElement.IsMouseOver%2A> (Siehe den ersten Schritt in diesem Abschnitt), erstellen Sie eine andere Eigenschaftentrigger für die <xref:System.Windows.UIElement.IsFocused%2A> Eigenschaft. Während **triggeraufzeichnung ist**, des Triggers die folgenden Aktionen hinzugefügt:  
  
    -   **GlassCube** Ruft eine <xref:System.Windows.UIElement.Opacity%2A> von 100 %.  
  
    -   **OuterRectangle** Ruft eine <xref:System.Windows.Shapes.Shape.Stroke%2A> benutzerdefinierten Ausdrucks-Wert von "{DynamicResource {X: Static SystemColors.HighlightBrushKey}}".  
  
 Als letzten Schritt in dieser exemplarischen Vorgehensweise fügen wir Animationen auf die Schaltfläche hinzu. Diese Animationen werden durch Ereignisse ausgelöst werden – insbesondere die <xref:System.Windows.UIElement.MouseEnter> und <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignisse.  
  
#### <a name="to-use-event-triggers-and-animations-to-add-interactivity"></a>Verwenden von Ereignistriggern und Animationen, Interaktivität hinzuzufügen  
  
1.  **Erstellen Sie einen MouseEnter-Ereignisauslöser:** Fügen Sie einen neuen Ereignistrigger hinzu, und wählen Sie <xref:System.Windows.UIElement.MouseEnter> als das Ereignis, das im Trigger verwendet.  
  
     ![Vorgehensweise: Erstellen Sie einen MouseEnter-Ereignisauslöser](./media/custom-button-blend-mouseovereventtrigger.png "Custom_button_blend_MouseOverEventTrigger")  
  
2.  **Erstellen Sie eine Animationszeitachse:** Als Nächstes ordnen Sie eine Animationszeitachse, die <xref:System.Windows.UIElement.MouseEnter> Ereignis.  
  
     ![Hinzufügen eine Animationszeitachse auf ein Ereignis](./media/custom-button-blend-mouseovereventtrigger2.png "custom_button_blend_MouseOverEventTrigger2")  
  
     Nach dem Drücken der **OK** um eine neue Zeitachse erstellen eine **Zeitachsen (Bereich)** angezeigt wird und "Zeitachse Aufzeichnung aktiviert ist" ist im Bereich Entwurf sichtbar. Dies bedeutet, dass wir die eigenschaftenänderungen aufzeichnen, in der Zeitachse (animieren eigenschaftenänderungen) beginnen können.  
  
    > [!NOTE]
    >  Sie müssen möglicherweise ändern der Größe des Fensters und/oder der Bereiche, um die Anzeige.  
  
     ![Der Zeitachsenbereich](./media/custom-button-blend-mouseovereventtrigger3.png "custom_button_blend_MouseOverEventTrigger3")  
  
3.  **Erstellen Sie einen Keyframe an:** Um eine Animation zu erstellen, wählen Sie das Objekt, die, das Sie animieren, erstellen zwei oder mehr Keyframes auf der Zeitachse, und klicken Sie für diese Keyframes, die Eigenschaftswerte, die Sie die Animation interpoliert zwischen möchten festlegen möchten. In der folgende Abbildung führt Sie durch die Erstellung eines Keyframes.  
  
     ![Gewusst wie: Erstellen eines Keyframes](./media/custom-button-blend-mouseovereventtrigger4.png "custom_button_blend_MouseOverEventTrigger4")  
  
4.  **Verkleinern von GlassCube bei diesen Keyframe:** Mit den zweiten Keyframe ausgewählt, deren Größe die **GlassCube** 90 % der vollständigen Größe mithilfe der **Größe transformieren**.  
  
     ![Gewusst wie: Verkleinern Sie eine Schaltfläche](./media/custom-button-blend-sizetransform.png "Custom_button_blend_SizeTransform")  
  
     Drücken Sie F5, um die Anwendung auszuführen. Verschieben Sie den Mauszeiger über der Schaltfläche. Beachten Sie, dass die Glass-Ebene auf die Schaltfläche mit den verkleinert wird.  
  
5.  **Erstellen Sie einen weiteren Ereignistrigger, und ordnen ihm eine andere Animation zu:** Fügen Sie eine weitere Animation an. Verwenden Sie ein ähnliches Verfahren, was Sie zum Erstellen von der vorherigen Ereignis Trigger Animation verwendet:  
  
    1.  Erstellen Sie ein neues Ereignis Trigger mit dem <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis.  
  
    2.  Ordnen Sie eine neue Zeitachse mit den <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis.  
  
     ![Vorgehensweise: Erstellen Sie eine neue Zeitachse](./media/custom-button-blend-clickeventtrigger1.png "custom_button_blend_ClickEventTrigger1")  
  
    1.  Erstellen Sie für diese Zeitachse zwei Keyframes, nacheinander 0,0 Sekunden und das zweite Argument bei 0,3 Sekunden.  
  
    2.  Legen Sie den Keyframe bei 0,3 Sekunden hervor, die **transformieren Winkel drehen** und 360 Grad.  
  
     ![Vorgehensweise: Erstellen Sie eine Rotationstransformation](./media/custom-button-blend-rotatetransform.gif "Custom_button_blend_RotateTransform")  
  
    1.  Drücken Sie F5, um die Anwendung auszuführen. Klicken Sie auf die Schaltfläche. Beachten Sie, dass die Glass-Ebene dreht.  
  
## <a name="conclusion"></a>Schlussbemerkung  
 Sie haben eine benutzerdefinierte Schaltfläche abgeschlossen. Sie haben dazu eine Schaltflächenvorlage, die auf alle Schaltflächen in der Anwendung angewendet wurde. Wenn Sie den Vorlagenbearbeitungsmodus lassen (siehe die folgende Abbildung) und weitere Schaltflächen erstellen, sehen Sie, dass ihr Aussehen und Verhalten sich wie Ihre benutzerdefinierte Schaltfläche und nicht wie die Schaltfläche "Standard".  
  
 ![Die benutzerdefinierte Schaltflächenvorlage](./media/custom-button-blend-scopeup.gif "Custom_button_blend_ScopeUp")  
  
 ![Mehrere Schaltflächen, die dieselbe Vorlage nutzen](./media/custom-button-blend-createmultiplebuttons.png "Custom_button_blend_CreateMultipleButtons")  
  
 Drücken Sie F5, um die Anwendung auszuführen. Klicken Sie auf die Schaltflächen, und beachten Sie, wie sie alle dasselbe Verhalten.  
  
 Beachten Sie, dass die Vorlage anpassen haben, Sie legen die <xref:System.Windows.Shapes.Shape.Fill%2A> Eigenschaft **InnerRectangle** und <xref:System.Windows.Shapes.Shape.Stroke%2A> Eigenschaft **OuterRectangle** in den Vorlagenhintergrund ({} TemplateBinding Hintergrund}). Aus diesem Grund beim Festlegen der Hintergrundfarbe der einzelnen Schaltflächen, werden die erforderlichen Hintergrundinformationen, die Sie festlegen, für die jeweiligen Eigenschaften verwendet werden. Versuchen Sie es jetzt den Hintergrund zu ändern. In der folgenden Abbildung werden unterschiedliche Verläufe verwendet. Daher auch eine Vorlage für allgemeine Anpassung von Steuerelementen wie Schaltfläche hilfreich ist, können Steuerelemente mit Vorlagen noch geändert werden um voneinander zu suchen.  
  
 ![Schaltflächen mit der gleichen Vorlage, die andere aussehen](./media/custom-button-blend-blendconclusion.jpg "Custom_button_blend_BlendConclusion")  
  
 Das bedeutet, haben Sie gerade eine Schaltflächenvorlage anpassen Vorgehensweise gehen in Microsoft Expression Blend gelernt:  
  
-   Passen Sie das Aussehen eines Steuerelements an.  
  
-   Festlegen von Eigenschaftstriggern. Eigenschaftstrigger sind sehr nützlich, da sie für die meisten Objekte, nicht nur für Steuerelemente verwendet werden können.  
  
-   Festlegen von Ereignistriggern. Ereignistrigger sind sehr nützlich, da sie für die meisten Objekte, nicht nur für Steuerelemente verwendet werden können.  
  
-   Erstellen von Animationen.  
  
-   Sonstiges: Erstellen von Farbverläufen, BitmapEffects hinzufügen, verwenden von Transformationen und legen Sie die grundlegende Eigenschaften von Objekten.  
  
## <a name="see-also"></a>Siehe auch
- [Erstellen einer Schaltfläche mit XAML](walkthrough-create-a-button-by-using-xaml.md)
- [Erstellen von Formaten und Vorlagen](styling-and-templating.md)
- [Übersicht über Animationen](../graphics-multimedia/animation-overview.md)
- [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [Übersicht über Bitmapeffekte](../graphics-multimedia/bitmap-effects-overview.md)

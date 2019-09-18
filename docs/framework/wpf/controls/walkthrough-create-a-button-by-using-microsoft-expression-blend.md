---
title: 'Exemplarische Vorgehensweise: Erstellen einer Schaltfläche mit Microsoft Expression Blend'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
- converting [WPF], shape to button
- Expression Blend [WPF Designer]
ms.assetid: ff5037c2-bba7-4cae-8abb-6475b686c48e
ms.openlocfilehash: 497cd520731d9a0c96ed2b7cb35fa9f53ba25245
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053465"
---
# <a name="walkthrough-create-a-button-by-using-microsoft-expression-blend"></a>Exemplarische Vorgehensweise: Erstellen einer Schaltfläche mit Microsoft Expression Blend

Diese exemplarische Vorgehensweise führt Sie durch den Prozess der [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Erstellung einer angepassten Schaltfläche mit Microsoft Expression Blend.

> [!IMPORTANT]
> Microsoft Expression Blend funktioniert, indem [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] es erzeugt, das dann kompiliert wird, um das ausführbare Programm zu erstellen. Wenn Sie lieber direkt mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] arbeiten, gibt es eine weitere Exemplarische Vorgehensweise, in der dieselbe Anwendung wie diese [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] mit Visual Studio und nicht Blend erstellt wird. Weitere Informationen finden [Sie unter Erstellen einer Schaltfläche mit XAML](walkthrough-create-a-button-by-using-xaml.md) .

Die folgende Abbildung zeigt die angepasste Schaltfläche, die Sie erstellen werden.

![Die benutzerdefinierte Schaltfläche, die Sie erstellen werden](./media/custom-button-blend-intro.jpg)

## <a name="convert-a-shape-to-a-button"></a>Konvertieren einer Form in eine Schaltfläche

Im ersten Teil dieser exemplarischen Vorgehensweise erstellen Sie das benutzerdefinierte Aussehen der benutzerdefinierten Schaltfläche. Zu diesem Zweck konvertieren Sie zuerst ein Rechteck in eine Schaltfläche. Fügen Sie dann der Vorlage der Schaltfläche Weitere Formen hinzu, und erstellen Sie eine komplexere Schaltfläche. Warum beginnen Sie nicht mit einer regulären Schaltfläche, und passen Sie Sie an? Eine Schaltfläche verfügt über integrierte Funktionen, die Sie nicht benötigen. bei benutzerdefinierten Schaltflächen ist es einfacher, mit einem Rechteck zu beginnen.

### <a name="to-create-a-new-project-in-expression-blend"></a>So erstellen Sie ein neues Projekt in Expression Blend

1. Starten Sie Expression Blend. (Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme**, zeigen Sie auf **Microsoft Expression**, und klicken Sie dann auf **Microsoft Expression Blend**.)

2. Maximieren Sie die Anwendung bei Bedarf.

3. Klicken Sie im Menü **Datei** auf **Neues Projekt**.

4. Wählen Sie **Standard Anwendung (. exe)** aus.

5. Benennen Sie das `CustomButton` Projekt, und klicken Sie auf **OK**.

An diesem Punkt verfügen Sie über ein [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] leeres Projekt. Sie können F5 drücken, um die Anwendung auszuführen. Wie Sie vielleicht erwarten, besteht die Anwendung nur aus einem leeren Fenster. Als Nächstes erstellen Sie ein abgerundetes Rechteck und konvertieren es in eine Schaltfläche.

### <a name="to-convert-a-rectangle-to-a-button"></a>So konvertieren Sie ein Rechteck in eine Schaltfläche

1. **Legen Sie die Eigenschaft Window Background auf Black fest:** Wählen Sie das Fenster aus, klicken Sie auf die **Registerkarte Eigenschaften**, `Black`und legen Sie die <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft auf fest.

    ![So legen Sie den Hintergrund einer Schaltfläche auf Schwarz fest](./media/custom-button-blend-changebackground.png)

2. **Zeichnen Sie ein Rechteck ungefähr die Größe einer Schaltfläche im Fenster:** Wählen Sie im linken Werkzeug Panel das Rechteck Tool aus, und ziehen Sie das Rechteck in das Fenster.

    ![So zeichnen Sie ein Rechteck](./media/custom-button-blend-drawrect.png)

3. **Runden Sie die Ecken des Rechtecks ab:** Ziehen Sie entweder die Steuerpunkte des Rechtecks, oder <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> legen <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> Sie die Eigenschaften und direkt fest. Legen Sie die Werte <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> von <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> und auf 20 fest.

    ![So runden Sie die Ecken eines Rechtecks ab](./media/custom-button-blend-roundcorners.png)

4. **Ändern Sie das Rechteck in eine Schaltfläche:** Wählen Sie das Rechteck aus. Klicken Sie **im Menü Extras** auf die **Schaltfläche erstellen**.

    ![So verwandeln Sie eine Form in eine Schaltfläche](./media/custom-button-blend-makebutton.png)

5. **Geben Sie den Bereich des Stils/der Vorlage an:** Ein Dialogfeld wie das folgende wird angezeigt.

    ![Das Dialogfeld "Stilressource erstellen"](./media/custom-button-blend-makebutton2.gif)

    Wählen Sie unter **Ressourcen Name (Schlüssel)** **die Option auf alle anwenden**aus.  Dadurch wird die resultierende Stil-und Schaltflächen Vorlage auf alle Objekte angewendet, bei denen es sich um Schaltflächen handelt. Wählen Sie **unter Definieren in**die Option **Anwendung**aus. Dadurch wird der resultierende Stil und die Schaltflächen Vorlage über die gesamte Anwendung verfügen. Wenn Sie die Werte in diesen beiden Feldern festlegen, werden der Schaltflächen Stil und die Vorlage auf alle Schaltflächen innerhalb der gesamten Anwendung angewendet, und jede Schaltfläche, die Sie in der Anwendung erstellen, wird standardmäßig diese Vorlage verwenden.

## <a name="edit-the-button-template"></a>Bearbeiten der Schaltflächen Vorlage

Sie verfügen jetzt über ein Rechteck, das in eine Schaltfläche geändert wurde. In diesem Abschnitt ändern Sie die Vorlage der Schaltfläche und passen Sie an, wie Sie aussieht.

### <a name="to-edit-the-button-template-to-change-the-button-appearance"></a>So bearbeiten Sie die Schaltflächen Vorlage zum Ändern der Schaltflächen Darstellung

1. **Wechseln Sie in Vorlagen Ansicht bearbeiten:** Um das Aussehen unserer Schaltfläche weiter anzupassen, müssen wir die Schaltflächen Vorlage bearbeiten. Diese Vorlage wurde erstellt, als das Rechteck in eine Schaltfläche konvertiert wurde. Klicken Sie zum Bearbeiten der Schaltflächen Vorlage mit der rechten Maustaste auf die Schaltfläche, und wählen Sie **Steuerelemente bearbeiten (Vorlage)** und dann **Vorlage bearbeiten**aus.

    ![So bearbeiten Sie eine Vorlage](./media/custom-button-blend-edittemplate.jpg)

    Beachten Sie im Vorlagen-Editor, dass die Schaltfläche jetzt in ein <xref:System.Windows.Shapes.Rectangle> und in <xref:System.Windows.Controls.ContentPresenter>den getrennt ist. <xref:System.Windows.Controls.ContentPresenter> Wird verwendet, um Inhalt in der Schaltfläche darzustellen (z. b. die Zeichenfolge "Button"). Sowohl das Rechteck als <xref:System.Windows.Controls.ContentPresenter> auch werden innerhalb <xref:System.Windows.Controls.Grid>eines angeordnet.

    ![Komponenten in der Darstellung eines Rechtecks](./media/custom-button-blend-templatepanel.png)

2. **Ändern Sie die Namen der Vorlagen Komponenten:** Klicken Sie mit der rechten Maustaste auf das Rechteck im Vorlagen bestand <xref:System.Windows.Shapes.Rectangle> , ändern Sie den Namen von "[Rechteck]" in "outerrechteck", und ändern Sie "[ContentPresenter]" in "myContentPresenter".

    ![So benennen Sie eine Komponente einer Vorlage um](./media/custom-button-blend-renamecomponents.png)

3. **Ändern Sie das Rechteck so, dass es in (z. b. in einem Ring) leer ist:** Wählen Sie **outerrechteck** aus <xref:System.Windows.Shapes.Shape.Fill%2A> , und legen Sie auf <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> "transparent" und auf 5 fest.

    ![So leeren Sie ein Rechteck](./media/custom-button-blend-changerectproperties.png)

    Legen Sie dann <xref:System.Windows.Shapes.Shape.Stroke%2A> die Farbe der Vorlage fest. Klicken Sie hierzu auf das kleine weiße Feld neben **Stroke**, wählen Sie **CustomExpression**aus, und geben Sie im Dialogfeld "{TemplateBinding Background}" ein.

    ![So legen Sie den Farbeeinsatz der Vorlage fest](./media/custom-button-blend-templatestroke.png)

4. **Erstellen eines inneren Rechtecks:** Erstellen Sie nun ein weiteres Rechteck (benennen Sie es "innerrechteck"), und positionieren Sie es symmetrisch im Inneren von **outerrechteck** . Für diese Art von Arbeit möchten Sie wahrscheinlich vergrößern, um die Schaltfläche im Bearbeitungsbereich zu vergrößern.

    > [!NOTE]
    > Das Rechteck kann sich von dem in der Abbildung abweichenden (z. b. möglicherweise gerundete Ecken) unterscheiden.

    ![So erstellen Sie ein Rechteck in einem anderen Rechteck](./media/custom-button-blend-innerrectangleproperties.png)

5. **Verschieben Sie ContentPresenter an den Anfang:** An diesem Punkt ist es möglich, dass der Text "Button" nicht mehr sichtbar ist. Wenn dies der Fall ist, liegt dies daran, dass **innerrechteck** oberhalb von **myContentPresenter**liegt. Um dieses Problem zu beheben, ziehen Sie **myContentPresenter** unterhalb des **innerrechtecks**. Ordnen Sie Rechtecke und **myContentPresenter** so an, dass Sie in etwa wie folgt aussehen.

    > [!NOTE]
    > Alternativ können Sie **myContentPresenter** auch oben positionieren, indem Sie mit der rechten Maustaste darauf klicken und dann auf **senden**klicken.

    ![So verschieben Sie eine Schaltfläche über eine andere Schaltfläche](./media/custom-button-blend-innerrectangle2.png)

6. **Ändern Sie das Aussehen des innerrechtecks:** Legen Sie <xref:System.Windows.Shapes.Rectangle.RadiusX%2A>die <xref:System.Windows.Shapes.Rectangle.RadiusY%2A>Werte für <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> , und auf 20 fest. Legen Sie außerdem den <xref:System.Windows.Shapes.Shape.Fill%2A> auf den Hintergrund der Vorlage fest, indem Sie den benutzerdefinierten Ausdruck "{TemplateBinding Background}" verwenden) und auf "transparent" festlegen. <xref:System.Windows.Shapes.Shape.Stroke%2A> Beachten Sie, dass die Einstellungen <xref:System.Windows.Shapes.Shape.Fill%2A> für <xref:System.Windows.Shapes.Shape.Stroke%2A> und von **innerrechteck** das Gegenteil von denen für **outerrechteck**sind.

    ![So ändern Sie die Darstellung eines Rechtecks](./media/custom-button-blend-glassrectangleproperties1.png)

7. **Fügen Sie oben eine Glasebene hinzu:** Das letzte Mal, das Aussehen der Schaltfläche anzupassen, besteht darin, eine Glasebene oben hinzuzufügen. Diese Glasschicht besteht aus einem dritten Rechteck. Da das Glas die gesamte Schaltfläche abdeckt, ähnelt das Glas Rechteck den Abmessungen des **outerrechtecks**. Erstellen Sie daher das Rechteck, indem Sie einfach eine Kopie des **outerrechtecks**erstellen. Markieren Sie **outerrechteck** , und verwenden Sie STRG + C und STRG + V, um eine Kopie zu erstellen. Nennen Sie dieses neue Rechteck "glassCube".

8. **Neupositionieren von glassCube, falls erforderlich:** Wenn **glassCube** nicht bereits so positioniert ist, dass es die gesamte Schaltfläche abdeckt, ziehen Sie es in die Position.

9. **Geben Sie glassCube eine etwas andere Form als outerrechteck an:** Ändern Sie die Eigenschaften von " **glassCube**". Beginnen Sie, indem Sie <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> die <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> -Eigenschaft und die- <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> Eigenschaft auf 10 und den auf 2 ändern.

    ![Die Darstellungseinstellungen für glassCube](./media/custom-button-blend-glasscubeappearance.gif)

10. **Lassen Sie glassCube wie Glas aussehen:** Legen Sie <xref:System.Windows.Shapes.Shape.Fill%2A> den auf einen Glassy-Look fest, indem Sie einen linearen Farbverlauf verwenden, der 75% deckend ist, und zwischen den Farben weiß und transparent über 6 in ungefähr gleichmäßigen Abständen wechseln. So legen Sie die Farbverlaufs Stopps fest:

    - Farbverlaufs Ende 1: Weiß mit Alpha-Wert von 75%

    - Farbverlaufs Ende 2: Transparent

    - Farbverlaufs Ende 3: Weiß mit Alpha-Wert von 75%

    - Farbverlaufs Ende 4: Transparent

    - Farbverlaufs Ende 5: Weiß mit Alpha-Wert von 75%

    - Farbverlaufs Ende 6: Transparent

    Dadurch wird eine "wellenförmige" Glas Suche erstellt.

    ![Ein Rechteck, das wie Glas aussieht.](./media/custom-button-blend-glassrectangleproperties2.png)

11. **Die Glasebene ausblenden:** Nachdem Sie nun sehen, wie die Glassy-Schicht aussieht, wechseln Sie in den Bereich Darstellung des **Eigenschaften Panels** , und legen **Sie die** Deckkraft auf 0% fest, um sie auszublenden. In den Abschnitten weiter oben verwenden wir Eigenschafts Trigger und-Ereignisse, um die Glasschicht anzuzeigen und zu bearbeiten.

    ![So blenden Sie das Glasrechteck aus](./media/custom-button-glassrectangleproperties3.gif)

## <a name="customize-the-button-behavior"></a>Anpassen des Schaltflächen Verhaltens

An diesem Punkt haben Sie die Darstellung der Schaltfläche angepasst, indem Sie die zugehörige Vorlage bearbeiten, aber die Schaltfläche reagiert nicht auf Benutzeraktionen wie normale Schaltflächen (z. b. das Ändern der Darstellung nach dem Mauszeiger, das Empfangen des Fokus und das Klicken auf). In den nächsten zwei Prozeduren wird veranschaulicht, wie Sie Verhalten wie diese in der benutzerdefinierten Schaltfläche erstellen. Wir beginnen mit einfachen Eigenschafts Triggern und fügen dann Ereignis Trigger und Animationen hinzu.

### <a name="to-set-property-triggers"></a>So legen Sie Eigenschafts Trigger fest

1. **Erstellen Sie einen neuen Eigenschafts--Auslöse** Wenn Sie die Option " **glassCube** " ausgewählt haben, klicken Sie im **triggerpanel** auf **+ Eigenschaft** (siehe die Abbildung, die dem nächsten Schritt folgt). Dadurch wird ein Eigenschafts-und ein Standard Eigenschafts-Auslösung erstellt.

2. **Machen Sie IsMouseOver der Eigenschaft, die vom-Auslösers verwendet wird:** Ändern Sie die- <xref:System.Windows.UIElement.IsMouseOver%2A>Eigenschaft in. Dadurch wird der Eigenschafts-und- <xref:System.Windows.UIElement.IsMouseOver%2A> Wert aktiviert `true` , wenn die-Eigenschaft ist (wenn der Benutzer auf die Schaltfläche mit der Maus zeigt).

    ![So legen Sie einen Auslöser für eine Eigenschaft fest](./media/custom-button-blend-ismousedoverpropertytrigger.png)

3. **IsMouseOver löst die Deckkraft von 100% für glassCube aus:** Beachten Sie, dass die **triggeraufzeichnung auf ON fest steht** (siehe vorherige Abbildung). Dies bedeutet, dass alle Änderungen, die Sie an den Eigenschafts Werten von **glassCube** vornehmen, während die Aufzeichnung aktiviert ist, zu <xref:System.Windows.UIElement.IsMouseOver%2A> einer `true`Aktion werden, die ausgeführt wird, wenn ist. Ändern Sie beim Aufzeichnen der <xref:System.Windows.UIElement.Opacity%2A> von **glassCube** in 100%.

    ![So legen Sie die Deckkraft einer Schaltfläche fest](./media/custom-button-blend-ismousedoverpropertytrigger2.gif)

    Sie haben jetzt Ihren ersten Eigenschafts--Auslösers erstellt. Beachten Sie, dass das **triggerpanel** des Editors aufgezeichnet <xref:System.Windows.UIElement.Opacity%2A> hat, dass der Wert in 100% geändert wird.

    ![Der Bereich "Trigger"](./media/custom-button-blend-propertytriggerinfo.png)

    Drücken Sie F5, um die Anwendung auszuführen, und bewegen Sie den Mauszeiger über die Schaltfläche. Sie sollten sehen, dass die Glasebene angezeigt wird, wenn Sie mit dem Mauszeiger auf die Schaltfläche klicken.

4. **IsMouseOver-Trigger: Änderung von Strich Werten:** Im folgenden werden einige weitere Aktionen mit dem <xref:System.Windows.UIElement.IsMouseOver%2A> -Auslösung verknüpft. Wenn die Aufzeichnung fortgesetzt wird, ändern Sie die Auswahl von **glassCube** zu **outerrechteck**. Legen Sie dann <xref:System.Windows.Shapes.Shape.Stroke%2A> den von **outerrechteck** auf den benutzerdefinierten Ausdruck "{dynamikresource {x:static SystemColors. HighlightBrushKey}}" fest. Dadurch wird der <xref:System.Windows.Shapes.Shape.Stroke%2A> auf die von Schaltflächen verwendete typische Hervorhebungs Farbe festgelegt. Drücken Sie F5, um die Auswirkung anzuzeigen, wenn Sie mit dem Mauszeiger auf die Schaltfläche

    ![So legen Sie den Strich auf die Markierungsfarbe fest](./media/custom-button-blend-ismousedoverpropertytrigger3.png)

5. **IsMouseOver löst verschwommene Text aus:** Ordnen Sie dem <xref:System.Windows.UIElement.IsMouseOver%2A> Eigenschafts-Triggervorgang eine weitere Aktion zu. Legen Sie den Inhalt der Schaltfläche ein wenig verschwommen, wenn das Glas darüber angezeigt wird. Zu diesem Zweck können wir einen <xref:System.Windows.Media.Effects.BitmapEffect> Weichzeichner <xref:System.Windows.Controls.ContentPresenter> auf (**myContentPresenter**) anwenden.

    ![So zeichnen Sie den Inhalt einer Schaltfläche weich](./media/custom-button-blend-propertytriggerwithbitmapeffect.png)

    > [!NOTE]
    > Löschen Sie den Text aus dem <xref:System.Windows.Media.Effects.BitmapEffect> **Suchfeld**, um den Eigenschaften Bereich wieder auf den Wert zurückzusetzen, den Sie vor dem Ausführen der Suche hatten.

    An diesem Punkt haben wir einen Eigenschafts-und mehrere zugeordneten Aktionen verwendet, um das Hervorhebungs Verhalten zu erstellen, wenn der Mauszeiger in den Schaltflächen Bereich wechselt und verlässt. Ein weiteres typisches Verhalten für eine Schaltfläche besteht darin, zu markieren, wann Sie den Fokus besitzt (wie nach dem klicken). Dieses Verhalten kann durch Hinzufügen eines weiteren Eigenschafts Auslösers für die <xref:System.Windows.UIElement.IsFocused%2A> Eigenschaft hinzugefügt werden.

6. **Erstellen eines Eigenschafts Auslösers für isfokussiert:** Erstellen Sie mit der gleichen Prozedur <xref:System.Windows.UIElement.IsMouseOver%2A> wie für (siehe den ersten Schritt dieses Abschnitts) einen weiteren Eigenschafts-- <xref:System.Windows.UIElement.IsFocused%2A> Auslösers für die-Eigenschaft. Während die **triggeraufzeichnung auf on basiert**, fügen Sie dem-Triggern die folgenden Aktionen hinzu:

    - **glassCube** erhält einen <xref:System.Windows.UIElement.Opacity%2A> von 100%.

    - **outerrechteck** <xref:System.Windows.Shapes.Shape.Stroke%2A> Ruft den benutzerdefinierten Ausdruckswert "{dynamikresource {x:static SystemColors. HighlightBrushKey}}" ab.

Als letzten Schritt in dieser exemplarischen Vorgehensweise fügen wir der Schaltfläche Animationen hinzu. Diese Animationen werden durch Ereignisse ausgelöst – insbesondere das-Ereignis <xref:System.Windows.UIElement.MouseEnter> und <xref:System.Windows.Controls.Primitives.ButtonBase.Click> das-Ereignis.

### <a name="to-use-event-triggers-and-animations-to-add-interactivity"></a>So verwenden Sie Ereignis Trigger und Animationen zum Hinzufügen von Interaktivität

1. **Erstellen eines mouevent Enter-Ereignis Auslösers:** Fügen Sie einen neuen Ereignis-- <xref:System.Windows.UIElement.MouseEnter> Auslösers hinzu, und wählen Sie als Ereignis aus, das Sie im-

     ![So erstellen Sie einen MouseEnter-Ereignisauslöser](./media/custom-button-blend-mouseovereventtrigger.png)

2. **Erstellen Sie eine Animations Zeitachse:** Ordnen Sie als nächstes dem <xref:System.Windows.UIElement.MouseEnter> Ereignis eine Animations Zeitachse zu.

    ![So fügen Sie eine Animationszeitachse zu einem Ereignis hinzu](./media/custom-button-blend-mouseovereventtrigger2.png)

    Nachdem Sie auf **OK** geklickt haben, um eine neue Zeitachse zu erstellen, wird ein **Zeitachsen Panel** angezeigt, und "Zeitachsen Aufzeichnung ist eingeschaltet" ist im Entwurfs Panel sichtbar. Dies bedeutet, dass die Aufzeichnung von Eigenschafts Änderungen in der Zeitachse gestartet werden kann (Animieren von Eigenschaften Änderungen)

    > [!NOTE]
    > Möglicherweise müssen Sie die Größe des Fensters und/oder der Panels ändern, damit die Anzeige angezeigt wird.

    ![Der Zeitachsenbereich](./media/custom-button-blend-mouseovereventtrigger3.png)

3. **Erstellen Sie einen Keyframe:** Wählen Sie zum Erstellen einer Animation das zu animierende Objekt aus, erstellen Sie zwei oder mehr Keyframes auf der Zeitachse, und legen Sie für diese Keyframes die Eigenschaftswerte fest, zwischen denen die Animation interpolieren soll. Die folgende Abbildung führt Sie durch die Erstellung eines Keyframes.

    ![So erstellen Sie einen Keyframe](./media/custom-button-blend-mouseovereventtrigger4.png)

4. **Verkleinern von glassCube an diesem Keyframe:** Wenn der zweite Keyframe ausgewählt ist, verkleinern Sie die Größe des **glassCube** auf 90% seiner vollen Größe, indem Sie die **Transformation Größe**verwenden.

    ![So verkleinern Sie eine Schaltfläche](./media/custom-button-blend-sizetransform.png)

    Drücken Sie F5, um die Anwendung auszuführen. Bewegen Sie den Mauszeiger über die Schaltfläche. Beachten Sie, dass sich die Glasschicht oberhalb der Schaltfläche verkleinert.

5. **Erstellen eines weiteren Ereignis Auslösers und Zuordnen einer anderen Animation:** Fügen wir eine weitere Animation hinzu. Verwenden Sie ein ähnliches Verfahren, das Sie zum Erstellen der vorherigen Ereignis auslöseranimation verwendet haben:

    1. Erstellen Sie mithilfe des <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignisses einen neuen Ereignis Auslösers.

    2. Ordnen Sie dem <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignis eine neue Zeitachse zu.

        ![So erstellen Sie eine neue Zeitachse](./media/custom-button-blend-clickeventtrigger1.png)

    3. Erstellen Sie für diese Zeitachse zwei Keyframes, eine mit 0,0 Sekunden und die zweite für 0,3 Sekunden.

    4. Legen Sie bei markiertem Keyframe um 0,3 Sekunden den **Winkel Drehung drehen** auf 360 Grad fest.

        ![So erstellen Sie eine Rotationstransformation](./media/custom-button-blend-rotatetransform.gif)

    5. Drücken Sie F5, um die Anwendung auszuführen. Klicken Sie auf die Schaltfläche. Beachten Sie, dass sich die Glasschicht dreht.

## <a name="conclusion"></a>Schlussbemerkung

Sie haben eine angepasste Schaltfläche abgeschlossen. Dazu haben Sie eine Schaltflächen Vorlage verwendet, die auf alle Schaltflächen in der Anwendung angewendet wurde. Wenn Sie den Vorlagen Bearbeitungsmodus verlassen (siehe folgende Abbildung) und weitere Schaltflächen erstellen, sehen Sie, dass Sie sich wie die benutzerdefinierte Schaltfläche und nicht wie die Standard Schaltfläche Verhalten.

![Die Vorlage für benutzerdefinierte Schaltflächen](./media/custom-button-blend-scopeup.gif)

![Mehrere Schaltflächen, die die gleiche Vorlage verwenden](./media/custom-button-blend-createmultiplebuttons.png)

Drücken Sie F5, um die Anwendung auszuführen. Klicken Sie auf die Schaltflächen, und sehen Sie sich an, wie sich alle Verhalten.

Beachten Sie, dass Sie beim Anpassen <xref:System.Windows.Shapes.Shape.Fill%2A> der Vorlage die-Eigenschaft von **innerrechteck** und die <xref:System.Windows.Shapes.Shape.Stroke%2A> -Eigenschaft **outerrechteck** auf den Vorlagen Hintergrund ({TemplateBinding background}) festgelegt haben. Wenn Sie daher die Hintergrundfarbe der einzelnen Schaltflächen festlegen, wird der von Ihnen festgelegte Hintergrund für die jeweiligen Eigenschaften verwendet. Ändern Sie nun die Hintergründe. In der folgenden Abbildung werden verschiedene Farbverläufe verwendet. Obwohl eine Vorlage für die allgemeine Anpassung von Steuerelementen wie Schaltfläche nützlich ist, können Steuerelemente mit Vorlagen so geändert werden, dass Sie unterschiedlich aussehen.

![Schaltflächen mit derselben Vorlage, die diferent aussehen](./media/custom-button-blend-blendconclusion.jpg "custom_button_blend_BlendConclusion")

Im Zuge der Anpassung einer Schaltflächen Vorlage haben Sie in Microsoft Expression Blend Folgendes gelernt:

- Passen Sie das Aussehen eines Steuer Elements an.

- Festlegen von Eigenschafts Triggern. Eigenschafts Trigger sind sehr nützlich, da Sie für die meisten Objekte verwendet werden können, nicht nur für Steuerelemente.

- Legen Sie Ereignis Trigger fest. Ereignis Trigger sind sehr nützlich, da Sie für die meisten Objekte verwendet werden können, nicht nur für Steuerelemente.

- Erstellen von Animationen

- Sonstige: Erstellen von Farbverläufen, Hinzufügen von bitmapeer-ffects, verwenden von Transformationen und Festlegen grundlegender Eigenschaften von Objekten.

## <a name="see-also"></a>Siehe auch

- [Erstellen einer Schaltfläche mit XAML](walkthrough-create-a-button-by-using-xaml.md)
- [Erstellen von Formaten und Vorlagen](styling-and-templating.md)
- [Übersicht über Animationen](../graphics-multimedia/animation-overview.md)
- [Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [Übersicht über Bitmapeffekte](../graphics-multimedia/bitmap-effects-overview.md)

---
title: 'Vorgehensweise: Erstellen einer Aktivität'
description: 'In diesem Artikel erfahren Sie, wie Sie zwei Aktivitäten in Workflow Foundation erstellen: eine, die Code verwendet, um die Logik zu implementieren, und eine, die mithilfe anderer Aktivitäten definiert wurde.'
ms.date: 09/14/2018
dev_langs:
- csharp
- vb
ms.assetid: c09b1e99-21b5-4d96-9c04-ec31db3f4436
ms.openlocfilehash: dae099d102b0c85d09a1ef8bcce56e8a9096bd20
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419589"
---
# <a name="how-to-create-an-activity"></a>Vorgehensweise: Erstellen einer Aktivität

Aktivitäten sind die wichtigsten Einheiten für das Verhalten in [!INCLUDE[wf1](../../../includes/wf1-md.md)]. Die Ausführungslogik einer Aktivität kann in verwaltetem Code oder mithilfe anderer Aktivitäten implementiert werden. In diesem Thema wird veranschaulicht, wie zwei Aktivitäten erstellt werden. Die erste Aktivität ist eine einfache Aktivität, die die Ausführungslogik auf der Basis von Code implementiert. Die Implementierung der zweiten Aktivität wird mithilfe anderer Aktivitäten definiert. Diese Aktivitäten werden in den folgenden Schritten des Lernprogramms verwendet.

> [!NOTE]
> Eine abgeschlossene Version des Tutorials können Sie im [Windows Workflow Foundation (WF45) Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976)herunterladen.

## <a name="create-the-activity-library-project"></a>Erstellen des Aktivitäts Bibliotheks Projekts

1. Öffnen Sie Visual Studio, **New**und wählen Sie  >  im Menü **Datei** die Option neues**Projekt** aus.

2. Wählen Sie im Dialogfeld **Neues Projekt** unter der Kategorie **installiert** die Option **Visual c#**-  >  **Workflow** (oder **Visual Basic**  >  **Workflow**) aus.

    > [!NOTE]
    > Wenn die Kategorie **Workflow** Vorlage nicht angezeigt wird, müssen Sie möglicherweise die **Windows Workflow Foundation** Komponente von Visual Studio installieren. Wählen Sie auf der linken Seite des Dialog Felds **Neues Projekt** den Link **Visual Studio-Installer öffnen** aus. Wählen Sie in Visual Studio-Installer die Registerkarte **einzelne Komponenten** aus. Wählen Sie dann unter der Kategorie **Entwicklungsaktivitäten** die **Windows Workflow Foundation** Komponente aus. Wählen Sie **ändern** aus, um die Komponente zu installieren.

3. Wählen Sie die Projektvorlage **Aktivitäts Bibliothek** aus. Geben Sie `NumberGuessWorkflowActivities` in das Feld **Name** ein, und klicken Sie dann auf **OK**.

4. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **Activity1.xaml**, und wählen Sie dann **Löschen** aus. Klicken Sie zum Bestätigen auf **OK**.

## <a name="create-the-readint-activity"></a>Erstellen der Read int-Aktivität

1. Wählen Sie im Menü **Projekt** die Option **Neues Element hinzufügen** aus.

2. Wählen Sie im Knoten **installierte**  >  **Allgemeine Elemente** die Option **Workflow**aus. Wählen Sie **Code Aktivität** aus der Liste **Workflow** aus.

3. Geben Sie `ReadInt` in das Feld **Name** ein, und klicken Sie dann auf **Hinzufügen**.

4. Ersetzen Sie die vorhandene `ReadInt`-Definition durch die folgende Definition.

     [!code-csharp[CFX_WF_GettingStarted#1](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/readint.cs#1)]
     [!code-vb[CFX_WF_GettingStarted#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/readint.vb#1)]

    > [!NOTE]
    > Die `ReadInt`-Aktivität wird von <xref:System.Activities.NativeActivity%601> statt von <xref:System.Activities.CodeActivity> abgeleitet. Das entspricht dem Standard für die Vorlage "Codeaktivität". <xref:System.Activities.CodeActivity%601> kann verwendet werden, wenn die Aktivität ein einziges Ergebnis bereitstellt, das durch das <xref:System.Activities.Activity%601.Result%2A>-Argument verfügbar gemacht wird, da <xref:System.Activities.CodeActivity%601> jedoch nicht die Verwendung von Lesezeichen unterstützt, wird <xref:System.Activities.NativeActivity%601> verwendet.

## <a name="create-the-prompt-activity"></a>Erstellen der prompt-Aktivität

1. Drücken Sie **STRG** + **UMSCHALT** + **B** , um das Projekt zu erstellen. Durch das Erstellen des Projekts wird die `ReadInt`-Aktivität in diesem Projekt erstellt, mit der die benutzerdefinierte Aktivität aus diesem Schritt erstellt werden soll.

2. Wählen Sie im Menü **Projekt** die Option **Neues Element hinzufügen** aus.

3. Wählen Sie im Knoten **installierte**  >  **Allgemeine Elemente** die Option **Workflow**aus. Wählen Sie **Aktivität** aus der Liste **Workflow** aus.

4. Geben Sie `Prompt` in das Feld **Name** ein, und klicken Sie dann auf **Hinzufügen**.

5. Doppelklicken Sie in **Projektmappen-Explorer** auf **prompt. XAML** , um Sie im Designer anzuzeigen, wenn Sie nicht bereits angezeigt wird.

6. Klicken Sie unten links im Aktivitäts-Designer auf **Argumente**, um den Bereich **Argumente** anzuzeigen.

7. Klicken Sie auf **Argument erstellen**.

8. Geben `BookmarkName` Sie in das Feld **Name** ein, wählen Sie in der Dropdown Liste **Richtung** die Option **in** aus, wählen Sie in der Dropdown Liste **Argumenttyp** die Option **Zeichenfolge** aus, und drücken **Sie** dann die EINGABETASTE, um das Argument

9. Klicken Sie auf **Argument erstellen**.

10. Geben `Result` Sie in das Feld **Name** unter dem neu hinzugefügten `BookmarkName` Argument ein, wählen Sie aus der Dropdown Liste **Richtung** die Option **aus** , wählen Sie in der Dropdown Liste **Argumenttyp** die Option **Int32** aus, und drücken Sie dann die **Eingabe**Taste.

11. Klicken Sie auf **Argument erstellen**.

12. Geben `Text` Sie in das Feld **Name** ein, wählen Sie in der Dropdown Liste **Richtung** die Option **in** aus, wählen Sie in der Dropdown Liste **Argumenttyp** die Option **Zeichenfolge** aus, und drücken **Sie** dann die EINGABETASTE, um das Argument

     Diese drei Argumente werden an die entsprechenden Argumente der <xref:System.Activities.Statements.WriteLine>-Aktivität und `ReadInt`-Aktivität gebunden, die der `Prompt`-Aktivität in den folgenden Schritten hinzugefügt werden.

13. Klicken Sie unten links im Aktivitäts-Designer auf **Argumente**, um den Bereich **Argumente** zu schließen.

14. Ziehen Sie eine **Sequence** -Aktivität aus dem Abschnitt **Ablauf Steuerung** der **Toolbox** , und legen Sie Sie auf der Bezeichnung **Aktivität hier ablegen** des **prompt** -Aktivitäts Designers ab.

    > [!TIP]
    > Wird das Fenster **Toolbox** nicht angezeigt, wählen Sie **Toolbox** im Menü **Ansicht** aus.

15. Ziehen Sie eine " **Write teline** "-Aktivität aus dem Abschnitt **primitive** der **Toolbox** , und legen Sie Sie auf der Bezeichnung **Aktivität hier ablegen** der **Sequence** -Aktivität ab.

16. Binden Sie das **Text** -Argument der " **Write teline** "-Aktivität an das **Text** -Argument der **prompt** -Aktivität `Text` , indem Sie in das Feld " **c#-Ausdruck eingeben** oder **VB-Ausdruck eingeben** " im **Eigenschaften** Fenster eingeben und dann zweimal die **Tab** -Taste drücken. Dadurch wird das Fenster mit den IntelliSense-Listenmembern geschlossen und der Eigenschaftswert gespeichert, indem die Auswahl der Eigenschaft aufgehoben wird. Diese Eigenschaft kann auch festgelegt werden, indem `Text` Sie in das Feld **c#-Ausdruck eingeben** oder **VB-Ausdruck eingeben** der Aktivität selbst eingeben.

    > [!TIP]
    > Wenn das **Fenster Eigenschaften** nicht angezeigt wird, wählen Sie im Menü **Ansicht** die Option **Eigenschaften Fenster** aus.

17. Ziehen Sie eine Aktivität vom Typ "read **int** " aus dem Abschnitt " **nummeriguess Workflow Activities** " der **Toolbox** , und legen Sie Sie in der **Sequence** -Aktivität ab, sodass Sie der Aktivität " **Write teline** " folgt.

18. Binden Sie das **BookmarkName** -Argument der Read **int** -Aktivität an das **BookmarkName** -Argument der **prompt** -Aktivität, indem `BookmarkName` Sie in das Feld **VB-Ausdruck eingeben** rechts neben dem **BookmarkName** -Argument im **Eigenschaften Fenster**eingeben. Drücken Sie dann zweimal die **Tab** -Taste, um das Fenster IntelliSense-Listenelemente zu schließen und die Eigenschaft zu speichern.

19. Binden Sie das **Ergebnis** Argument der Aktivität "read **int** " an das **Ergebnis** Argument **der prompt** -Aktivität, indem Sie in `Result` das Feld "vb- **Ausdruck eingeben** " rechts neben dem **Ergebnis** Argument im **Eigenschaften Fenster**eingeben und dann die **Tab** -Taste zweimal drücken.

20. Drücken Sie **STRG** + **UMSCHALT** + **B** , um die Projekt Mappe zu erstellen.

## <a name="next-steps"></a>Nächste Schritte

Anweisungen zum Erstellen eines Workflows mithilfe dieser Aktivitäten finden Sie im nächsten Schritt des Tutorials, Vorgehens [Weise: Erstellen eines Workflows](how-to-create-a-workflow.md).

## <a name="see-also"></a>Siehe auch

- <xref:System.Activities.CodeActivity>
- <xref:System.Activities.NativeActivity%601>
- [Entwerfen und Implementieren von benutzerdefinierten Aktivitäten](designing-and-implementing-custom-activities.md)
- [Tutorial zu den ersten Schritten](getting-started-tutorial.md)
- [Vorgehensweise: Erstellen eines Workflows](how-to-create-a-workflow.md)
- [Verwenden des ExpressionTextBox in einem benutzerdefinierten Aktivitätsdesigner](./samples/using-the-expressiontextbox-in-a-custom-activity-designer.md)

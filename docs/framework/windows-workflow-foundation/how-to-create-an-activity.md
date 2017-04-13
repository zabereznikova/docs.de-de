---
title: "Vorgehensweise: Erstellen einer Aktivit&#228;t | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c09b1e99-21b5-4d96-9c04-ec31db3f4436
caps.latest.revision: 39
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 39
---
# Vorgehensweise: Erstellen einer Aktivit&#228;t
Aktivitäten sind die wichtigsten Einheiten für das Verhalten in [!INCLUDE[wf1](../../../includes/wf1-md.md)].Die Ausführungslogik einer Aktivität kann in verwaltetem Code oder mithilfe anderer Aktivitäten implementiert werden.In diesem Thema wird veranschaulicht, wie zwei Aktivitäten erstellt werden.Die erste Aktivität ist eine einfache Aktivität, die die Ausführungslogik auf der Basis von Code implementiert.Die Implementierung der zweiten Aktivität wird mithilfe anderer Aktivitäten definiert.Diese Aktivitäten werden in den folgenden Schritten des Lernprogramms verwendet.  
  
> [!NOTE]
>  Um eine abgeschlossene Version des Lernprogramms herunterzuladen, informieren Sie sich unter [Windows Workflow Foundation \(WF45\) – Lernprogramm "Erste Schritte"](http://go.microsoft.com/fwlink/?LinkID=248976).  
  
### So erstellen Sie das Workflow\-Aktivitätsbibliothekprojekt  
  
1.  Öffnen Sie [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], und wählen Sie im Menü **Datei** die Optionen **Neu**, **Projekt** aus.  
  
2.  Erweitern Sie in der Liste **InstallierteVorlagen** den Knoten **Andere Projekttypen**, und wählen Sie **Visual Studio\-Projektmappen** aus.  
  
3.  Wählen Sie in der Liste **Visual Studio\-Projektmappen** die Option **Leere Projektmappe** aus.Stellen Sie sicher, dass in der Dropdownliste mit der .NET Framework\-Version **.NET Framework 4.5** ausgewählt ist.Geben Sie im Feld **Name** den Namen `WF45GettingStartedTutorial` ein, und klicken Sie anschließend auf **OK**.  
  
4.  Klicken Sie im **Projektmappen\-Explorer** auf **WF45GettingStartedTutorial**, zeigen Sie auf **Hinzufügen**, und wählen Sie **Neues Projekt** aus.  
  
    > [!TIP]
    >  Wenn das Fenster **Projektmappen\-Explorer** nicht angezeigt wird, wählen Sie im Menü **Ansicht** die Option **Projektmappen\-Explorer** aus.  
  
5.  Wählen Sie im Knoten **Installiert** die Option **Visual C\#** und anschließend **Workflow** \(oder **Visual Basic**, **Workflow**\) aus.Stellen Sie sicher, dass in der Dropdownliste mit der [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]\-Version **.NET Framework 4.5** ausgewählt ist.Wählen Sie in der Liste **Workflow** die Option **Aktivitätsbibliothek** aus.Geben Sie im Feld `Name` die Bezeichnung **NumberGuessWorkflowActivities** ein, und klicken Sie dann auf **OK**.  
  
    > [!NOTE]
    >  In Abhängigkeit davon, welche Programmiersprache als die primäre Sprache in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] konfiguriert ist, befindet sich der Knoten **Visual C\#** oder **Visual Basic** möglicherweise nicht unter dem Knoten **Andere Sprachen** im Knoten **Installiert**.  
  
6.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf **Activity1.xaml**, und wählen Sie dann **Löschen** aus.Klicken Sie zur Bestätigung auf **OK**.  
  
### So erstellen Sie die ReadInt\-Aktivität  
  
1.  Wählen Sie im Menü **Projekt** die Option **Neues Element hinzufügen** aus.  
  
2.  Wählen Sie im Knoten **Gemeinsame Elemente** unter **Installiert** die Option **Workflow** aus.Wählen Sie in der Liste **Workflow** die Option **Codeaktivität** aus.  
  
3.  Geben Sie in das Feld **Name** den Text `ReadInt` ein, und klicken Sie auf **Hinzufügen**.  
  
4.  Ersetzen Sie die vorhandene `ReadInt`\-Definition durch die folgende Definition.  
  
     [!code-csharp[CFX_WF_GettingStarted#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/readint.cs#1)]
     [!code-vb[CFX_WF_GettingStarted#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/readint.vb#1)]  
  
    > [!NOTE]
    >  Die `ReadInt`\-Aktivität wird von <xref:System.Activities.NativeActivity%601> statt von <xref:System.Activities.CodeActivity> abgeleitet. Das entspricht dem Standard für die Vorlage "Codeaktivität".<xref:System.Activities.CodeActivity%601> kann verwendet werden, wenn die Aktivität ein einziges Ergebnis bereitstellt, das durch das <xref:System.Activities.Activity%601.Result%2A>\-Argument verfügbar gemacht wird, da <xref:System.Activities.CodeActivity%601> jedoch nicht die Verwendung von Lesezeichen unterstützt, wird <xref:System.Activities.NativeActivity%601> verwendet.  
  
### So erstellen Sie die Prompt\-Aktivität  
  
1.  Drücken Sie STRG\+UMSCHALT\+B, um das Projekt zu erstellen.Durch das Erstellen des Projekts wird die `ReadInt`\-Aktivität in diesem Projekt erstellt, mit der die benutzerdefinierte Aktivität aus diesem Schritt erstellt werden soll.  
  
2.  Wählen Sie im Menü **Projekt** die Option **Neues Element hinzufügen** aus.  
  
3.  Wählen Sie im Knoten **Gemeinsame Elemente** unter **Installiert** die Option **Workflow** aus.Wählen Sie in der Liste **Workflow** die Option **Aktivität** aus.  
  
4.  Geben Sie `Prompt` in das Feld **Name** den Text ein, und klicken Sie auf **Hinzufügen**.  
  
5.  Doppelklicken Sie im Projektmappen\-Explorer auf **Prompt.xaml**, um die Datei im Designer anzuzeigen, falls dies nicht bereits der Fall ist.  
  
6.  Klicken Sie links unten im Aktivitäts\-Designer auf die Schaltfläche **Argumente**, um den Bereich **Argumente** anzuzeigen.  
  
7.  Klicken Sie auf **Argument erstellen**.  
  
8.  Geben Sie `BookmarkName` in das Feld **Name** ein, wählen Sie aus der Dropdownliste **Richtung** die Richtung **In** und aus der Dropdownliste **Argumenttyp** die Option **String** aus, und drücken Sie dann die EINGABETASTE, um das Argument zu speichern.  
  
9. Klicken Sie auf **Argument erstellen**.  
  
10. Geben Sie in das Feld **Name**, das unter dem neu hinzugefügten Argument `BookmarkName` angezeigt wird, `Result` ein. Wählen Sie aus der Dropdownliste **Richtung** die Richtung **Out** und aus der Dropdownliste **Argumenttyp** die Option **Int32** aus, und drücken Sie dann die EINGABETASTE.  
  
11. Klicken Sie auf **Argument erstellen**.  
  
12. Geben Sie `Subtotal` im Feld **Name** ein, und wählen Sie aus der Dropdownliste **Richtung** die Option **In** aus. Wählen Sie **String** aus der Dropdownliste **Argumenttyp** aus. Drücken Sie dann die EINGABETASTE, um das Argument zu speichern.  
  
     Diese drei Argumente werden an die entsprechenden Argumente der <xref:System.Activities.Statements.WriteLine>\-Aktivität und `ReadInt`\-Aktivität gebunden, die der `Prompt`\-Aktivität in den folgenden Schritten hinzugefügt werden.  
  
13. Klicken Sie links unten im Aktivitäts\-Designer auf die Schaltfläche **Argumente**, um den Bereich **Argumente** zu schließen.  
  
14. Ziehen Sie eine **Sequence**\-Aktivität aus dem Abschnitt **Ablaufsteuerung** der **Toolbox**, und legen Sie sie auf der Bezeichnung **Aktivität hier ablegen** des Designers der **Prompt**\-Aktivität ab.  
  
    > [!TIP]
    >  Wenn das Fenster **Toolbox** nicht sichtbar ist, wählen Sie im Menü **Ansicht** die Option **Toolbox** aus.  
  
15. Ziehen Sie eine **WriteLine**\-Aktivität aus dem Abschnitt **Primitive** der **Toolbox**, und legen Sie sie auf der Bezeichnung **Aktivität hier ablegen** der **Sequence**\-Aktivität ab.  
  
16. Binden Sie das **Text**\-Argument der **WriteLine**\-Aktivität an das **Text**\-Argument der **Prompt**\-Aktivität, indem Sie im Fenster **Eigenschaften** im Feld **C\#\-Ausdruck eingeben** oder **VB\-Ausdruck eingeben** die Bezeichnung `Result` eingeben. Drücken Sie dann zwei Mal die TAB\-TASTE.Dadurch wird das Fenster mit den IntelliSense\-Listenmembern geschlossen und der Eigenschaftswert gespeichert, indem die Auswahl der Eigenschaft aufgehoben wird.Diese Eigenschaft kann auch festgelegt werden, indem Sie in das Feld **C\#\-Ausdruck eingeben** oder **VB\-Ausdruck eingeben** der Aktivität `Text` eingeben.  
  
    > [!TIP]
    >  Klicken Sie im Menü **Ansicht** auf **Eigenschaftenfenster**, falls das Fenster **Eigenschaften** nicht angezeigt wird.  
  
17. Ziehen Sie eine **ReadInt**\-Aktivität aus dem Abschnitt **ANumberGuessWorkflowActivities** der **Toolbox**, und legen Sie sie in der **Sequence**\-Aktivität ab, sodass sie unmittelbar auf die **WriteLine**\-Aktivität folgt.  
  
18. Binden Sie das **BookmarkName**\-Argument der **ReadInt**\-Aktivität an das **BookmarkName**\-Argument der **Prompt**\-Aktivität, indem Sie im Fenster **Eigenschaften** im Feld **VB\-Ausdruck eingeben** neben dem **BookmarkName**\-Argument die Bezeichnung `BookmarkName` eingeben. Drücken Sie dann die TAB\-TASTE zwei Mal, um das Fenster mit den IntelliSense\-Listenmembern zu schließen und die Eigenschaft zu speichern.  
  
19. Binden Sie das **Result**\-Argument der **ReadInt**\-Aktivität an das **Result**\-Argument der **Prompt**\-Aktivität, indem Sie im Fenster **Eigenschaften** im Feld **VB\-Ausdruck eingeben** neben dem **Result**\-Argument die Bezeichnung `Result` eingeben. Drücken Sie dann die TAB\-TASTE zwei Mal, um das Fenster mit den IntelliSense\-Listenmembern zu schließen und die Eigenschaft zu speichern.  
  
20. Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen.  
  
     Anweisungen zum Erstellen eines Workflows mithilfe dieser Aktivitäten finden Sie im nächsten Lernprogrammschritt [Vorgehensweise: Erstellen eines Workflows](../../../docs/framework/windows-workflow-foundation//how-to-create-a-workflow.md).  
  
## Siehe auch  
 <xref:System.Activities.CodeActivity>   
 <xref:System.Activities.NativeActivity%601>   
 [Entwerfen und Implementieren von benutzerdefinierten Aktivitäten](../../../docs/framework/windows-workflow-foundation//designing-and-implementing-custom-activities.md)   
 [Lernprogramm 'Erste Schritte'](../../../docs/framework/windows-workflow-foundation//getting-started-tutorial.md)   
 [Vorgehensweise: Erstellen eines Workflows](../../../docs/framework/windows-workflow-foundation//how-to-create-a-workflow.md)   
 [Verwenden des ExpressionTextBox in einem benutzerdefinierten Aktivitätsdesigner](../../../docs/framework/windows-workflow-foundation/samples/using-the-expressiontextbox-in-a-custom-activity-designer.md)
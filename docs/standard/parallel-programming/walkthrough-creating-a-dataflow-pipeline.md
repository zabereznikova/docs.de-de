---
title: 'Exemplarische Vorgehensweise: Erstellen einer Datenflusspipeline'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dataflow pipelines, creating with TPL
- Task Parallel Library, dataflows
- TPL dataflow library, creating dataflow pipeline
ms.assetid: 69308f82-aa22-4ac5-833d-e748533b58e8
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d63fb872382bfc0a3ba3b8637c7357ab65c58fbf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-creating-a-dataflow-pipeline"></a>Exemplarische Vorgehensweise: Erstellen einer Datenflusspipeline
Sie können zwar die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A?displayProperty=nameWithType>, und <xref:System.Threading.Tasks.Dataflow.DataflowBlock.TryReceive%2A?displayProperty=nameWithType> -Methode zum Empfangen von Nachrichten von quellblöcken, Sie können auch Nachrichtenblöcke verbinden, in Form einer *Datenflusspipeline*. Eine Datenpipeline besteht aus einer Reihe von Komponenten, oder *Datenflussblöcke*, von denen jede eine bestimmte Aufgabe, die zu einem größeren Ziel beiträgt ausführt. Jeder Datenflussblock in einer Datenflusspipeline erledigt eine Aufgabe, wenn er eine Meldung von einem anderen Datenflussblock empfangen hat. Eine Analogie hierzu ist eine Fertigungsstraße eines Fahrzeugherstellers. Jedes Fahrzeug durchläuft die Fertigungsstraße: In einer Station wird das Fahrgestell montiert, in der nächsten wird der Motor eingebaut usw. Da eine Fertigungsstraße ermöglicht, dass mehrere Fahrzeuge gleichzeitig montiert werden, bietet sie einen besseren Durchsatz als eine Einzelmontage eines vollständigen Fahrzeugs.  
  
> [!TIP]
>  Die TPL-Datenflussbibliothek (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType>-Namespace) ist nicht in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] enthalten. Öffnen Sie zum Installieren des <xref:System.Threading.Tasks.Dataflow>-Namespace das Projekt in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], wählen Sie im Menü "Projekt" die Option **NuGet-Pakete verwalten** aus, und suchen Sie online nach dem `Microsoft.Tpl.Dataflow` -Paket.  
  
 Dieses Dokument veranschaulicht eine Datenflusspipeline, die das Buch downloads *The Iliad of Homer* aus einer Website und Suchvorgänge Wörter der Text, der mit einzelnen Wörtern, Reverse das erste Wort Zeichen. Die Entwicklung der Datenflusspipeline in diesem Dokument besteht aus den folgenden Schritten:  
  
1.  Erstellen Sie die Datenflussblöcke, die Bestandteile der Pipeline sein sollen.  
  
2.  Verbinden Sie jeden Datenflussblock mit dem nächsten Block in der Pipeline. Jeder Block empfängt als Eingabe die Ausgabe des jeweils vorherigen Blocks in der Pipeline.  
  
3.  Erstellen Sie für jeden Datenflussblock eine Fortsetzungsaufgabe, die den nächsten Datenblock in den Zustand Abgeschlossen schaltet, nachdem der vorherige Block beendet wurde.  
  
4.  Senden Sie Daten an den Anfang der Pipeline.  
  
5.  Kennzeichnen Sie den Anfang der Pipeline als abgeschlossen.  
  
6.  Warten Sie, bis die Pipeline alle Aufgaben ausgeführt hat.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Lesen Sie das Thema [Datenfluss](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md), bevor Sie mit dieser exemplarischen Vorgehensweise beginnen.  
  
## <a name="creating-a-console-application"></a>Erstellen einer Konsolenanwendung  
 Erstellen Sie in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] ein [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]- oder ein [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]-Konsolenanwendungsprojekt. Fügen Sie einen Verweis auf „System.Threading.Tasks.Dataflow.dll“ hinzu.  
  
 Alternativ können Sie eine Datei erstellen, und nennen Sie sie `ReverseWords.cs` (`ReverseWords.vb` für [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), und führen Sie dann den folgenden Befehl in einem Visual Studio-Eingabeaufforderung Fenster, um das Projekt zu kompilieren.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe /r:System.Threading.Tasks.Dataflow.dll ReverseWords.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe /r:System.Threading.Tasks.Dataflow.dll ReverseWords.vb**  
  
 Fügen Sie Ihrem Projekt den folgenden Code hinzu , um die Grundanwendung zu erstellen.  
  
 [!code-csharp[TPLDataflow_Palindromes#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#2)]
 [!code-vb[TPLDataflow_Palindromes#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#2)]  
  
## <a name="creating-the-dataflow-blocks"></a>Erstellen der Datenflussblöcke  
 Fügen Sie der `Main`-Methode den folgenden Code hinzu, um die Datenflussblöcke zu erstellen, die Bestandteile der Pipeline sein sollen. Die folgende Tabelle enthält eine Übersicht über die Rollen, die die Elemente (Member) der Pipeline haben.  
  
 [!code-csharp[TPLDataflow_Palindromes#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#3)]
 [!code-vb[TPLDataflow_Palindromes#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#3)]  
  
|Member|Typ|Beschreibung|  
|------------|----------|-----------------|  
|`downloadString`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|Lädt den Text des Buchs aus dem Internet herunter.|  
|`createWordList`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|Trennt den Text des Buchs in ein Array aus einzelnen Wörtern.|  
|`filterWordList`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|Entfernt kurze Wörter aus dem Wortarray, sortiert die verbliebenen Wörter alphabetisch und entfernt Duplikate.|  
|`findReversedWords`|<xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602>|Sucht in der gefilterten Wortarrayauflistung nach allen Wörtern, deren Umkehrung ebenfalls im Wortarray enthalten ist.|  
|`printReversedWords`|<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>|Zeigt die jeweiligen Wörter und die entsprechenden Umkehrwörter in der Konsole an.|  
  
 Obwohl Sie mehrere Schritte in der Datenflusspipeline in diesem Beispiel in einem einzigen Schritt kombinieren könnten, veranschaulicht dieses Beispiel das Konzept des Zusammenstellens mehrerer unabhängiger Datenflussaufgaben, um eine größere Aufgabe auszuführen. In dem Beispiel wird <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> verwendet, damit jedes Element der Pipeline einen Vorgang für seine Eingabedaten ausführen und die Ergebnisse an den nächsten Schritt in der Pipeline senden kann. Das `findReversedWords`-Element der Pipeline ist ein <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602>-Objekt, da es für jede Eingabe mehrere unabhängige Ausgaben erzeugt. Das Ende der Pipeline, `printReversedWords`, ist ein <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>-Objekt, weil es eine Aktion für seine Eingabe ausführt und kein Ergebnis erzeugt.  
  
## <a name="forming-the-pipeline"></a>Aufbauen der Pipeline  
 Fügen Sie den folgenden Code ein, um jeden Block mit dem nächsten Block in der Pipeline zu verbinden.  
  
 Wenn Sie die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.LinkTo%2A>-Methode aufrufen, um einen Quelldatenflussblock mit einem Zieldatenflussblock zu verbinden, überträgt der Quelldatenflussblock Daten an den Zielblock, sobald Daten verfügbar sind.  
  
 [!code-csharp[TPLDataflow_Palindromes#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#4)]
 [!code-vb[TPLDataflow_Palindromes#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#4)]  
  
## <a name="creating-the-completion-tasks"></a>Erstellen der Abschlussaufgaben (Completion-Aufgaben)  
 Fügen Sie den folgenden Code hinzu, damit jeder Datenflussblock eine abschließende Aktion ausführt, nachdem er alle Daten verarbeitet hat.  
  
 [!code-csharp[TPLDataflow_Palindromes#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#5)]
 [!code-vb[TPLDataflow_Palindromes#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#5)]  
  
 Um den Abschluss durch die Pipeline zu übermitteln, legt jede Abschlussaufgabe den nächsten Datenflussblock auf den Zustand Abgeschlossen (Completed) fest. Wird beispielsweise der Anfang der Pipeline auf den Zustand Abgeschlossen festgelegt, verarbeitet er alle verbliebenen gepufferten Nachrichten und führt dann seine Abschlussaufgabe aus, die das zweite Element der Pipeline auf den Zustand Abgeschlossen festlegt. Das zweite Element der Pipeline verarbeitet wiederum alle verbliebenen gepufferten Nachrichten und führt dann seine Abschlussaufgabe aus, die das dritte Element der Pipeline auf den Zustand Abgeschlossen festlegt. Diese Vorgehensweise wird fortgesetzt, bis alle Elemente der Pipeline abgeschlossen sind. In diesem Beispiel wird das Schlüsselwort `delegate` (`Function` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) verwendet, um die Fortsetzungsaufgaben zu definieren.  
  
## <a name="posting-data-to-the-pipeline"></a>Senden von Daten an die Pipeline  
 Fügen Sie folgenden Code, um die URL des Buchs buchen *The Iliad of Homer* an den Anfang der Datenflusspipeline zu senden.  
  
 [!code-csharp[TPLDataflow_Palindromes#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#6)]
 [!code-vb[TPLDataflow_Palindromes#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#6)]  
  
 In diesem Beispiel wird <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A?displayProperty=nameWithType> verwendet, damit die Daten synchron an den Anfang der Pipeline gesendet werden. Verwenden Sie die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A?displayProperty=nameWithType>-Methode, wenn Sie Daten asynchron an einen Datenflussknoten senden müssen.  
  
## <a name="completing-pipeline-activity"></a>Abschließen der Pipelineaktivität  
 Fügen Sie den folgenden Code ein, um den Anfang der Pipeline als abgeschlossen zu kennzeichnen. Der Anfang der Pipeline führt seine Fortsetzungsaufgabe aus, nachdem er alle gepufferten Nachrichten verarbeitet hat. Diese Fortsetzungsaufgabe überträgt den Zustand Abgeschlossen durch die Pipeline.  
  
 [!code-csharp[TPLDataflow_Palindromes#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#7)]
 [!code-vb[TPLDataflow_Palindromes#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#7)]  
  
 In diesem Beispiel wird eine URL durch die Datenflusspipeline gesendet, um verarbeitet zu werden. Wenn Sie mehrere Eingaben durch eine Pipeline senden, rufen Sie die <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A?displayProperty=nameWithType>-Methode auf, nachdem Sie alle Eingaben übertragen haben. Sie können auf diesen Schritt verzichten, wenn Ihre Anwendung keinen wohldefinierten Punkt hat, an dem keine Daten mehr verfügbar sind, oder wenn die Anwendung nicht warten muss, bis die Pipeline beendet ist.  
  
## <a name="waiting-for-the-pipeline-to-finish"></a>Warten bis zum Beenden der Pipeline  
 Fügen Sie den folgenden Code hinzu, damit gewartet wird, bis die Pipeline beendet ist. Da in diesem Beispiel Fortsetzungsaufgaben verwendet werden, um Abschluss durch die Pipeline zu übertragen, ist der gesamte Vorgang abgeschlossen, wenn das Ende der Pipeline abgeschlossen ist.  
  
 [!code-csharp[TPLDataflow_Palindromes#8](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#8)]
 [!code-vb[TPLDataflow_Palindromes#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#8)]  
  
 Sie können von jedem Thread oder von mehreren Threads gleichzeitig auf den Datenflussabschluss warten.  
  
## <a name="the-complete-example"></a>Vollständiges Beispiel  
 Das folgende Beispiel enthält den vollständigen Code für diese exemplarische Vorgehensweise.  
  
 [!code-csharp[TPLDataflow_Palindromes#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#1)]
 [!code-vb[TPLDataflow_Palindromes#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#1)]  
  
## <a name="next-steps"></a>Nächste Schritte  
 In diesem Beispiel wird eine zu verarbeitende URL durch die Datenflusspipeline gesendet. Wenn Sie mehrere Eingabewerte durch eine Pipeline senden, können Sie eine Form von Parallelität in Ihrer Anwendung implementieren, die der Art und Weise ähnelt, wie Teile durch eine Automobilfabrik bewegt werden. Wenn das erste Element der Pipeline sein Ergebnis an das zweite Element gesendet hat, kann es parallel ein weiteres Objekt verarbeiten, während das zweite Element das erste Ergebnis verarbeitet.  
  
 Die Parallelität, die durch Verwenden von datenflusspipelines erreicht wird, wird als bezeichnet *grobmaschige Parallelität* , da es in der Regel weniger, größere Aufgaben besteht. Sie können auch eine *eine differenzierte Parallelität* von kleineren Aufgaben mit kurzer Ausführungszeit in einer Datenflusspipeline. In diesem Beispiel wird für das `findReversedWords`-Element der Pipeline die <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>-Methode verwendet, um mehrere Elemente in der Arbeitsliste parallel zu verarbeiten. Die Verwendung von feinmaschiger Parallelität in einer grobmaschigen Pipeline kann den Gesamtdurchsatz verbessern.  
  
 Sie können auch einen quelldatenflussblock mit mehreren Zielblöcken erstellen Verbinden einer *Datenflussnetzwerk*. Die überladene Version der <xref:System.Threading.Tasks.Dataflow.DataflowBlock.LinkTo%2A>-Methode übernimmt ein <xref:System.Predicate%601>-Objekt, das definiert, ob der Zielblock jede Nachricht anhand dessen Wert akzeptiert. Die meisten Datenflussblocktypen, die als Quellen fungieren, senden Nachrichten an alle verbundenen Zielblöcke in der Reihenfolge, in der sie verbunden wurden, bis einer der Blöcke die jeweilige Nachricht akzeptiert hat. Durch Verwenden dieser Filtermechanismus können Sie Systeme von verbundenen Datenflussblöcken erstellen, mit denen bestimmte Daten durch einen Pfad und andere Daten durch einen anderen Pfad geleitet werden. Ein Beispiel für die Filterung verwendet wird, um ein Datenflussnetzwerk zu erstellen, finden Sie unter [Exemplarische Vorgehensweise: Datenfluss in einer Windows Forms-Anwendung](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Dataflow (Datenfluss)](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)

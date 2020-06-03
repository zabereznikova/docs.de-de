---
title: 'Exemplarische Vorgehensweise: Erstellen einer Datenflusspipeline'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dataflow pipelines, creating with TPL
- Task Parallel Library, dataflows
- TPL dataflow library, creating dataflow pipeline
ms.assetid: 69308f82-aa22-4ac5-833d-e748533b58e8
ms.openlocfilehash: cfe3296815dc344b0d9d1f7bad1ab4a130380e2b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84284610"
---
# <a name="walkthrough-creating-a-dataflow-pipeline"></a>Exemplarische Vorgehensweise: Erstellen einer Datenflusspipeline
Obwohl Sie die Methoden <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A?displayProperty=nameWithType> und <xref:System.Threading.Tasks.Dataflow.DataflowBlock.TryReceive%2A?displayProperty=nameWithType> verwenden können, um Nachrichten von Quellblöcken zu empfangen, können Sie auch Nachrichtenblöcke verbinden, um eine *Datenflusspipeline* zu bilden. Eine Datenpipeline besteht aus einer Reihe von Komponenten, oder *Datenflussblöcken*, von denen jede eine bestimmte Aufgabe ausführt, die zu einem größeren Ziel beiträgt. Jeder Datenflussblock in einer Datenflusspipeline erledigt eine Aufgabe, wenn er eine Meldung von einem anderen Datenflussblock empfangen hat. Eine Analogie hierzu ist eine Fertigungsstraße eines Fahrzeugherstellers. Jedes Fahrzeug durchläuft die Fertigungsstraße: In einer Station wird das Fahrgestell montiert, in der nächsten wird der Motor eingebaut usw. Da eine Fertigungsstraße ermöglicht, dass mehrere Fahrzeuge gleichzeitig montiert werden, bietet sie einen besseren Durchsatz als eine Einzelmontage eines vollständigen Fahrzeugs.

 Dieses Dokument veranschaulicht eine Datenflusspipeline, die das Buch *The Iliad of Homer* von einer Website herunterlädt und den Text durchsucht, um einzelne Wörter mit Wörtern abzugleichen, in denen die Zeichen des ersten Worts umgekehrt sind. Die Entwicklung der Datenflusspipeline in diesem Dokument besteht aus den folgenden Schritten:  
  
1. Erstellen Sie die Datenflussblöcke, die Bestandteile der Pipeline sein sollen.  
  
2. Verbinden Sie jeden Datenflussblock mit dem nächsten Block in der Pipeline. Jeder Block empfängt als Eingabe die Ausgabe des jeweils vorherigen Blocks in der Pipeline.  
  
3. Erstellen Sie für jeden Datenflussblock eine Fortsetzungsaufgabe, die den nächsten Datenblock in den Zustand Abgeschlossen schaltet, nachdem der vorherige Block beendet wurde.  
  
4. Senden Sie Daten an den Anfang der Pipeline.  
  
5. Kennzeichnen Sie den Anfang der Pipeline als abgeschlossen.  
  
6. Warten Sie, bis die Pipeline alle Aufgaben ausgeführt hat.  
  
## <a name="prerequisites"></a>Voraussetzungen  
 Lesen Sie das Thema [Datenfluss](dataflow-task-parallel-library.md), bevor Sie mit dieser exemplarischen Vorgehensweise beginnen.  
  
## <a name="creating-a-console-application"></a>Erstellen einer Konsolenanwendung  
 Erstellen Sie in Visual Studio ein Visual C#- oder Visual Basic-Projekt des Typs „Konsolenanwendung“. Installieren Sie das NuGet-Paket „System.Threading.Tasks.Dataflow“.

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

 Fügen Sie Ihrem Projekt den folgenden Code hinzu , um die Grundanwendung zu erstellen.  
  
 [!code-csharp[TPLDataflow_Palindromes#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#2)]
 [!code-vb[TPLDataflow_Palindromes#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromesemptymain.vb#2)]  
  
## <a name="creating-the-dataflow-blocks"></a>Erstellen der Datenflussblöcke  
 Fügen Sie der `Main`-Methode den folgenden Code hinzu, um die Datenflussblöcke zu erstellen, die Bestandteile der Pipeline sein sollen. Die folgende Tabelle enthält eine Übersicht über die Rollen, die die Elemente (Member) der Pipeline haben.  
  
 [!code-csharp[TPLDataflow_Palindromes#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#3)]
 [!code-vb[TPLDataflow_Palindromes#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#3)]  
  
|Member|Typ|Beschreibung|  
|------------|----------|-----------------|  
|`downloadString`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|Lädt den Text des Buchs aus dem Internet herunter.|  
|`createWordList`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|Trennt den Text des Buchs in ein Array aus einzelnen Wörtern.|  
|`filterWordList`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|Entfernt kurze Wörter und Duplikate aus dem Wortarray.|  
|`findReversedWords`|<xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602>|Sucht in der gefilterten Wortarrayauflistung nach allen Wörtern, deren Umkehrung ebenfalls im Wortarray enthalten ist.|  
|`printReversedWords`|<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>|Zeigt die jeweiligen Wörter und die entsprechenden Umkehrwörter in der Konsole an.|  
  
 Obwohl Sie mehrere Schritte in der Datenflusspipeline in diesem Beispiel in einem einzigen Schritt kombinieren könnten, veranschaulicht dieses Beispiel das Konzept des Zusammenstellens mehrerer unabhängiger Datenflussaufgaben, um eine größere Aufgabe auszuführen. In dem Beispiel wird <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> verwendet, damit jedes Element der Pipeline einen Vorgang für seine Eingabedaten ausführen und die Ergebnisse an den nächsten Schritt in der Pipeline senden kann. Das `findReversedWords`-Element der Pipeline ist ein <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602>-Objekt, da es für jede Eingabe mehrere unabhängige Ausgaben erzeugt. Das Ende der Pipeline, `printReversedWords`, ist ein <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>-Objekt, weil es eine Aktion für seine Eingabe ausführt und kein Ergebnis erzeugt.  
  
## <a name="forming-the-pipeline"></a>Aufbauen der Pipeline  
 Fügen Sie den folgenden Code ein, um jeden Block mit dem nächsten Block in der Pipeline zu verbinden.  
  
 Wenn Sie die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.LinkTo%2A>-Methode aufrufen, um einen Quelldatenflussblock mit einem Zieldatenflussblock zu verbinden, überträgt der Quelldatenflussblock Daten an den Zielblock, sobald Daten verfügbar sind. Wenn Sie auch <xref:System.Threading.Tasks.Dataflow.DataflowLinkOptions> mit <xref:System.Threading.Tasks.Dataflow.DataflowLinkOptions.PropagateCompletion> (Wert auf „true“ gesetzt) angeben, führt ein erfolgreicher oder nicht erfolgreicher Abschluss eines Blocks in der Pipeline dazu, dass der nächste Block in der Pipeline abgeschlossen wird.
  
 [!code-csharp[TPLDataflow_Palindromes#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#4)]
 [!code-vb[TPLDataflow_Palindromes#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#4)]  
  
## <a name="posting-data-to-the-pipeline"></a>Senden von Daten an die Pipeline  
 Fügen Sie folgenden Code hinzu, um die URL des Buchs *The Iliad of Homer* an den Anfang der Datenflusspipeline zu senden.  
  
 [!code-csharp[TPLDataflow_Palindromes#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#6)]
 [!code-vb[TPLDataflow_Palindromes#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#6)]  
  
 In diesem Beispiel wird <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A?displayProperty=nameWithType> verwendet, damit die Daten synchron an den Anfang der Pipeline gesendet werden. Verwenden Sie die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A?displayProperty=nameWithType>-Methode, wenn Sie Daten asynchron an einen Datenflussknoten senden müssen.  
  
## <a name="completing-pipeline-activity"></a>Abschließen der Pipelineaktivität  
 Fügen Sie den folgenden Code ein, um den Anfang der Pipeline als abgeschlossen zu kennzeichnen. Der Anfang der Pipeline überträgt seinen Abschluss, nachdem er alle gepufferten Nachrichten verarbeitet hat.
  
 [!code-csharp[TPLDataflow_Palindromes#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#7)]
 [!code-vb[TPLDataflow_Palindromes#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#7)]  
  
 In diesem Beispiel wird eine URL durch die Datenflusspipeline gesendet, um verarbeitet zu werden. Wenn Sie mehrere Eingaben durch eine Pipeline senden, rufen Sie die <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A?displayProperty=nameWithType>-Methode auf, nachdem Sie alle Eingaben übertragen haben. Sie können auf diesen Schritt verzichten, wenn Ihre Anwendung keinen wohldefinierten Punkt hat, an dem keine Daten mehr verfügbar sind, oder wenn die Anwendung nicht warten muss, bis die Pipeline beendet ist.  
  
## <a name="waiting-for-the-pipeline-to-finish"></a>Warten bis zum Beenden der Pipeline  
 Fügen Sie den folgenden Code hinzu, damit gewartet wird, bis die Pipeline beendet ist. Der gesamte Vorgang ist abgeschlossen, wenn das Ende der Pipeline beendet ist.  
  
 [!code-csharp[TPLDataflow_Palindromes#8](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#8)]
 [!code-vb[TPLDataflow_Palindromes#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#8)]  
  
 Sie können von jedem Thread oder von mehreren Threads gleichzeitig auf den Datenflussabschluss warten.  
  
## <a name="the-complete-example"></a>Vollständiges Beispiel  
 Das folgende Beispiel enthält den vollständigen Code für diese exemplarische Vorgehensweise.  
  
 [!code-csharp[TPLDataflow_Palindromes#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#1)]
 [!code-vb[TPLDataflow_Palindromes#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#1)]  
  
## <a name="next-steps"></a>Nächste Schritte  
 In diesem Beispiel wird eine zu verarbeitende URL durch die Datenflusspipeline gesendet. Wenn Sie mehrere Eingabewerte durch eine Pipeline senden, können Sie eine Form von Parallelität in Ihrer Anwendung implementieren, die der Art und Weise ähnelt, wie Teile durch eine Automobilfabrik bewegt werden. Wenn das erste Element der Pipeline sein Ergebnis an das zweite Element gesendet hat, kann es parallel ein weiteres Objekt verarbeiten, während das zweite Element das erste Ergebnis verarbeitet.  
  
 Die Parallelität, die durch ein Verwenden von Datenflusspipelines erreicht wird, wird als *grobmaschige Parallelität* bezeichnet, weil sie in der Regel aus weniger, dafür aber größeren Aufgaben besteht. Sie können auch eine *feinmaschigere Parallelität* von kleineren Aufgaben mit kurzer Ausführungszeit in einer Datenflusspipeline verwenden. In diesem Beispiel wird für das `findReversedWords`-Element der Pipeline [PLINQ](introduction-to-plinq.md) verwendet, um mehrere Elemente in der Arbeitsliste parallel zu verarbeiten. Die Verwendung von feinmaschiger Parallelität in einer grobmaschigen Pipeline kann den Gesamtdurchsatz verbessern.  
  
 Sie können auch einen Quelldatenflussblock mit mehreren Zielblöcken verbinden, um ein *Datenflussnetzwerk* zu erstellen. Die überladene Version der <xref:System.Threading.Tasks.Dataflow.DataflowBlock.LinkTo%2A>-Methode übernimmt ein <xref:System.Predicate%601>-Objekt, das definiert, ob der Zielblock jede Nachricht anhand dessen Wert akzeptiert. Die meisten Datenflussblocktypen, die als Quellen fungieren, senden Nachrichten an alle verbundenen Zielblöcke in der Reihenfolge, in der sie verbunden wurden, bis einer der Blöcke die jeweilige Nachricht akzeptiert hat. Durch Verwenden dieser Filtermechanismus können Sie Systeme von verbundenen Datenflussblöcken erstellen, mit denen bestimmte Daten durch einen Pfad und andere Daten durch einen anderen Pfad geleitet werden. Ein Beispiel, in dem Filterung zum Erstellen eines Datenflussnetzwerks verwendet wird, finden Sie unter [Exemplarische Vorgehensweise: Using Dataflow in a Windows Forms Application (Exemplarische Vorgehensweise: Verwenden von Datenflüssen in einer Windows Forms-Anwendung)](walkthrough-using-dataflow-in-a-windows-forms-application.md).  
  
## <a name="see-also"></a>Siehe auch

- [Dataflow (Datenfluss)](dataflow-task-parallel-library.md)

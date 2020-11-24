---
title: 'Exemplarische Vorgehensweise: Erstellen eines Datenflussblock-Typs'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, creating custom dataflow blocks
- dataflow blocks, creating custom in TPL
ms.assetid: a6147146-0a6a-4d9b-ab0f-237b3c1ac691
ms.openlocfilehash: 71f9002cc13f30bfe7988540472b09979d4e9d0a
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829959"
---
# <a name="walkthrough-creating-a-custom-dataflow-block-type"></a>Exemplarische Vorgehensweise: Erstellen eines Datenflussblock-Typs
Obwohl die TPL Dataflow Library mehrere Datenflussblocktypen zur Verfügung stellt, die eine Vielzahl von Funktionen ermöglichen, können Sie auch benutzerdefinierte Blocktypen erstellen. Dieses Dokument beschreibt, wie Sie einen Datenflussblocktyp erstellen, der benutzerdefiniertes Verhalten implementiert.  
  
## <a name="prerequisites"></a>Voraussetzungen  
 Lesen Sie zunächst [Datenfluss](dataflow-task-parallel-library.md), bevor Sie dieses Dokument lesen.  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]
  
## <a name="defining-the-sliding-window-dataflow-block"></a>Definieren des Datenflussblocks für gleitende Fenster  
 Erwägen Sie die Nutzung einer Datenflussanwendung, die erfordert, dass Eingabewerte gepuffert und dann in einem gleitenden Fenster ausgegeben werden. Zum Beispiel erzeugt für die Eingabewerte {0, 1, 2, 3, 3, 4, 5} und eine Fenstergröße von drei, ein Datenflussblock für gleitende Fenster die Ausgabearrays {0, 1, 2}, {1, 2, 3}, {2, 3, 4} und {3, 4, 5}. Die folgenden Abschnitte veranschaulichen zwei Möglichkeiten, einen Datenflussblocktyp zu erstellen, der benutzerdefiniertes Verhalten implementiert. Das erste Verfahren verwendet die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A>-Methode, um die Funktionalität eine <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>-Objekts und eines <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>-Objekts in einem Weitergabeblock zu kombinieren. Das zweite Verfahren definiert eine Klasse, die aus <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602> abgeleitet ist und vorhandene Funktionen kombiniert, um benutzerdefiniertes Verhalten auszuführen.  
  
## <a name="using-the-encapsulate-method-to-define-the-sliding-window-dataflow-block"></a>Verwendung der Kapselmethode zum Definieren des Datenflussblocks für gleitende Fenster  
 Im folgenden Beispiel wird die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A>-Methode verwendet, um einen Weitergabeblock aus einem Ziel und einer Quelle zu erstellen. Ein Weitergabeblock ermöglicht es einem Quellblock und einem Zielblock, als Empfänger und Sender von Daten zu fungieren.  
  
 Diese Vorgehensweise ist nützlich, wenn Sie eine benutzerdefinierte Datenflussfunktionalität, aber keinen Typ benötigen, der zusätzliche Methoden, Eigenschaften oder Felder bereitstellt.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#1)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#1)]  
  
## <a name="deriving-from-ipropagatorblock-to-define-the-sliding-window-dataflow-block"></a>Ableiten aus „IPropagatorBlock“ zum Definieren des Datenflussblocks für gleitende Fenster  
 Im folgenden Beispiel wird die `SlidingWindowBlock`-Klasse gezeigt. Diese Klasse leitet sich aus <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602> ab, sodass sie sowohl als Quelle als auch als Ziel von Daten fungieren kann. Wie im vorherigen Beispiel wird die `SlidingWindowBlock`-Klasse auf bestehenden Datenflussblocktypen aufgebaut. Die `SlidingWindowBlock`-Klasse implementiert jedoch auch die Methoden, die von den Schnittstellen <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>, <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> und <xref:System.Threading.Tasks.Dataflow.IDataflowBlock> benötigt werden. Alle diese Methoden leiten die Arbeit an die vordefinierten Datenflussblocktyp-Elemente weiter. Zum Beispiel stellt die `Post`-Methode die Arbeit auf das `m_target`-Datenelement zurück, das auch ein <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>-Objekt ist.  
  
 Diese Vorgehensweise ist nützlich, wenn Sie eine benutzerdefinierte Datenflussfunktionalität und zudem einen Typ benötigen, der zusätzliche Methoden, Eigenschaften oder Felder bereitstellt. Beispielsweise leitet sich die Klasse `SlidingWindowBlock` auch aus <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601> ab, sodass sie die Methoden <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> und <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceiveAll%2A> bereitstellen kann. Außerdem veranschaulicht die `SlidingWindowBlock`-Klasse die Erweiterbarkeit, indem sie die `WindowSize`-Eigenschaft bereitstellt, die die Anzahl der Elemente im gleitenden Fenster ermittelt.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#2)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#2)]  
  
## <a name="the-complete-example"></a>Vollständiges Beispiel  
 Das folgende Beispiel enthält den vollständigen Code für diese exemplarische Vorgehensweise. Es zeigt auch, wie man die beiden Blöcke für gleitende Fenster in einer Methode verwendet, die in den Block schreibt, ihn liest und die Ergebnisse auf der Konsole ausgibt.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#100)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#100)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Dataflow (Datenfluss)](dataflow-task-parallel-library.md)

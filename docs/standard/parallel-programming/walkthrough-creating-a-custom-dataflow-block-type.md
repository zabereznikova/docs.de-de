---
title: 'Exemplarische Vorgehensweise: Erstellen eines Datenflussblock-Typs'
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
- Task Parallel Library, dataflows
- TPL dataflow library, creating custom dataflow blocks
- dataflow blocks, creating custom in TPL
ms.assetid: a6147146-0a6a-4d9b-ab0f-237b3c1ac691
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 809b21fa6e1470890011604792d849998dd03ede
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-creating-a-custom-dataflow-block-type"></a>Exemplarische Vorgehensweise: Erstellen eines Datenflussblock-Typs
Obwohl die TPL-Datenflussbibliothek mehrere datenflussblocktypen, die eine Vielzahl von Funktionen zu aktivieren enthält, können Sie auch benutzerdefinierte Blocktypen erstellen. Dieses Dokument beschreibt, wie Sie einen datenflussblocktyp zu erstellen, der benutzerdefiniertes Verhalten implementiert.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Lesen [Datenfluss](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) , bevor Sie dieses Dokument zu lesen.  
  
> [!TIP]
>  Die TPL-Datenflussbibliothek (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType>-Namespace) ist nicht in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] enthalten. Öffnen Sie zum Installieren des <xref:System.Threading.Tasks.Dataflow>-Namespace das Projekt in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], wählen Sie im Menü "Projekt" die Option **NuGet-Pakete verwalten** aus, und suchen Sie online nach dem `Microsoft.Tpl.Dataflow` -Paket.  
  
## <a name="defining-the-sliding-window-dataflow-block"></a>Definieren das gleitende Fenster Datenflussblock  
 Erwägen Sie eine Datenfluss-Anwendung, die erfordert, dass die Eingabewerte gepuffert werden, und klicken Sie dann auf eine gleitende Fenster Weise ausgegeben. Ein gleitendes Fenster Datenflussblock erzeugt z. B. für die Eingabewerte {0, 1, 2, 3, 4, 5} und einer Fenstergröße von drei Ausgabearrays, {0, 1, 2}, {1, 2, 3}, {2, 3, 4}, und {3, 4, 5}. Den folgenden Abschnitten werden zwei Möglichkeiten, einen datenflussblocktyp zu erstellen, der diesem benutzerdefinierte Verhalten implementiert. Das erste Verfahren verwendet die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> Methode, um die Funktionalität kombinieren einer <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> Objekt und ein <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> Objekt in ein Weitergabeblock. Die zweite Methode definiert eine Klasse, die abgeleitet <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602> und vorhandene Funktionen, um benutzerdefiniertes Verhalten auszuführen, kombiniert.  
  
## <a name="using-the-encapsulate-method-to-define-the-sliding-window-dataflow-block"></a>Mithilfe der Methode zum Definieren der gleitende Fenster Datenflussblock kapseln  
 Im folgenden Beispiel wird die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> Methode, um ein Weitergabeblock aus Ziel und eine Quelle zu erstellen. Ein Weitergabeblock ermöglicht ein Quellblock und als Zielblock fungiert als Empfänger und Absender der Daten.  
  
 Diese Technik ist nützlich, wenn Sie benutzerdefinierte datenflussfunktionalität benötigen, aber Sie benötigen keinen Typ, der zusätzliche Methoden, Eigenschaften oder Felder enthält.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#1)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#1)]  
  
## <a name="deriving-from-ipropagatorblock-to-define-the-sliding-window-dataflow-block"></a>Ableiten von IPropagatorBlock das gleitende Fenster Datenflussblock definieren  
 Das folgende Beispiel zeigt die `SlidingWindowBlock` Klasse. Diese Klasse leitet sich von <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602> , damit es als eine Quelle und ein Ziel der Daten verwendet werden kann. Wie im vorherigen Beispiel die `SlidingWindowBlock` Klasse basiert auf vorhandenen datenflussblocktypen. Allerdings die `SlidingWindowBlock` Klasse implementiert auch Methoden, die erforderlich sind die <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>, <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>, und <xref:System.Threading.Tasks.Dataflow.IDataflowBlock> Schnittstellen. Diese Methoden alle vorwärts funktionieren auf die vordefinierten Datenfluss Block Typmember. Z. B. die `Post` -Methode verzögert Arbeit der `m_target` Datenmember, die auch ist ein <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> Objekt.  
  
 Diese Technik ist nützlich, wenn Sie benutzerdefinierte datenflussfunktionalität erfordern erforderlich, und einen Typ, der zusätzliche Methoden, Eigenschaften oder Felder enthält. Z. B. die `SlidingWindowBlock` Klasse auch abgeleitet <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601> so, dass diese bereitstellen, kann die <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> und <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceiveAll%2A> Methoden. Die `SlidingWindowBlock` Klasse veranschaulicht auch Erweiterbarkeit durch Bereitstellen der `WindowSize` -Eigenschaft, die die Anzahl der Elemente in das gleitende Fenster abruft.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#2)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#2)]  
  
## <a name="the-complete-example"></a>Vollständiges Beispiel  
 Das folgende Beispiel enthält den vollständigen Code für diese exemplarische Vorgehensweise. Es wird veranschaulicht, wie beide gleitende Fenster Blöcke in einer Methode verwenden, die an den Block schreibt, liest aus und gibt die Ergebnisse an die Konsole.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#100)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#100)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `SlidingWindowBlock.cs` (`SlidingWindowBlock.vb` für [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) und dann den folgenden Befehl in eine Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe /r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe /r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.vb**  
  
## <a name="next-steps"></a>Nächste Schritte  
  
## <a name="see-also"></a>Siehe auch  
 [Dataflow (Datenfluss)](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)

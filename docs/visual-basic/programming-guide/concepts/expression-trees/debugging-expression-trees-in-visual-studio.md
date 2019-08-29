---
title: Debuggen von Ausdrucks Baumstrukturen in Visual Studio (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: 3334828475ef5d933ea660ea33ae264d4ccce172
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106871"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a>Debuggen von Ausdrucks Baumstrukturen in Visual Studio (Visual Basic)
Sie können die Struktur und den Inhalt von Ausdrucksbaumstrukturen beim Debuggen Ihrer Anwendung analysieren. Um eine Übersicht über die Ausdrucksbaumstruktur zu erhalten, können Sie die `DebugView`-Eigenschaft verwenden, die Ausdrucksbaumstrukturen mit einer [speziellen Syntax](debugview-syntax.md) darstellt. (Beachten Sie, dass `DebugView` nur im Debugmodus verfügbar ist.)  

![DebugView der Ausdrucksbaumstruktur im Visual Studio-Debugger](media/debugging-expression-trees-in-visual-studio/debugview_vb.png)

Da `DebugView` eine Zeichenfolge ist, können Sie die [integrierte Text-Schnellansicht](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) verwenden, um eine Ansicht mit mehreren Zeilen zu erhalten. Wählen Sie hierzu über das Lupensymbol neben `DebugView` die Option **Text-Schnellansicht**.

 ![Text-Schnellansicht für Ergebnisse von „DebugView“](media/debugging-expression-trees-in-visual-studio/string_visualizer_vb.png)

Alternativ dazu können Sie eine [benutzerdefinierte Schnellansicht](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) für Ausdrucksbaumstrukturen installieren und verwenden, wie z.B.:

- Mit [lesbaren Ausdrücken](https://github.com/agileobjects/ReadableExpressions) ([MIT-Lizenz](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), die über den [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers) verfügbar ist) wird die Ausdrucksbaumstruktur als C#-Code gerendert:

  ![Schnellansicht für lesbare Ausdrücke](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

- [Ausdrucks Baum](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) Struktur-Schnellansicht ([Mit-Lizenz](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), stellt eine grafische Ansicht der Ausdrucks Baumstruktur, ihrer Eigenschaften und der zugehörigen Objekte bereit. und können die Ausdrucks Baumstruktur mithilfe Visual Basic Codes Rendering:

  ![ExpressionToString-Schnellansicht](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer_vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a>So öffnen Sie eine Schnellansicht für eine Ausdrucksbaumstruktur  
  
1. Klicken Sie auf das Lupensymbol, das in **DataTips** neben einer Ausdrucksbaumstruktur, in einem **Überwachungsfenster**, einem **Auto**- oder einem **Lokalfenster** angezeigt wird.  
  
     Eine Liste mit den verfügbaren Schnellansichten wird angezeigt: 

      ![Öffnen von Schnellansichten über Visual Studio](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers_vb.png)

2. Klicken Sie auf die gewünschte Schnellansicht.  

## <a name="see-also"></a>Siehe auch

- [Ausdrucksbaumstrukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [Debuggen in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio)
- [Erstellen benutzerdefinierter Schnellansichten](/visualstudio/debugger/create-custom-visualizers-of-data)
- [`DebugView`-Syntax](debugview-syntax.md)

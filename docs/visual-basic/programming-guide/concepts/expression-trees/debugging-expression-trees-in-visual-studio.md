---
title: Debuggen von Ausdrucksbäumen in Visual Studio
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: 3811958353d1d55ce74da41c6a45dbe730cc9790
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84375433"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a>Debuggen von Ausdrucks Baumstrukturen in Visual Studio (Visual Basic)
Sie können die Struktur und den Inhalt von Ausdrucksbaumstrukturen beim Debuggen Ihrer Anwendung analysieren. Um eine Übersicht über die Ausdrucksbaumstruktur zu erhalten, können Sie die `DebugView`-Eigenschaft verwenden, die Ausdrucksbaumstrukturen mit einer [speziellen Syntax](debugview-syntax.md) darstellt. (Beachten Sie, dass `DebugView` nur im Debugmodus verfügbar ist.)  

![Screenshot der Debug-Ansicht der Ausdrucks Baumstruktur.](media/debugging-expression-trees-in-visual-studio/debugview-visual-basic.png)

Da `DebugView` eine Zeichenfolge ist, können Sie die [integrierte Text-Schnellansicht](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) verwenden, um eine Ansicht mit mehreren Zeilen zu erhalten. Wählen Sie hierzu über das Lupensymbol neben `DebugView` die Option **Text-Schnellansicht**.

 ![Screenshot der Text Schnellansicht, die auf die Ergebnisse von DebugView angewendet wird.](media/debugging-expression-trees-in-visual-studio/string-visualizer-vb.png)

Alternativ dazu können Sie eine [benutzerdefinierte Schnellansicht](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) für Ausdrucksbaumstrukturen installieren und verwenden, wie z.B.:

- Mit [lesbaren Ausdrücken](https://github.com/agileobjects/ReadableExpressions) ([MIT-Lizenz](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), die über den [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers) verfügbar ist) wird die Ausdrucksbaumstruktur als C#-Code, der ein Design zugewiesen werden kann, und mit verschiedenen Renderingoptionen gerendert:

  ![Screenshot der Schnellansicht für lesbare Ausdrücke.](media/debugging-expression-trees-in-visual-studio/readable-expressions-visualizer.png)

- [Ausdrucks Baum](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/README.md) Struktur-Schnellansicht ([mit-Lizenz](https://github.com/zspitz/ExpressionTreeVisualizer/blob/master/LICENSE)) stellt eine Strukturansicht der Ausdrucks Baumstruktur und der einzelnen Knoten bereit. und können die Ausdrucks Baumstruktur mithilfe Visual Basic Syntax Rendering:

  ![Screenshot der Schnellansicht der Ausdrucksbaumstruktur.](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizer-vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a>So öffnen Sie eine Schnellansicht für eine Ausdrucksbaumstruktur  
  
1. Klicken Sie auf das Lupensymbol, das in **DataTips** neben einer Ausdrucksbaumstruktur, in einem **Überwachungsfenster**, einem **Auto**- oder einem **Lokalfenster** angezeigt wird.  
  
    Eine Liste mit den verfügbaren Schnellansichten wird angezeigt:

    ![Screenshot der Benutzer, die Visualisierungen aus Visual Studio öffnen](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizers-vb.png)

2. Klicken Sie auf die gewünschte Schnellansicht.  

## <a name="see-also"></a>Siehe auch

- [Ausdrucksbaumstrukturen (Visual Basic)](index.md)
- [Debuggen in Visual Studio](/visualstudio/debugger/debugger-feature-tour)
- [Erstellen benutzerdefinierter Schnellansichten](/visualstudio/debugger/create-custom-visualizers-of-data)
- [`DebugView`-Syntax](debugview-syntax.md)

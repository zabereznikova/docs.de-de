---
title: Debuggen von Ausdrucksbäumen in Visual Studio
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: c6c44d079ab0854b2325b82d3569280752da32fb
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266832"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a>Debuggen von Ausdrucksstrukturen in Visual Studio (Visual Basic)
Sie können die Struktur und den Inhalt von Ausdrucksbaumstrukturen beim Debuggen Ihrer Anwendung analysieren. Um eine Übersicht über die Ausdrucksbaumstruktur zu erhalten, können Sie die `DebugView`-Eigenschaft verwenden, die Ausdrucksbaumstrukturen mit einer [speziellen Syntax](debugview-syntax.md) darstellt. (Beachten Sie, dass `DebugView` nur im Debugmodus verfügbar ist.)  

![Screenshot der DebugView-Struktur der Ausdrucksstruktur.](media/debugging-expression-trees-in-visual-studio/debugview-visual-basic.png)

Da `DebugView` eine Zeichenfolge ist, können Sie die [integrierte Text-Schnellansicht](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) verwenden, um eine Ansicht mit mehreren Zeilen zu erhalten. Wählen Sie hierzu über das Lupensymbol neben **die Option**Text-Schnellansicht`DebugView`.

 ![Screenshot von Text Visualizer, der auf die Ergebnisse von DebugView angewendet wird.](media/debugging-expression-trees-in-visual-studio/string-visualizer-vb.png)

Alternativ dazu können Sie eine [benutzerdefinierte Schnellansicht](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) für Ausdrucksbaumstrukturen installieren und verwenden, wie z.B.:

- Mit [lesbaren Ausdrücken](https://github.com/agileobjects/ReadableExpressions) ([MIT-Lizenz](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), die über den [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers) verfügbar ist) wird die Ausdrucksbaumstruktur als C#-Code gerendert:

  ![Screenshot der Schnellansicht für lesbare Ausdrücke.](media/debugging-expression-trees-in-visual-studio/readable-expressions-visualizer.png)

- [Expression Tree Visualizer](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT-Lizenz](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), bietet eine grafische Ansicht der Ausdrucksstruktur, ihrer Eigenschaften und verwandten Objekte. und kann die Ausdrucksstruktur mithilfe von Visual Basic-Code rendern:

  ![Screenshot der ExpressionToString-Visualisierung.](media/debugging-expression-trees-in-visual-studio/expression-to-string-visualizer-vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a>So öffnen Sie eine Schnellansicht für eine Ausdrucksbaumstruktur  
  
1. Klicken Sie auf das Lupensymbol, das in **DataTips** neben einer Ausdrucksbaumstruktur, in einem **Überwachungsfenster**, einem **Auto**- oder einem **Lokalfenster** angezeigt wird.  
  
    Eine Liste mit den verfügbaren Schnellansichten wird angezeigt:

    ![Screenshot des Benutzers, der Visualisierer aus Visual Studio öffnet.](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizers-vb.png)

2. Klicken Sie auf die gewünschte Schnellansicht.  

## <a name="see-also"></a>Weitere Informationen

- [Ausdrucksbaumstrukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [Debuggen in Visual Studio](/visualstudio/debugger/debugger-feature-tour)
- [Erstellen benutzerdefinierter Schnellansichten](/visualstudio/debugger/create-custom-visualizers-of-data)
- [`DebugView`-Syntax](debugview-syntax.md)

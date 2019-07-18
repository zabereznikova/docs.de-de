---
title: Debuggen von Ausdrucksbäumen in Visual Studio (C#)
ms.date: 07/20/2015
ms.assetid: 1369fa25-0fbd-4b92-98d0-8df79c49c27a
ms.openlocfilehash: 93b1b660181cd81c31055f5d30d43e535171bb55
ms.sourcegitcommit: 96543603ae29bc05cecccb8667974d058af63b4a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2019
ms.locfileid: "66195990"
---
# <a name="debugging-expression-trees-in-visual-studio-c"></a>Debuggen von Ausdrucksbäumen in Visual Studio (C#)
Sie können die Struktur und den Inhalt von Ausdrucksbaumstrukturen beim Debuggen Ihrer Anwendung analysieren. Um eine Übersicht über die Ausdrucksbaumstruktur zu erhalten, können Sie die `DebugView`-Eigenschaft verwenden, die Ausdrucksbaumstrukturen mit einer [speziellen Syntax](debugview-syntax.md) darstellt. (Beachten Sie, dass `DebugView` nur im Debugmodus verfügbar ist.)  

![DebugView der Ausdrucksbaumstruktur im Visual Studio-Debugger](media/debugging-expression-trees-in-visual-studio/debugview.png)

Da `DebugView` eine Zeichenfolge ist, können Sie die [integrierte Text-Schnellansicht](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) verwenden, um eine Ansicht mit mehreren Zeilen zu erhalten. Wählen Sie hierzu über das Lupensymbol neben `DebugView` die Option **Text-Schnellansicht**.

 ![Text-Schnellansicht für Ergebnisse von „DebugView“](media/debugging-expression-trees-in-visual-studio/string_visualizer.png)

Alternativ dazu können Sie eine [benutzerdefinierte Schnellansicht](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) für Ausdrucksbaumstrukturen installieren und verwenden, wie z.B.:

* Mit [lesbaren Ausdrücken](https://github.com/agileobjects/ReadableExpressions) ([MIT-Lizenz](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), die über den [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers) verfügbar ist) wird die Ausdrucksbaumstruktur als C#-Code gerendert:

  ![Schnellansicht für lesbare Ausdrücke](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

* Bei der [Schnellansicht für lesbare Ausdrücke](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([MIT-Lizenz](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)) wird eine grafische Ansicht der Ausdrucksbaumstruktur, der zugehörigen Eigenschaften und der verwandten Objekte bereitgestellt:

  ![ExpressionToString-Schnellansicht](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a>So öffnen Sie eine Schnellansicht für eine Ausdrucksbaumstruktur  
  
1. Klicken Sie auf das Lupensymbol, das in **DataTips** neben einer Ausdrucksbaumstruktur, in einem **Überwachungsfenster**, einem **Auto**- oder einem **Lokalfenster** angezeigt wird.  
  
     Eine Liste mit den verfügbaren Schnellansichten wird angezeigt: 

      ![Öffnen von Schnellansichten über Visual Studio](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers.png)

2. Klicken Sie auf die gewünschte Schnellansicht.  
  
## <a name="see-also"></a>Siehe auch

- [Ausdrucksbaumstrukturen (C#)](../../../../csharp/programming-guide/concepts/expression-trees/index.md)
- [Debuggen in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio)
- [Erstellen benutzerdefinierter Schnellansichten](/visualstudio/debugger/create-custom-visualizers-of-data)
- [`DebugView`-Syntax](debugview-syntax.md)

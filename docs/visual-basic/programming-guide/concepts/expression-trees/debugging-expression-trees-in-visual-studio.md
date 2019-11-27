---
title: Debuggen von Ausdrucksbäumen in Visual Studio
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: ff56a10b6c25f3165066edb727829cc460f3e96c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344727"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a>Debuggen von Ausdrucks Baumstrukturen in Visual Studio (Visual Basic)
Sie können die Struktur und den Inhalt von Ausdrucksbaumstrukturen beim Debuggen Ihrer Anwendung analysieren. Um eine Übersicht über die Ausdrucksbaumstruktur zu erhalten, können Sie die `DebugView`-Eigenschaft verwenden, die Ausdrucksbaumstrukturen mit einer [speziellen Syntax](debugview-syntax.md) darstellt. (Beachten Sie, dass `DebugView` nur im Debugmodus verfügbar ist.)  

![Screenshot der Debug-Ansicht der Ausdrucks Baumstruktur.](media/debugging-expression-trees-in-visual-studio/debugview-visual-basic.png)

Da `DebugView` eine Zeichenfolge ist, können Sie die [integrierte Text-Schnellansicht](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) verwenden, um eine Ansicht mit mehreren Zeilen zu erhalten. Wählen Sie hierzu über das Lupensymbol neben **die Option**Text-Schnellansicht`DebugView`.

 ![Screenshot der Text Schnellansicht, die auf die Ergebnisse von DebugView angewendet wird.](media/debugging-expression-trees-in-visual-studio/string-visualizer-vb.png)

Alternativ dazu können Sie eine [benutzerdefinierte Schnellansicht](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) für Ausdrucksbaumstrukturen installieren und verwenden, wie z.B.:

- Mit [lesbaren Ausdrücken](https://github.com/agileobjects/ReadableExpressions) ([MIT-Lizenz](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), die über den [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers) verfügbar ist) wird die Ausdrucksbaumstruktur als C#-Code gerendert:

  ![Screenshot der Schnellansicht für lesbare Ausdrücke.](media/debugging-expression-trees-in-visual-studio/readable-expressions-visualizer.png)

- [Ausdrucks Baum](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) Struktur-Schnellansicht ([mit-Lizenz](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), stellt eine grafische Ansicht der Ausdrucks Baumstruktur, der zugehörigen Eigenschaften und verknüpften Objekte bereit. und können die Ausdrucks Baumstruktur mithilfe Visual Basic Codes Rendering:

  ![Screenshot der expressionto String-Schnellansicht.](media/debugging-expression-trees-in-visual-studio/expression-to-string-visualizer-vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a>So öffnen Sie eine Schnellansicht für eine Ausdrucksbaumstruktur  
  
1. Klicken Sie auf das Lupensymbol, das in **DataTips** neben einer Ausdrucksbaumstruktur, in einem **Überwachungsfenster**, einem **Auto**- oder einem **Lokalfenster** angezeigt wird.  
  
    Eine Liste mit den verfügbaren Schnellansichten wird angezeigt: 

    ![Screenshot der Benutzer, die Visualisierungen aus Visual Studio öffnen](media/debugging-expression-trees-in-visual-studio/expression-tree-visualizers-vb.png)

2. Klicken Sie auf die gewünschte Schnellansicht.  

## <a name="see-also"></a>Siehe auch

- [Ausdrucksbaumstrukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
- [Debuggen in Visual Studio](/visualstudio/debugger/debugger-feature-tour)
- [Erstellen benutzerdefinierter Schnellansichten](/visualstudio/debugger/create-custom-visualizers-of-data)
- [`DebugView`-Syntax](debugview-syntax.md)

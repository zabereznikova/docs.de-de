---
title: "How to: Enable Tabbing Between Shapes (Visual Studio) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Line control, implementing tabbing"
  - "Shape control, implementing tabbing"
ms.assetid: 09731b34-3900-4fcb-a9df-ce5280328433
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# How to: Enable Tabbing Between Shapes (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Das Line\- und das Shape\-Steuerelement verfügen nicht über die Eigenschaften `TabStop` oder `TabIndex`. Sie können jedoch trotzdem das Wechseln zwischen Formen mit der Tabulatortaste aktivieren.  Wenn Sie in dem folgenden Beispiel gleichzeitig die STRG\-TASTE und die Tabulatortaste drücken, wechseln Sie zwischen Formen. Wenn Sie nur die Tabulatortaste drücken, wechseln Sie zwischen den Schaltflächen.  
  
> [!NOTE]
>  Auf Ihrem Computer werden möglicherweise andere Namen oder Speicherorte für die Benutzeroberflächenelemente von Visual Studio angezeigt als die in den folgenden Anweisungen aufgeführten.  Die von Ihnen verwendete Visual Studio\-Edition und die Einstellungen legen diese Elemente fest.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So aktivieren Sie das Wechseln zwischen Formen mit der Tabulatortaste  
  
1.  Ziehen Sie drei <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>\-Steuerelemente und zwei <xref:System.Windows.Forms.Button>\-Steuerelemente aus der **Toolbox** in ein Formular.  
  
2.  Fügen Sie im **Code\-Editor** am Anfang des Moduls eine `Imports`\-Anweisung oder eine `using`\-Anweisung hinzu:  
  
    ```vb#  
    Imports Microsoft.VisualBasic.PowerPacks  
    ```  
  
    ```c#  
    using Microsoft.VisualBasic.PowerPacks;  
    ```  
  
3.  Fügen Sie in einer Ereignisprozedur den folgenden Code hinzu:  
  
     [!code-cs[VbPowerPacksTabbing#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-enable-tabbing-between-shapes-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksTabbing#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-enable-tabbing-between-shapes-visual-studio_1.vb)]  
  
4.  Fügen Sie in der `Button1_PreviewKeyDown`\-Ereignisprozedur den folgenden Code hinzu:  
  
     [!code-cs[VbPowerPacksTabbing#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-enable-tabbing-between-shapes-visual-studio_2.cs)]
     [!code-vb[VbPowerPacksTabbing#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-enable-tabbing-between-shapes-visual-studio_2.vb)]  
  
## Siehe auch  
 [How to: Draw Shapes with the OvalShape and RectangleShape Controls](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)   
 [How to: Draw Lines with the LineShape Control](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)   
 [Introduction to the Line and Shape Controls](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)
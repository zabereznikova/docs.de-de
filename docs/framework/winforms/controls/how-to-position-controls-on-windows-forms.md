---
title: "Gewusst wie: Positionieren von Steuerelementen in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Location
- Location.Y
- Location.X
helpviewer_keywords:
- controls [Windows Forms]
- controls [Windows Forms], moving
- snaplines
- controls [Windows Forms], positioning
ms.assetid: 4693977e-34a4-4f19-8221-68c3120c2b2b
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9ff1096e6397f4422e0fbf6400a87041cfac6470
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-position-controls-on-windows-forms"></a>Gewusst wie: Positionieren von Steuerelementen in Windows Forms
Positionieren von Steuerelementen, die Windows Forms-Designer verwenden, oder geben den <xref:System.Windows.Forms.Control.Location%2A> Eigenschaft.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a>Um ein Steuerelement auf der Entwurfsoberfläche der Windows Forms-Designer zu positionieren.  
  
-   Ziehen Sie das Steuerelement an die gewünschte Position mit der Maus ein.  
  
    > [!NOTE]
    >  Wählen Sie das Steuerelement, und verschieben Sie es mit dem Pfeil Schlüssel, um genauer zu positionieren. Darüber hinaus *Ausrichtungslinien* unterstützen Sie beim Einfügen von Steuerelementen auf dem Formular genau. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).  
  
### <a name="to-position-a-control-using-the-properties-window"></a>Um ein Steuerelement über das Eigenschaftenfenster zu positionieren.  
  
1.  Klicken Sie auf das Steuerelement, das Sie positionieren möchten.  
  
2.  In der **Eigenschaften** Fenster geben Werte für die <xref:System.Windows.Forms.Control.Location%2A> -Eigenschaft, getrennt durch ein Komma, um das Steuerelement innerhalb des Containers zu positionieren.  
  
     Die erste Zahl (X) entspricht dem Abstand vom linken Rand des Containers; die zweite Zahl (Y) entspricht dem Abstand vom oberen Rand der Containerbereich, gemessen in Pixel.  
  
    > [!NOTE]
    >  Sie erweitern, können die <xref:System.Windows.Forms.Control.Location%2A> -Eigenschaft, um die **X** und **Y** einzeln Werte.  
  
### <a name="to-position-a-control-programmatically"></a>Um ein Steuerelement programmgesteuert zu positionieren.  
  
1.  Legen Sie die <xref:System.Windows.Forms.Control.Location%2A> Eigenschaft des Steuerelements ein <xref:System.Drawing.Point>.  
  
    ```vb  
    Button1.Location = New Point(100, 100)  
    ```  
  
    ```csharp  
    button1.Location = new Point(100, 100);  
    ```  
  
    ```cpp  
    button1->Location = Point(100, 100);  
    ```  
  
2.  Ändern Sie die X-Koordinate der Position des Steuerelements mithilfe der <xref:System.Windows.Forms.Control.Left%2A> Untereigenschaften.  
  
    ```vb  
    Button1.Left = 300  
    ```  
  
    ```csharp  
    button1.Left = 300;  
    ```  
  
    ```cpp  
    button1->Left = 300;  
    ```  
  
### <a name="to-increment-a-controls-location-programmatically"></a>Um die Position eines Steuerelements programmgesteuert erhöht  
  
1.  Legen Sie die <xref:System.Windows.Forms.Control.Left%2A> untergeordnete Eigenschaft, um die X-Koordinate des Steuerelements zu erhöhen.  
  
    ```vb  
    Button1.Left += 200  
    ```  
  
    ```csharp  
    button1.Left += 200;  
    ```  
  
    ```cpp  
    button1->Left += 200;  
    ```  
  
    > [!NOTE]
    >  Verwenden der <xref:System.Windows.Forms.Control.Location%2A> -Eigenschaft festzulegende eines Steuerelements X- und Y-Positionen gleichzeitig. Um eine Position einzeln festzulegen, verwenden Sie des Steuerelements <xref:System.Windows.Forms.Control.Left%2A> (**X**) oder <xref:System.Windows.Forms.Control.Top%2A> (**Y**) Untereigenschaften. Versuchen Sie nicht implizit die X- und Y-Koordinaten der Festlegen der <xref:System.Drawing.Point> -Struktur, die Position der Schaltfläche, darstellt, da diese Struktur eine Kopie der Schaltfläche Koordinaten enthält.  
  
## <a name="see-also"></a>Siehe auch  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/index.md)  
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von Ausrichtungslinien](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von TableLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [Exemplarische Vorgehensweise: Anordnen von Steuerelementen in Windows Forms mithilfe von FlowLayoutPanel](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [Anordnen von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Windows Forms-Steuerelemente nach Funktion](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)  
 [Vorgehensweise: festlegen die Bildschirmposition von Windows Forms](http://msdn.microsoft.com/en-us/cb023ab7-dea7-4284-9aa6-8c03c59b60c6)

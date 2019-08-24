---
title: 'Vorgehensweise: Positionieren von Steuerelementen in Windows Forms'
ms.date: 03/30/2017
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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 1cc2cb4c749b7290a6edf914a8e6a697006ef43c
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987077"
---
# <a name="how-to-position-controls-on-windows-forms"></a>Vorgehensweise: Positionieren von Steuerelementen auf Windows Forms

Verwenden Sie zum Positionieren von Steuerelementen die Windows Forms-Designer in Visual Studio, <xref:System.Windows.Forms.Control.Location%2A> oder geben Sie die-Eigenschaft an.

## <a name="position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a>Positionieren eines Steuer Elements auf der Entwurfs Oberfläche des Windows Forms-Designer

Ziehen Sie das Steuerelement in Visual Studio mit der Maus an die entsprechende Position.

> [!NOTE]
> Wählen Sie das Steuerelement aus, und verschieben Sie es mit den Pfeiltasten, um es genauer zu positionieren. Außerdem unterstützen Sie mit den Richtungs *Linien* , dass Sie Steuerelemente genau in Ihrem Formular platzieren. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Anordnen von Steuerelementen auf Windows Forms mithilfe](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)von Richtungslinien.

## <a name="position-a-control-using-the-properties-window"></a>Positionieren eines Steuer Elements mithilfe des Eigenschaftenfenster

1. Wählen Sie in Visual Studio das Steuerelement aus, das Sie positionieren möchten.

2. Geben Sie im Fenster **Eigenschaften** Werte für die <xref:System.Windows.Forms.Control.Location%2A> durch Kommas getrennte Eigenschaft ein, um das Steuerelement in seinem Container zu positionieren.

   Die erste Zahl (X) ist die Entfernung vom linken Rand des Containers. die zweite Zahl (Y) ist der Abstand zwischen dem oberen Rand des Container Bereichs (gemessen in Pixel).

   > [!NOTE]
   > Sie können die <xref:System.Windows.Forms.Control.Location%2A> -Eigenschaft erweitern, um die **X** -und **Y** -Werte einzeln einzugeben.

## <a name="position-a-control-programmatically"></a>Programm gesteuertes Positionieren eines Steuer Elements

1. <xref:System.Windows.Forms.Control.Location%2A> Legen<xref:System.Drawing.Point>Sie die-Eigenschaft des-Steuer Elements auf fest.

    ```vb
    Button1.Location = New Point(100, 100)
    ```

    ```csharp
    button1.Location = new Point(100, 100);
    ```

    ```cpp
    button1->Location = Point(100, 100);
    ```

2. Ändern Sie die X-Koordinate der Position des Steuer <xref:System.Windows.Forms.Control.Left%2A> Elements mithilfe der untergeordneten Eigenschaft.

    ```vb
    Button1.Left = 300
    ```

    ```csharp
    button1.Left = 300;
    ```

    ```cpp
    button1->Left = 300;
    ```

## <a name="increment-a-controls-location-programmatically"></a>Programm gesteuertes erhöhen der Position eines Steuer Elements

Legen Sie <xref:System.Windows.Forms.Control.Left%2A> die untergeordnete Eigenschaft fest, um die X-Koordinate des Steuer Elements zu erhöhen.

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
> Mit der <xref:System.Windows.Forms.Control.Location%2A> -Eigenschaft können Sie die X-und Y-Positionen eines Steuer Elements gleichzeitig festlegen. Um eine Position einzeln festzulegen, verwenden Sie die <xref:System.Windows.Forms.Control.Left%2A> untergeordnete Eigenschaft ( <xref:System.Windows.Forms.Control.Top%2A> **X**) oder (**Y**) des Steuer Elements. Versuchen Sie nicht, die X-und Y-Koordinaten der <xref:System.Drawing.Point> -Struktur, die die Position der Schaltfläche darstellt, implizit festzulegen, da diese Struktur eine Kopie der Koordinaten der Schaltfläche enthält.

## <a name="see-also"></a>Siehe auch

- [Windows Forms-Steuerelemente](index.md)
- [Exemplarische Vorgehensweise: Anordnen von Steuerelementen auf Windows Forms mithilfe von Richtungslinien](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [Exemplarische Vorgehensweise: Anordnen von Steuerelementen auf Windows Forms mithilfe von TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Exemplarische Vorgehensweise: Anordnen von Steuerelementen auf Windows Forms mithilfe von FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Windows Forms-Steuerelemente](controls-to-use-on-windows-forms.md)
- [Windows Forms-Steuerelemente nach Funktion](windows-forms-controls-by-function.md)
- [Vorgehensweise: Festlegen der Bildschirmposition von Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))

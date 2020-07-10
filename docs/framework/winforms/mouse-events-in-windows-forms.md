---
title: Mausereignisse
description: Erfahren Sie, wie Sie die Mausposition von Mausereignissen ermitteln und die Reihenfolge verstehen, in der Maus Klick Ereignisse in Windows Forms Steuerelementen ausgelöst werden.
ms.date: 03/30/2017
helpviewer_keywords:
- MouseLeave event [Windows Forms]
- events [Windows Forms], mouse
- Click event [Windows Forms], raising order
- Windows Forms controls, click events
- MouseDoubleClick event [Windows Forms]
- MouseEnter event [Windows Forms]
- MouseHover event [Windows Forms]
- MouseDown event [Windows Forms]
- MouseClick event [Windows Forms]
- MouseMove event [Windows Forms]
- mouse [Windows Forms], events
- MouseUp event
ms.assetid: 8cf0070d-793b-4876-b09e-d20d28280fab
ms.openlocfilehash: 640448109961ea5fdf3600ef9e72d7d10e8c9e49
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174379"
---
# <a name="mouse-events-in-windows-forms"></a>Mausereignisse in Windows Forms

Wenn Sie Mauseingaben behandeln, möchten Sie in der Regel die Position des Mauszeigers und den Zustand der Maustasten kennen. Dieses Thema enthält Details zum Abrufen dieser Informationen von Mausereignissen und erörtert die Reihenfolge, in der Mausklickereignisse in Windows Forms-Steuerelementen ausgelöst werden. Eine Liste und Beschreibung aller Mausereignisse finden Sie unter [How Mouse Input in Windows Forms](how-mouse-input-works-in-windows-forms.md).  Weitere Informationen finden Sie auch unter [Übersicht über Ereignishandler (Windows Forms)](event-handlers-overview-windows-forms.md) und [Übersicht über Ereignisse (Windows Forms)](events-overview-windows-forms.md).

## <a name="mouse-information"></a>Mausinformationen

Ein <xref:System.Windows.Forms.MouseEventArgs> wird an Handler von Mausereignissen gesendet, die beim Drücken einer Maustaste und Verfolgen von Mausbewegungen ausgelöst werden. <xref:System.Windows.Forms.MouseEventArgs> enthält Informationen zum aktuellen Zustand der Maus, z. B. die Position des Mauszeigers in Clientkoordinaten, welche Maustasten gedrückt werden und ob das Mausrad bewegt wurde. Zahlreiche Mausereignisse, beispielsweise Ereignisse, die lediglich darüber informieren, dass der Mauszeiger die Grenzen eines Steuerelements überschritten hat, senden ein <xref:System.EventArgs> ohne weitere Informationen an den Ereignishandler.

Wenn Sie den aktuellen Zustand der Maustasten oder die Position des Mauszeigers erfahren möchten, ohne ein Mausereignis zu behandeln, können Sie auch die <xref:System.Windows.Forms.Control.MouseButtons%2A>-Eigenschaft und die <xref:System.Windows.Forms.Control.MousePosition%2A>-Eigenschaft der <xref:System.Windows.Forms.Control>-Klasse verwenden. <xref:System.Windows.Forms.Control.MouseButtons%2A> gibt Informationen darüber zurück, welche Maustasten aktuell gedrückt werden. <xref:System.Windows.Forms.Control.MousePosition%2A> gibt die Bildschirmkoordinaten des Mauszeigers zurück, was dem von <xref:System.Windows.Forms.Cursor.Position%2A> zurückgegebenen Wert entspricht.

## <a name="converting-between-screen-and-client-coordinates"></a>Konvertieren zwischen Bildschirm- und Clientkoordinaten

Da einige Mauspositionsinformationen in Clientkoordinaten und einige in Bildschirmkoordinaten vorhanden sind, müssen Sie möglicherweise einen Punkt aus einem Koordinatensystem in das andere Koordinatensystem konvertieren. Eine einfache Möglichkeit hierzu bieten die <xref:System.Windows.Forms.Control.PointToClient%2A>-Methode und die <xref:System.Windows.Forms.Control.PointToScreen%2A>-Methode der <xref:System.Windows.Forms.Control>-Klasse.

## <a name="standard-click-event-behavior"></a>Standardverhalten bei Mausklickereignissen

Wenn Sie Mausklickereignisse in der richtigen Reihenfolge behandeln möchten, müssen Sie die Reihenfolge kennen, in der Mausklickereignisse in Windows Forms-Steuerelementen ausgelöst werden. Wenn eine Maustaste gedrückt und wieder losgelassen wird (unabhängig davon, um welche Maustaste es sich handelt), lösen alle Windows Forms-Steuerelemente Mausklickereignisse in derselben Reihenfolge aus. In der folgenden Liste ist die Reihenfolge der Ereignisse aufgeführt, die bei einem einzelnen Mausklick ausgelöst werden:

1. <xref:System.Windows.Forms.Control.MouseDown> -Ereignis.

2. <xref:System.Windows.Forms.Control.Click> -Ereignis.

3. <xref:System.Windows.Forms.Control.MouseClick> -Ereignis.

4. <xref:System.Windows.Forms.Control.MouseUp> -Ereignis.

Im folgenden finden Sie die Reihenfolge der Ereignisse, die bei einem doppelten Mausklick ausgelöst werden:

1. <xref:System.Windows.Forms.Control.MouseDown> -Ereignis.

2. <xref:System.Windows.Forms.Control.Click> -Ereignis.

3. <xref:System.Windows.Forms.Control.MouseClick> -Ereignis.

4. <xref:System.Windows.Forms.Control.MouseUp> -Ereignis.

5. <xref:System.Windows.Forms.Control.MouseDown> -Ereignis.

6. <xref:System.Windows.Forms.Control.DoubleClick> -Ereignis. (Dies kann abhängig davon variieren, ob für das betreffende Steuerelement das <xref:System.Windows.Forms.ControlStyles.StandardDoubleClick>-Stilbit auf `true` festgelegt ist. Weitere Informationen zum Festlegen eines <xref:System.Windows.Forms.ControlStyles>-Bits finden Sie unter der <xref:System.Windows.Forms.Control.SetStyle%2A>-Methode.)

7. <xref:System.Windows.Forms.Control.MouseDoubleClick> -Ereignis.

8. <xref:System.Windows.Forms.Control.MouseUp> -Ereignis.

Ein Codebeispiel, das die Reihenfolge der Maus Klick Ereignisse veranschaulicht, finden [Sie unter Gewusst wie: Behandeln von Benutzereingabe Ereignissen in Windows Forms](how-to-handle-user-input-events-in-windows-forms-controls.md)-Steuerelementen.

### <a name="individual-controls"></a>Einzelne Steuerelemente

Die folgenden Steuerelemente weisen nicht das Standardverhalten bei Mausklickereignissen auf:

- <xref:System.Windows.Forms.Button>
- <xref:System.Windows.Forms.CheckBox>
- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.RadioButton>

  > [!NOTE]
  > Für das <xref:System.Windows.Forms.ComboBox>-Steuerelement tritt das im Folgenden beschriebene Verhalten auf, wenn der Benutzer auf das Bearbeitungsfeld, die Schaltfläche oder ein Element in der Liste klickt.

  - Klick mit der linken Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>

  - Klick mit der rechten Maustaste: Es werden keine Click-Ereignisse ausgelöst.

  - Doppelklick mit der linken Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>

  - Doppelklick mit der rechten Maustaste: Es werden keine Click-Ereignisse ausgelöst.

- <xref:System.Windows.Forms.TextBox>-Steuerelement, <xref:System.Windows.Forms.RichTextBox>-Steuerelement, <xref:System.Windows.Forms.ListBox>-Steuerelement, <xref:System.Windows.Forms.MaskedTextBox>-Steuerelement und <xref:System.Windows.Forms.CheckedListBox>-Steuerelement

  > [!NOTE]
  > Das im Folgenden beschriebene Verhalten tritt auf, wenn der Benutzer innerhalb dieser Steuerelemente auf eine beliebige Stelle klickt.

  - Klick mit der linken Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>

  - Klick mit der rechten Maustaste: Es werden keine Click-Ereignisse ausgelöst.

  - Doppelklick mit der linken Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>, <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick>

  - Doppelklick mit der rechten Maustaste: Es werden keine Click-Ereignisse ausgelöst.

- <xref:System.Windows.Forms.ListView>-Steuerelement

  > [!NOTE]
  > Das im Folgenden beschriebene Verhalten tritt nur auf, wenn der Benutzer auf die Elemente im <xref:System.Windows.Forms.ListView>-Steuerelement klickt. Wenn der Benutzer im Steuerelement auf eine andere Stelle klickt, werden keine Ereignisse ausgelöst. Neben den weiter unten beschriebenen Ereignissen könnten auch das <xref:System.Windows.Forms.ListView.BeforeLabelEdit>-Ereignis und das <xref:System.Windows.Forms.ListView.AfterLabelEdit>-Ereignis für Sie von Interesse sein, wenn Sie eine Validierung mit dem <xref:System.Windows.Forms.ListView>-Steuerelement durchführen möchten.

  - Klick mit der linken Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>

  - Klick mit der rechten Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>

  - Doppelklick mit der linken Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick>

  - Doppelklick mit der rechten Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick>

- <xref:System.Windows.Forms.TreeView>-Steuerelement

  > [!NOTE]
  > Das im Folgenden beschriebene Verhalten tritt nur auf, wenn der Benutzer im <xref:System.Windows.Forms.TreeView>-Steuerelement auf die Elemente selbst oder rechts neben sie klickt. Wenn der Benutzer im Steuerelement auf eine andere Stelle klickt, werden keine Ereignisse ausgelöst. Neben den weiter unten beschriebenen Ereignissen könnten auch die Ereignisse <xref:System.Windows.Forms.TreeView.BeforeCheck>, <xref:System.Windows.Forms.TreeView.BeforeSelect>, <xref:System.Windows.Forms.TreeView.BeforeLabelEdit>, <xref:System.Windows.Forms.TreeView.AfterSelect>, <xref:System.Windows.Forms.TreeView.AfterCheck> und <xref:System.Windows.Forms.TreeView.AfterLabelEdit> für Sie von Interesse sein, wenn Sie eine Validierung mit dem <xref:System.Windows.Forms.TreeView>-Steuerelement durchführen möchten.

  - Klick mit der linken Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>

  - Klick mit der rechten Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>

  - Doppelklick mit der linken Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick>

  - Doppelklick mit der rechten Maustaste: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick>

### <a name="painting-behavior-of-toggle-controls"></a>Zeichen Verhalten beim Umschalten von Steuerelementen

Umschaltbare Steuerelemente, wie die Steuerelemente, die von der <xref:System.Windows.Forms.ButtonBase>-Klasse abgeleitet werden, weisen bei Mausklickereignissen das folgende Zeichnungsverhalten auf:

1. Der Benutzer drückt die Maustaste.

2. Das Steuerelement zeichnet im gedrückten Zustand.

3. Das <xref:System.Windows.Forms.Control.MouseDown>-Ereignis wird ausgelöst.

4. Der Benutzer lässt die Maustaste los.

5. Das Steuerelement zeichnet im erhöhten Zustand.

6. Das <xref:System.Windows.Forms.Control.Click>-Ereignis wird ausgelöst.

7. Das <xref:System.Windows.Forms.Control.MouseClick>-Ereignis wird ausgelöst.

8. Das <xref:System.Windows.Forms.Control.MouseUp>-Ereignis wird ausgelöst.

    > [!NOTE]
    > Wenn der Benutzer den Mauszeiger bei gedrückter Maustaste aus dem umschaltbaren Steuerelement bewegt (z. B. wenn er die Maus bei gedrückter Maustaste vom <xref:System.Windows.Forms.Button>-Steuerelement weg bewegt), zeichnet das umschaltbare Steuerelement im erhöhten Zustand, und es tritt nur das <xref:System.Windows.Forms.Control.MouseUp>-Ereignis auf. Das <xref:System.Windows.Forms.Control.Click>-Ereignis oder das <xref:System.Windows.Forms.Control.MouseClick>-Ereignis tritt in dieser Situation nicht auf.

## <a name="see-also"></a>Weitere Informationen

- [Mauseingabe in einer Windows Forms-Anwendung](mouse-input-in-a-windows-forms-application.md)

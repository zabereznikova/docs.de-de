---
title: 'Gewusst wie: Steuern, wann der TextBox-Text die Quelle aktualisiert'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source updates [WPF], timing of
- data binding [WPF], timing of source updates
- timing of source updates [WPF]
ms.assetid: ffb7b96a-351d-4c68-81e7-054033781c64
ms.openlocfilehash: b211eb67e3bac95f74255935a39cc0d6aec61531
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974787"
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a>Gewusst wie: Steuern, wann der TextBox-Text die Quelle aktualisiert
In diesem Thema wird beschrieben, wie Sie die <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>-Eigenschaft verwenden, um die zeitliche Steuerung von Bindungs Quell Aktualisierungen zu steuern. In diesem Thema wird das <xref:System.Windows.Controls.TextBox>-Steuerelement als Beispiel verwendet.

## <a name="example"></a>Beispiel
 Die <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>-Eigenschaft hat den Standard <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Wert <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>. Dies bedeutet, dass eine Anwendung, die eine <xref:System.Windows.Controls.TextBox> mit einer Daten gebundenen <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> Eigenschaft aufweist, den Text, den Sie in die <xref:System.Windows.Controls.TextBox> eingeben, nicht aktualisiert, bis die <xref:System.Windows.Controls.TextBox> den Fokus verliert (wenn Sie beispielsweise auf den <xref:System.Windows.Controls.TextBox>klicken).

 Wenn die Quelle während der typaktualisierung aktualisiert werden soll, legen Sie den <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> der Bindung auf <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>fest. Im folgenden Beispiel zeigen die markierten Codezeilen, dass die `Text` Eigenschaften des <xref:System.Windows.Controls.TextBox> und des <xref:System.Windows.Controls.TextBlock> an dieselbe Quell Eigenschaft gebunden sind. Die <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>-Eigenschaft der <xref:System.Windows.Controls.TextBox> Bindung ist auf <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>festgelegt.

 [!code-xaml[SimpleBinding#USTHowTo](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=33-39,41-42)]

 Folglich zeigt der <xref:System.Windows.Controls.TextBlock> den gleichen Text an (weil sich die Quelle ändert), wenn der Benutzer Text in die <xref:System.Windows.Controls.TextBox>eingibt, wie im folgenden Screenshot des Beispiels veranschaulicht:

 ![Screenshot, der eine einfache Datenbindung anzeigt.](./media/how-to-control-when-the-textbox-text-updates-the-source/data-binding-simple-binding-sample.png)

 Wenn Sie über ein Dialogfeld oder ein vom Benutzer bearbeitbares Formular verfügen und Quell Updates verzögern möchten, bis der Benutzer die Bearbeitung der Felder abgeschlossen hat, und auf "OK" klicken, können Sie den <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Wert ihrer Bindungen auf <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>festlegen, wie im folgenden Beispiel gezeigt:

 [!code-xaml[UpdateSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]

 Wenn Sie den <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Wert auf <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>festlegen, ändert sich der Quellwert nur, wenn die Anwendung die <xref:System.Windows.Data.BindingExpression.UpdateSource%2A>-Methode aufruft. Im folgenden Beispiel wird gezeigt, wie <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> für `itemNameTextBox`aufgerufen wird:

 [!code-csharp[UpdateSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]

> [!NOTE]
> Sie können das gleiche Verfahren für Eigenschaften anderer Steuerelemente verwenden, beachten Sie jedoch, dass die meisten anderen Eigenschaften einen Standard <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Wert <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>haben. Weitere Informationen finden Sie auf der Eigenschaften Seite <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.

> [!NOTE]
> Die <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>-Eigenschaft behandelt Quell Updates und ist daher nur für <xref:System.Windows.Data.BindingMode.TwoWay>-oder <xref:System.Windows.Data.BindingMode.OneWayToSource> Bindungen relevant. Damit <xref:System.Windows.Data.BindingMode.TwoWay>-und <xref:System.Windows.Data.BindingMode.OneWayToSource> Bindungen funktionieren, muss das Quell Objekt Benachrichtigungen über Eigenschafts Änderungen bereitstellen. Weitere Informationen finden Sie in den Beispielen in diesem Thema. Zusätzliche Informationen können Sie auch dem Dokument [Implementieren von Benachrichtigungen bei Eigenschaftenänderungen](how-to-implement-property-change-notification.md) entnehmen.

## <a name="see-also"></a>Siehe auch

- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)

---
title: 'Gewusst wie: Steuern, wann der TextBox-Text die Quelle aktualisiert'
description: Steuern Sie die zeitliche Steuerung von Bindungs Quell Updates mithilfe der updatesourcetriggereigenschaft in Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source updates [WPF], timing of
- data binding [WPF], timing of source updates
- timing of source updates [WPF]
ms.assetid: ffb7b96a-351d-4c68-81e7-054033781c64
ms.openlocfilehash: 8f6eb5beb0d14a951f6e6cf6eb81e130f5a3e194
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622782"
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a>Gewusst wie: Steuern, wann der TextBox-Text die Quelle aktualisiert
In diesem Thema wird beschrieben, wie die-Eigenschaft verwendet wird <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> , um die zeitliche Steuerung von Bindungs Quell Aktualisierungen zu steuern. In diesem Thema wird das- <xref:System.Windows.Controls.TextBox> Steuerelement als Beispiel verwendet.

## <a name="example"></a>Beispiel
 Die- <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> Eigenschaft hat den Standard <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Wert <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> . Dies bedeutet, dass eine Anwendung, die über eine <xref:System.Windows.Controls.TextBox> -Eigenschaft mit einer Daten gebundenen <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> Eigenschaft verfügt, die <xref:System.Windows.Controls.TextBox> Quelle nicht aktualisiert, bis der den <xref:System.Windows.Controls.TextBox> Fokus verliert (wenn Sie z. h. auf den Weg von der klicken <xref:System.Windows.Controls.TextBox> ).

 Wenn die Quelle während der typaktualisierung aktualisiert werden soll, legen Sie die <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> der Bindung auf fest <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> . Im folgenden Beispiel zeigen die markierten Codezeilen, dass die `Text` Eigenschaften von <xref:System.Windows.Controls.TextBox> und <xref:System.Windows.Controls.TextBlock> an dieselbe Quell Eigenschaft gebunden sind. Die- <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Eigenschaft der <xref:System.Windows.Controls.TextBox> Bindung ist auf festgelegt <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> .

 [!code-xaml[SimpleBinding#USTHowTo](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=33-39,41-42)]

 Folglich <xref:System.Windows.Controls.TextBlock> zeigt den gleichen Text an (weil sich die Quelle ändert), wenn der Benutzer Text in den eingibt <xref:System.Windows.Controls.TextBox> , wie im folgenden Screenshot des Beispiels veranschaulicht:

 ![Screenshot, der eine einfache Datenbindung anzeigt.](./media/how-to-control-when-the-textbox-text-updates-the-source/data-binding-simple-binding-sample.png)

 Wenn Sie über ein Dialogfeld oder ein vom Benutzer bearbeitbares Formular verfügen und die Quell Updates verzögern möchten, bis der Benutzer die Bearbeitung der Felder abgeschlossen hat und auf "OK" klickt, können Sie den <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Wert der Bindungen auf festlegen <xref:System.Windows.Data.UpdateSourceTrigger.Explicit> , wie im folgenden Beispiel gezeigt:

 [!code-xaml[UpdateSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]

 Wenn Sie den <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Wert auf festlegen <xref:System.Windows.Data.UpdateSourceTrigger.Explicit> , wird der Quellwert nur geändert, wenn die Anwendung die- <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> Methode aufruft. Im folgenden Beispiel wird gezeigt, wie <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> für aufgerufen wird `itemNameTextBox` :

 [!code-csharp[UpdateSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]

> [!NOTE]
> Sie können das gleiche Verfahren für Eigenschaften anderer Steuerelemente verwenden, beachten Sie jedoch, dass die meisten anderen Eigenschaften den Standard <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Wert aufweisen <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> . Weitere Informationen finden Sie auf der <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Eigenschaften Seite.

> [!NOTE]
> Die <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> -Eigenschaft behandelt Quell Updates und ist daher nur für- <xref:System.Windows.Data.BindingMode.TwoWay> oder- <xref:System.Windows.Data.BindingMode.OneWayToSource> Bindungen relevant. Damit <xref:System.Windows.Data.BindingMode.TwoWay> <xref:System.Windows.Data.BindingMode.OneWayToSource> die Bindungen und funktionieren, muss das Quell Objekt Benachrichtigungen über Eigenschafts Änderungen bereitstellen. Weitere Informationen finden Sie in den Beispielen in diesem Thema. Zusätzliche Informationen können Sie auch dem Dokument [Implementieren von Benachrichtigungen bei Eigenschaftenänderungen](how-to-implement-property-change-notification.md) entnehmen.

## <a name="see-also"></a>Weitere Informationen

- [Artikel zu Vorgehensweisen](data-binding-how-to-topics.md)

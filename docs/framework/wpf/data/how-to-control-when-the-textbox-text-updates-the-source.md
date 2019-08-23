---
title: 'Vorgehensweise: Steuern, wann der TextBox-Text die Quelle aktualisiert'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source updates [WPF], timing of
- data binding [WPF], timing of source updates
- timing of source updates [WPF]
ms.assetid: ffb7b96a-351d-4c68-81e7-054033781c64
ms.openlocfilehash: d1d624d7550a1135431b7fffc7450e3a510855a7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966445"
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a>Vorgehensweise: Steuern, wann der TextBox-Text die Quelle aktualisiert
In diesem Thema wird beschrieben, wie <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> die-Eigenschaft verwendet wird, um die zeitliche Steuerung von Bindungs Quell Aktualisierungen zu steuern. In diesem Thema wird <xref:System.Windows.Controls.TextBox> das-Steuerelement als Beispiel verwendet.  
  
## <a name="example"></a>Beispiel  
 Das Sprachelement <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> die-Eigenschaft hat <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> den Standard <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>Wert. Dies bedeutet, wenn eine Anwendung über <xref:System.Windows.Controls.TextBox> eine mit Datenbindung <xref:System.Windows.Controls.TextBox>verfügt.<xref:System.Windows.Controls.TextBox.Text%2A> -Eigenschaft: der Text, den Sie <xref:System.Windows.Controls.TextBox> in den eingeben, aktualisiert die Quelle <xref:System.Windows.Controls.TextBox> erst, wenn der den Fokus verliert (wenn Sie beispielsweise <xref:System.Windows.Controls.TextBox>von der entfernt haben).  
  
 Wenn die Quelle während der typaktualisierung aktualisiert werden soll, legen Sie die <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> der Bindung auf <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>fest. Im folgenden Beispiel zeigen die markierten Codezeilen, dass die `Text` Eigenschaften von <xref:System.Windows.Controls.TextBox> und <xref:System.Windows.Controls.TextBlock> an dieselbe Quell Eigenschaft gebunden sind. Die <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> -Eigenschaft <xref:System.Windows.Controls.TextBox> der Bindung ist auf <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>festgelegt.  
  
 [!code-xaml[SimpleBinding#USTHowTo](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=33-39,41-42)]  
  
 Folglich <xref:System.Windows.Controls.TextBlock> zeigt den gleichen Text an (weil sich die Quelle ändert), wenn der Benutzer Text in den <xref:System.Windows.Controls.TextBox>eingibt, wie im folgenden Screenshot des Beispiels veranschaulicht:  
  
 ![Screenshot, der eine einfache Datenbindung anzeigt.](./media/how-to-control-when-the-textbox-text-updates-the-source/data-binding-simple-binding-sample.png)  
  
 Wenn Sie über ein Dialogfeld oder ein vom Benutzer bearbeitbares Formular verfügen und die Quell Updates verzögern möchten, bis der Benutzer die Bearbeitung der Felder abgeschlossen hat und auf "OK" klickt <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> , können Sie den Wert <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>der Bindungen auf festlegen, wie im folgenden Beispiel gezeigt:  
  
 [!code-xaml[UpdateSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]  
  
 Wenn Sie den <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Wert auf <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>festlegen, wird der Quellwert nur geändert, wenn die Anwendung <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> die-Methode aufruft. Im folgenden Beispiel wird gezeigt, <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> wie für `itemNameTextBox`aufgerufen wird:  
  
 [!code-csharp[UpdateSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]  
  
> [!NOTE]
> Sie können das gleiche Verfahren für Eigenschaften anderer Steuerelemente verwenden, beachten Sie jedoch, dass die meisten anderen Eigenschaften den Standard <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>Wert aufweisen. Weitere Informationen finden Sie auf der <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Eigenschaften Seite.  
  
> [!NOTE]
> Die <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> -Eigenschaft behandelt Quell Updates und ist daher nur für <xref:System.Windows.Data.BindingMode.TwoWay> -oder <xref:System.Windows.Data.BindingMode.OneWayToSource> -Bindungen relevant. Damit <xref:System.Windows.Data.BindingMode.TwoWay> die <xref:System.Windows.Data.BindingMode.OneWayToSource> Bindungen und funktionieren, muss das Quell Objekt Benachrichtigungen über Eigenschafts Änderungen bereitstellen. Weitere Informationen finden Sie in den Beispielen in diesem Thema. Zusätzliche Informationen können Sie auch dem Dokument [Implementieren von Benachrichtigungen bei Eigenschaftenänderungen](how-to-implement-property-change-notification.md) entnehmen.  
  
## <a name="see-also"></a>Siehe auch

- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)

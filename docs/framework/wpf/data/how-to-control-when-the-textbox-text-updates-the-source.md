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
ms.openlocfilehash: 52f3a8d3a5d78a211367722b3042eb50f6ac36d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557224"
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a>Gewusst wie: Steuern, wann der TextBox-Text die Quelle aktualisiert
Dieses Thema beschreibt, wie die <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Eigenschaft, um die zeitliche Steuerung von bindungsquellenaktualisierungen steuern. Das Thema verwendet die <xref:System.Windows.Controls.TextBox> Steuerelement als Beispiel.  
  
## <a name="example"></a>Beispiel  
 Das Sprachelement <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft hat den Standardwert <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Wert <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>. Dies bedeutet, wenn eine Anwendung eine <xref:System.Windows.Controls.TextBox> mit einem datengebundenen <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft, die den Text, die Sie eingeben, die <xref:System.Windows.Controls.TextBox> aktualisiert sich nicht auf die Quelle erst die <xref:System.Windows.Controls.TextBox> verliert den Fokus (z. B. beim Klicken auf aus der <xref:System.Windows.Controls.TextBox>).  
  
 Wenn die Quelle während der Eingabe aktualisiert werden soll, legen Sie die <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Bindung mit <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>. Im folgenden Beispiel zeigen die hervorgehobenen Codezeilen, die die `Text` Eigenschaften beider der <xref:System.Windows.Controls.TextBox> und <xref:System.Windows.Controls.TextBlock> an die gleichen Source-Eigenschaft gebunden sind. Die <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Eigenschaft von der <xref:System.Windows.Controls.TextBox> Bindung festgelegt ist, um <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.  
  
 [!code-xaml[SimpleBinding#USTHowTo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=33-39,41-42)]  
  
 Daher die <xref:System.Windows.Controls.TextBlock> derselben Text (da die Quelle ändert) zeigt, wie die vom Benutzer Text in eingegebene die <xref:System.Windows.Controls.TextBox>, wie der folgende Screenshot des Beispiels veranschaulicht:  
  
 ![Screenshot des einfachen Datenbindungsbeispiels](../../../../docs/framework/wpf/data/media/databindingsimplebindingsample2.png "DataBindingSimpleBindingSample2")  
  
 Wenn Sie ein Dialogfeld oder einem Benutzer bearbeitbare Formular und quellenaktualisierungen zu verzögern, bis der Benutzer die Felder Bearbeitung abgeschlossen ist, und klickt auf "OK" werden sollen, können Sie festlegen, die <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Wert Ihre Bindungen <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, wie im folgenden Beispiel:  
  
 [!code-xaml[UpdateSource#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]  
  
 Beim Festlegen der <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Wert <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, der Quellwert nur geändert werden, wenn die Anwendung aufruft, die <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> Methode. Im folgende Beispiel wird gezeigt, wie Aufrufen <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> für `itemNameTextBox`:  
  
 [!code-csharp[UpdateSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]  
  
> [!NOTE]
>  Verwenden Sie das gleiche Verfahren für Eigenschaften von anderen Steuerelementen, aber beachten Sie, dass die meisten anderen Eigenschaften ein Standardwert ist <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Wert <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>. Weitere Informationen finden Sie unter der <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Eigenschaftenseite.  
  
> [!NOTE]
>  Die <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Eigenschaft Quellupdates und ist daher nur für relevante <xref:System.Windows.Data.BindingMode.TwoWay> oder <xref:System.Windows.Data.BindingMode.OneWayToSource> Bindungen. Für <xref:System.Windows.Data.BindingMode.TwoWay> und <xref:System.Windows.Data.BindingMode.OneWayToSource> Bindungen funktioniert, muss die Quelle änderungsbenachrichtigungen für die Eigenschaft angeben. Weitere Informationen finden Sie in den Beispielen in diesem Thema. Zusätzliche Informationen können Sie auch dem Dokument [Implementieren von Benachrichtigungen bei Eigenschaftenänderungen](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md) entnehmen.  
  
## <a name="see-also"></a>Siehe auch  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)

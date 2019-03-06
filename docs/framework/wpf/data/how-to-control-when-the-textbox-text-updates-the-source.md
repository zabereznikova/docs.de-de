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
ms.openlocfilehash: 702f06a37aa98e3a84858a590655e8a4311cfa48
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362135"
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a>Vorgehensweise: Steuern, wann der TextBox-Text die Quelle aktualisiert
In diesem Thema wird beschrieben, wie Sie mit der <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Eigenschaft, um Aktualisierungen von Bindungsquellen zeitlich steuern. In diesem Thema wird die <xref:System.Windows.Controls.TextBox> Steuerelement als Beispiel.  
  
## <a name="example"></a>Beispiel  
 Das Sprachelement <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft hat den Standardwert <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Wert <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>. Dies bedeutet, wenn eine Anwendung eine <xref:System.Windows.Controls.TextBox> mit einem datengebundenen <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft, die den Text, die Sie eingeben, die <xref:System.Windows.Controls.TextBox> aktualisiert nicht die Quelle erst die <xref:System.Windows.Controls.TextBox> den Fokus verliert (z. B. beim Klicken auf aus der <xref:System.Windows.Controls.TextBox>).  
  
 Wenn die Quelle aktualisiert werden, während der Eingabe werden sollen, legen Sie die <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> zur Bindung mit <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>. Im folgenden Beispiel zeigen die hervorgehobenen Codezeilen, die die `Text` Eigenschaften sowohl die <xref:System.Windows.Controls.TextBox> und <xref:System.Windows.Controls.TextBlock> an die gleiche Quelleneigenschaft gebunden sind. Die <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Eigenschaft der <xref:System.Windows.Controls.TextBox> Bindung nastaven NA hodnotu <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.  
  
 [!code-xaml[SimpleBinding#USTHowTo](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=33-39,41-42)]  
  
 Daher die <xref:System.Windows.Controls.TextBlock> zeigt denselben Text (da die Quelle ändert), wenn der Benutzer Text in die <xref:System.Windows.Controls.TextBox>, wie im folgenden Screenshot des Beispiels veranschaulicht:  
  
 ![Screenshot des einfachen Datenbindungsbeispiels](./media/databindingsimplebindingsample2.png "DataBindingSimpleBindingSample2")  
  
 Wenn Sie ein Dialogfeld oder eine vom Benutzer bearbeitbaren Formular und quellenaktualisierungen zu verzögern, bis der Benutzer die Felder bearbeiten abgeschlossen ist, und klickt auf "OK" werden sollen, Sie können festlegen, die <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> -Wert Ihrer Bindungen auf <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, wie im folgenden Beispiel:  
  
 [!code-xaml[UpdateSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]  
  
 Beim Festlegen der <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Wert <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, der Quellwert nur geändert werden, wenn die Anwendung aufruft der <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> Methode. Das folgende Beispiel zeigt das Aufrufen von <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> für `itemNameTextBox`:  
  
 [!code-csharp[UpdateSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]  
  
> [!NOTE]
>  Sie können das gleiche Verfahren für Eigenschaften anderer Steuerelemente verwenden, aber denken Sie daran, dass die meisten anderen Eigenschaften einen Standardwert verfügen <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Wert <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>. Weitere Informationen finden Sie unter den <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Eigenschaftenseite.  
  
> [!NOTE]
>  Die <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> -Eigenschaft behandelt Quellupdates und ist daher nur relevant, für <xref:System.Windows.Data.BindingMode.TwoWay> oder <xref:System.Windows.Data.BindingMode.OneWayToSource> Bindungen. Für <xref:System.Windows.Data.BindingMode.TwoWay> und <xref:System.Windows.Data.BindingMode.OneWayToSource> -Bindung funktionieren, muss das Quellobjekt Benachrichtigungen für Eigenschaftenänderung bereitstellen. Weitere Informationen finden Sie in den Beispielen in diesem Thema. Zusätzliche Informationen können Sie auch dem Dokument [Implementieren von Benachrichtigungen bei Eigenschaftenänderungen](how-to-implement-property-change-notification.md) entnehmen.  
  
## <a name="see-also"></a>Siehe auch
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)

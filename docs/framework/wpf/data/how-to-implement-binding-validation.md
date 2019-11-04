---
title: 'Gewusst wie: Implementieren der Bindungsvalidierung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validation of binding [WPF]
- data binding [WPF], validation of binding
- binding [WPF], validation of
ms.assetid: eb98b33d-9866-49ae-b981-bc5ff20d607a
ms.openlocfilehash: 245b05d9cfa7ca66dec310bd9a5291def0101d19
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459111"
---
# <a name="how-to-implement-binding-validation"></a>Gewusst wie: Implementieren der Bindungsvalidierung

In diesem Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> und ein Formatvorlagen-Auslösers verwendet werden, um den Benutzer zu informieren, wenn ein ungültiger Wert auf der Grundlage einer benutzerdefinierten Validierungs Regel eingegeben wird.

## <a name="example"></a>Beispiel

Der Text Inhalt der <xref:System.Windows.Controls.TextBox> im folgenden Beispiel ist an die `Age`-Eigenschaft (vom Typ "int") eines Bindungs Quell Objekts mit dem Namen `ods`gebunden. Die Bindung ist so eingerichtet, dass die Validierungsregel mit `AgeRangeRule` verwendet wird. Wenn der Benutzer ein nicht numerisches Zeichen oder einen Wert kleiner als 21 oder größer als 130 eingibt, werden neben dem Textfeld ein rotes Ausrufezeichen und eine QuickInfo mit einer Fehlermeldung angezeigt, sobald der Mauszeiger über das Textfeld bewegt wird.

[!code-xaml[BindValidation#2](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#2)]

Das folgende Beispiel zeigt die Implementierung von `AgeRangeRule`, die von <xref:System.Windows.Controls.ValidationRule> erbt und die <xref:System.Windows.Controls.ValidationRule.Validate%2A>-Methode überschreibt. Die `Int32.Parse`-Methode wird für den-Wert aufgerufen, um sicherzustellen, dass Sie keine ungültigen Zeichen enthält. Die <xref:System.Windows.Controls.ValidationRule.Validate%2A>-Methode gibt eine <xref:System.Windows.Controls.ValidationResult> zurück, die angibt, ob der Wert gültig ist, je nachdem, ob eine Ausnahme während der Verarbeitung abgefangen wird und ob der Alters Wert außerhalb der unteren und oberen Begrenzungen liegt.

[!code-csharp[BindValidation#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/AgeRangeRule.cs#3)]
[!code-vb[BindValidation#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindValidation/VisualBasic/AgeRangeRule.vb#3)]

Das folgende Beispiel zeigt die benutzerdefinierte <xref:System.Windows.Controls.ControlTemplate> `validationTemplate`, die ein rotes Ausrufezeichen erstellt, um den Benutzer über einen Validierungs Fehler zu benachrichtigen. Steuerelementvorlagen werden verwendet, um die Darstellung eines Steuerelements neu zu definieren.

[!code-xaml[BindValidation#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#4)]

Wie im folgenden Beispiel gezeigt, wird der <xref:System.Windows.Controls.ToolTip>, der die Fehlermeldung anzeigt, mit dem Format "`textBoxInError`" erstellt. Wenn der Wert <xref:System.Windows.Controls.Validation.HasError%2A> `true`ist, legt der-Fehler die QuickInfo des aktuellen <xref:System.Windows.Controls.TextBox> auf den ersten Validierungs Fehler fest. Der <xref:System.Windows.Data.Binding.RelativeSource%2A> wird auf <xref:System.Windows.Data.RelativeSourceMode.Self>festgelegt, was auf das aktuelle Element verweist.

[!code-xaml[BindValidation#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#5)]

Das komplette Beispiel finden Sie unter Beispiel für die [Bind-Validierung](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation).
  
Beachten Sie Folgendes: Wenn Sie keine benutzerdefinierte <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> bereitstellen, wird die Standardfehler Vorlage angezeigt, um dem Benutzer beim Auftreten eines Validierungs Fehlers visuelles Feedback zu geben. Weitere Informationen finden Sie unter „Datenvalidierung“ in [Übersicht über die Datenbindung](../../../desktop-wpf/data/data-binding-overview.md). [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet außerdem eine integrierte Validierungsregel, die die während der Aktualisierung der Bindungsquelleneigenschaft ausgelöste Ausnahmen abfängt. Weitere Informationen finden Sie unter <xref:System.Windows.Controls.ExceptionValidationRule>.

## <a name="see-also"></a>Siehe auch

- [Übersicht zur Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)

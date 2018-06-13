---
title: 'Gewusst wie: Implementieren der Bindungsvalidierung'
ms.date: 03/30/2017
helpviewer_keywords:
- validation of binding [WPF]
- data binding [WPF], validation of binding
- binding [WPF], validation of
ms.assetid: eb98b33d-9866-49ae-b981-bc5ff20d607a
ms.openlocfilehash: 347e38ba036e5c1a716a9edb75572c1a49f99631
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556964"
---
# <a name="how-to-implement-binding-validation"></a>Gewusst wie: Implementieren der Bindungsvalidierung
Dieses Beispiel zeigt, wie ein <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> und ein Stil Trigger visuelles Feedback, um den Benutzer zu informieren, wenn ein ungültiger Wert eingegeben wird, basierend auf einer benutzerdefinierten Validierungsregel.  
  
## <a name="example"></a>Beispiel  
 Der Textinhalt des der <xref:System.Windows.Controls.TextBox> im folgenden Beispiel wird gebunden an die `Age` -Eigenschaft (vom Typ "Int") von einem Bindungsquellobjekt, das mit dem Namen `ods`. Die Bindung ist so eingerichtet, dass die Validierungsregel mit `AgeRangeRule` verwendet wird. Wenn der Benutzer ein nicht numerisches Zeichen oder einen Wert kleiner als 21 oder größer als 130 eingibt, werden neben dem Textfeld ein rotes Ausrufezeichen und eine QuickInfo mit einer Fehlermeldung angezeigt, sobald der Mauszeiger über das Textfeld bewegt wird.  
  
 [!code-xaml[BindValidation#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#2)]  
  
 Das folgende Beispiel zeigt die Implementierung der `AgeRangeRule`, erbt die <xref:System.Windows.Controls.ValidationRule> und überschreibt die <xref:System.Windows.Controls.ValidationRule.Validate%2A> Methode. Die Int32.Parse()-Methode wird für den Wert aufgerufen, um sicherzustellen, dass keine ungültigen Zeichen enthalten sind. Die <xref:System.Windows.Controls.ValidationRule.Validate%2A> Methode gibt ein <xref:System.Windows.Controls.ValidationResult> , der angibt, ob der Wert gültig ist, basierend auf, ob eine Ausnahme abgefangen wird, während der Analyse und gibt an, ob die ALTER-Wert außerhalb der unter- und Obergrenzen ist.  
  
 [!code-csharp[BindValidation#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/AgeRangeRule.cs#3)]  
  
 Das folgende Beispiel zeigt die benutzerdefinierte <xref:System.Windows.Controls.ControlTemplate> `validationTemplate` , erstellt ein rotes Ausrufezeichen auf die Benachrichtigung des Benutzers einen Validierungsfehler. Steuerelementvorlagen werden verwendet, um die Darstellung eines Steuerelements neu zu definieren.  
  
 [!code-xaml[BindValidation#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#4)]  
  
 Wie im folgenden Beispiel gezeigt die <xref:System.Windows.Controls.ToolTip> , die anzeigt, die Fehlermeldung wird mit dem Namen erstellt `textBoxInError`. Wenn der Wert der <xref:System.Windows.Controls.Validation.HasError%2A> ist `true`, des Triggers legt die QuickInfo des aktuellen <xref:System.Windows.Controls.TextBox> auf den ersten Validierungsfehler. Die <xref:System.Windows.Data.Binding.RelativeSource%2A> festgelegt ist, um <xref:System.Windows.Data.RelativeSourceMode.Self>, das auf das aktuelle Element.  
  
 [!code-xaml[BindValidation#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#5)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für Bindungsvalidierung](http://go.microsoft.com/fwlink/?LinkID=159972).  
  
 Beachten Sie, dass, wenn Sie keine, dass eine benutzerdefinierte ergeben <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> die Standardvorlage für den Fehler visuelles Feedback an den Benutzer bei ein Überprüfungsfehler wird angezeigt. Weitere Informationen finden Sie unter „Datenvalidierung“ in [Übersicht über die Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md). [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet außerdem eine integrierte Validierungsregel, die die während der Aktualisierung der Bindungsquelleneigenschaft ausgelöste Ausnahmen abfängt. Weitere Informationen finden Sie unter <xref:System.Windows.Controls.ExceptionValidationRule>.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht zur Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)

---
title: 'Vorgehensweise: Implementieren der Bindungsvalidierung'
ms.date: 03/30/2017
helpviewer_keywords:
- validation of binding [WPF]
- data binding [WPF], validation of binding
- binding [WPF], validation of
ms.assetid: eb98b33d-9866-49ae-b981-bc5ff20d607a
ms.openlocfilehash: 3950df8b6f4b48a035c6ebf37d8d65c18cb82e1e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197216"
---
# <a name="how-to-implement-binding-validation"></a>Vorgehensweise: Implementieren der Bindungsvalidierung
Dieses Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> und ein Formattriggers zum Bereitstellen von visuellen Feedback, um den Benutzer zu informieren, wenn ein ungültiger Wert eingegeben wird, auf Grundlage einer benutzerdefinierten Validierungsregel.  
  
## <a name="example"></a>Beispiel  
 Der Textinhalt von der <xref:System.Windows.Controls.TextBox> im folgenden Beispiel an gebunden ist die `Age` -Eigenschaft (vom Typ "Int") von einem mit dem Namen Bindungsquellen-Objekts `ods`. Die Bindung ist so eingerichtet, dass die Validierungsregel mit `AgeRangeRule` verwendet wird. Wenn der Benutzer ein nicht numerisches Zeichen oder einen Wert kleiner als 21 oder größer als 130 eingibt, werden neben dem Textfeld ein rotes Ausrufezeichen und eine QuickInfo mit einer Fehlermeldung angezeigt, sobald der Mauszeiger über das Textfeld bewegt wird.  
  
 [!code-xaml[BindValidation#2](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#2)]  
  
 Das folgende Beispiel zeigt die Implementierung der `AgeRangeRule`, erbt von <xref:System.Windows.Controls.ValidationRule> und überschreibt die <xref:System.Windows.Controls.ValidationRule.Validate%2A> Methode. Die Int32.Parse()-Methode wird für den Wert aufgerufen, um sicherzustellen, dass keine ungültigen Zeichen enthalten sind. Die <xref:System.Windows.Controls.ValidationRule.Validate%2A> Methode gibt eine <xref:System.Windows.Controls.ValidationResult> die angibt, ob der Wert gültig ist, basierend auf gibt an, ob eine Ausnahme abgefangen wird, während der Analyse und gibt an, ob der Alterswert außerhalb der unter- und Obergrenzen ist.  
  
 [!code-csharp[BindValidation#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/AgeRangeRule.cs#3)]  
  
 Das folgende Beispiel zeigt die benutzerdefinierte <xref:System.Windows.Controls.ControlTemplate> `validationTemplate` erstellt ein rotes Ausrufezeichen zur Benachrichtigung des Benutzers eines Validierungsfehlers. Steuerelementvorlagen werden verwendet, um die Darstellung eines Steuerelements neu zu definieren.  
  
 [!code-xaml[BindValidation#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#4)]  
  
 Wie im folgenden Beispiel gezeigt die <xref:System.Windows.Controls.ToolTip> , die zeigt die Fehlermeldung wird erstellt, mit dem Stil, die mit dem Namen `textBoxInError`. Wenn der Wert des <xref:System.Windows.Controls.Validation.HasError%2A> ist `true`, des Triggers legt die QuickInfo des aktuellen <xref:System.Windows.Controls.TextBox> zu den ersten Validierungsfehler. Die <xref:System.Windows.Data.Binding.RelativeSource%2A> nastaven NA hodnotu <xref:System.Windows.Data.RelativeSourceMode.Self>, bezieht sich auf das aktuelle Element.  
  
 [!code-xaml[BindValidation#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#5)]  
  
 Das vollständige Beispiel finden Sie unter [Beispiel für Bindungsvalidierung](https://go.microsoft.com/fwlink/?LinkID=159972).  
  
 Beachten Sie, dass Sie keine benutzerdefinierte bereitstellen <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> Standardwert wird durch die zum Bereitstellen von visuellem Feedback, die dem Benutzer, wenn ein Überprüfungsfehler vorliegt. Weitere Informationen finden Sie unter „Datenvalidierung“ in [Übersicht über die Datenbindung](data-binding-overview.md). [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet außerdem eine integrierte Validierungsregel, die die während der Aktualisierung der Bindungsquelleneigenschaft ausgelöste Ausnahmen abfängt. Weitere Informationen finden Sie unter <xref:System.Windows.Controls.ExceptionValidationRule>.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht zur Datenbindung](data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)

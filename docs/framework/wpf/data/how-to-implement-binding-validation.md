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
ms.openlocfilehash: 7a1a8df78a785066992472c7de37f958ae3467f1
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920157"
---
# <a name="how-to-implement-binding-validation"></a><span data-ttu-id="764d2-102">Gewusst wie: Implementieren der Bindungsvalidierung</span><span class="sxs-lookup"><span data-stu-id="764d2-102">How to: Implement Binding Validation</span></span>

<span data-ttu-id="764d2-103">In diesem Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> und ein Formatvorlagen-Auslösers verwendet werden, um den Benutzer zu informieren, wenn ein ungültiger Wert auf der Grundlage einer benutzerdefinierten Validierungs Regel eingegeben wird.</span><span class="sxs-lookup"><span data-stu-id="764d2-103">This example shows how to use an <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> and a style trigger to provide visual feedback to inform the user when an invalid value is entered, based on a custom validation rule.</span></span>

## <a name="example"></a><span data-ttu-id="764d2-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="764d2-104">Example</span></span>

<span data-ttu-id="764d2-105">Der Text Inhalt der <xref:System.Windows.Controls.TextBox> im folgenden Beispiel ist an die `Age`-Eigenschaft (vom Typ "int") eines Bindungs Quell Objekts mit dem Namen `ods`gebunden.</span><span class="sxs-lookup"><span data-stu-id="764d2-105">The text content of the <xref:System.Windows.Controls.TextBox> in the following example is bound to the `Age` property (of type int) of a binding source object named `ods`.</span></span> <span data-ttu-id="764d2-106">Die Bindung ist so eingerichtet, dass die Validierungsregel mit `AgeRangeRule` verwendet wird. Wenn der Benutzer ein nicht numerisches Zeichen oder einen Wert kleiner als 21 oder größer als 130 eingibt, werden neben dem Textfeld ein rotes Ausrufezeichen und eine QuickInfo mit einer Fehlermeldung angezeigt, sobald der Mauszeiger über das Textfeld bewegt wird.</span><span class="sxs-lookup"><span data-stu-id="764d2-106">The binding is set up to use a validation rule named `AgeRangeRule` so that if the user enters non-numeric characters or a value that is smaller than 21 or greater than 130, a red exclamation mark appears next to the text box and a tool tip with the error message appears when the user moves the mouse over the text box.</span></span>

[!code-xaml[BindValidation#2](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#2)]

<span data-ttu-id="764d2-107">Das folgende Beispiel zeigt die Implementierung von `AgeRangeRule`, die von <xref:System.Windows.Controls.ValidationRule> erbt und die <xref:System.Windows.Controls.ValidationRule.Validate%2A>-Methode überschreibt.</span><span class="sxs-lookup"><span data-stu-id="764d2-107">The following example shows the implementation of `AgeRangeRule`, which inherits from <xref:System.Windows.Controls.ValidationRule> and overrides the <xref:System.Windows.Controls.ValidationRule.Validate%2A> method.</span></span> <span data-ttu-id="764d2-108">Die `Int32.Parse`-Methode wird für den-Wert aufgerufen, um sicherzustellen, dass Sie keine ungültigen Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="764d2-108">The `Int32.Parse` method is called on the value to make sure that it does not contain any invalid characters.</span></span> <span data-ttu-id="764d2-109">Die <xref:System.Windows.Controls.ValidationRule.Validate%2A>-Methode gibt eine <xref:System.Windows.Controls.ValidationResult> zurück, die angibt, ob der Wert gültig ist, je nachdem, ob eine Ausnahme während der Verarbeitung abgefangen wird und ob der Alters Wert außerhalb der unteren und oberen Begrenzungen liegt.</span><span class="sxs-lookup"><span data-stu-id="764d2-109">The <xref:System.Windows.Controls.ValidationRule.Validate%2A> method returns a <xref:System.Windows.Controls.ValidationResult> that indicates if the value is valid based on whether an exception is caught during the parsing and whether the age value is outside of the lower and upper bounds.</span></span>

[!code-csharp[BindValidation#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/AgeRangeRule.cs#3)]
[!code-vb[BindValidation#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindValidation/VisualBasic/AgeRangeRule.vb#3)]

<span data-ttu-id="764d2-110">Das folgende Beispiel zeigt die benutzerdefinierte <xref:System.Windows.Controls.ControlTemplate> `validationTemplate`, die ein rotes Ausrufezeichen erstellt, um den Benutzer über einen Validierungs Fehler zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="764d2-110">The following example shows the custom <xref:System.Windows.Controls.ControlTemplate> `validationTemplate` that creates a red exclamation mark to notify the user of a validation error.</span></span> <span data-ttu-id="764d2-111">Steuerelementvorlagen werden verwendet, um die Darstellung eines Steuerelements neu zu definieren.</span><span class="sxs-lookup"><span data-stu-id="764d2-111">Control templates are used to redefine the appearance of a control.</span></span>

[!code-xaml[BindValidation#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#4)]

<span data-ttu-id="764d2-112">Wie im folgenden Beispiel gezeigt, wird der <xref:System.Windows.Controls.ToolTip>, der die Fehlermeldung anzeigt, mit dem Format "`textBoxInError`" erstellt.</span><span class="sxs-lookup"><span data-stu-id="764d2-112">As shown in the following example, the <xref:System.Windows.Controls.ToolTip> that shows the error message is created using the style named `textBoxInError`.</span></span> <span data-ttu-id="764d2-113">Wenn der Wert <xref:System.Windows.Controls.Validation.HasError%2A> `true`ist, legt der-Fehler die QuickInfo des aktuellen <xref:System.Windows.Controls.TextBox> auf den ersten Validierungs Fehler fest.</span><span class="sxs-lookup"><span data-stu-id="764d2-113">If the value of <xref:System.Windows.Controls.Validation.HasError%2A> is `true`, the trigger sets the tool tip of the current <xref:System.Windows.Controls.TextBox> to its first validation error.</span></span> <span data-ttu-id="764d2-114">Der <xref:System.Windows.Data.Binding.RelativeSource%2A> wird auf <xref:System.Windows.Data.RelativeSourceMode.Self>festgelegt, was auf das aktuelle Element verweist.</span><span class="sxs-lookup"><span data-stu-id="764d2-114">The <xref:System.Windows.Data.Binding.RelativeSource%2A> is set to <xref:System.Windows.Data.RelativeSourceMode.Self>, referring to the current element.</span></span>

[!code-xaml[BindValidation#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#5)]

<span data-ttu-id="764d2-115">Das komplette Beispiel finden Sie unter Beispiel für die [Bind-Validierung](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation).</span><span class="sxs-lookup"><span data-stu-id="764d2-115">For the complete example, see [Bind Validation sample](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation).</span></span>
  
<span data-ttu-id="764d2-116">Beachten Sie Folgendes: Wenn Sie keine benutzerdefinierte <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> bereitstellen, wird die Standardfehler Vorlage angezeigt, um dem Benutzer beim Auftreten eines Validierungs Fehlers visuelles Feedback zu geben.</span><span class="sxs-lookup"><span data-stu-id="764d2-116">Note that if you do not provide a custom <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> the default error template appears to provide visual feedback to the user when there is a validation error.</span></span> <span data-ttu-id="764d2-117">Weitere Informationen finden Sie unter „Datenvalidierung“ in [Übersicht über die Datenbindung](data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="764d2-117">See "Data Validation" in [Data Binding Overview](data-binding-overview.md) for more information.</span></span> <span data-ttu-id="764d2-118">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet außerdem eine integrierte Validierungsregel, die die während der Aktualisierung der Bindungsquelleneigenschaft ausgelöste Ausnahmen abfängt.</span><span class="sxs-lookup"><span data-stu-id="764d2-118">Also, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] provides a built-in validation rule that catches exceptions that are thrown during the update of the binding source property.</span></span> <span data-ttu-id="764d2-119">Weitere Informationen finden Sie unter <xref:System.Windows.Controls.ExceptionValidationRule>.</span><span class="sxs-lookup"><span data-stu-id="764d2-119">For more information, see <xref:System.Windows.Controls.ExceptionValidationRule>.</span></span>

## <a name="see-also"></a><span data-ttu-id="764d2-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="764d2-120">See also</span></span>

- [<span data-ttu-id="764d2-121">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="764d2-121">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="764d2-122">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="764d2-122">How-to Topics</span></span>](data-binding-how-to-topics.md)

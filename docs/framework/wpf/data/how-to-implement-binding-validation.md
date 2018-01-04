---
title: 'Gewusst wie: Implementieren der Bindungsvalidierung'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- validation of binding [WPF]
- data binding [WPF], validation of binding
- binding [WPF], validation of
ms.assetid: eb98b33d-9866-49ae-b981-bc5ff20d607a
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2d57fb099fa364d34b7df5c5fce792eb42079a31
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-binding-validation"></a><span data-ttu-id="52ffd-102">Gewusst wie: Implementieren der Bindungsvalidierung</span><span class="sxs-lookup"><span data-stu-id="52ffd-102">How to: Implement Binding Validation</span></span>
<span data-ttu-id="52ffd-103">Dieses Beispiel zeigt, wie ein <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> und ein Stil Trigger visuelles Feedback, um den Benutzer zu informieren, wenn ein ungültiger Wert eingegeben wird, basierend auf einer benutzerdefinierten Validierungsregel.</span><span class="sxs-lookup"><span data-stu-id="52ffd-103">This example shows how to use an <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> and a style trigger to provide visual feedback to inform the user when an invalid value is entered, based on a custom validation rule.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52ffd-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="52ffd-104">Example</span></span>  
 <span data-ttu-id="52ffd-105">Der Textinhalt des der <xref:System.Windows.Controls.TextBox> im folgenden Beispiel wird gebunden an die `Age` -Eigenschaft (vom Typ "Int") von einem Bindungsquellobjekt, das mit dem Namen `ods`.</span><span class="sxs-lookup"><span data-stu-id="52ffd-105">The text content of the <xref:System.Windows.Controls.TextBox> in the following example is bound to the `Age` property (of type int) of a binding source object named `ods`.</span></span> <span data-ttu-id="52ffd-106">Die Bindung ist so eingerichtet, dass die Validierungsregel mit `AgeRangeRule` verwendet wird. Wenn der Benutzer ein nicht numerisches Zeichen oder einen Wert kleiner als 21 oder größer als 130 eingibt, werden neben dem Textfeld ein rotes Ausrufezeichen und eine QuickInfo mit einer Fehlermeldung angezeigt, sobald der Mauszeiger über das Textfeld bewegt wird.</span><span class="sxs-lookup"><span data-stu-id="52ffd-106">The binding is set up to use a validation rule named `AgeRangeRule` so that if the user enters non-numeric characters or a value that is smaller than 21 or greater than 130, a red exclamation mark appears next to the text box and a tool tip with the error message appears when the user moves the mouse over the text box.</span></span>  
  
 [!code-xaml[BindValidation#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="52ffd-107">Das folgende Beispiel zeigt die Implementierung der `AgeRangeRule`, erbt die <xref:System.Windows.Controls.ValidationRule> und überschreibt die <xref:System.Windows.Controls.ValidationRule.Validate%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="52ffd-107">The following example shows the implementation of `AgeRangeRule`, which inherits from <xref:System.Windows.Controls.ValidationRule> and overrides the <xref:System.Windows.Controls.ValidationRule.Validate%2A> method.</span></span> <span data-ttu-id="52ffd-108">Die Int32.Parse()-Methode wird für den Wert aufgerufen, um sicherzustellen, dass keine ungültigen Zeichen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="52ffd-108">The Int32.Parse() method is called on the value to make sure that it does not contain any invalid characters.</span></span> <span data-ttu-id="52ffd-109">Die <xref:System.Windows.Controls.ValidationRule.Validate%2A> Methode gibt ein <xref:System.Windows.Controls.ValidationResult> , der angibt, ob der Wert gültig ist, basierend auf, ob eine Ausnahme abgefangen wird, während der Analyse und gibt an, ob die ALTER-Wert außerhalb der unter- und Obergrenzen ist.</span><span class="sxs-lookup"><span data-stu-id="52ffd-109">The <xref:System.Windows.Controls.ValidationRule.Validate%2A> method returns a <xref:System.Windows.Controls.ValidationResult> that indicates if the value is valid based on whether an exception is caught during the parsing and whether the age value is outside of the lower and upper bounds.</span></span>  
  
 [!code-csharp[BindValidation#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/AgeRangeRule.cs#3)]  
  
 <span data-ttu-id="52ffd-110">Das folgende Beispiel zeigt die benutzerdefinierte <xref:System.Windows.Controls.ControlTemplate> `validationTemplate` , erstellt ein rotes Ausrufezeichen auf die Benachrichtigung des Benutzers einen Validierungsfehler.</span><span class="sxs-lookup"><span data-stu-id="52ffd-110">The following example shows the custom <xref:System.Windows.Controls.ControlTemplate> `validationTemplate` that creates a red exclamation mark to notify the user of a validation error.</span></span> <span data-ttu-id="52ffd-111">Steuerelementvorlagen werden verwendet, um die Darstellung eines Steuerelements neu zu definieren.</span><span class="sxs-lookup"><span data-stu-id="52ffd-111">Control templates are used to redefine the appearance of a control.</span></span>  
  
 [!code-xaml[BindValidation#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#4)]  
  
 <span data-ttu-id="52ffd-112">Wie im folgenden Beispiel gezeigt die <xref:System.Windows.Controls.ToolTip> , die anzeigt, die Fehlermeldung wird mit dem Namen erstellt `textBoxInError`.</span><span class="sxs-lookup"><span data-stu-id="52ffd-112">As shown in the following example, the <xref:System.Windows.Controls.ToolTip> that shows the error message is created using the style named `textBoxInError`.</span></span> <span data-ttu-id="52ffd-113">Wenn der Wert der <xref:System.Windows.Controls.Validation.HasError%2A> ist `true`, des Triggers legt die QuickInfo des aktuellen <xref:System.Windows.Controls.TextBox> auf den ersten Validierungsfehler.</span><span class="sxs-lookup"><span data-stu-id="52ffd-113">If the value of <xref:System.Windows.Controls.Validation.HasError%2A> is `true`, the trigger sets the tool tip of the current <xref:System.Windows.Controls.TextBox> to its first validation error.</span></span> <span data-ttu-id="52ffd-114">Die <xref:System.Windows.Data.Binding.RelativeSource%2A> festgelegt ist, um <xref:System.Windows.Data.RelativeSourceMode.Self>, das auf das aktuelle Element.</span><span class="sxs-lookup"><span data-stu-id="52ffd-114">The <xref:System.Windows.Data.Binding.RelativeSource%2A> is set to <xref:System.Windows.Data.RelativeSourceMode.Self>, referring to the current element.</span></span>  
  
 [!code-xaml[BindValidation#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#5)]  
  
 <span data-ttu-id="52ffd-115">Das vollständige Beispiel finden Sie unter [Beispiel für Bindungsvalidierung](http://go.microsoft.com/fwlink/?LinkID=159972).</span><span class="sxs-lookup"><span data-stu-id="52ffd-115">For the complete example, see [Binding Validation Sample](http://go.microsoft.com/fwlink/?LinkID=159972).</span></span>  
  
 <span data-ttu-id="52ffd-116">Beachten Sie, dass, wenn Sie keine, dass eine benutzerdefinierte ergeben <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> die Standardvorlage für den Fehler visuelles Feedback an den Benutzer bei ein Überprüfungsfehler wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="52ffd-116">Note that if you do not provide a custom <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> the default error template appears to provide visual feedback to the user when there is a validation error.</span></span> <span data-ttu-id="52ffd-117">Weitere Informationen finden Sie unter „Datenvalidierung“ in [Übersicht über die Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="52ffd-117">See "Data Validation" in [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md) for more information.</span></span> <span data-ttu-id="52ffd-118">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet außerdem eine integrierte Validierungsregel, die die während der Aktualisierung der Bindungsquelleneigenschaft ausgelöste Ausnahmen abfängt.</span><span class="sxs-lookup"><span data-stu-id="52ffd-118">Also, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] provides a built-in validation rule that catches exceptions that are thrown during the update of the binding source property.</span></span> <span data-ttu-id="52ffd-119">Weitere Informationen finden Sie unter <xref:System.Windows.Controls.ExceptionValidationRule>.</span><span class="sxs-lookup"><span data-stu-id="52ffd-119">For more information, see <xref:System.Windows.Controls.ExceptionValidationRule>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52ffd-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52ffd-120">See Also</span></span>  
 [<span data-ttu-id="52ffd-121">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="52ffd-121">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="52ffd-122">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="52ffd-122">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)

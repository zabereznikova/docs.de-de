---
title: 'Gewusst wie: Steuern, wann der TextBox-Text die Quelle aktualisiert'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source updates [WPF], timing of
- data binding [WPF], timing of source updates
- timing of source updates [WPF]
ms.assetid: ffb7b96a-351d-4c68-81e7-054033781c64
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 00fc64938e6a063ffbda77961f967e08c169ebd7
ms.sourcegitcommit: 973a12d1e6962cd9a9c263fbfaad040ec8267fe9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/22/2018
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a><span data-ttu-id="00be6-102">Gewusst wie: Steuern, wann der TextBox-Text die Quelle aktualisiert</span><span class="sxs-lookup"><span data-stu-id="00be6-102">How to: Control When the TextBox Text Updates the Source</span></span>
<span data-ttu-id="00be6-103">Dieses Thema beschreibt, wie die <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Eigenschaft, um die zeitliche Steuerung von bindungsquellenaktualisierungen steuern.</span><span class="sxs-lookup"><span data-stu-id="00be6-103">This topic describes how to use the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property to control the timing of binding source updates.</span></span> <span data-ttu-id="00be6-104">Das Thema verwendet die <xref:System.Windows.Controls.TextBox> Steuerelement als Beispiel.</span><span class="sxs-lookup"><span data-stu-id="00be6-104">The topic uses the <xref:System.Windows.Controls.TextBox> control as an example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00be6-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="00be6-105">Example</span></span>  
 <span data-ttu-id="00be6-106">Die <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> Eigenschaft hat den Standardwert <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Wert <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>.</span><span class="sxs-lookup"><span data-stu-id="00be6-106">The <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> property has a default <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value of <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>.</span></span> <span data-ttu-id="00be6-107">Dies bedeutet, wenn eine Anwendung eine <xref:System.Windows.Controls.TextBox> mit einem datengebundenen <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> -Eigenschaft, die den Text, die Sie eingeben, die <xref:System.Windows.Controls.TextBox> aktualisiert sich nicht auf die Quelle erst die <xref:System.Windows.Controls.TextBox> verliert den Fokus (z. B. beim Klicken auf Weg von der <xref:System.Windows.Controls.TextBox>).</span><span class="sxs-lookup"><span data-stu-id="00be6-107">This means if an application has a <xref:System.Windows.Controls.TextBox> with a data-bound <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> property, the text you type into the <xref:System.Windows.Controls.TextBox> does not update the source until the <xref:System.Windows.Controls.TextBox> loses focus (for instance, when you click away from the <xref:System.Windows.Controls.TextBox>).</span></span>  
  
 <span data-ttu-id="00be6-108">Wenn die Quelle während der Eingabe aktualisiert werden soll, legen Sie die <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Bindung mit <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="00be6-108">If you want the source to be updated as you type, set the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> of the binding to <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span></span> <span data-ttu-id="00be6-109">Im folgenden Beispiel zeigen die hervorgehobenen Codezeilen, die die `Text` Eigenschaften beider der <xref:System.Windows.Controls.TextBox> und <xref:System.Windows.Controls.TextBlock> an die gleichen Source-Eigenschaft gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="00be6-109">In the following example, the highlighted lines of code show that the `Text` properties of both the <xref:System.Windows.Controls.TextBox> and the <xref:System.Windows.Controls.TextBlock> are bound to the same source property.</span></span> <span data-ttu-id="00be6-110">Die <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Eigenschaft von der <xref:System.Windows.Controls.TextBox> Bindung festgelegt ist, um <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="00be6-110">The <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property of the <xref:System.Windows.Controls.TextBox> binding is set to <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span></span>  
  
 [!code-xaml[SimpleBinding#USTHowTo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=33-39,41-42)]  
  
 <span data-ttu-id="00be6-111">Daher die <xref:System.Windows.Controls.TextBlock> derselben Text (da die Quelle ändert) zeigt, wie die vom Benutzer Text in eingegebene die <xref:System.Windows.Controls.TextBox>, wie der folgende Screenshot des Beispiels veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="00be6-111">As a result, the <xref:System.Windows.Controls.TextBlock> shows the same text (because the source changes) as the user enters text into the <xref:System.Windows.Controls.TextBox>, as illustrated by the following screenshot of the sample:</span></span>  
  
 <span data-ttu-id="00be6-112">![Screenshot des einfachen Datenbindungsbeispiels](../../../../docs/framework/wpf/data/media/databindingsimplebindingsample2.png "DataBindingSimpleBindingSample2")</span><span class="sxs-lookup"><span data-stu-id="00be6-112">![Simple data binding sample screen shot](../../../../docs/framework/wpf/data/media/databindingsimplebindingsample2.png "DataBindingSimpleBindingSample2")</span></span>  
  
 <span data-ttu-id="00be6-113">Wenn Sie ein Dialogfeld oder einem Benutzer bearbeitbare Formular und quellenaktualisierungen zu verzögern, bis der Benutzer die Felder Bearbeitung abgeschlossen ist, und klickt auf "OK" werden sollen, können Sie festlegen, die <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Wert Ihre Bindungen <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="00be6-113">If you have a dialog or a user-editable form and you want to defer source updates until the user is finished editing the fields and clicks "OK", you can set the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value of your bindings to <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, as in the following example:</span></span>  
  
 [!code-xaml[UpdateSource#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="00be6-114">Beim Festlegen der <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Wert <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, der Quellwert nur geändert werden, wenn die Anwendung aufruft, die <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="00be6-114">When you set the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value to <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, the source value only changes when the application calls the <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> method.</span></span> <span data-ttu-id="00be6-115">Im folgende Beispiel wird gezeigt, wie Aufrufen <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> für `itemNameTextBox`:</span><span class="sxs-lookup"><span data-stu-id="00be6-115">The following example shows how to call <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> for `itemNameTextBox`:</span></span>  
  
 [!code-csharp[UpdateSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]  
  
> [!NOTE]
>  <span data-ttu-id="00be6-116">Verwenden Sie das gleiche Verfahren für Eigenschaften von anderen Steuerelementen, aber beachten Sie, dass die meisten anderen Eigenschaften ein Standardwert ist <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Wert <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="00be6-116">You can use the same technique for properties of other controls, but keep in mind that most other properties have a default <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value of <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span></span> <span data-ttu-id="00be6-117">Weitere Informationen finden Sie unter der <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Eigenschaftenseite.</span><span class="sxs-lookup"><span data-stu-id="00be6-117">For more information, see the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property page.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00be6-118">Die <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Eigenschaft Quellupdates und ist daher nur für relevante <xref:System.Windows.Data.BindingMode.TwoWay> oder <xref:System.Windows.Data.BindingMode.OneWayToSource> Bindungen.</span><span class="sxs-lookup"><span data-stu-id="00be6-118">The <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property deals with source updates and therefore is only relevant for <xref:System.Windows.Data.BindingMode.TwoWay> or <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings.</span></span> <span data-ttu-id="00be6-119">Für <xref:System.Windows.Data.BindingMode.TwoWay> und <xref:System.Windows.Data.BindingMode.OneWayToSource> Bindungen funktioniert, muss die Quelle änderungsbenachrichtigungen für die Eigenschaft angeben.</span><span class="sxs-lookup"><span data-stu-id="00be6-119">For <xref:System.Windows.Data.BindingMode.TwoWay> and <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings to work, the source object needs to provide property change notifications.</span></span> <span data-ttu-id="00be6-120">Weitere Informationen finden Sie in den Beispielen in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="00be6-120">You can refer to the samples cited in this topic for more information.</span></span> <span data-ttu-id="00be6-121">Zusätzliche Informationen können Sie auch dem Dokument [Implementieren von Benachrichtigungen bei Eigenschaftenänderungen](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md) entnehmen.</span><span class="sxs-lookup"><span data-stu-id="00be6-121">In addition, you can look at [Implement Property Change Notification](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00be6-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00be6-122">See Also</span></span>  
 [<span data-ttu-id="00be6-123">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="00be6-123">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)

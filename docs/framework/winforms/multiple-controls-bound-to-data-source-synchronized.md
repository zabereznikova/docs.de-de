---
title: 'Gewusst wie: Sicherstellen, dass mehrere Steuerelemente, die an die gleiche Datenquelle gebunden sind, synchronisiert bleiben'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], binding multiple
- controls [Windows Forms], synchronizing with data source
ms.assetid: c2f0ecc6-11e6-4c2c-a1ca-0759630c451e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 227ad36e87c3deceb7fefe3cd19013fc8e76c686
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-ensure-multiple-controls-bound-to-the-same-data-source-remain-synchronized"></a><span data-ttu-id="96b1a-102">Gewusst wie: Sicherstellen, dass mehrere Steuerelemente, die an die gleiche Datenquelle gebunden sind, synchronisiert bleiben</span><span class="sxs-lookup"><span data-stu-id="96b1a-102">How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized</span></span>
<span data-ttu-id="96b1a-103">Häufig bei der Arbeit mit dem Datenbindung in Windows Forms werden mehrere Steuerelemente, die an die gleiche Datenquelle gebunden.</span><span class="sxs-lookup"><span data-stu-id="96b1a-103">Oftentimes when working with data binding in Windows Forms, multiple controls are bound to the same data source.</span></span> <span data-ttu-id="96b1a-104">In einigen Fällen kann es erforderlich sein, zusätzliche Schritte ausführen, um sicherzustellen, dass die gebundenen Eigenschaften der Steuerelemente untereinander und mit der Datenquelle synchronisiert bleiben.</span><span class="sxs-lookup"><span data-stu-id="96b1a-104">In some cases, it may be necessary to take extra steps to ensure that the bound properties of the controls remain synchronized with each other and the data source.</span></span> <span data-ttu-id="96b1a-105">Diese Schritte sind in zwei Situationen notwendig:</span><span class="sxs-lookup"><span data-stu-id="96b1a-105">These steps are necessary in two situations:</span></span>  
  
-   <span data-ttu-id="96b1a-106">Wenn die Datenquelle keine implementiert <xref:System.ComponentModel.IBindingList>, und daher generieren <xref:System.ComponentModel.IBindingList.ListChanged> Ereignisse des Typs <xref:System.ComponentModel.ListChangedType.ItemChanged>.</span><span class="sxs-lookup"><span data-stu-id="96b1a-106">If the data source does not implement <xref:System.ComponentModel.IBindingList>, and therefore generate <xref:System.ComponentModel.IBindingList.ListChanged> events of type <xref:System.ComponentModel.ListChangedType.ItemChanged>.</span></span>  
  
-   <span data-ttu-id="96b1a-107">Wenn die Datenquelle implementiert <xref:System.ComponentModel.IEditableObject>.</span><span class="sxs-lookup"><span data-stu-id="96b1a-107">If the data source implements <xref:System.ComponentModel.IEditableObject>.</span></span>  
  
 <span data-ttu-id="96b1a-108">Im ersten Fall können Sie eine <xref:System.Windows.Forms.BindingSource> die Datenquelle an Steuerelemente binden.</span><span class="sxs-lookup"><span data-stu-id="96b1a-108">In the former case, you can use a <xref:System.Windows.Forms.BindingSource> to bind the data source to the controls.</span></span> <span data-ttu-id="96b1a-109">In letzterem Fall verwenden Sie eine <xref:System.Windows.Forms.BindingSource> und behandeln die <xref:System.Windows.Forms.BindingSource.BindingComplete> Ereignis, und rufen <xref:System.Windows.Forms.BindingManagerBase.EndCurrentEdit%2A> auf dem zugeordneten <xref:System.Windows.Forms.BindingManagerBase>.</span><span class="sxs-lookup"><span data-stu-id="96b1a-109">In the latter case, you use a <xref:System.Windows.Forms.BindingSource> and handle the <xref:System.Windows.Forms.BindingSource.BindingComplete> event and call <xref:System.Windows.Forms.BindingManagerBase.EndCurrentEdit%2A> on the associated <xref:System.Windows.Forms.BindingManagerBase>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96b1a-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="96b1a-110">Example</span></span>  
 <span data-ttu-id="96b1a-111">Im folgenden Codebeispiel wird veranschaulicht, wie drei Steuerelemente binden – zwei Textfeld Steuerelemente und ein <xref:System.Windows.Forms.DataGridView> Steuerelement – an derselben Spalte in einer <xref:System.Data.DataSet> mithilfe einer <xref:System.Windows.Forms.BindingSource> Komponente.</span><span class="sxs-lookup"><span data-stu-id="96b1a-111">The following code example demonstrates how to bind three controls—two text-box controls and a <xref:System.Windows.Forms.DataGridView> control—to the same column in a <xref:System.Data.DataSet> using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="96b1a-112">In diesem Beispiel wird veranschaulicht, wie behandelt die <xref:System.Windows.Forms.BindingSource.BindingComplete> Ereignis und sicherstellen, dass, wenn der Textwert, der ein Textfeld geändert wird, wird das zusätzliche Textfeld und die <xref:System.Windows.Forms.DataGridView> Steuerelement mit dem richtigen Wert aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="96b1a-112">This example demonstrates how to handle the <xref:System.Windows.Forms.BindingSource.BindingComplete> event and ensure that when the text value of one text box is changed, the additional text box and the <xref:System.Windows.Forms.DataGridView> control are updated with the correct value.</span></span>  
  
 <span data-ttu-id="96b1a-113">Im Beispiel wird eine <xref:System.Windows.Forms.BindingSource> der Datenquelle und die Steuerelemente binden.</span><span class="sxs-lookup"><span data-stu-id="96b1a-113">The example uses a <xref:System.Windows.Forms.BindingSource> to bind the data source and the controls.</span></span> <span data-ttu-id="96b1a-114">Alternativ können Sie die Steuerelemente direkt an die Datenquelle binden und Abrufen der <xref:System.Windows.Forms.BindingManagerBase> für die Bindung aus des Formulars <xref:System.Windows.Forms.Control.BindingContext%2A> und behandeln Sie anschließend die <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> -Ereignis für die <xref:System.Windows.Forms.BindingManagerBase>.</span><span class="sxs-lookup"><span data-stu-id="96b1a-114">Alternatively, you can bind the controls directly to the data source and retrieve the <xref:System.Windows.Forms.BindingManagerBase> for the binding from the form's <xref:System.Windows.Forms.Control.BindingContext%2A> and then handle the <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> event for the <xref:System.Windows.Forms.BindingManagerBase>.</span></span> <span data-ttu-id="96b1a-115">Ein Beispiel hierzu finden Sie die Hilfeseite zum der <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> -Ereignis <xref:System.Windows.Forms.BindingManagerBase>.</span><span class="sxs-lookup"><span data-stu-id="96b1a-115">For an example of how to do this, see the Help page about the <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> event of <xref:System.Windows.Forms.BindingManagerBase>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleControls#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleControls#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="96b1a-116">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="96b1a-116">Compiling the Code</span></span>  
  
-   <span data-ttu-id="96b1a-117">Dieses Codebeispiel erfordert</span><span class="sxs-lookup"><span data-stu-id="96b1a-117">This code example requires</span></span>  
  
-   <span data-ttu-id="96b1a-118">Verweise auf die Assemblys <xref:System>, <xref:System.Windows.Forms> und <xref:System.Drawing>.</span><span class="sxs-lookup"><span data-stu-id="96b1a-118">References to the <xref:System>, <xref:System.Windows.Forms>, and <xref:System.Drawing> assemblies.</span></span>  
  
-   <span data-ttu-id="96b1a-119">Ein Formular mit der <xref:System.Windows.Forms.Form.Load> Ereignis behandelt und einem Aufruf an die `InitializeControlsAndDataSource` -Methode im Beispiel aus des Formulars <xref:System.Windows.Forms.Form.Load> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="96b1a-119">A form with the <xref:System.Windows.Forms.Form.Load> event handled and a call to the `InitializeControlsAndDataSource` method in the example from the form's <xref:System.Windows.Forms.Form.Load> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96b1a-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96b1a-120">See Also</span></span>  
 [<span data-ttu-id="96b1a-121">Vorgehensweise: Freigeben von gebundenen Daten in Formularen mithilfe der BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="96b1a-121">How to: Share Bound Data Across Forms Using the BindingSource Component</span></span>](../../../docs/framework/winforms/controls/how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)  
 [<span data-ttu-id="96b1a-122">Änderungsbenachrichtigung in der Windows Forms-Datenbindung</span><span class="sxs-lookup"><span data-stu-id="96b1a-122">Change Notification in Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [<span data-ttu-id="96b1a-123">Auf Datenbindung bezogene Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="96b1a-123">Interfaces Related to Data Binding</span></span>](../../../docs/framework/winforms/interfaces-related-to-data-binding.md)  
 [<span data-ttu-id="96b1a-124">Windows Forms-Datenbindung</span><span class="sxs-lookup"><span data-stu-id="96b1a-124">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)

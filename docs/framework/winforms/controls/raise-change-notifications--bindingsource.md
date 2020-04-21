---
title: 'Vorgehensweise: Auslösen von Änderungsbenachrichtigungen mithilfe von BindingSource und der INotifyPropertyChanged-Schnittstelle'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- change notifications [Windows Forms], raising
- BindingSource component [Windows Forms], and IPropertyChange
- data sources [Windows Forms], detecting changes
- examples [Windows Forms], BindingSource component
- change notifications
- INotifyPropertyChanged interface [Windows Forms], using with BindingSource
- BindingSource component [Windows Forms], examples
ms.assetid: 7fa2cf51-c09f-4375-adf0-e36c5617f099
ms.openlocfilehash: 2fe4458aa43144a9c29ed67fd7bee99a37fe1434
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739685"
---
# <a name="how-to-raise-change-notifications-using-a-bindingsource-and-the-inotifypropertychanged-interface"></a><span data-ttu-id="71476-102">Vorgehensweise: Auslösen von Änderungsbenachrichtigungen mithilfe von BindingSource und der INotifyPropertyChanged-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71476-102">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>
<span data-ttu-id="71476-103">Die <xref:System.Windows.Forms.BindingSource> Komponente erkennt automatisch Änderungen in einer Datenquelle, wenn der <xref:System.ComponentModel.INotifyPropertyChanged> in <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> der Datenquelle enthaltene Typ Ereignisse implementiert und auslöst, wenn ein Eigenschaftswert geändert wird.</span><span class="sxs-lookup"><span data-stu-id="71476-103">The <xref:System.Windows.Forms.BindingSource> component automatically detects changes in a data source when the type contained in the data source implements <xref:System.ComponentModel.INotifyPropertyChanged> and raises <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> events when a property value is changed.</span></span> <span data-ttu-id="71476-104">Diese Änderungserkennung ist nützlich, <xref:System.Windows.Forms.BindingSource> da Steuerelemente, die an die automatische Aktualisierung gebunden sind, wenn sich die Datenquellenwerte ändern.</span><span class="sxs-lookup"><span data-stu-id="71476-104">This change detection is useful because controls bound to the <xref:System.Windows.Forms.BindingSource> automatically update as the data source values change.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="71476-105">Wenn die Datenquelle <xref:System.ComponentModel.INotifyPropertyChanged> implementiert, sollten Sie beim Durchführen asynchroner Operationen keine Änderungen an der Datenquelle in einem Hintergrundthread vornehmen.</span><span class="sxs-lookup"><span data-stu-id="71476-105">If your data source implements <xref:System.ComponentModel.INotifyPropertyChanged> and you are performing asynchronous operations, you should not make changes to the data source on a background thread.</span></span> <span data-ttu-id="71476-106">Lesen Sie die Daten stattdessen in einem Hintergrundthread, und führen Sie sie in einer Liste auf dem UI-Thread zusammen.</span><span class="sxs-lookup"><span data-stu-id="71476-106">Instead, you should read the data on a background thread and merge the data into a list on the UI thread.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71476-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="71476-107">Example</span></span>  
 <span data-ttu-id="71476-108">Das folgende Codebeispiel veranschaulicht eine einfache Implementierung der <xref:System.ComponentModel.INotifyPropertyChanged>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="71476-108">The following code example demonstrates a simple implementation of the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="71476-109">Darüber hinaus wird gezeigt, wie <xref:System.Windows.Forms.BindingSource> automatisch eine Datenquellenänderung an ein gebundenes Steuerelement übergibt, wenn <xref:System.Windows.Forms.BindingSource> an eine Liste des <xref:System.ComponentModel.INotifyPropertyChanged>-Typs gebunden ist. </span><span class="sxs-lookup"><span data-stu-id="71476-109">It also shows how the <xref:System.Windows.Forms.BindingSource> automatically passes a data source change to a bound control when the <xref:System.Windows.Forms.BindingSource> is bound to a list of the <xref:System.ComponentModel.INotifyPropertyChanged> type.</span></span>  
  
 <span data-ttu-id="71476-110">Wenn Sie das `CallerMemberName`-Attribut verwenden, müssen Aufrufe der `NotifyPropertyChanged`-Methode den Eigenschaftennamen nicht als Zeichenfolgenargument angeben.</span><span class="sxs-lookup"><span data-stu-id="71476-110">If you use the `CallerMemberName` attribute, calls to the `NotifyPropertyChanged` method don't have to specify the property name as a string argument.</span></span> <span data-ttu-id="71476-111">Weitere Informationen finden Sie unter [Anruferinformationen (C- oder](../../../csharp/language-reference/attributes/caller-information.md) [Anruferinformationen (Visual Basic)](../../../visual-basic/programming-guide/concepts/caller-information.md).</span><span class="sxs-lookup"><span data-stu-id="71476-111">For more information, see [Caller Information (C#)](../../../csharp/language-reference/attributes/caller-information.md) or [Caller Information (Visual Basic)](../../../visual-basic/programming-guide/concepts/caller-information.md).</span></span>  
  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="71476-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="71476-112">Compiling the Code</span></span>  
 <span data-ttu-id="71476-113">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="71476-113">This example requires:</span></span>  
  
- <span data-ttu-id="71476-114">Verweise auf die Assemblys System,Data, System.Drawing und System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="71476-114">References to the System, System.Data, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71476-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71476-115">See also</span></span>

- <xref:System.ComponentModel.INotifyPropertyChanged>
- [<span data-ttu-id="71476-116">BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="71476-116">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="71476-117">Vorgehensweise: Auslösen von Änderungsbenachrichtigungen mithilfe der ResetItem-Methode einer BindingSource</span><span class="sxs-lookup"><span data-stu-id="71476-117">How to: Raise Change Notifications Using the BindingSource ResetItem Method</span></span>](how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)

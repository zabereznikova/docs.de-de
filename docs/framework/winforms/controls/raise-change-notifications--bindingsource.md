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
ms.openlocfilehash: 71fb0a09387c77dbc792180dac1b8594d11b3642
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948043"
---
# <a name="how-to-raise-change-notifications-using-a-bindingsource-and-the-inotifypropertychanged-interface"></a><span data-ttu-id="f32f2-102">Vorgehensweise: Auslösen von Änderungsbenachrichtigungen mithilfe von BindingSource und der INotifyPropertyChanged-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f32f2-102">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>
<span data-ttu-id="f32f2-103">Die <xref:System.Windows.Forms.BindingSource>-Komponente erkennt automatisch Änderungen in einer Datenquelle, wenn der in der Datenquelle enthaltene Typ die <xref:System.ComponentModel.INotifyPropertyChanged>-Schnittstelle implementiert und <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged>-Ereignisse auslöst, sobald ein Eigenschaftswert geändert wird.</span><span class="sxs-lookup"><span data-stu-id="f32f2-103">The <xref:System.Windows.Forms.BindingSource> component will automatically detect changes in a data source when the type contained in the data source implements the <xref:System.ComponentModel.INotifyPropertyChanged> interface and raises <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> events when a property value is changed.</span></span> <span data-ttu-id="f32f2-104">Dies ist nützlich, da an die <xref:System.Windows.Forms.BindingSource> gebundene Steuerelemente automatisch aktualisiert werden, wenn sich die Datenquellenwerte ändern.</span><span class="sxs-lookup"><span data-stu-id="f32f2-104">This is useful because controls bound to the <xref:System.Windows.Forms.BindingSource> will then automatically update as the data source values change.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f32f2-105">Wenn die Datenquelle <xref:System.ComponentModel.INotifyPropertyChanged> implementiert, sollten Sie beim Durchführen asynchroner Operationen keine Änderungen an der Datenquelle in einem Hintergrundthread vornehmen.</span><span class="sxs-lookup"><span data-stu-id="f32f2-105">If your data source implements <xref:System.ComponentModel.INotifyPropertyChanged> and you are performing asynchronous operations, you should not make changes to the data source on a background thread.</span></span> <span data-ttu-id="f32f2-106">Lesen Sie die Daten stattdessen in einem Hintergrundthread, und führen Sie sie in einer Liste auf dem UI-Thread zusammen.</span><span class="sxs-lookup"><span data-stu-id="f32f2-106">Instead, you should read the data on a background thread and merge the data into a list on the UI thread.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f32f2-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f32f2-107">Example</span></span>  
 <span data-ttu-id="f32f2-108">Das folgende Codebeispiel veranschaulicht eine einfache Implementierung der <xref:System.ComponentModel.INotifyPropertyChanged>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="f32f2-108">The following code example demonstrates a simple implementation of the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="f32f2-109">Darüber hinaus wird gezeigt, wie <xref:System.Windows.Forms.BindingSource> automatisch eine Datenquellenänderung an ein gebundenes Steuerelement übergibt, wenn <xref:System.Windows.Forms.BindingSource> an eine Liste des <xref:System.ComponentModel.INotifyPropertyChanged>-Typs gebunden ist. </span><span class="sxs-lookup"><span data-stu-id="f32f2-109">It also shows how the <xref:System.Windows.Forms.BindingSource> automatically passes a data source change to a bound control when the <xref:System.Windows.Forms.BindingSource> is bound to a list of the <xref:System.ComponentModel.INotifyPropertyChanged> type.</span></span>  
  
 <span data-ttu-id="f32f2-110">Wenn Sie das `CallerMemberName`-Attribut verwenden, müssen Aufrufe der `NotifyPropertyChanged`-Methode den Eigenschaftennamen nicht als Zeichenfolgenargument angeben.</span><span class="sxs-lookup"><span data-stu-id="f32f2-110">If you use the `CallerMemberName` attribute, calls to the `NotifyPropertyChanged` method don't have to specify the property name as a string argument.</span></span> <span data-ttu-id="f32f2-111">Weitere Informationen finden Sie unter [Caller Information (C#)](../../../csharp/programming-guide/concepts/caller-information.md) oder [Aufruferinformationen (Visual Basic)](../../../visual-basic/programming-guide/concepts/caller-information.md).</span><span class="sxs-lookup"><span data-stu-id="f32f2-111">For more information, see [Caller Information (C#)](../../../csharp/programming-guide/concepts/caller-information.md) or [Caller Information (Visual Basic)](../../../visual-basic/programming-guide/concepts/caller-information.md).</span></span>  
  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f32f2-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="f32f2-112">Compiling the Code</span></span>  
 <span data-ttu-id="f32f2-113">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f32f2-113">This example requires:</span></span>  
  
- <span data-ttu-id="f32f2-114">Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="f32f2-114">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="f32f2-115">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="f32f2-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="f32f2-116">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="f32f2-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span> <span data-ttu-id="f32f2-117">Weitere Informationen hierzu finden Sie auch unter [Gewusst wie: Kompilieren und Ausführen einer vollständigen Windows Forms-Codebeispiels mit Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb129228(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f32f2-117">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb129228(v=vs.100)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f32f2-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f32f2-118">See also</span></span>

- <xref:System.ComponentModel.INotifyPropertyChanged>
- [<span data-ttu-id="f32f2-119">BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="f32f2-119">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="f32f2-120">Vorgehensweise: Auslösen von Änderungsbenachrichtigungen mithilfe der BindingSource ResetItem-Methode</span><span class="sxs-lookup"><span data-stu-id="f32f2-120">How to: Raise Change Notifications Using the BindingSource ResetItem Method</span></span>](how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)

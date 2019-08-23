---
title: 'Vorgehensweise: Anpassen der Hinzufügung von Elementen mithilfe der BindingSource in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], creating new items
- BindingSource component [Windows Forms], customizing item addition with
- examples [Windows Forms], BindingSource component
- BindingSource component [Windows Forms], examples
ms.assetid: 1aae11fc-6fb2-4cb9-b3d0-e0638fe77ef0
ms.openlocfilehash: 59522791408eb9c8cabf97a62be2049aeb17f864
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935352"
---
# <a name="how-to-customize-item-addition-with-the-windows-forms-bindingsource"></a><span data-ttu-id="fd766-102">Vorgehensweise: Anpassen der Hinzufügung von Elementen mithilfe der BindingSource in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fd766-102">How to: Customize Item Addition with the Windows Forms BindingSource</span></span>
<span data-ttu-id="fd766-103">Wenn Sie eine <xref:System.Windows.Forms.BindingSource> -Komponente zum Binden eines Windows Forms-Steuerelements an eine Datenquelle verwenden, kann es ggf. erforderlich sein, die Erstellung neuer Elemente anzupassen.</span><span class="sxs-lookup"><span data-stu-id="fd766-103">When you use a <xref:System.Windows.Forms.BindingSource> component to bind a Windows Forms control to a data source, you may find it necessary to customize the creation of new items.</span></span> <span data-ttu-id="fd766-104">Die <xref:System.Windows.Forms.BindingSource> -Komponente vereinfacht dies durch die Bereitstellung des <xref:System.Windows.Forms.BindingSource.AddingNew> -Ereignisses, das in der Regel ausgelöst wird, wenn das gebundene Steuerelement ein neues Element erstellen muss.</span><span class="sxs-lookup"><span data-stu-id="fd766-104">The <xref:System.Windows.Forms.BindingSource> component makes this straightforward by providing the <xref:System.Windows.Forms.BindingSource.AddingNew> event, which is typically raised when the bound control needs to create a new item.</span></span> <span data-ttu-id="fd766-105">Ihr Ereignishandler kann jedes erforderliche benutzerdefinierte Verhalten (z. B. das Aufrufen einer Methode für einen Webdienst oder das Abrufen eines neuen Objekts aus einer Klassenfactory) bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="fd766-105">Your event handler can provide whatever custom behavior is required (for example, calling a method on a Web service or getting a new object from a class factory).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fd766-106">Wenn ein Element durch Verarbeiten des <xref:System.Windows.Forms.BindingSource.AddingNew> -Ereignisses hinzugefügt wird, kann die Hinzufügung nicht abgebrochen werden.</span><span class="sxs-lookup"><span data-stu-id="fd766-106">When an item is added by handling the <xref:System.Windows.Forms.BindingSource.AddingNew> event, the addition cannot be canceled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd766-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fd766-107">Example</span></span>  
 <span data-ttu-id="fd766-108">Das folgende Beispiel zeigt, wie ein <xref:System.Windows.Forms.DataGridView> -Steuerelement mithilfe einer <xref:System.Windows.Forms.BindingSource> -Komponente an eine Klassenfactory gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="fd766-108">The following example demonstrates how to bind a <xref:System.Windows.Forms.DataGridView> control to a class factory by using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="fd766-109">Wenn der Benutzer auf die neue Zeile des <xref:System.Windows.Forms.DataGridView> -Steuerelements klickt, wird das <xref:System.Windows.Forms.BindingSource.AddingNew> -Ereignis ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="fd766-109">When the user clicks the <xref:System.Windows.Forms.DataGridView> control's new row, the <xref:System.Windows.Forms.BindingSource.AddingNew> event is raised.</span></span> <span data-ttu-id="fd766-110">Der Ereignishandler erstellt ein neues `DemoCustomer`-Objekt, das der Eigenschaft <xref:System.ComponentModel.AddingNewEventArgs.NewObject%2A?displayProperty=nameWithType> zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="fd766-110">The event handler creates a new `DemoCustomer` object, which is assigned to the <xref:System.ComponentModel.AddingNewEventArgs.NewObject%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="fd766-111">Dies bewirkt, dass das neue `DemoCustomer` -Objekt der Liste der <xref:System.Windows.Forms.BindingSource> -Komponente hinzugefügt und in der neuen Zeile des <xref:System.Windows.Forms.DataGridView> -Steuerelements angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="fd766-111">This causes the new `DemoCustomer` object to be added to the <xref:System.Windows.Forms.BindingSource> component's list and to be displayed in the new row of the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.AddingNew#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.AddingNew#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.AddingNew#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fd766-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="fd766-112">Compiling the Code</span></span>  
 <span data-ttu-id="fd766-113">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="fd766-113">This example requires:</span></span>  
  
- <span data-ttu-id="fd766-114">Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="fd766-114">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd766-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd766-115">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="fd766-116">BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="fd766-116">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="fd766-117">Vorgehensweise: Binden eines Windows Forms-Steuer Elements an einen Typ</span><span class="sxs-lookup"><span data-stu-id="fd766-117">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)

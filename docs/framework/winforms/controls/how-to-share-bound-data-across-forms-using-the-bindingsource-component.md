---
title: 'Vorgehensweise: Freigeben von gebundenen Daten in Formularen mithilfe der BindingSource-Komponente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], BindingSource component
- data binding [Windows Forms], sharing data across forms
- BindingSource component [Windows Forms], examples
- BindingSource [Windows Forms], using with multiple forms
ms.assetid: a1a49630-db9c-4485-b888-1f62a373a4f7
ms.openlocfilehash: aa497194fd4ac65f48773a45175333a1d862b453
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956073"
---
# <a name="how-to-share-bound-data-across-forms-using-the-bindingsource-component"></a><span data-ttu-id="4f0dc-102">Vorgehensweise: Freigeben von gebundenen Daten in Formularen mithilfe der BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="4f0dc-102">How to: Share Bound Data Across Forms Using the BindingSource Component</span></span>
<span data-ttu-id="4f0dc-103">Sie können Daten einfach in mehreren Formularen gemeinsam nutzen (freigeben), indem Sie die <xref:System.Windows.Forms.BindingSource>-Komponente verwenden.</span><span class="sxs-lookup"><span data-stu-id="4f0dc-103">You can easily share data across forms using the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="4f0dc-104">Beispielsweise könnte es sein, dass Sie ein schreibgeschütztes Formular, in dem die Datenquellendaten zusammengefasst werden, sowie ein bearbeitbares Formular anzeigen möchten, das detaillierte Informationen über das Element enthält, das momentan in der Datenquelle ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="4f0dc-104">For example, you may want to display one read-only form that summarizes the data-source data and another editable form that contains detailed information about the currently selected item in the data source.</span></span> <span data-ttu-id="4f0dc-105">In diesem Beispiel wird dieses Szenario veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="4f0dc-105">This example demonstrates this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f0dc-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4f0dc-106">Example</span></span>  
 <span data-ttu-id="4f0dc-107">Im folgenden Codebeispiel wird veranschaulicht, wie eine <xref:System.Windows.Forms.BindingSource> und die an sie gebundenen Daten in mehreren Formularen gemeinsam genutzt werden können.</span><span class="sxs-lookup"><span data-stu-id="4f0dc-107">The following code example demonstrates how to share a <xref:System.Windows.Forms.BindingSource> and its bound data across forms.</span></span> <span data-ttu-id="4f0dc-108">In diesem Beispiel wird die gemeinsam genutzte <xref:System.Windows.Forms.BindingSource> an den Konstruktor des untergeordneten Formulars übergeben.</span><span class="sxs-lookup"><span data-stu-id="4f0dc-108">In this example, the shared <xref:System.Windows.Forms.BindingSource> is passed to the constructor of the child form.</span></span> <span data-ttu-id="4f0dc-109">Das untergeordnete Formular ermöglicht es dem Benutzer, die Daten für das aktuell ausgewählte Element im Hauptformular zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="4f0dc-109">The child form allows the user to edit the data for the currently selected item in the main form.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4f0dc-110">Das <xref:System.Windows.Forms.BindingSource.BindingComplete>-Ereignis für die <xref:System.Windows.Forms.BindingSource>-Komponente wird in diesem Beispiel, um sicherzustellen, dass die beiden Formulare synchronisiert bleiben.</span><span class="sxs-lookup"><span data-stu-id="4f0dc-110">The <xref:System.Windows.Forms.BindingSource.BindingComplete> event for the <xref:System.Windows.Forms.BindingSource> component is handled in the example to ensure that the two forms remain synchronized.</span></span> <span data-ttu-id="4f0dc-111">Weitere Informationen dazu, warum dies geschieht, finden [Sie unter Vorgehensweise: Stellen Sie sicher, dass mehrere an dieselbe Datenquelle gebundene](../multiple-controls-bound-to-data-source-synchronized.md)Steuerelemente synchronisiert bleiben.</span><span class="sxs-lookup"><span data-stu-id="4f0dc-111">For more information about why this is done, see [How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized](../multiple-controls-bound-to-data-source-synchronized.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleForms#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleForms#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4f0dc-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="4f0dc-112">Compiling the Code</span></span>  
 <span data-ttu-id="4f0dc-113">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="4f0dc-113">This example requires:</span></span>  
  
- <span data-ttu-id="4f0dc-114">Verweise auf die Assemblys "System", "System.Windows.Forms", "System.Drawing", "System.Data" und "System.Xml".</span><span class="sxs-lookup"><span data-stu-id="4f0dc-114">References to the System, System.Windows.Forms, System.Drawing, System.Data, and System.Xml assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f0dc-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f0dc-115">See also</span></span>

- [<span data-ttu-id="4f0dc-116">BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="4f0dc-116">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="4f0dc-117">Windows Forms-Datenbindung</span><span class="sxs-lookup"><span data-stu-id="4f0dc-117">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="4f0dc-118">Vorgehensweise: Behandeln von Fehlern und Ausnahmen, die beim DataBinding auftreten</span><span class="sxs-lookup"><span data-stu-id="4f0dc-118">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)

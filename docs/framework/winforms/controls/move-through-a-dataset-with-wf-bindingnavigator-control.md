---
title: Durchlaufen eines Datasets mit BindingNavigator-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- datasets [Windows Forms], moving through
- BindingNavigator control [Windows Forms], moving through datasets
- examples [Windows Forms], BindingNavigator control
ms.assetid: 146d97be-3d97-400e-accb-860bbf47729d
ms.openlocfilehash: 73a102da74a3a2a00b5042331cffcaf3d858ea5b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742153"
---
# <a name="how-to-move-through-a-dataset-with-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="7d55c-102">Gewusst wie: Navigieren durch ein "DataSet" mithilfe des BindingNavigator-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7d55c-102">How to: Move Through a DataSet with the Windows Forms BindingNavigator Control</span></span>
<span data-ttu-id="7d55c-103">Wenn Sie datengesteuerte Anwendungen erstellen, müssen Sie oft Auflistungen von Daten für Benutzer anzeigen.</span><span class="sxs-lookup"><span data-stu-id="7d55c-103">As you build data-driven applications, you will often need to display collections of data to users.</span></span> <span data-ttu-id="7d55c-104">Das <xref:System.Windows.Forms.BindingNavigator>-Steuerelement in Verbindung mit der <xref:System.Windows.Forms.BindingSource>-Komponente stellt eine bequeme und erweiterbare Lösung bereit, um eine Auflistung zu durchlaufen und Elemente nacheinander anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7d55c-104">The <xref:System.Windows.Forms.BindingNavigator> control, in conjunction with the <xref:System.Windows.Forms.BindingSource> component, provides a convenient and extensible solution for moving through a collection and displaying items sequentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d55c-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7d55c-105">Example</span></span>  
 <span data-ttu-id="7d55c-106">Im folgenden Codebeispiel wird veranschaulicht, wie Sie ein <xref:System.Windows.Forms.BindingNavigator>-Steuerelement verwenden, um Daten zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="7d55c-106">The following code example demonstrates how to use a <xref:System.Windows.Forms.BindingNavigator> control to move through data.</span></span> <span data-ttu-id="7d55c-107">Das Dataset befindet sich in <xref:System.Data.DataView>, die an ein <xref:System.Windows.Forms.TextBox>-Steuerelement mit einer <xref:System.Windows.Forms.BindingSource>-Komponente gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="7d55c-107">The set is contained in a <xref:System.Data.DataView>, which is bound to a <xref:System.Windows.Forms.TextBox> control with a <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7d55c-108">Das Speichern vertraulicher Informationen (z. B. eines Kennworts) innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="7d55c-108">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="7d55c-109">Der Zugriff auf eine Datenbank lässt sich mithilfe der Windows-Authentifizierung (wird auch als integrierte Sicherheit bezeichnet) sicherer steuern.</span><span class="sxs-lookup"><span data-stu-id="7d55c-109">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="7d55c-110">Weitere Informationen finden Sie unter [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="7d55c-110">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataNavigator#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataNavigator#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7d55c-111">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="7d55c-111">Compiling the Code</span></span>  
 <span data-ttu-id="7d55c-112">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="7d55c-112">This example requires:</span></span>  
  
- <span data-ttu-id="7d55c-113">Verweise auf die Assemblys "System", "System.Data", "System.Drawing", "System.Windows.Forms" und "System.Xml".</span><span class="sxs-lookup"><span data-stu-id="7d55c-113">References to the System, System.Data, System.Drawing, System.Windows.Forms and System.Xml assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d55c-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d55c-114">See also</span></span>

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="7d55c-115">BindingNavigator-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7d55c-115">BindingNavigator Control</span></span>](bindingnavigator-control-windows-forms.md)
- [<span data-ttu-id="7d55c-116">BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="7d55c-116">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="7d55c-117">Vorgehensweise: Binden eines Windows Forms-Steuerelements an einen Typ</span><span class="sxs-lookup"><span data-stu-id="7d55c-117">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)

---
title: 'Vorgehensweise: Navigieren Sie durch ein DataSet mit dem BindingNavigator-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- datasets [Windows Forms], moving through
- BindingNavigator control [Windows Forms], moving through datasets
- examples [Windows Forms], BindingNavigator control
ms.assetid: 146d97be-3d97-400e-accb-860bbf47729d
ms.openlocfilehash: d8db965993e82040cfe88c22aaabfaed21462a40
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709752"
---
# <a name="how-to-move-through-a-dataset-with-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="d7169-102">Vorgehensweise: Navigieren Sie durch ein DataSet mit dem BindingNavigator-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d7169-102">How to: Move Through a DataSet with the Windows Forms BindingNavigator Control</span></span>
<span data-ttu-id="d7169-103">Wenn Sie datengesteuerte Anwendungen erstellen, müssen Sie oft Auflistungen von Daten für Benutzer anzeigen.</span><span class="sxs-lookup"><span data-stu-id="d7169-103">As you build data-driven applications, you will often need to display collections of data to users.</span></span> <span data-ttu-id="d7169-104">Das <xref:System.Windows.Forms.BindingNavigator>-Steuerelement in Verbindung mit der <xref:System.Windows.Forms.BindingSource>-Komponente stellt eine bequeme und erweiterbare Lösung bereit, um eine Auflistung zu durchlaufen und Elemente nacheinander anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d7169-104">The <xref:System.Windows.Forms.BindingNavigator> control, in conjunction with the <xref:System.Windows.Forms.BindingSource> component, provides a convenient and extensible solution for moving through a collection and displaying items sequentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7169-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d7169-105">Example</span></span>  
 <span data-ttu-id="d7169-106">Im folgenden Codebeispiel wird veranschaulicht, wie Sie ein <xref:System.Windows.Forms.BindingNavigator>-Steuerelement verwenden, um Daten zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="d7169-106">The following code example demonstrates how to use a <xref:System.Windows.Forms.BindingNavigator> control to move through data.</span></span> <span data-ttu-id="d7169-107">Das Dataset befindet sich in <xref:System.Data.DataView>, die an ein <xref:System.Windows.Forms.TextBox>-Steuerelement mit einer <xref:System.Windows.Forms.BindingSource>-Komponente gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="d7169-107">The set is contained in a <xref:System.Data.DataView>, which is bound to a <xref:System.Windows.Forms.TextBox> control with a <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7169-108">Das Speichern vertraulicher Informationen (z. B. eines Kennworts) innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="d7169-108">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="d7169-109">Der Zugriff auf eine Datenbank lässt sich mithilfe der Windows-Authentifizierung (wird auch als integrierte Sicherheit bezeichnet) sicherer steuern.</span><span class="sxs-lookup"><span data-stu-id="d7169-109">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="d7169-110">Weitere Informationen finden Sie unter [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="d7169-110">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataNavigator#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataNavigator#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d7169-111">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="d7169-111">Compiling the Code</span></span>  
 <span data-ttu-id="d7169-112">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d7169-112">This example requires:</span></span>  
  
-   <span data-ttu-id="d7169-113">Verweise auf die Assemblys "System", "System.Data", "System.Drawing", "System.Windows.Forms" und "System.Xml".</span><span class="sxs-lookup"><span data-stu-id="d7169-113">References to the System, System.Data, System.Drawing, System.Windows.Forms and System.Xml assemblies.</span></span>  
  
 <span data-ttu-id="d7169-114">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="d7169-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="d7169-115">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="d7169-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7169-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7169-116">See also</span></span>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="d7169-117">BindingNavigator-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="d7169-117">BindingNavigator Control</span></span>](bindingnavigator-control-windows-forms.md)
- [<span data-ttu-id="d7169-118">BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="d7169-118">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="d7169-119">Vorgehensweise: Binden eines Windows Forms-Steuerelements an einen Typ</span><span class="sxs-lookup"><span data-stu-id="d7169-119">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)

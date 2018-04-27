---
title: 'Gewusst wie: Binden eines Windows Forms-Steuerelements an einen Typ'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 94faeebb-d2bc-45d6-86d7-96a42661b43d
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a1782d7af7dc7155834926f4b94cf57adf6c4d53
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type"></a><span data-ttu-id="4d91a-102">Gewusst wie: Binden eines Windows Forms-Steuerelements an einen Typ</span><span class="sxs-lookup"><span data-stu-id="4d91a-102">How to: Bind a Windows Forms Control to a Type</span></span>
<span data-ttu-id="4d91a-103">Beim Erstellen von Steuerelementen, die mit Daten interagieren, ist es manchmal erforderlich, ein Steuerelement an einen Typ statt an ein Objekt zu binden.</span><span class="sxs-lookup"><span data-stu-id="4d91a-103">When you are building controls that interact with data, you will sometimes find it necessary to bind a control to a type, rather than an object.</span></span> <span data-ttu-id="4d91a-104">Diese Situation tritt vor allem zur Entwurfszeit auf, wenn Daten möglicherweise nicht verfügbar sind, aber die datengebundenen Steuerelemente dennoch Informationen von der öffentlichen Schnittstelle eines Typs anzeigen müssen.</span><span class="sxs-lookup"><span data-stu-id="4d91a-104">This situation arises especially at design time, when data may not be available, but your data-bound controls still need to display information from a type's public interface.</span></span> <span data-ttu-id="4d91a-105">Sie können beispielsweise ein <xref:System.Windows.Forms.DataGridView>-Steuerelement an ein von einem Webdienst bereitgestelltes Objekt binden, und dafür sorgen, dass das <xref:System.Windows.Forms.DataGridView>-Steuerelement zur Entwurfszeit die zugehörigen Spalten mit den Membernamen eines benutzerdefinierten Typs beschriftet.</span><span class="sxs-lookup"><span data-stu-id="4d91a-105">For example, you may bind a <xref:System.Windows.Forms.DataGridView> control to an object exposed by a Web service and want the <xref:System.Windows.Forms.DataGridView> control to label its columns at design time with the member names of a custom type.</span></span>  
  
 <span data-ttu-id="4d91a-106">Mit der <xref:System.Windows.Forms.BindingSource>-Komponente können Sie ein Steuerelement problemlos an einen Typ binden.</span><span class="sxs-lookup"><span data-stu-id="4d91a-106">You can easily bind a control to a type with the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d91a-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4d91a-107">Example</span></span>  
 <span data-ttu-id="4d91a-108">Im folgenden Codebeispiel wird veranschaulicht, wie ein <xref:System.Windows.Forms.DataGridView>-Steuerelement mithilfe einer <xref:System.Windows.Forms.BindingSource>-Komponente an einen benutzerdefinierten Typ gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="4d91a-108">The following code example demonstrates how to bind a <xref:System.Windows.Forms.DataGridView> control to a custom type by using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="4d91a-109">Beim Ausführen des Beispiels werden Sie feststellen, dass <xref:System.Windows.Forms.DataGridView> die Spalten, die die Eigenschaften eines `Customer`-Objekts darstellen, beschriftet hat, bevor das Steuerelement mit Daten gefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="4d91a-109">When you run the example, you'll notice the <xref:System.Windows.Forms.DataGridView> has labeled columns that reflect the properties of a `Customer` object, before the control is populated with data.</span></span> <span data-ttu-id="4d91a-110">In dem Beispiel ist eine Schaltfläche "Add Customer" enthalten, mit der dem <xref:System.Windows.Forms.DataGridView>-Steuerelement Daten hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="4d91a-110">The example has an Add Customer button to add data to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="4d91a-111">Wenn Sie auf die Schaltfläche klicken, wird <xref:System.Windows.Forms.BindingSource> ein neues `Customer`-Objekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4d91a-111">When you click the button, a new `Customer` object is added to the <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="4d91a-112">In einem realen Szenario könnten die Daten durch den Aufruf eines Webdiensts oder einer anderen Datenquelle abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="4d91a-112">In a real-world scenario, the data might be obtained by a call to a Web service or other data source.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnector.BindingToType#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindingToType#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4d91a-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="4d91a-113">Compiling the Code</span></span>  
 <span data-ttu-id="4d91a-114">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="4d91a-114">This example requires:</span></span>  
  
-   <span data-ttu-id="4d91a-115">Verweise auf die Assemblys "System" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="4d91a-115">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="4d91a-116">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="4d91a-116">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="4d91a-117">Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="4d91a-117">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="4d91a-118">Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="4d91a-118">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d91a-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d91a-119">See Also</span></span>  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="4d91a-120">BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="4d91a-120">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)

---
title: 'Gewusst wie: Verwenden von Modifizierern und GenerateMember-Eigenschaften'
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
f1_keywords:
- Designer_GenerateMember
- Designer_Modifiers
helpviewer_keywords:
- base forms
- inheritance [Windows Forms], forms
- inherited forms [Windows Forms], Windows Forms
- inherited forms
- form inheritance
- Windows Forms, inheritance
ms.assetid: 3381a5e4-e1a3-44e2-a765-a0b758937b85
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f11595daac74ceb76c5d017af015d5523506bdf3
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-use-the-modifiers-and-generatemember-properties"></a><span data-ttu-id="f726d-102">Gewusst wie: Verwenden von Modifizierern und GenerateMember-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f726d-102">How to: Use the Modifiers and GenerateMember Properties</span></span>
<span data-ttu-id="f726d-103">Wenn Sie eine Komponente in einem Windows Form platzieren, werden zwei Eigenschaften von der entwurfsumgebung bereitgestellt: `GenerateMember` und `Modifiers`.</span><span class="sxs-lookup"><span data-stu-id="f726d-103">When you place a component on a Windows Form, two properties are provided by the design environment: `GenerateMember` and `Modifiers`.</span></span> <span data-ttu-id="f726d-104">Die `GenerateMember` Eigenschaft gibt an, wann eine Membervariable für eine Komponente von Windows Forms-Designer generiert.</span><span class="sxs-lookup"><span data-stu-id="f726d-104">The `GenerateMember` property specifies when the Windows Forms Designer generates a member variable for a component.</span></span> <span data-ttu-id="f726d-105">Die `Modifiers` Eigenschaft ist für den Zugriffsmodifizierer auf diese Membervariable zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="f726d-105">The `Modifiers` property is the access modifier assigned to that member variable.</span></span> <span data-ttu-id="f726d-106">Wenn der Wert von der `GenerateMember` Eigenschaft ist `false`, den Wert des der `Modifiers` Eigenschaft hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="f726d-106">If the value of the `GenerateMember` property is `false`, the value of the `Modifiers` property has no effect.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f726d-107">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="f726d-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f726d-108">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f726d-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f726d-109">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="f726d-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-specify-whether-a-component-is-a-member-of-the-form"></a><span data-ttu-id="f726d-110">Um anzugeben, ob eine Komponente des Formulars angehört</span><span class="sxs-lookup"><span data-stu-id="f726d-110">To specify whether a component is a member of the form</span></span>  
  
1.  <span data-ttu-id="f726d-111">Öffnen Sie in Windows Forms-Designer das Formular aus.</span><span class="sxs-lookup"><span data-stu-id="f726d-111">In the Windows Forms Designer, open your form.</span></span>  
  
2.  <span data-ttu-id="f726d-112">Öffnen der **Toolbox**, und platzieren Sie auf dem Formular drei <xref:System.Windows.Forms.Button> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="f726d-112">Open the **Toolbox**, and on the form, place three <xref:System.Windows.Forms.Button> controls.</span></span>  
  
3.  <span data-ttu-id="f726d-113">Legen Sie die `GenerateMember` und `Modifiers` Eigenschaften für die einzelnen <xref:System.Windows.Forms.Button> Steuerelement entsprechend der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="f726d-113">Set the `GenerateMember` and `Modifiers` properties for each <xref:System.Windows.Forms.Button> control according to the following table.</span></span>  
  
    |<span data-ttu-id="f726d-114">Schaltflächenname</span><span class="sxs-lookup"><span data-stu-id="f726d-114">Button name</span></span>|<span data-ttu-id="f726d-115">GenerateMember-Wert</span><span class="sxs-lookup"><span data-stu-id="f726d-115">GenerateMember value</span></span>|<span data-ttu-id="f726d-116">Modifizierer Wert</span><span class="sxs-lookup"><span data-stu-id="f726d-116">Modifiers value</span></span>|  
    |-----------------|--------------------------|---------------------|  
    |`button1`|`true`|`private`|  
    |`button2`|`true`|`protected`|  
    |`button3`|`false`|<span data-ttu-id="f726d-117">Keine Änderung</span><span class="sxs-lookup"><span data-stu-id="f726d-117">No change</span></span>|  
  
4.  <span data-ttu-id="f726d-118">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="f726d-118">Build the solution.</span></span>  
  
5.  <span data-ttu-id="f726d-119">Klicken Sie im **Projektmappen-Explorer** auf die Schaltfläche **Alle Dateien anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="f726d-119">In **Solution Explorer**, click the **Show All Files** button.</span></span>  
  
6.  <span data-ttu-id="f726d-120">Öffnen Sie die **Form1** Knoten, und klicken Sie in der **Code-Editor**öffnen die **Form1.Designer.vb** oder **Form1.Designer.cs** Datei.</span><span class="sxs-lookup"><span data-stu-id="f726d-120">Open the **Form1** node, and in the **Code Editor**,open the **Form1.Designer.vb** or **Form1.Designer.cs** file.</span></span> <span data-ttu-id="f726d-121">Diese Datei enthält den Code ausgegeben, die für Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="f726d-121">This file contains the code emitted by the Windows Forms Designer.</span></span>  
  
7.  <span data-ttu-id="f726d-122">Suchen Sie die Deklarationen für die drei Schaltflächen.</span><span class="sxs-lookup"><span data-stu-id="f726d-122">Find the declarations for the three buttons.</span></span> <span data-ttu-id="f726d-123">Das folgende Codebeispiel zeigt die Unterschiede, die gemäß der `GenerateMember` und `Modifiers` Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="f726d-123">The following code example shows the differences specified by the `GenerateMember` and `Modifiers` properties.</span></span>  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]  
  
> [!NOTE]
>  <span data-ttu-id="f726d-124">Windows Forms-Designer weist standardmäßig den `private` (`Friend` in Visual Basic) Modifizierer Containersteuerelementen wie <xref:System.Windows.Forms.Panel>.</span><span class="sxs-lookup"><span data-stu-id="f726d-124">By default, the Windows Forms Designer assigns the `private` (`Friend` in Visual Basic) modifier to container controls like <xref:System.Windows.Forms.Panel>.</span></span> <span data-ttu-id="f726d-125">Wenn Ihre Basis <xref:System.Windows.Forms.UserControl> oder <xref:System.Windows.Forms.Form> ist ein Container-Steuerelement akzeptiert keine neuen untergeordneten Elemente in geerbte Steuerelemente und Formulare.</span><span class="sxs-lookup"><span data-stu-id="f726d-125">If your base <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Form> has a container control, it will not accept new children in inherited controls and forms.</span></span> <span data-ttu-id="f726d-126">Die Lösung besteht darin, den Modifizierer des Steuerelements basiscontainerobjekts ändern `protected` oder `public`.</span><span class="sxs-lookup"><span data-stu-id="f726d-126">The solution is to change the modifier of the base container control to `protected` or `public`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f726d-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f726d-127">See Also</span></span>  
 <xref:System.Windows.Forms.Button>  
 [<span data-ttu-id="f726d-128">Visuelle Vererbung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f726d-128">Windows Forms Visual Inheritance</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)  
 [<span data-ttu-id="f726d-129">Exemplarische Vorgehensweise: Demonstrieren der visuellen Vererbung</span><span class="sxs-lookup"><span data-stu-id="f726d-129">Walkthrough: Demonstrating Visual Inheritance</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-demonstrating-visual-inheritance.md)  
 [<span data-ttu-id="f726d-130">Vorgehensweise: Erben von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f726d-130">How to: Inherit Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)

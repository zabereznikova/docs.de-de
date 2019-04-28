---
title: 'Vorgehensweise: Verwenden von Modifizierern und GenerateMember-Eigenschaften'
ms.date: 03/30/2017
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
ms.openlocfilehash: 6194ef288bd43267c2b00fa6d7c6250e90b37c75
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778858"
---
# <a name="how-to-use-the-modifiers-and-generatemember-properties"></a><span data-ttu-id="6da98-102">Vorgehensweise: Verwenden von Modifizierern und GenerateMember-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="6da98-102">How to: Use the Modifiers and GenerateMember Properties</span></span>
<span data-ttu-id="6da98-103">Wenn Sie eine Komponente in einem Windows-Formular platzieren, werden zwei Eigenschaften von der entwurfsumgebung bereitgestellt: `GenerateMember` und `Modifiers`.</span><span class="sxs-lookup"><span data-stu-id="6da98-103">When you place a component on a Windows Form, two properties are provided by the design environment: `GenerateMember` and `Modifiers`.</span></span> <span data-ttu-id="6da98-104">Die `GenerateMember` Eigenschaft gibt an, wenn der Windows Forms-Designer eine Membervariable für eine Komponente generiert.</span><span class="sxs-lookup"><span data-stu-id="6da98-104">The `GenerateMember` property specifies when the Windows Forms Designer generates a member variable for a component.</span></span> <span data-ttu-id="6da98-105">Die `Modifiers` Eigenschaft wird der Zugriffsmodifizierer, die auf diese Membervariable zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="6da98-105">The `Modifiers` property is the access modifier assigned to that member variable.</span></span> <span data-ttu-id="6da98-106">Wenn der Wert des der `GenerateMember` Eigenschaft `false`, den Wert des der `Modifiers` Eigenschaft hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="6da98-106">If the value of the `GenerateMember` property is `false`, the value of the `Modifiers` property has no effect.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6da98-107">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="6da98-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="6da98-108">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="6da98-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="6da98-109">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="6da98-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-specify-whether-a-component-is-a-member-of-the-form"></a><span data-ttu-id="6da98-110">Um anzugeben, ob eine Komponente des Formulars angehört</span><span class="sxs-lookup"><span data-stu-id="6da98-110">To specify whether a component is a member of the form</span></span>  
  
1. <span data-ttu-id="6da98-111">Öffnen Sie im Windows Forms-Designer das Formular ein.</span><span class="sxs-lookup"><span data-stu-id="6da98-111">In the Windows Forms Designer, open your form.</span></span>  
  
2. <span data-ttu-id="6da98-112">Öffnen der **Toolbox**, und klicken Sie im Formular platzieren drei <xref:System.Windows.Forms.Button> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="6da98-112">Open the **Toolbox**, and on the form, place three <xref:System.Windows.Forms.Button> controls.</span></span>  
  
3. <span data-ttu-id="6da98-113">Legen Sie die `GenerateMember` und `Modifiers` Eigenschaften für jede <xref:System.Windows.Forms.Button> Steuerelement gemäß der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="6da98-113">Set the `GenerateMember` and `Modifiers` properties for each <xref:System.Windows.Forms.Button> control according to the following table.</span></span>  
  
    |<span data-ttu-id="6da98-114">Schaltflächenname</span><span class="sxs-lookup"><span data-stu-id="6da98-114">Button name</span></span>|<span data-ttu-id="6da98-115">GenerateMember-Wert</span><span class="sxs-lookup"><span data-stu-id="6da98-115">GenerateMember value</span></span>|<span data-ttu-id="6da98-116">Modifizierer Wert</span><span class="sxs-lookup"><span data-stu-id="6da98-116">Modifiers value</span></span>|  
    |-----------------|--------------------------|---------------------|  
    |`button1`|`true`|`private`|  
    |`button2`|`true`|`protected`|  
    |`button3`|`false`|<span data-ttu-id="6da98-117">Keine Änderung</span><span class="sxs-lookup"><span data-stu-id="6da98-117">No change</span></span>|  
  
4. <span data-ttu-id="6da98-118">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="6da98-118">Build the solution.</span></span>  
  
5. <span data-ttu-id="6da98-119">Klicken Sie im **Projektmappen-Explorer** auf die Schaltfläche **Alle Dateien anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="6da98-119">In **Solution Explorer**, click the **Show All Files** button.</span></span>  
  
6. <span data-ttu-id="6da98-120">Öffnen Sie die **Form1** Knoten, und klicken Sie in der **Code-Editor**öffnen die **Form1.Designer.vb** oder **Form1.Designer.cs** Datei.</span><span class="sxs-lookup"><span data-stu-id="6da98-120">Open the **Form1** node, and in the **Code Editor**,open the **Form1.Designer.vb** or **Form1.Designer.cs** file.</span></span> <span data-ttu-id="6da98-121">Diese Datei enthält den Code ausgegeben, die vom Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="6da98-121">This file contains the code emitted by the Windows Forms Designer.</span></span>  
  
7. <span data-ttu-id="6da98-122">Suchen Sie die Deklarationen für die drei Schaltflächen.</span><span class="sxs-lookup"><span data-stu-id="6da98-122">Find the declarations for the three buttons.</span></span> <span data-ttu-id="6da98-123">Das folgende Codebeispiel zeigt die Unterschiede, die gemäß der `GenerateMember` und `Modifiers` Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="6da98-123">The following code example shows the differences specified by the `GenerateMember` and `Modifiers` properties.</span></span>  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]  
  
> [!NOTE]
>  <span data-ttu-id="6da98-124">Standardmäßig wird in der Windows Forms-Designer die `private` (`Friend` in Visual Basic) Modifizierer Containersteuerelementen wie <xref:System.Windows.Forms.Panel>.</span><span class="sxs-lookup"><span data-stu-id="6da98-124">By default, the Windows Forms Designer assigns the `private` (`Friend` in Visual Basic) modifier to container controls like <xref:System.Windows.Forms.Panel>.</span></span> <span data-ttu-id="6da98-125">Wenn Ihre <xref:System.Windows.Forms.UserControl> oder <xref:System.Windows.Forms.Form> ist ein Container-Steuerelement akzeptiert keine neuen untergeordneten Elemente in geerbte Steuerelemente und Formulare.</span><span class="sxs-lookup"><span data-stu-id="6da98-125">If your base <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Form> has a container control, it will not accept new children in inherited controls and forms.</span></span> <span data-ttu-id="6da98-126">Die Lösung besteht darin, ändern Sie den Modifizierer des Steuerelements basiscontainer `protected` oder `public`.</span><span class="sxs-lookup"><span data-stu-id="6da98-126">The solution is to change the modifier of the base container control to `protected` or `public`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6da98-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6da98-127">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="6da98-128">Visuelle Vererbung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6da98-128">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
- [<span data-ttu-id="6da98-129">Exemplarische Vorgehensweise: Demonstrieren der visuellen Vererbung</span><span class="sxs-lookup"><span data-stu-id="6da98-129">Walkthrough: Demonstrating Visual Inheritance</span></span>](walkthrough-demonstrating-visual-inheritance.md)
- [<span data-ttu-id="6da98-130">Vorgehensweise: Erben von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6da98-130">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)

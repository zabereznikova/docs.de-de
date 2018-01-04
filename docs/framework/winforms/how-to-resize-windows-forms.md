---
title: "Gewusst wie: Ändern der Größe von Windows Forms"
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
- cpp
helpviewer_keywords:
- resizing Windows Forms
- Windows Forms, resizing
ms.assetid: 5d9dd47e-e68c-48c9-a0a3-a9ff34ba009d
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cc2e9f81094d16030dbe4595a8132569edab782a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-resize-windows-forms"></a><span data-ttu-id="93908-102">Gewusst wie: Ändern der Größe von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="93908-102">How to: Resize Windows Forms</span></span>
<span data-ttu-id="93908-103">Sie können die Größe eines Windows Forms auf verschiedene Weise angeben.</span><span class="sxs-lookup"><span data-stu-id="93908-103">You can specify the size of your Windows Form in several ways.</span></span> <span data-ttu-id="93908-104">Sie können die Höhe und Breite des Formulars programmgesteuert ändern, indem Sie einen neuen Wert für die <xref:System.Windows.Forms.Form.Size%2A>-Eigenschaft festlegen oder die <xref:System.Windows.Forms.Control.Height%2A>- oder die <xref:System.Windows.Forms.Control.Width%2A>-Eigenschaft einzeln anpassen.</span><span class="sxs-lookup"><span data-stu-id="93908-104">You can change both the height and the width of the form programmatically by setting a new value for the <xref:System.Windows.Forms.Form.Size%2A> property, or adjust the <xref:System.Windows.Forms.Control.Height%2A> or <xref:System.Windows.Forms.Control.Width%2A> properties individually.</span></span> <span data-ttu-id="93908-105">Wenn Sie [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] verwenden, können Sie die Größe mit dem Windows Forms-Designer ändern.</span><span class="sxs-lookup"><span data-stu-id="93908-105">If you are using [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], you can change the size using the Windows Forms Designer.</span></span> <span data-ttu-id="93908-106">Siehe auch [Vorgehensweise: Ändern der Größe Windows Forms mithilfe des Designers](http://msdn.microsoft.com/library/37k2zkwx\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="93908-106">Also see [How to: Resize Windows Forms Using the Designer](http://msdn.microsoft.com/library/37k2zkwx\(v=vs.110\)).</span></span>  
  
### <a name="to-resize-a-form-programmatically"></a><span data-ttu-id="93908-107">So ändern Sie die Größe eines Formulars programmgesteuert</span><span class="sxs-lookup"><span data-stu-id="93908-107">To resize a form programmatically</span></span>  
  
-   <span data-ttu-id="93908-108">Sie können die Größe eines Formulars zur Laufzeit definieren, indem Sie die <xref:System.Windows.Forms.Form.Size%2A>-Eigenschaft des Formulars festlegen.</span><span class="sxs-lookup"><span data-stu-id="93908-108">Define the size of a form at run time by setting the <xref:System.Windows.Forms.Form.Size%2A> property of the form.</span></span>  
  
     <span data-ttu-id="93908-109">Im folgenden Codebeispiel wird die Formulargröße auf 100 x 100 Pixel festgelegt.</span><span class="sxs-lookup"><span data-stu-id="93908-109">The following code example shows the form size set to 100 × 100 pixels.</span></span>  
  
    ```vb  
    Form1.Size = New System.Drawing.Size(100, 100)  
    ```  
  
    ```csharp  
    Form1.Size = new System.Drawing.Size(100, 100);  
    ```  
  
    ```cpp  
    Form1->Size = System::Drawing::Size(100, 100);  
    ```  
  
### <a name="to-change-form-width-and-height-programmatically"></a><span data-ttu-id="93908-110">So ändern Sie Breite und Höhe des Formulars programmgesteuert</span><span class="sxs-lookup"><span data-stu-id="93908-110">To change form width and height programmatically</span></span>  
  
-   <span data-ttu-id="93908-111">Nachdem <xref:System.Windows.Forms.Form.Size%2A> definiert ist, ändern Sie entweder die Formularhöhe oder -breite über die <xref:System.Windows.Forms.Control.Width%2A>- oder die <xref:System.Windows.Forms.Control.Height%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="93908-111">After the <xref:System.Windows.Forms.Form.Size%2A> is defined, change either the form height or width by using the <xref:System.Windows.Forms.Control.Width%2A> or <xref:System.Windows.Forms.Control.Height%2A> properties.</span></span>  
  
     <span data-ttu-id="93908-112">Im folgenden Codebeispiel wird die Breite des Formulars ab dem linken Formularrand auf 300 Pixel festgelegt, während die Höhe konstant bleibt.</span><span class="sxs-lookup"><span data-stu-id="93908-112">The following code example shows the width of the form set to 300 pixels from the left edge of the form, whereas the height stays constant.</span></span>  
  
    ```vb  
    Form1.Width = 300  
    ```  
  
    ```csharp  
    Form1.Width = 300;  
    ```  
  
    ```cpp  
    Form1->Width = 300;  
    ```  
  
     <span data-ttu-id="93908-113">- oder - </span><span class="sxs-lookup"><span data-stu-id="93908-113">-or-</span></span>  
  
     <span data-ttu-id="93908-114">Ändern Sie <xref:System.Drawing.Size.Width%2A> oder <xref:System.Drawing.Size.Height%2A>, indem Sie die <xref:System.Windows.Forms.Form.Size%2A>-Eigenschaft festlegen.</span><span class="sxs-lookup"><span data-stu-id="93908-114">Change <xref:System.Drawing.Size.Width%2A> or <xref:System.Drawing.Size.Height%2A> by setting the <xref:System.Windows.Forms.Form.Size%2A> property.</span></span>  
  
     <span data-ttu-id="93908-115">Wie Sie jedoch dem folgenden Codebeispiel entnehmen können, ist diese Vorgehensweise komplizierter als das Festlegen der <xref:System.Windows.Forms.Control.Width%2A>- oder der <xref:System.Windows.Forms.Control.Height%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="93908-115">However, as the following code example shows, this approach is more cumbersome than just setting <xref:System.Windows.Forms.Control.Width%2A> or <xref:System.Windows.Forms.Control.Height%2A> properties.</span></span>  
  
    ```vb  
    Form1.Size = New Size(300, Form1.Size.Height)  
    ```  
  
    ```csharp  
    Form1.Size = new Size(300, Form1.Size.Height);  
    ```  
  
    ```cpp  
    Form1->Size = System::Drawing::Size(300, Form1->Size.Height);  
    ```  
  
### <a name="to-change-form-size-by-increments-programmatically"></a><span data-ttu-id="93908-116">So ändern Sie Formulargröße programmgesteuert in Schritten</span><span class="sxs-lookup"><span data-stu-id="93908-116">To change form size by increments programmatically</span></span>  
  
-   <span data-ttu-id="93908-117">Um das Formular zu vergrößern, legen Sie die <xref:System.Drawing.Size.Width%2A>- und die <xref:System.Drawing.Size.Height%2A>-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="93908-117">To increment the size of the form, set the <xref:System.Drawing.Size.Width%2A> and <xref:System.Drawing.Size.Height%2A> properties.</span></span>  
  
     <span data-ttu-id="93908-118">Im folgenden Codebeispiel wird das Formular mit einer Breite angezeigt, die um 200 Pixel größer ist als die aktuelle Einstellung.</span><span class="sxs-lookup"><span data-stu-id="93908-118">The following code example shows the width of the form set to 200 pixels wider than the current setting.</span></span>  
  
    ```vb  
    Form1.Width += 200  
    ```  
  
    ```csharp  
    Form1.Width += 200;  
    ```  
  
    ```cpp  
    Form1->Width += 200;  
    ```  
  
    > [!CAUTION]
    >  <span data-ttu-id="93908-119">Sie sollten immer die <xref:System.Drawing.Size.Height%2A>- oder die <xref:System.Drawing.Size.Width%2A>-Eigenschaft verwenden, um ein Maß eines Formulars zu ändern, es sei denn, Sie legen das Höhen- und das Breitenmaß gleichzeitig fest, indem Sie die <xref:System.Windows.Forms.Form.Size%2A>-Eigenschaft auf eine neue <xref:System.Drawing.Size>-Struktur festlegen.</span><span class="sxs-lookup"><span data-stu-id="93908-119">Always use the <xref:System.Drawing.Size.Height%2A> or <xref:System.Drawing.Size.Width%2A> property to change a dimension of a form, unless you are setting both height and width dimensions at the same time by setting the <xref:System.Windows.Forms.Form.Size%2A> property to a new <xref:System.Drawing.Size> structure.</span></span> <span data-ttu-id="93908-120">Die <xref:System.Windows.Forms.Form.Size%2A>-Eigenschaft gibt eine <xref:System.Drawing.Size>-Struktur zurück, die ein Werttyp ist.</span><span class="sxs-lookup"><span data-stu-id="93908-120">The <xref:System.Windows.Forms.Form.Size%2A> property returns a <xref:System.Drawing.Size> structure, which is a value type.</span></span> <span data-ttu-id="93908-121">Sie können der Eigenschaft eines Werttyps keinen neuen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="93908-121">You cannot assign a new value to the property of a value type.</span></span> <span data-ttu-id="93908-122">Daher kann das folgende Codebeispiel nicht kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="93908-122">Therefore, the following code example will not compile.</span></span>  
  
    ```vb  
    ' NOTE: CODE WILL NOT COMPILE  
    Dim f As New Form()  
    f.Size.Width += 100  
    ```  
  
    ```csharp  
    // NOTE: CODE WILL NOT COMPILE  
    Form f = new Form();  
    f.Size.Width += 100;  
    ```  
  
    ```cpp  
    // NOTE: CODE WILL NOT COMPILE  
    Form^ f = gcnew Form();  
    f->Size->X += 100;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="93908-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93908-123">See Also</span></span>  
 [<span data-ttu-id="93908-124">Erste Schritte mit Windows Forms</span><span class="sxs-lookup"><span data-stu-id="93908-124">Getting Started with Windows Forms</span></span>](../../../docs/framework/winforms/getting-started-with-windows-forms.md)  
 [<span data-ttu-id="93908-125">Erweitern von Windows Forms-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="93908-125">Enhancing Windows Forms Applications</span></span>](../../../docs/framework/winforms/advanced/index.md)

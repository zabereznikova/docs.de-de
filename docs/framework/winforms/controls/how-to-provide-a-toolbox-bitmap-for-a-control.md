---
title: 'Gewusst wie: Bereitstellen einer Toolboxbitmap für ein Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Toolbox [Windows Forms], adding bitmaps for custom controls
- custom controls [Windows Forms], Toolbox bitmaps
- bitmaps [Windows Forms], custom controls
ms.assetid: 0ed0840a-616d-41ba-a27d-3573241932ad
ms.openlocfilehash: 3698d2fdbd0375d0a154d6ecea3a248b31da2aeb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537520"
---
# <a name="how-to-provide-a-toolbox-bitmap-for-a-control"></a><span data-ttu-id="01e71-102">Gewusst wie: Bereitstellen einer Toolboxbitmap für ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="01e71-102">How to: Provide a Toolbox Bitmap for a Control</span></span>
<span data-ttu-id="01e71-103">Wenn Sie möchten ein besonderes Symbol für das Steuerelement angezeigt werden, der **Toolbox**, können, geben Sie ein bestimmtes Abbild mithilfe der <xref:System.Drawing.ToolboxBitmapAttribute>.</span><span class="sxs-lookup"><span data-stu-id="01e71-103">If you want to have a special icon for your control appear in the **Toolbox**, you can specify a particular image by using the <xref:System.Drawing.ToolboxBitmapAttribute>.</span></span> <span data-ttu-id="01e71-104">Diese Klasse ist ein *Attribut*, eine besondere Klassenform, die Sie an andere Klassen anfügen können.</span><span class="sxs-lookup"><span data-stu-id="01e71-104">This class is an *attribute*, a special kind of class you can attach to other classes.</span></span> <span data-ttu-id="01e71-105">Weitere Informationen zu Attributen finden Sie unter [nicht im BUILD: Übersicht über Attribute in Visual Basic](http://msdn.microsoft.com/library/0d0cff64-892d-4f57-83bd-bef388553d4f) für Visual Basic und [Attribute](http://msdn.microsoft.com/library/ae334cee-d96c-4243-a5e3-06dd7fcaf205) für Visual c#.</span><span class="sxs-lookup"><span data-stu-id="01e71-105">For more information about attributes, see [NOT IN BUILD: Attributes Overview in Visual Basic](http://msdn.microsoft.com/library/0d0cff64-892d-4f57-83bd-bef388553d4f) for Visual Basic and [Attributes](http://msdn.microsoft.com/library/ae334cee-d96c-4243-a5e3-06dd7fcaf205) for Visual C#.</span></span>  
  
 <span data-ttu-id="01e71-106">Mithilfe der <xref:System.Drawing.ToolboxBitmapAttribute>, können Sie angeben, eine Zeichenfolge, die den Pfad und den Namen für eine 16 x 16-Pixel-Bitmap angibt.</span><span class="sxs-lookup"><span data-stu-id="01e71-106">Using the <xref:System.Drawing.ToolboxBitmapAttribute>, you can specify a string that indicates the path and file name for a 16 by 16 pixel bitmap.</span></span> <span data-ttu-id="01e71-107">Diese Bitmap wird dann neben dem Steuerelement angezeigt, wenn sie zur **Toolbox** hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="01e71-107">This bitmap then appears next to your control when added to the **Toolbox**.</span></span> <span data-ttu-id="01e71-108">Sie können auch angeben, ein <xref:System.Type>, in diesem Fall die Bitmap, die diesem Typ zugeordnete geladen wird.</span><span class="sxs-lookup"><span data-stu-id="01e71-108">You can also specify a <xref:System.Type>, in which case the bitmap associated with that type is loaded.</span></span> <span data-ttu-id="01e71-109">Wenn Sie beide angeben einer <xref:System.Type> und eine Zeichenfolge, das Steuerelement für eine Bildressource sucht, mit dem Namen gemäß der Zeichenfolgenparameter in die Assembly mit den vom angegebenen Typ der <xref:System.Type> Parameter.</span><span class="sxs-lookup"><span data-stu-id="01e71-109">If you specify both a <xref:System.Type> and a string, the control searches for an image resource with the name specified by the string parameter in the assembly containing the type specified by the <xref:System.Type> parameter.</span></span>  
  
### <a name="to-specify-a-toolbox-bitmap-for-your-control"></a><span data-ttu-id="01e71-110">So geben sie eine Toolboxbitmap für Ihr Steuerelement an</span><span class="sxs-lookup"><span data-stu-id="01e71-110">To specify a Toolbox bitmap for your control</span></span>  
  
1.  <span data-ttu-id="01e71-111">Hinzufügen der <xref:System.Drawing.ToolboxBitmapAttribute> der Klassendeklaration des Steuerelements vor dem `Class` Schlüsselwort für Visual Basic und oberhalb der Klassendeklaration für Visual c#.</span><span class="sxs-lookup"><span data-stu-id="01e71-111">Add the <xref:System.Drawing.ToolboxBitmapAttribute> to the class declaration of your control before the `Class` keyword for visual Basic, and above the class declaration for Visual C#.</span></span>  
  
    ```vb  
    ' Specifies the bitmap associated with the Button type.  
    <ToolboxBitmap(GetType(Button))> Class MyControl1  
    ' Specifies a bitmap file.  
    End Class  
    <ToolboxBitmap("C:\Documents and Settings\Joe\MyPics\myImage.bmp")> _  
       Class MyControl2  
    End Class  
    ' Specifies a type that indicates the assembly to search, and the name   
    ' of an image resource to look for.  
    <ToolboxBitmap(GetType(MyControl), "MyControlBitmap")> Class MyControl  
    End Class  
    ```  
  
    ```csharp  
    // Specifies the bitmap associated with the Button type.  
    [ToolboxBitmap(typeof(Button))]  
    class MyControl1 : UserControl  
    {  
    }  
    // Specifies a bitmap file.  
    [ToolboxBitmap(@"C:\Documents and Settings\Joe\MyPics\myImage.bmp")]  
    class MyControl2 : UserControl  
    {  
    }  
    // Specifies a type that indicates the assembly to search, and the name   
    // of an image resource to look for.  
    [ToolboxBitmap(typeof(MyControl), "MyControlBitmap")]  
    class MyControl : UserControl  
    {  
    }  
    ```  
  
2.  <span data-ttu-id="01e71-112">Erstellen Sie das Projekt neu.</span><span class="sxs-lookup"><span data-stu-id="01e71-112">Rebuild the project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="01e71-113">Die Bitmap wird nicht in der Toolbox für automatisch generierte Steuerelemente und Komponenten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="01e71-113">The bitmap does not appear in the Toolbox for autogenerated controls and components.</span></span> <span data-ttu-id="01e71-114">Laden Sie das Steuerelement mithilfe des Dialogfelds **Toolboxelemente auswählen** neu, um die Bitmap anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="01e71-114">To see the bitmap, reload the control by using the **Choose Toolbox Items** dialog box.</span></span> <span data-ttu-id="01e71-115">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span><span class="sxs-lookup"><span data-stu-id="01e71-115">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01e71-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01e71-116">See Also</span></span>  
 <xref:System.Drawing.ToolboxBitmapAttribute>  
 [<span data-ttu-id="01e71-117">Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten</span><span class="sxs-lookup"><span data-stu-id="01e71-117">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)  
 [<span data-ttu-id="01e71-118">Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="01e71-118">Developing Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)  
 [<span data-ttu-id="01e71-119">Attribute (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01e71-119">Attributes (Visual Basic)</span></span>](~/docs/visual-basic/language-reference/attributes.md)  
 [<span data-ttu-id="01e71-120">Attribute</span><span class="sxs-lookup"><span data-stu-id="01e71-120">Attributes</span></span>](http://msdn.microsoft.com/library/ae334cee-d96c-4243-a5e3-06dd7fcaf205)

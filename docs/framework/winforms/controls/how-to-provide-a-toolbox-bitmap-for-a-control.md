---
title: 'Vorgehensweise: Bereitstellen einer Toolboxbitmap für ein Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Toolbox [Windows Forms], adding bitmaps for custom controls
- custom controls [Windows Forms], Toolbox bitmaps
- bitmaps [Windows Forms], custom controls
ms.assetid: 0ed0840a-616d-41ba-a27d-3573241932ad
ms.openlocfilehash: 7c26e00acd4278ced53ad29c748ac076e0215a23
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61913210"
---
# <a name="how-to-provide-a-toolbox-bitmap-for-a-control"></a><span data-ttu-id="f02d9-102">Vorgehensweise: Bereitstellen einer Toolboxbitmap für ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="f02d9-102">How to: Provide a Toolbox Bitmap for a Control</span></span>
<span data-ttu-id="f02d9-103">Wenn Sie möchten ein besonderes Symbol für das Steuerelement angezeigt werden, der **Toolbox**, Sie können ein bestimmtes Image angeben, mit der <xref:System.Drawing.ToolboxBitmapAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f02d9-103">If you want to have a special icon for your control appear in the **Toolbox**, you can specify a particular image by using the <xref:System.Drawing.ToolboxBitmapAttribute>.</span></span> <span data-ttu-id="f02d9-104">Diese Klasse ist ein *Attribut*, eine besondere Klassenform, die Sie an andere Klassen anfügen können.</span><span class="sxs-lookup"><span data-stu-id="f02d9-104">This class is an *attribute*, a special kind of class you can attach to other classes.</span></span> <span data-ttu-id="f02d9-105">Weitere Informationen zu Attributen finden Sie unter [Übersicht über Attribute (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md) für Visual Basic oder [Attribute (c#)](../../../csharp/programming-guide/concepts/attributes/index.md) für C#-Code.</span><span class="sxs-lookup"><span data-stu-id="f02d9-105">For more information about attributes, see [Attributes overview (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md) for Visual Basic or [Attributes (C#)](../../../csharp/programming-guide/concepts/attributes/index.md) for C#.</span></span>  
  
 <span data-ttu-id="f02d9-106">Mithilfe der <xref:System.Drawing.ToolboxBitmapAttribute>, können Sie angeben, eine Zeichenfolge, die den Pfad und Dateiname für eine 16 x 16-Pixel-Bitmap angibt.</span><span class="sxs-lookup"><span data-stu-id="f02d9-106">Using the <xref:System.Drawing.ToolboxBitmapAttribute>, you can specify a string that indicates the path and file name for a 16 by 16 pixel bitmap.</span></span> <span data-ttu-id="f02d9-107">Diese Bitmap wird dann neben dem Steuerelement angezeigt, wenn sie zur **Toolbox** hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="f02d9-107">This bitmap then appears next to your control when added to the **Toolbox**.</span></span> <span data-ttu-id="f02d9-108">Sie können auch angeben, ein <xref:System.Type>, in diesem Fall die Bitmap, die diesem Typ zugeordnete geladen wird.</span><span class="sxs-lookup"><span data-stu-id="f02d9-108">You can also specify a <xref:System.Type>, in which case the bitmap associated with that type is loaded.</span></span> <span data-ttu-id="f02d9-109">Wenn Sie beide angeben einer <xref:System.Type> und eine Zeichenfolge, das Steuerelement für eine Bildressource gesucht, mit dem Namen gemäß der Zeichenfolgenparameter in der Assembly, die den vom angegebenen Typ enthält die <xref:System.Type> Parameter.</span><span class="sxs-lookup"><span data-stu-id="f02d9-109">If you specify both a <xref:System.Type> and a string, the control searches for an image resource with the name specified by the string parameter in the assembly containing the type specified by the <xref:System.Type> parameter.</span></span>  
  
### <a name="to-specify-a-toolbox-bitmap-for-your-control"></a><span data-ttu-id="f02d9-110">So geben sie eine Toolboxbitmap für Ihr Steuerelement an</span><span class="sxs-lookup"><span data-stu-id="f02d9-110">To specify a Toolbox bitmap for your control</span></span>  
  
1. <span data-ttu-id="f02d9-111">Hinzufügen der <xref:System.Drawing.ToolboxBitmapAttribute> zur Klassendeklaration Ihres Steuerelements vor dem `Class` Schlüsselwort oberhalb der Klassendeklaration für Visual c# und Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f02d9-111">Add the <xref:System.Drawing.ToolboxBitmapAttribute> to the class declaration of your control before the `Class` keyword for visual Basic, and above the class declaration for Visual C#.</span></span>  
  
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
  
2. <span data-ttu-id="f02d9-112">Erstellen Sie das Projekt neu.</span><span class="sxs-lookup"><span data-stu-id="f02d9-112">Rebuild the project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f02d9-113">Die Bitmap wird nicht in der Toolbox für automatisch generierte Steuerelemente und Komponenten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f02d9-113">The bitmap does not appear in the Toolbox for autogenerated controls and components.</span></span> <span data-ttu-id="f02d9-114">Laden Sie das Steuerelement mithilfe des Dialogfelds **Toolboxelemente auswählen** neu, um die Bitmap anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f02d9-114">To see the bitmap, reload the control by using the **Choose Toolbox Items** dialog box.</span></span> <span data-ttu-id="f02d9-115">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span><span class="sxs-lookup"><span data-stu-id="f02d9-115">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f02d9-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f02d9-116">See also</span></span>

- <xref:System.Drawing.ToolboxBitmapAttribute>
- [<span data-ttu-id="f02d9-117">Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten</span><span class="sxs-lookup"><span data-stu-id="f02d9-117">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
- [<span data-ttu-id="f02d9-118">Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="f02d9-118">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- [<span data-ttu-id="f02d9-119">Übersicht über Attribute (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f02d9-119">Attributes overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="f02d9-120">Attribute (C#)</span><span class="sxs-lookup"><span data-stu-id="f02d9-120">Attributes (C#)</span></span>](../../../csharp/programming-guide/concepts/attributes/index.md)

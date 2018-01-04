---
title: "Gewusst wie: Bereitstellen einer Toolboxbitmap für ein Steuerelement"
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
helpviewer_keywords:
- Toolbox [Windows Forms], adding bitmaps for custom controls
- custom controls [Windows Forms], Toolbox bitmaps
- bitmaps [Windows Forms], custom controls
ms.assetid: 0ed0840a-616d-41ba-a27d-3573241932ad
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 947ac4f8783b388135cf9e8147bb48eda93cfa08
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-provide-a-toolbox-bitmap-for-a-control"></a><span data-ttu-id="eb1d2-102">Gewusst wie: Bereitstellen einer Toolboxbitmap für ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="eb1d2-102">How to: Provide a Toolbox Bitmap for a Control</span></span>
<span data-ttu-id="eb1d2-103">Wenn Sie möchten ein besonderes Symbol für das Steuerelement angezeigt werden, der **Toolbox**, können, geben Sie ein bestimmtes Abbild mithilfe der <xref:System.Drawing.ToolboxBitmapAttribute>.</span><span class="sxs-lookup"><span data-stu-id="eb1d2-103">If you want to have a special icon for your control appear in the **Toolbox**, you can specify a particular image by using the <xref:System.Drawing.ToolboxBitmapAttribute>.</span></span> <span data-ttu-id="eb1d2-104">Diese Klasse ist ein *Attribut*, eine besondere Klassenform, die Sie an andere Klassen anfügen können.</span><span class="sxs-lookup"><span data-stu-id="eb1d2-104">This class is an *attribute*, a special kind of class you can attach to other classes.</span></span> <span data-ttu-id="eb1d2-105">Weitere Informationen zu Attributen finden Sie unter [NICHT IM BUILD: Übersicht über Attribute in Visual Basic](http://msdn.microsoft.com/en-us/0d0cff64-892d-4f57-83bd-bef388553d4f) für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], und [Attributes (Attribute)](http://msdn.microsoft.com/library/ae334cee-d96c-4243-a5e3-06dd7fcaf205) für [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb1d2-105">For more information about attributes, see [NOT IN BUILD: Attributes Overview in Visual Basic](http://msdn.microsoft.com/en-us/0d0cff64-892d-4f57-83bd-bef388553d4f) for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] and [Attributes](http://msdn.microsoft.com/library/ae334cee-d96c-4243-a5e3-06dd7fcaf205) for [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)].</span></span>  
  
 <span data-ttu-id="eb1d2-106">Mithilfe der <xref:System.Drawing.ToolboxBitmapAttribute>, können Sie angeben, eine Zeichenfolge, die den Pfad und den Namen für eine 16 x 16-Pixel-Bitmap angibt.</span><span class="sxs-lookup"><span data-stu-id="eb1d2-106">Using the <xref:System.Drawing.ToolboxBitmapAttribute>, you can specify a string that indicates the path and file name for a 16 by 16 pixel bitmap.</span></span> <span data-ttu-id="eb1d2-107">Diese Bitmap wird dann neben dem Steuerelement angezeigt, wenn sie zur **Toolbox** hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="eb1d2-107">This bitmap then appears next to your control when added to the **Toolbox**.</span></span> <span data-ttu-id="eb1d2-108">Sie können auch angeben, ein <xref:System.Type>, in diesem Fall die Bitmap, die diesem Typ zugeordnete geladen wird.</span><span class="sxs-lookup"><span data-stu-id="eb1d2-108">You can also specify a <xref:System.Type>, in which case the bitmap associated with that type is loaded.</span></span> <span data-ttu-id="eb1d2-109">Wenn Sie beide angeben einer <xref:System.Type> und eine Zeichenfolge, das Steuerelement für eine Bildressource sucht, mit dem Namen gemäß der Zeichenfolgenparameter in die Assembly mit den vom angegebenen Typ der <xref:System.Type> Parameter.</span><span class="sxs-lookup"><span data-stu-id="eb1d2-109">If you specify both a <xref:System.Type> and a string, the control searches for an image resource with the name specified by the string parameter in the assembly containing the type specified by the <xref:System.Type> parameter.</span></span>  
  
### <a name="to-specify-a-toolbox-bitmap-for-your-control"></a><span data-ttu-id="eb1d2-110">So geben sie eine Toolboxbitmap für Ihr Steuerelement an</span><span class="sxs-lookup"><span data-stu-id="eb1d2-110">To specify a Toolbox bitmap for your control</span></span>  
  
1.  <span data-ttu-id="eb1d2-111">Hinzufügen der <xref:System.Drawing.ToolboxBitmapAttribute> der Klassendeklaration des Steuerelements vor dem `Class` Schlüsselwort für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], und oberhalb der Klassendeklaration für [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb1d2-111">Add the <xref:System.Drawing.ToolboxBitmapAttribute> to the class declaration of your control before the `Class` keyword for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], and above the class declaration for [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)].</span></span>  
  
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
  
2.  <span data-ttu-id="eb1d2-112">Erstellen Sie das Projekt neu.</span><span class="sxs-lookup"><span data-stu-id="eb1d2-112">Rebuild the project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eb1d2-113">Die Bitmap wird nicht in der Toolbox für automatisch generierte Steuerelemente und Komponenten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eb1d2-113">The bitmap does not appear in the Toolbox for autogenerated controls and components.</span></span> <span data-ttu-id="eb1d2-114">Laden Sie das Steuerelement mithilfe des Dialogfelds **Toolboxelemente auswählen** neu, um die Bitmap anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="eb1d2-114">To see the bitmap, reload the control by using the **Choose Toolbox Items** dialog box.</span></span> <span data-ttu-id="eb1d2-115">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span><span class="sxs-lookup"><span data-stu-id="eb1d2-115">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb1d2-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eb1d2-116">See Also</span></span>  
 <xref:System.Drawing.ToolboxBitmapAttribute>  
 [<span data-ttu-id="eb1d2-117">Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten</span><span class="sxs-lookup"><span data-stu-id="eb1d2-117">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)  
 [<span data-ttu-id="eb1d2-118">Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="eb1d2-118">Developing Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)  
 [<span data-ttu-id="eb1d2-119">Attribute (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eb1d2-119">Attributes (Visual Basic)</span></span>](~/docs/visual-basic/language-reference/attributes.md)  
 [<span data-ttu-id="eb1d2-120">Attribute</span><span class="sxs-lookup"><span data-stu-id="eb1d2-120">Attributes</span></span>](http://msdn.microsoft.com/library/ae334cee-d96c-4243-a5e3-06dd7fcaf205)

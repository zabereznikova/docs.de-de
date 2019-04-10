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
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59337707"
---
# <a name="how-to-provide-a-toolbox-bitmap-for-a-control"></a>Vorgehensweise: Bereitstellen einer Toolboxbitmap für ein Steuerelement
Wenn Sie möchten ein besonderes Symbol für das Steuerelement angezeigt werden, der **Toolbox**, Sie können ein bestimmtes Image angeben, mit der <xref:System.Drawing.ToolboxBitmapAttribute>. Diese Klasse ist ein *Attribut*, eine besondere Klassenform, die Sie an andere Klassen anfügen können. Weitere Informationen zu Attributen finden Sie unter [Übersicht über Attribute (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md) für Visual Basic oder [Attribute (c#)](../../../csharp/programming-guide/concepts/attributes/index.md) für C#-Code.  
  
 Mithilfe der <xref:System.Drawing.ToolboxBitmapAttribute>, können Sie angeben, eine Zeichenfolge, die den Pfad und Dateiname für eine 16 x 16-Pixel-Bitmap angibt. Diese Bitmap wird dann neben dem Steuerelement angezeigt, wenn sie zur **Toolbox** hinzugefügt wird. Sie können auch angeben, ein <xref:System.Type>, in diesem Fall die Bitmap, die diesem Typ zugeordnete geladen wird. Wenn Sie beide angeben einer <xref:System.Type> und eine Zeichenfolge, das Steuerelement für eine Bildressource gesucht, mit dem Namen gemäß der Zeichenfolgenparameter in der Assembly, die den vom angegebenen Typ enthält die <xref:System.Type> Parameter.  
  
### <a name="to-specify-a-toolbox-bitmap-for-your-control"></a>So geben sie eine Toolboxbitmap für Ihr Steuerelement an  
  
1. Hinzufügen der <xref:System.Drawing.ToolboxBitmapAttribute> zur Klassendeklaration Ihres Steuerelements vor dem `Class` Schlüsselwort oberhalb der Klassendeklaration für Visual c# und Visual Basic.  
  
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
  
2. Erstellen Sie das Projekt neu.  
  
    > [!NOTE]
    >  Die Bitmap wird nicht in der Toolbox für automatisch generierte Steuerelemente und Komponenten angezeigt. Laden Sie das Steuerelement mithilfe des Dialogfelds **Toolboxelemente auswählen** neu, um die Bitmap anzuzeigen. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.ToolboxBitmapAttribute>
- [Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
- [Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit](developing-windows-forms-controls-at-design-time.md)
- [Übersicht über Attribute (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [Attribute (C#)](../../../csharp/programming-guide/concepts/attributes/index.md)

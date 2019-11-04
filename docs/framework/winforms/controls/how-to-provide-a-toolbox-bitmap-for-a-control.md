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
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 61f60aaeab904dff80408a1dc46c2882fb5e22b9
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458315"
---
# <a name="how-to-provide-a-toolbox-bitmap-for-a-control"></a>Gewusst wie: Bereitstellen einer Toolboxbitmap für ein Steuerelement

Wenn Sie ein spezielles Symbol für das Steuerelement in der **Toolbox** von Visual Studio anzeigen möchten, können Sie ein bestimmtes Bild mithilfe der <xref:System.Drawing.ToolboxBitmapAttribute>angeben. Diese Klasse ist ein *Attribut*, eine besondere Klassenform, die Sie an andere Klassen anfügen können. Weitere Informationen zu Attributen finden Sie unter [Übersicht über Attribute (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md) für Visual Basic oder [AttributeC#()](../../../csharp/programming-guide/concepts/attributes/index.md) für. C#

Mithilfe der <xref:System.Drawing.ToolboxBitmapAttribute>können Sie eine Zeichenfolge angeben, die den Pfad und den Dateinamen für eine 16 x 16 Pixel-Bitmap angibt. Diese Bitmap wird dann neben dem Steuerelement angezeigt, wenn sie zur **Toolbox** hinzugefügt wird. Sie können auch einen <xref:System.Type>angeben. in diesem Fall wird die Bitmap geladen, die diesem Typ zugeordnet ist. Wenn Sie sowohl eine <xref:System.Type> als auch eine Zeichenfolge angeben, sucht das Steuerelement nach einer Bildressource mit dem Namen, der durch den Zeichen folgen Parameter in der Assembly angegeben ist, die den vom <xref:System.Type>-Parameter angegebenen Typ enthält.

## <a name="to-specify-a-toolbox-bitmap-for-your-control"></a>So geben sie eine Toolboxbitmap für Ihr Steuerelement an

1. Fügen Sie der Klassen Deklaration Ihres Steuer Elements vor dem `Class`-Schlüsselwort für Visual Basic und oberhalb der Klassen Deklaration für C#Visual die <xref:System.Drawing.ToolboxBitmapAttribute> hinzu.

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
    > Die Bitmap wird nicht in der Toolbox für automatisch generierte Steuerelemente und Komponenten angezeigt. Laden Sie das Steuerelement mithilfe des Dialogfelds **Toolboxelemente auswählen** neu, um die Bitmap anzuzeigen. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).

## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.ToolboxBitmapAttribute>
- [Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
- [Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit](developing-windows-forms-controls-at-design-time.md)
- [Übersicht über Attribute (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [Attribute (C#)](../../../csharp/programming-guide/concepts/attributes/index.md)

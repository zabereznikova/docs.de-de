---
title: "Gewusst wie: Bereitstellen einer Toolboxbitmap f&#252;r ein Steuerelement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Bitmaps [Windows Forms], Benutzerdefinierte Steuerelemente"
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Toolboxbitmaps"
  - "Toolbox [Windows Forms], Hinzufügen von Bitmaps für benutzerdefinierte Steuerelemente"
ms.assetid: 0ed0840a-616d-41ba-a27d-3573241932ad
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Gewusst wie: Bereitstellen einer Toolboxbitmap f&#252;r ein Steuerelement
Wenn in der **Toolbox** ein spezielles Symbol für das Steuerelement angezeigt werden soll, können Sie mithilfe des <xref:System.Drawing.ToolboxBitmapAttribute> ein Bild festlegen.  Diese Klasse ist ein *Attribut*, d. h. eine besondere Art von Klasse, die an andere Klassen angefügt werden kann.  Weitere Informationen über Attribute finden Sie unter [NOT IN BUILD: Attributes Overview in Visual Basic](http://msdn.microsoft.com/de-de/0d0cff64-892d-4f57-83bd-bef388553d4f) für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] und [Attribute](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md) für [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)].  
  
 Mithilfe von <xref:System.Drawing.ToolboxBitmapAttribute> können Sie eine Zeichenfolge angeben, die den Pfad und den Dateinamen für eine Bitmap von 16 x 16 Pixel angibt.  Diese Bitmap wird, nachdem sie der **Toolbox** hinzugefügt wurde, neben dem Steuerelement angezeigt.  Sie können auch einen <xref:System.Type> angeben, sodass die diesem Typ zugeordnete Bitmap geladen wird.  Wenn Sie sowohl <xref:System.Type> als auch eine Zeichenfolge angeben, sucht das Steuerelement in der Assembly, die den vom <xref:System.Type>\-Parameter angegebenen Typ enthält, nach einer Bildressource mit dem vom Zeichenfolgenparameter angegebenen Namen.  
  
### So geben Sie eine Toolboxbitmap für das Steuerelement an  
  
1.  Fügen Sie der Klassendeklaration des Steuerelements vor dem Schlüsselwort `Class` für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] und oberhalb der Klassendeklaration für [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] das <xref:System.Drawing.ToolboxBitmapAttribute> hinzu.  
  
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
  
2.  Erstellen Sie das Projekt neu.  
  
    > [!NOTE]
    >  Die Bitmap wird in der Toolbox für automatisch generierte Steuerelemente und Komponenten nicht angezeigt.  Damit die Bitmap angezeigt wird, müssen Sie das Steuerelement über das Dialogfeld **Toolboxelemente auswählen** neu laden.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).  
  
## Siehe auch  
 <xref:System.Drawing.ToolboxBitmapAttribute>   
 [Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)   
 [Entwickeln von Windows Forms\-Steuerelementen zur Entwurfszeit](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)   
 [Attributes](../Topic/Attributes%20\(Visual%20Basic\)1.md)   
 [Attribute](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)
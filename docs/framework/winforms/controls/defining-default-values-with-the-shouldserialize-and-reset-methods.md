---
title: "Definieren von Standardwerten mit der ShouldSerialize-Methode und der Reset-Methode | Microsoft Docs"
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
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Eigenschaftenmethoden"
  - "Reset-Methode"
  - "ShouldPersist-Methode"
ms.assetid: 7b6c5e00-3771-46b4-9142-5a80d5864a5e
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Definieren von Standardwerten mit der ShouldSerialize-Methode und der Reset-Methode
`ShouldSerialize` und `Reset` sind optionale Methoden, die Sie für eine Eigenschaft bereitstellen können, wenn die Eigenschaft keinen einfachen Standardwert aufweist.  Bei einem einfachen Standardwert hingegen sollten Sie das <xref:System.ComponentModel.DefaultValueAttribute> anwenden und den Standardwert stattdessen dem Konstruktor der Attributklasse zur Verfügung stellen.  Durch beide Verfahren werden die folgenden Features des Designers aktiviert:  
  
-   Wenn der Standardwert der Eigenschaft geändert wurde, wird dies im Eigenschaftenbrowser visuell angezeigt.  
  
-   Der Benutzer kann mit der rechten Maustaste auf die Eigenschaft klicken und die Option **Zurücksetzen** wählen, um den Standardwert der Eigenschaft wiederherzustellen.  
  
-   Der Designer generiert effizienteren Code.  
  
    > [!NOTE]
    >  Wenden Sie entweder <xref:System.ComponentModel.DefaultValueAttribute> an, oder stellen Sie die `Reset`*PropertyName*\-Methode und die `ShouldSerialize`*PropertyName*\-Methode bereit.  Verwenden Sie nicht beide gleichzeitig.  
  
 Die `Reset`*PropertyName*\-Methode setzt eine Eigenschaft auf ihren Standardwert zurück, wie im folgenden Codefragment dargestellt.  
  
```vb  
Public Sub ResetMyFont()  
   MyFont = Nothing  
End Sub  
```  
  
```csharp  
public void ResetMyFont() {  
   MyFont = null;  
}  
```  
  
> [!NOTE]
>  Wenn eine Eigenschaft nicht über eine `Reset` \-Methode verfügt, nicht mit einem <xref:System.ComponentModel.DefaultValueAttribute> gekennzeichnet ist und in ihrer Deklaration nicht über einen Standardwert verfügt, ist die Option `Reset` für diese Eigenschaft im Kontextmenü des **Eigenschaftenfenster** im Windows Forms\-Designer von [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] deaktiviert.  
  
 Designer wie [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] verwenden die `ShouldSerialize`*PropertyName*\-Methode, um zu überprüfen, ob der Standardwert einer Eigenschaft geändert wurde, und um Code in ein Formular zu schreiben, sofern eine Eigenschaft geändert wurde. Dadurch wird das Generieren von Code effizienter.  Beispiele:  
  
```vb  
'Returns true if the font has changed; otherwise, returns false.  
' The designer writes code to the form only if true is returned.  
Public Function ShouldSerializeMyFont() As Boolean  
   Return Not (thefont Is Nothing)  
End Function  
```  
  
```csharp  
// Returns true if the font has changed; otherwise, returns false.  
// The designer writes code to the form only if true is returned.  
public bool ShouldSerializeMyFont() {  
   return thefont != null;  
}  
```  
  
 Es folgt ein vollständiges Codebeispiel.  
  
```vb  
Option Explicit  
Option Strict  
  
Imports System  
Imports System.Windows.Forms  
Imports System.Drawing  
  
Public Class MyControl  
   Inherits Control  
  
   ' Declare an instance of the Font class  
   ' and set its default value to Nothing.  
   Private thefont As Font = Nothing  
  
   ' The MyFont property.   
   Public Property MyFont() As Font  
      ' Note that the Font property never  
      ' returns null.  
      Get  
         If Not (thefont Is Nothing) Then  
            Return thefont  
         End If  
         If Not (Parent Is Nothing) Then  
            Return Parent.Font  
         End If  
         Return Control.DefaultFont  
      End Get  
      Set  
         thefont = value  
      End Set  
   End Property  
  
   Public Function ShouldSerializeMyFont() As Boolean  
      Return Not (thefont Is Nothing)  
   End Function  
  
   Public Sub ResetMyFont()  
      MyFont = Nothing  
   End Sub  
End Class  
```  
  
```csharp  
using System;  
using System.Windows.Forms;  
using System.Drawing;  
  
public class MyControl : Control {  
   // Declare an instance of the Font class  
   // and set its default value to null.  
   private Font thefont = null;  
  
   // The MyFont property.      
   public Font MyFont {  
      // Note that the MyFont property never  
      // returns null.  
      get {  
         if (thefont != null) return thefont;  
         if (Parent != null) return Parent.Font;  
         return Control.DefaultFont;  
      }  
      set {  
         thefont = value;  
      }  
   }  
  
   public bool ShouldSerializeMyFont() {  
      return thefont != null;  
   }  
  
   public void ResetMyFont() {  
      MyFont = null;  
   }  
}  
```  
  
 Auch wenn der Wert der privaten Variable, der von der `MyFont`\-Eigenschaft aufgerufen wird, in diesem Fall `null` lautet, wird im Eigenschaftenbrowser nicht `null` angezeigt. Stattdessen wird die <xref:System.Windows.Forms.Control.Font%2A>\-Eigenschaft des übergeordneten Elements angezeigt, sofern sie nicht `null` lautet, oder der in <xref:System.Windows.Forms.Control> definierte <xref:System.Windows.Forms.Control.Font%2A>\-Standardwert.  Daher kann der Standardwert für `MyFont`  nicht einfach festgelegt werden, und ein <xref:System.ComponentModel.DefaultValueAttribute> kann auf diese Eigenschaft nicht angewendet werden.  Stattdessen müssen die `ShouldSerialize`\-Methode und `Reset`\-Methode für die `MyFont`\-Eigenschaft implementiert werden.  
  
## Siehe auch  
 [Eigenschaften von Windows Forms\-Steuerelementen](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)   
 [Definieren einer Eigenschaft](../../../../docs/framework/winforms/controls/defining-a-property-in-windows-forms-controls.md)   
 [Durch geänderte Eigenschaften ausgelöste Ereignisse](../../../../docs/framework/winforms/controls/property-changed-events.md)
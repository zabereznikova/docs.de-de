---
title: Definieren von Standardwerten mit der ShouldSerialize-Methode und der Reset-Methode
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property methods
- ShouldPersist method
ms.assetid: 7b6c5e00-3771-46b4-9142-5a80d5864a5e
ms.openlocfilehash: 609fe4896a2b01b8a69ff8a3d0854c85ddbd6a26
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969096"
---
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a>Definieren von Standardwerten mit der ShouldSerialize-Methode und der Reset-Methode
`ShouldSerialize`und `Reset` sind optionale Methoden, die Sie für eine-Eigenschaft bereitstellen können, wenn die-Eigenschaft keinen einfachen Standardwert hat. Wenn die Eigenschaft über einen einfachen Standardwert verfügt, sollten Sie den <xref:System.ComponentModel.DefaultValueAttribute> anwenden und stattdessen den Standardwert für den attributklassenkonstruktor angeben. Beide Mechanismen ermöglichen die folgenden Funktionen im Designer:

- Die-Eigenschaft stellt im Eigenschaften Browser eine visuelle Anzeige dar, wenn Sie von ihrem Standardwert geändert wurde.

- Der Benutzer kann mit der rechten Maustaste auf die Eigenschaft klicken und **Zurücksetzen** auswählen, um die Eigenschaft auf den Standardwert wiederherzustellen.

- Der Designer generiert effizienteren Code.

    > [!NOTE]
    > Wenden Sie entweder <xref:System.ComponentModel.DefaultValueAttribute> an, `Reset`oder stellen Sie die `ShouldSerialize`Methoden *propertyName* und *propertyName* bereit. Verwenden Sie nicht beides.

 Mit `Reset`der *propertyName* -Methode wird eine Eigenschaft auf ihren Standardwert festgelegt, wie im folgenden Code Fragment dargestellt.

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
> Wenn eine Eigenschaft nicht über `Reset` eine-Methode verfügt, nicht mit einem <xref:System.ComponentModel.DefaultValueAttribute>gekennzeichnet ist und in der Deklaration kein Standardwert angegeben ist, wird die `Reset` Option für diese Eigenschaft im Kontextmenü des **Eigenschaften** Fensters von deaktiviert. der Windows Forms-Designer in Visual Studio.

 Designer wie Visual Studio verwenden die `ShouldSerialize` *propertyName* -Methode, um zu überprüfen, ob sich eine Eigenschaft von ihrem Standardwert geändert hat, und schreiben Code nur in das Formular, wenn eine Eigenschaft geändert wird, was eine effizientere Codegenerierung ermöglicht. Beispiel:

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

 Ein umfassendes Codebeispiel folgt.

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

 In diesem Fall wird der Eigenschaften Browser nicht angezeigt, auch wenn der Wert der `MyFont` privaten Variablen, auf die von der-Eigenschaft `null`zugegriffen wird, nicht angezeigt wird <xref:System.Windows.Forms.Control.Font%2A> `null`. stattdessen wird die-Eigenschaft des übergeordneten `null`Elements angezeigt, wenn dies nicht der Fall ist. oder der Standard <xref:System.Windows.Forms.Control.Font%2A> Wert, der <xref:System.Windows.Forms.Control>in definiert ist. Daher kann der Standardwert `MyFont` für nicht einfach festgelegt werden, <xref:System.ComponentModel.DefaultValueAttribute> und ein kann nicht auf diese Eigenschaft angewendet werden. Stattdessen müssen die `ShouldSerialize` - `Reset` Methode und die-Methode für `MyFont` die-Eigenschaft implementiert werden.

## <a name="see-also"></a>Siehe auch

- [Eigenschaften in Windows Forms-Steuerelementen](properties-in-windows-forms-controls.md)
- [Definieren einer Eigenschaft](defining-a-property-in-windows-forms-controls.md)
- [Durch geänderte Eigenschaften ausgelöste Ereignisse](property-changed-events.md)

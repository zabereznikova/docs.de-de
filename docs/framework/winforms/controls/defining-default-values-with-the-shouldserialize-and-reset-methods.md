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
ms.openlocfilehash: 11181bacdb919693ffc82c48c061357463a6343b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74336763"
---
# <a name="defining-default-values-with-the-shouldserialize-and-reset-methods"></a><span data-ttu-id="6eaa8-102">Definieren von Standardwerten mit der ShouldSerialize-Methode und der Reset-Methode</span><span class="sxs-lookup"><span data-stu-id="6eaa8-102">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>
<span data-ttu-id="6eaa8-103">`ShouldSerialize` und `Reset` sind optionale Methoden, die Sie für eine-Eigenschaft bereitstellen können, wenn die-Eigenschaft keinen einfachen Standardwert hat.</span><span class="sxs-lookup"><span data-stu-id="6eaa8-103">`ShouldSerialize` and `Reset` are optional methods that you can provide for a property, if the property does not a have simple default value.</span></span> <span data-ttu-id="6eaa8-104">Wenn die Eigenschaft über einen einfachen Standardwert verfügt, sollten Sie den <xref:System.ComponentModel.DefaultValueAttribute> anwenden und stattdessen den Standardwert für den attributklassenkonstruktor angeben.</span><span class="sxs-lookup"><span data-stu-id="6eaa8-104">If the property has a simple default value, you should apply the <xref:System.ComponentModel.DefaultValueAttribute> and supply the default value to the attribute class constructor instead.</span></span> <span data-ttu-id="6eaa8-105">Beide Mechanismen ermöglichen die folgenden Funktionen im Designer:</span><span class="sxs-lookup"><span data-stu-id="6eaa8-105">Either of these mechanisms enables the following features in the designer:</span></span>

- <span data-ttu-id="6eaa8-106">Die-Eigenschaft stellt im Eigenschaften Browser eine visuelle Anzeige dar, wenn Sie von ihrem Standardwert geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="6eaa8-106">The property provides visual indication in the property browser if it has been modified from its default value.</span></span>

- <span data-ttu-id="6eaa8-107">Der Benutzer kann mit der rechten Maustaste auf die Eigenschaft klicken und **Zurücksetzen** auswählen, um die Eigenschaft auf den Standardwert wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="6eaa8-107">The user can right-click on the property and choose **Reset** to restore the property to its default value.</span></span>

- <span data-ttu-id="6eaa8-108">Der Designer generiert effizienteren Code.</span><span class="sxs-lookup"><span data-stu-id="6eaa8-108">The designer generates more efficient code.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6eaa8-109">Wenden Sie entweder den <xref:System.ComponentModel.DefaultValueAttribute> an, oder stellen Sie `Reset`*propertyName* -und `ShouldSerialize`*propertyName* -Methode bereit.</span><span class="sxs-lookup"><span data-stu-id="6eaa8-109">Either apply the <xref:System.ComponentModel.DefaultValueAttribute> or provide `Reset`*PropertyName* and `ShouldSerialize`*PropertyName* methods.</span></span> <span data-ttu-id="6eaa8-110">Verwenden Sie nicht beides.</span><span class="sxs-lookup"><span data-stu-id="6eaa8-110">Do not use both.</span></span>

 <span data-ttu-id="6eaa8-111">Mit der `Reset`*propertyName* -Methode wird eine Eigenschaft auf ihren Standardwert festgelegt, wie im folgenden Code Fragment dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6eaa8-111">The `Reset`*PropertyName* method sets a property to its default value, as shown in the following code fragment.</span></span>

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
> <span data-ttu-id="6eaa8-112">Wenn eine Eigenschaft nicht über eine `Reset`-Methode verfügt, nicht mit einem <xref:System.ComponentModel.DefaultValueAttribute>gekennzeichnet ist und in der Deklaration kein Standardwert angegeben ist, wird die `Reset`-Option für diese Eigenschaft im Kontextmenü des Fensters **Eigenschaften** der Windows Forms-Designer in Visual Studio deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="6eaa8-112">If a property does not have a `Reset` method, is not marked with a <xref:System.ComponentModel.DefaultValueAttribute>, and does not have a default value supplied in its declaration, the `Reset` option for that property is disabled in the shortcut menu of the **Properties** window of the Windows Forms Designer in Visual Studio.</span></span>

 <span data-ttu-id="6eaa8-113">Designer wie Visual Studio verwenden die `ShouldSerialize`*propertyName* -Methode, um zu überprüfen, ob eine Eigenschaft von ihrem Standardwert geändert wurde, und schreiben Code nur in das Formular, wenn eine Eigenschaft geändert wird, was eine effizientere Codegenerierung ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="6eaa8-113">Designers such as Visual Studio use the `ShouldSerialize`*PropertyName* method to check whether a property has changed from its default value and write code into the form only if a property is changed, thus allowing for more efficient code generation.</span></span> <span data-ttu-id="6eaa8-114">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6eaa8-114">For example:</span></span>

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

 <span data-ttu-id="6eaa8-115">Ein umfassendes Codebeispiel folgt.</span><span class="sxs-lookup"><span data-stu-id="6eaa8-115">A complete code example follows.</span></span>

```vb
Option Explicit
Option Strict

Imports System.Drawing
Imports System.Windows.Forms

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
using System.Drawing;
using System.Windows.Forms;

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

 <span data-ttu-id="6eaa8-116">In diesem Fall wird der Eigenschaften Browser nicht `null`angezeigt, auch wenn der Wert der privaten Variablen, auf die die `MyFont`-Eigenschaft zugreift, `null`ist. Stattdessen wird die <xref:System.Windows.Forms.Control.Font%2A>-Eigenschaft des übergeordneten Elements angezeigt, wenn es nicht `null`ist, oder der Standard <xref:System.Windows.Forms.Control.Font%2A> Wert, der in <xref:System.Windows.Forms.Control>definiert ist.</span><span class="sxs-lookup"><span data-stu-id="6eaa8-116">In this case, even when the value of the private variable accessed by the `MyFont` property is `null`, the property browser does not display `null`; instead, it displays the <xref:System.Windows.Forms.Control.Font%2A> property of the parent, if it is not `null`, or the default <xref:System.Windows.Forms.Control.Font%2A> value defined in <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="6eaa8-117">Daher kann der Standardwert für `MyFont` nicht einfach festgelegt werden, und ein <xref:System.ComponentModel.DefaultValueAttribute> kann nicht auf diese Eigenschaft angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="6eaa8-117">Thus the default value for `MyFont` cannot be simply set, and a <xref:System.ComponentModel.DefaultValueAttribute> cannot be applied to this property.</span></span> <span data-ttu-id="6eaa8-118">Stattdessen müssen die Methoden `ShouldSerialize` und `Reset` für die Eigenschaft `MyFont` implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="6eaa8-118">Instead, the `ShouldSerialize` and `Reset` methods must be implemented for the `MyFont` property.</span></span>

## <a name="see-also"></a><span data-ttu-id="6eaa8-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6eaa8-119">See also</span></span>

- [<span data-ttu-id="6eaa8-120">Eigenschaften in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="6eaa8-120">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="6eaa8-121">Definieren einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="6eaa8-121">Defining a Property</span></span>](defining-a-property-in-windows-forms-controls.md)
- [<span data-ttu-id="6eaa8-122">Durch geänderte Eigenschaften ausgelöste Ereignisse</span><span class="sxs-lookup"><span data-stu-id="6eaa8-122">Property-Changed Events</span></span>](property-changed-events.md)

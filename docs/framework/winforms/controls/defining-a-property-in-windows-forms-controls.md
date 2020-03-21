---
title: Definieren von Steuerelementeigenschaften
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties [Windows Forms], defining in code
- custom controls [Windows Forms], defining properties in code
ms.assetid: c2eb8277-a842-4d99-89a9-647b901a0434
ms.openlocfilehash: 7223f8c88bee4ee9c1db621cc39bbcf70d0c4589
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182370"
---
# <a name="defining-a-property-in-windows-forms-controls"></a><span data-ttu-id="763ae-102">Definieren einer Eigenschaft in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="763ae-102">Defining a Property in Windows Forms Controls</span></span>
<span data-ttu-id="763ae-103">Eine Übersicht über Eigenschaften finden Sie unter [Übersicht über Eigenschaften](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="763ae-103">For an overview of properties, see [Properties Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v=vs.120)).</span></span> <span data-ttu-id="763ae-104">Es gibt einige wichtige Überlegungen beim Definieren einer Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="763ae-104">There are a few important considerations when defining a property:</span></span>  
  
- <span data-ttu-id="763ae-105">Sie müssen auf die Eigenschaften, die Sie definieren, Attribute anwenden.</span><span class="sxs-lookup"><span data-stu-id="763ae-105">You must apply attributes to the properties you define.</span></span> <span data-ttu-id="763ae-106">Attribute geben an, wie der Designer eine Eigenschaft anzeigen sollte.</span><span class="sxs-lookup"><span data-stu-id="763ae-106">Attributes specify how the designer should display a property.</span></span> <span data-ttu-id="763ae-107">Einzelheiten hierzu finden Sie unter [Attribute für Komponenten in der Entwurfszeit](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="763ae-107">For details, see [Design-Time Attributes for Components](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120)).</span></span>  
  
- <span data-ttu-id="763ae-108">Wenn sich das Ändern der Eigenschaft auf <xref:System.Windows.Forms.Control.Invalidate%2A> die visuelle Anzeige des Steuerelements auswirkt, rufen Sie die Methode (von <xref:System.Windows.Forms.Control>der das Steuerelement erbt) vom `set` Accessor auf.</span><span class="sxs-lookup"><span data-stu-id="763ae-108">If changing the property affects the visual display of the control, call the <xref:System.Windows.Forms.Control.Invalidate%2A> method (that your control inherits from <xref:System.Windows.Forms.Control>) from the `set` accessor.</span></span> <span data-ttu-id="763ae-109"><xref:System.Windows.Forms.Control.Invalidate%2A>Ruft wiederum <xref:System.Windows.Forms.Control.OnPaint%2A> die Methode auf, die das Steuerelement neu zeichnet.</span><span class="sxs-lookup"><span data-stu-id="763ae-109"><xref:System.Windows.Forms.Control.Invalidate%2A> in turn calls the <xref:System.Windows.Forms.Control.OnPaint%2A> method, which redraws the control.</span></span> <span data-ttu-id="763ae-110">Mehrere Aufrufe, die zu <xref:System.Windows.Forms.Control.Invalidate%2A> <xref:System.Windows.Forms.Control.OnPaint%2A> einem einzigen Aufruf zur Effizienz führen.</span><span class="sxs-lookup"><span data-stu-id="763ae-110">Multiple calls to <xref:System.Windows.Forms.Control.Invalidate%2A> result in a single call to <xref:System.Windows.Forms.Control.OnPaint%2A> for efficiency.</span></span>  
  
- <span data-ttu-id="763ae-111">Die .NET Framework-Klassenbibliothek stellt Typkonverter für häufig verwendete Datentypen wie z.B. ganze Zahlen, Dezimalzahlen, boolesche Werte und andere bereit.</span><span class="sxs-lookup"><span data-stu-id="763ae-111">The .NET Framework class library provides type converters for common data types such as integers, decimal numbers, Boolean values, and others.</span></span> <span data-ttu-id="763ae-112">Der Zweck eines Typkonverters ist im Allgemeinen, die Konvertierung von einer Zeichenfolge in einen Wert (von Zeichenfolgedaten in andere Datentypen) bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="763ae-112">The purpose of a type converter is generally to provide string-to-value conversion (from string data to other data types).</span></span> <span data-ttu-id="763ae-113">Allgemeine Datentypen sind Standardtypkonverter, die Werte in Zeichenfolgen und Zeichenfolgen in die entsprechenden Datentypen konvertieren.</span><span class="sxs-lookup"><span data-stu-id="763ae-113">Common data types are associated with default type converters that convert values into strings and strings into the appropriate data types.</span></span> <span data-ttu-id="763ae-114">Wenn Sie eine Eigenschaft definieren (d.h. nicht dem Standard entsprechend), die einen benutzerdefinierten Datentyp aufweist, müssen Sie ein Attribut anwenden, das den dieser Eigenschaft zuzuordnenden Typkonverter angibt.</span><span class="sxs-lookup"><span data-stu-id="763ae-114">If you define a property that is a custom (that is, nonstandard) data type, you will have to apply an attribute that specifies the type converter to associate with that property.</span></span> <span data-ttu-id="763ae-115">Sie können ein Attribut auch verwenden, um einer Eigenschaft einen benutzerdefinierten Typeditor für die Benutzeroberfläche zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="763ae-115">You can also use an attribute to associate a custom UI type editor with a property.</span></span> <span data-ttu-id="763ae-116">Ein Typeditor für die Benutzeroberfläche stellt eine Benutzeroberfläche für die Bearbeitung einer Eigenschaft oder eines Datentyps bereit.</span><span class="sxs-lookup"><span data-stu-id="763ae-116">A UI type editor provides a user interface for editing a property or data type.</span></span> <span data-ttu-id="763ae-117">So ist beispielsweise ein Farbwähler ein Typeditor für die Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="763ae-117">A color picker is an example of a UI type editor.</span></span> <span data-ttu-id="763ae-118">Beispiele für Attribute werden am Ende dieses Themas angegeben.</span><span class="sxs-lookup"><span data-stu-id="763ae-118">Examples of attributes are given at the end of this topic.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="763ae-119">Wenn für Ihre benutzerdefinierte Eigenschaft kein Typkonverter oder Typeditor für die Benutzeroberfläche verfügbar ist, können Sie einen implementieren, wie unter [Erweitern der Entwurfszeitunterstützung](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="763ae-119">If a type converter or a UI type editor is not available for your custom property, you can implement one as described in [Extending Design-Time Support](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120)).</span></span>  
  
 <span data-ttu-id="763ae-120">Das folgende Codefragment definiert eine benutzerdefinierte Eigenschaft mit dem Namen `EndColor` für das benutzerdefinierte Steuerelement `FlashTrackBar`.</span><span class="sxs-lookup"><span data-stu-id="763ae-120">The following code fragment defines a custom property named `EndColor` for the custom control `FlashTrackBar`.</span></span>  
  
```vb  
Public Class FlashTrackBar  
   Inherits Control  
   ...  
   ' Private data member that backs the EndColor property.  
   Private _endColor As Color = Color.LimeGreen  
  
   ' The Category attribute tells the designer to display  
   ' it in the Flash grouping.
   ' The Description attribute provides a description of  
   ' the property.
   <Category("Flash"), _  
   Description("The ending color of the bar.")>  _  
   Public Property EndColor() As Color  
      ' The public property EndColor accesses _endColor.  
      Get  
         Return _endColor  
      End Get  
      Set  
         _endColor = value  
         If Not (baseBackground Is Nothing) And showGradient Then  
            baseBackground.Dispose()  
            baseBackground = Nothing  
         End If  
         ' The Invalidate method calls the OnPaint method, which redraws
         ' the control.  
         Invalidate()  
      End Set  
   End Property  
   ...  
End Class  
```  
  
```csharp  
public class FlashTrackBar : Control {  
   ...  
   // Private data member that backs the EndColor property.  
   private Color endColor = Color.LimeGreen;  
   // The Category attribute tells the designer to display  
   // it in the Flash grouping.
   // The Description attribute provides a description of  
   // the property.
   [  
   Category("Flash"),  
   Description("The ending color of the bar.")  
   ]  
   // The public property EndColor accesses endColor.  
   public Color EndColor {  
      get {  
         return endColor;  
      }  
      set {  
         endColor = value;  
         if (baseBackground != null && showGradient) {  
            baseBackground.Dispose();  
            baseBackground = null;  
         }  
         // The Invalidate method calls the OnPaint method, which redraws
         // the control.  
         Invalidate();  
      }  
   }  
   ...  
}  
```  
  
 <span data-ttu-id="763ae-121">Das folgende Codefragment ordnet der Eigenschaft `Value` einen Typkonverter und einen Typeditor für die Benutzeroberfläche zu.</span><span class="sxs-lookup"><span data-stu-id="763ae-121">The following code fragment associates a type converter and a UI type editor with the property `Value`.</span></span> <span data-ttu-id="763ae-122">In diesem `Value` Fall handelt es sich um eine ganze <xref:System.ComponentModel.TypeConverterAttribute> Zahl, die über`FlashTrackBarValueConverter`einen Standardtypkonverter verfügt, aber das Attribut wendet einen benutzerdefinierten Typkonverter ( ) an, der es dem Designer ermöglicht, ihn als Prozentsatz anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="763ae-122">In this case `Value` is an integer and has a default type converter, but the <xref:System.ComponentModel.TypeConverterAttribute> attribute applies a custom type converter (`FlashTrackBarValueConverter`) that enables the designer to display it as a percentage.</span></span> <span data-ttu-id="763ae-123">Im Typeditor für die Benutzeroberfläche, `FlashTrackBarValueEditor`, kann der Prozentwert visuell angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="763ae-123">The UI type editor, `FlashTrackBarValueEditor`, allows the percentage to be displayed visually.</span></span> <span data-ttu-id="763ae-124">Dieses Beispiel zeigt auch, dass der <xref:System.ComponentModel.TypeConverterAttribute> vom <xref:System.ComponentModel.EditorAttribute> oder-Attribut angegebene Typkonverter oder -editor den Standardkonverter überschreibt.</span><span class="sxs-lookup"><span data-stu-id="763ae-124">This example also shows that the type converter or editor specified by the <xref:System.ComponentModel.TypeConverterAttribute> or <xref:System.ComponentModel.EditorAttribute> attribute overrides the default converter.</span></span>  
  
```vb  
<Category("Flash"), _  
TypeConverter(GetType(FlashTrackBarValueConverter)), _  
Editor(GetType(FlashTrackBarValueEditor), _  
GetType(UITypeEditor)), _  
Description("The current value of the track bar.  You can enter an actual value or a percentage.")>  _  
Public ReadOnly Property Value() As Integer  
...  
End Property  
```  
  
```csharp  
[  
Category("Flash"),
TypeConverter(typeof(FlashTrackBarValueConverter)),  
Editor(typeof(FlashTrackBarValueEditor), typeof(UITypeEditor)),  
Description("The current value of the track bar.  You can enter an actual value or a percentage.")  
]  
public int Value {  
...  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="763ae-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="763ae-125">See also</span></span>

- [<span data-ttu-id="763ae-126">Eigenschaften von Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="763ae-126">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="763ae-127">Definieren von Standardwerten mit der ShouldSerialize-Methode und der Reset-Methode</span><span class="sxs-lookup"><span data-stu-id="763ae-127">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>](defining-default-values-with-the-shouldserialize-and-reset-methods.md)
- [<span data-ttu-id="763ae-128">Durch geänderte Eigenschaften ausgelöste Ereignisse</span><span class="sxs-lookup"><span data-stu-id="763ae-128">Property-Changed Events</span></span>](property-changed-events.md)
- [<span data-ttu-id="763ae-129">Attribute in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="763ae-129">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)

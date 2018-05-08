---
title: Definieren einer Eigenschaft in Windows Forms-Steuerelementen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties [Windows Forms], defining in code
- custom controls [Windows Forms], defining properties in code
ms.assetid: c2eb8277-a842-4d99-89a9-647b901a0434
ms.openlocfilehash: dc47d7152419d55b3e52aec70257e2b39e9aaca0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="defining-a-property-in-windows-forms-controls"></a>Definieren einer Eigenschaft in Windows Forms-Steuerelementen
Eine Übersicht über Eigenschaften finden Sie unter [Übersicht über Eigenschaften](http://msdn.microsoft.com/library/8f1a1ff1-0f05-40e0-bfdf-80de8fff7d52). Es gibt einige wichtige Überlegungen beim Definieren einer Eigenschaft:  
  
-   Sie müssen auf die Eigenschaften, die Sie definieren, Attribute anwenden. Attribute geben an, wie der Designer eine Eigenschaft anzeigen sollte. Einzelheiten hierzu finden Sie unter [Attribute für Komponenten in der Entwurfszeit](http://msdn.microsoft.com/library/12050fe3-9327-4509-9e21-4ee2494b95c3).  
  
-   Wenn die visuelle Darstellung des Steuerelements ändern der Eigenschaft betroffen sind, rufen die <xref:System.Windows.Forms.Control.Invalidate%2A> Methode (, die das Steuerelement erbt von <xref:System.Windows.Forms.Control>) aus der `set` Accessor. <xref:System.Windows.Forms.Control.Invalidate%2A> Ruft die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode, die das Steuerelement neu gezeichnet wird. Mehrere Aufrufe <xref:System.Windows.Forms.Control.Invalidate%2A> führen zu einem einzigen Aufruf <xref:System.Windows.Forms.Control.OnPaint%2A> Gründen der Effizienz.  
  
-   Die .NET Framework-Klassenbibliothek stellt Typkonverter für häufig verwendete Datentypen wie z.B. ganze Zahlen, Dezimalzahlen, boolesche Werte und andere bereit. Der Zweck eines Typkonverters ist im Allgemeinen, die Konvertierung von einer Zeichenfolge in einen Wert (von Zeichenfolgedaten in andere Datentypen) bereitzustellen. Allgemeine Datentypen sind Standardtypkonverter, die Werte in Zeichenfolgen und Zeichenfolgen in die entsprechenden Datentypen konvertieren. Wenn Sie eine Eigenschaft definieren (d.h. nicht dem Standard entsprechend), die einen benutzerdefinierten Datentyp aufweist, müssen Sie ein Attribut anwenden, das den dieser Eigenschaft zuzuordnenden Typkonverter angibt. Sie können ein Attribut auch verwenden, um einer Eigenschaft einen benutzerdefinierten Typeditor für die Benutzeroberfläche zuzuordnen. Ein Typeditor für die Benutzeroberfläche stellt eine Benutzeroberfläche für die Bearbeitung einer Eigenschaft oder eines Datentyps bereit. So ist beispielsweise ein Farbwähler ein Typeditor für die Benutzeroberfläche. Beispiele für Attribute werden am Ende dieses Themas angegeben.  
  
    > [!NOTE]
    >  Wenn für Ihre benutzerdefinierte Eigenschaft kein Typkonverter oder Typeditor für die Benutzeroberfläche verfügbar ist, können Sie einen implementieren, wie unter [Erweitern der Entwurfszeitunterstützung](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2).  
  
 Das folgende Codefragment definiert eine benutzerdefinierte Eigenschaft mit dem Namen `EndColor` für das benutzerdefinierte Steuerelement `FlashTrackBar`.  
  
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
  
 Das folgende Codefragment ordnet der Eigenschaft `Value` einen Typkonverter und einen Typeditor für die Benutzeroberfläche zu. In diesem Fall `Value` ist eine ganze Zahl und verfügt über einen Standard-Typkonverter, aber die <xref:System.ComponentModel.TypeConverterAttribute> Attribut angewendet wird, einen benutzerdefinierten Typkonverter (`FlashTrackBarValueConverter`) mit der der Designer für die anzuzeigenden als Prozentsatz. Im Typeditor für die Benutzeroberfläche, `FlashTrackBarValueEditor`, kann der Prozentwert visuell angezeigt werden. In diesem Beispiel wird außerdem gezeigt, dass der Typkonverter oder Editor gemäß der <xref:System.ComponentModel.TypeConverterAttribute> oder <xref:System.ComponentModel.EditorAttribute> Attribut überschreibt der Standardkonverter.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaften in Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)  
 [Definieren von Standardwerten mit der ShouldSerialize-Methode und der Reset-Methode](../../../../docs/framework/winforms/controls/defining-default-values-with-the-shouldserialize-and-reset-methods.md)  
 [Durch geänderte Eigenschaften ausgelöste Ereignisse](../../../../docs/framework/winforms/controls/property-changed-events.md)  
 [Attribute in Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)

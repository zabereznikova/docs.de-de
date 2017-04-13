---
title: "Definieren einer Eigenschaft in Windows&#160;Forms-Steuerelementen | Microsoft Docs"
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
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Definieren von Eigenschaften im Code"
  - "Eigenschaften [Windows Forms], Definieren im Code"
ms.assetid: c2eb8277-a842-4d99-89a9-647b901a0434
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Definieren einer Eigenschaft in Windows&#160;Forms-Steuerelementen
Eine Übersicht über Eigenschaften finden Sie unter [Properties Overview](../Topic/Properties%20Overview.md).  Beim Definieren von Eigenschaften sind einige wichtige Aspekte zu beachten:  
  
-   Sie müssen den Eigenschaften, die Sie definieren, Attribute zuweisen.  Attribute legen fest, wie der Designer eine Eigenschaft anzeigen soll.  Ausführliche Informationen finden Sie unter [Design\-Time Attributes for Components](../Topic/Design-Time%20Attributes%20for%20Components.md).  
  
-   Wenn sich die Änderung der Eigenschaft auf die visuelle Darstellung des Steuerelements auswirkt, rufen Sie die <xref:System.Windows.Forms.Control.Invalidate%2A>\-Methode \(die das Steuerelement von <xref:System.Windows.Forms.Control> geerbt hat\) vom `set`\-Accessor auf.  Dagegen ruft <xref:System.Windows.Forms.Control.Invalidate%2A> die <xref:System.Windows.Forms.Control.OnPaint%2A>\-Methode auf, durch die das Steuerelement neu gezeichnet wird.  Aus Effizienzgründen wird das mehrmalige Aufrufen von <xref:System.Windows.Forms.Control.Invalidate%2A> zu einem einzigen Aufruf von <xref:System.Windows.Forms.Control.OnPaint%2A> zusammengefasst.  
  
-   Die.NET Framework\-Klassenbibliothek stellt Typkonverter für häufig verwendete Datentypen wie ganze Zahlen, Dezimalwerte, boolesche Werte und andere bereit.  Typkonverter werden in erster Linie für Umwandlungen von Zeichenfolgen in Werte verwendet \(von Zeichenfolgendaten in andere Datentypen\).  Geläufige Datentypen werden Standardtypkonvertern zugeordnet, die Werte in Zeichenfolgen bzw. Zeichenfolgendaten in die entsprechenden Datentypen konvertieren.  Wenn Sie eine Eigenschaft definieren, die ein benutzerdefinierter Datentyp ist \(d. h. kein Standardtyp\), müssen Sie ein Attribut zur Festlegung des Typkonverters anwenden, der dieser Eigenschaft zugewiesen wird.  Sie können auch ein Attribut verwenden, um einem benutzerdefinierten Typ\-Editor für Benutzeroberflächen eine Eigenschaft zuzuweisen.  Ein Typ\-Editor für Benutzeroberflächen stellt eine Benutzeroberfläche zur Bearbeitung von Eigenschaften oder Datentypen bereit.  Ein Beispiel für einen Typ\-Editor für Benutzeroberflächen ist die Farbauswahl.  Beispiele für Attribute werden am Ende dieses Themas gegeben.  
  
    > [!NOTE]
    >  Wenn kein Typkonverter oder Typ\-Editor für Benutzeroberflächen für die benutzerdefinierte Eigenschaft verfügbar ist, können Sie diesen gemäß der Beschreibung in [Extending Design\-Time Support](../Topic/Extending%20Design-Time%20Support.md) implementieren.  
  
 Im folgenden Codefragment wird eine benutzerdefinierte Eigenschaft mit dem Namen `EndColor` für das benutzerdefinierte Steuerelement `FlashTrackBar` definiert.  
  
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
  
 Im folgenden Codefragment wird einem Typkonverter und einem Typ\-Editor für Benutzeroberflächen die Eigenschaft `Value` zugewiesen.  In diesem Fall handelt es sich bei `Value` um eine ganze Zahl mit einem Standardtypkonverter. Allerdings wendet das <xref:System.ComponentModel.TypeConverterAttribute>\-Attribut einen benutzerdefinierten Typkonverter \(`FlashTrackBarValueConverter`\) an, wodurch der Designer die Eigenschaft als Prozentsatz anzeigt.  Der Typ\-Editor für Benutzeroberflächen, `FlashTrackBarValueEditor`, ermöglicht die visuelle Darstellung der Prozentangabe.  In diesem Beispiel wird auch deutlich, dass der Standardkonverter durch den Typkonverter bzw. Typ\-Editor überschrieben wird, der durch das Attribut <xref:System.ComponentModel.TypeConverterAttribute> oder <xref:System.ComponentModel.EditorAttribute> festgelegt wurde.  
  
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
  
## Siehe auch  
 [Eigenschaften von Windows Forms\-Steuerelementen](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)   
 [Definieren von Standardwerten mit der ShouldSerialize\-Methode und der Reset\-Methode](../../../../docs/framework/winforms/controls/defining-default-values-with-the-shouldserialize-and-reset-methods.md)   
 [Durch geänderte Eigenschaften ausgelöste Ereignisse](../../../../docs/framework/winforms/controls/property-changed-events.md)   
 [Attribute in Windows Forms\-Steuerelementen](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)
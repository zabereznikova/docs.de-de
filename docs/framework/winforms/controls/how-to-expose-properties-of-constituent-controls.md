---
title: "Gewusst wie: Verf&#252;gbarmachen der Eigenschaften konstituierender Steuerelemente | Microsoft Docs"
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
  - "Konstituierende Steuerelemente"
  - "Steuerelemente [Windows Forms], Konstituierende"
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Verfügbarmachen von Eigenschaften"
  - "Benutzersteuerelemente [Windows Forms], Verfügbarmachen von konstituierenden Steuerelementen"
ms.assetid: 5c1ec98b-aa48-4823-986e-4712551cfdf1
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Verf&#252;gbarmachen der Eigenschaften konstituierender Steuerelemente
Die Steuerelemente, aus denen ein zusammengesetztes Steuerelement besteht, werden als *konstituierende Steuerelemente* bezeichnet.  Sie werden im Allgemeinen als privat deklariert, daher kann der Entwickler nicht auf sie zugreifen.  Wenn Eigenschaften dieser Steuerelemente zukünftigen Benutzern verfügbar gemacht werden sollen, müssen sie dem Benutzer gegenüber verfügbar gemacht werden.  Eine Eigenschaft eines konstituierenden Steuerelements wird verfügbar gemacht, indem eine Eigenschaft im Benutzersteuerelement erstellt wird. Anschließend werden die Accessoren `get` und `set` dieser Eigenschaft verwendet, um die Änderung in der privaten Eigenschaft des konstituierenden Steuerelements auszuführen.  
  
 Stellen Sie sich ein hypothetisches Benutzersteuerelement mit einer konstituierenden Schaltfläche mit dem Namen `MyButton` vor.  Wenn ein Benutzer in diesem Beispiel die `ConstituentButtonBackColor`\-Eigenschaft anfordert, wird der Wert übermittelt, der in der <xref:System.Windows.Forms.Control.BackColor%2A>\-Eigenschaft von `MyButton` gespeichert ist.  Wenn der Benutzer dieser Eigenschaft einen Wert zuweist, wird dieser automatisch an die <xref:System.Windows.Forms.Control.BackColor%2A>\-Eigenschaft von `MyButton` übergeben. Außerdem wird der `set`\-Code ausgeführt, sodass sich die Farbe von `MyButton` ändert.  
  
 Im nachstehenden Beispiel wird gezeigt, wie die <xref:System.Windows.Forms.Control.BackColor%2A>\-Eigenschaft der konstituierenden Schaltfläche verfügbar gemacht wird:  
  
```vb  
Public Property ButtonColor() as System.Drawing.Color  
   Get  
      Return MyButton.BackColor  
   End Get  
   Set(Value as System.Drawing.Color)  
      MyButton.BackColor = Value  
   End Set  
End Property  
```  
  
```csharp  
public Color ButtonColor  
{  
   get  
   {  
      return(myButton.BackColor);  
   }  
   set  
   {  
      myButton.BackColor = value;  
   }  
}  
```  
  
### So machen Sie eine Eigenschaft eines konstituierenden Steuerelements verfügbar  
  
1.  Erstellen Sie eine öffentliche Eigenschaft für das Benutzersteuerelement.  
  
2.  Schreiben Sie im `get`\-Abschnitt der Eigenschaft Code, mit dem der Wert der Eigenschaft abgerufen wird, die verfügbar gemacht werden soll.  
  
3.  Schreiben Sie im `set`\-Abschnitt der Eigenschaft Code, mit dem der Wert der Eigenschaft an die verfügbar gemachte Eigenschaft des konstituierenden Steuerelements übergeben wird.  
  
## Siehe auch  
 <xref:System.Windows.Forms.UserControl>   
 [Eigenschaften von Windows Forms\-Steuerelementen](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)   
 [Arten von benutzerdefinierten Steuerelementen](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
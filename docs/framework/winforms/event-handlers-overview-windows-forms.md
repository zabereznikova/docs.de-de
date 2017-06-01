---
title: "&#220;bersicht &#252;ber Ereignishandler (Windows&#160;Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Ereignishandler, Informationen über Ereignishandler"
  - "Ereignisbehandlung, Windows Forms"
  - "Windows Forms, Ereignisbehandlung"
ms.assetid: 228112e1-1711-42ee-8ffa-ff3555bffe66
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# &#220;bersicht &#252;ber Ereignishandler (Windows&#160;Forms)
Ein Ereignishandler ist eine an ein Ereignis gebundene Methode.  Sobald das Ereignis ausgelöst wird, wird der Code innerhalb des Ereignishandlers ausgeführt.  Jeder Ereignishandler verfügt über zwei Parameter, die es Ihnen ermöglichen, ein Ereignis auf geeignete Weise zu behandeln.  Das folgende Beispiel enthält einen Ereignishandler für das <xref:System.Windows.Forms.Control.Click>\-Ereignis eines <xref:System.Windows.Forms.Button>\-Steuerelements.  
  
```vb  
Private Sub button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles button1.Click  
  
End Sub  
  
```  
  
```csharp  
private void button1_Click(object sender, System.EventArgs e)   
{  
  
}  
  
```  
  
```cpp  
private:  
  void button1_Click(System::Object ^ sender,  
    System::EventArgs ^ e)  
  {  
  
  }  
```  
  
 Der erste Parameter,`sender`, gibt einen Verweis auf das Objekt, durch den das Ereignis ausgelöst wurde.  Der zweite Parameter, im obigen Beispiel `e`, übergibt ein für das behandelte Ereignis spezifisches Objekt.  Durch einen Verweis auf die Objekteigenschaften \(und, falls erforderlich, auch auf seine Methoden\) können Sie spezifische Informationen abrufen: Bei Mausereignissen beispielsweise die Position des Mauszeigers oder bei Drag & Drop\-Ereignissen die verschobenen Daten.  
  
 Jedes Ereignis erzeugt in der Regel einen Ereignishandler, der für den zweiten Parameter einen anderen Ereignisobjekttyp verwendet.  Bei einigen Ereignishandlern, z. B. denen für die Ereignisse <xref:System.Windows.Forms.Control.MouseDown> und <xref:System.Windows.Forms.Control.MouseUp>, sind die Objekttypen des ersten und zweiten Parameters identisch.  Für diese Ereignistypen kann derselbe Ereignishandler zur Behandlung beider Ereignisse verwendet werden.  
  
 Sie können auch ein\- und denselben Ereignishandler einsetzen, um dasselbe Ereignis für unterschiedliche Steuerelemente zu verarbeiten.  Wenn ein Formular beispielsweise eine Gruppe von <xref:System.Windows.Forms.RadioButton>\-Steuerelementen enthält, könnten Sie einen einzelnen Ereignishandler für das <xref:System.Windows.Forms.Control.Click>\-Ereignis erstellen und das <xref:System.Windows.Forms.Control.Click>\-Ereignis jedes Steuerelements an den einzelnen Ereignishandler binden lassen.  Weitere Informationen finden Sie unter [Gewusst wie: Verbinden mehrerer Ereignisse mit einem einzelnen Ereignishandler in Windows Forms](../../../docs/framework/winforms/how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).  
  
## Siehe auch  
 [Erstellen von Ereignishandlern in Windows Forms](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)   
 [Übersicht über Ereignisse](../../../docs/framework/winforms/events-overview-windows-forms.md)
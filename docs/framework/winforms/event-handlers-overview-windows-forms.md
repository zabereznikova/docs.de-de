---
title: Übersicht über Ereignishandler
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handling [Windows Forms], Windows Forms
- event handlers [Windows Forms], about event handlers
ms.assetid: 228112e1-1711-42ee-8ffa-ff3555bffe66
ms.openlocfilehash: 10ba458197973ede35849a86fec35003f139b8d2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743498"
---
# <a name="event-handlers-overview-windows-forms"></a>Übersicht über Ereignishandler (Windows Forms)
Ein Ereignishandler ist eine Methode, die an ein Ereignis gebunden ist. Wenn das-Ereignis ausgelöst wird, wird der Code im-Ereignishandler ausgeführt. Jeder Ereignishandler stellt zwei Parameter bereit, mit denen Sie das Ereignis ordnungsgemäß behandeln können. Das folgende Beispiel zeigt einen Ereignishandler für das <xref:System.Windows.Forms.Control.Click> Ereignis eines <xref:System.Windows.Forms.Button>-Steuer Elements.  
  
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
  
 Der erste Parameter,`sender`, stellt einen Verweis auf das Objekt bereit, das das Ereignis ausgelöst hat. Der zweite Parameter, `e`im obigen Beispiel, übergibt ein Objekt, das für das behandelte Ereignis spezifisch ist. Wenn Sie auf die Eigenschaften des Objekts (und manchmal auf seine Methoden) verweisen, können Sie Informationen wie die Position der Maus für Mausereignisse oder Daten abrufen, die in Drag & Drop-Ereignissen übertragen werden.  
  
 In der Regel erzeugt jedes Ereignis einen Ereignishandler mit einem anderen Ereignis Objekttyp für den zweiten Parameter. Einige Ereignishandler, z. b. die Ereignisse für das <xref:System.Windows.Forms.Control.MouseDown>-Ereignis und das <xref:System.Windows.Forms.Control.MouseUp>-Ereignis, haben den gleichen Objekttyp für den zweiten Parameter. Für diese Ereignis Typen können Sie denselben Ereignishandler zum Verarbeiten beider Ereignisse verwenden.  
  
 Sie können auch denselben Ereignishandler verwenden, um das gleiche Ereignis für verschiedene Steuerelemente zu verarbeiten. Wenn Sie z. b. über eine Gruppe von <xref:System.Windows.Forms.RadioButton>-Steuerelementen in einem Formular verfügen, können Sie einen einzelnen Ereignishandler für das <xref:System.Windows.Forms.Control.Click>-Ereignis erstellen und festlegen, dass das <xref:System.Windows.Forms.Control.Click> Ereignis jedes Steuer Elements an den einzelnen Ereignishandler gebunden ist. Weitere Informationen finden Sie unter Gewusst [wie: Verbinden mehrerer Ereignisse mit einem einzelnen Ereignis Handler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen von Ereignishandlern in Windows Forms](creating-event-handlers-in-windows-forms.md)
- [Übersicht über Ereignisse](events-overview-windows-forms.md)

---
title: Übersicht über Ereignishandler (Windows Forms)
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
ms.openlocfilehash: 05acbfaf427060d015c2445360a7d73ebe97d070
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61966828"
---
# <a name="event-handlers-overview-windows-forms"></a>Übersicht über Ereignishandler (Windows Forms)
Ein Ereignishandler ist eine Methode, die auf ein Ereignis gebunden ist. Wenn das Ereignis ausgelöst wird, wird der Code innerhalb des ereignishandlers ausgeführt. Jeder Ereignishandler enthält zwei Parameter, die Ihnen ermöglichen, die das Ereignis ordnungsgemäß zu behandeln. Das folgende Beispiel zeigt einen Ereignishandler für ein <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Click> Ereignis.  
  
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
  
 Der erste Parameter,`sender`, stellt einen Verweis auf das Objekt, das das Ereignis ausgelöst hat. Der zweite Parameter, `e`, im obigen Beispiel übergibt ein spezifisches Objekt an das Ereignis, das behandelt wird. Durch Verweisen auf die Eigenschaften des Objekts (und in einigen Fällen ihre Methoden), erhalten Sie Informationen wie z. B. die Position des Mauszeigers für Mausereignisse oder Daten, die Drag & Drop-Ereignisse übertragen werden.  
  
 In der Regel führt jedes Ereignis einen Ereignishandler mit einem anderen Ereignis-Objekt für den zweiten Parameter. Einige Ereignishandler, etwa solche für die <xref:System.Windows.Forms.Control.MouseDown> und <xref:System.Windows.Forms.Control.MouseUp> Ereignisse weisen denselben Objekttyp für ihre zweite Parameter. Für diese Arten von Ereignissen können Sie denselben Ereignishandler, um beide Ereignisse zu behandeln.  
  
 Sie können auch den Ereignishandler zum Behandeln des gleichen Ereignisses für verschiedene Steuerelemente verwenden. Für, wenn Sie z. B. eine Gruppe von <xref:System.Windows.Forms.RadioButton> Steuerelemente eines Formulars, können Sie einen einzelnen Ereignishandler für erstellen die <xref:System.Windows.Forms.Control.Click> Ereignis und jedes Steuerelement die <xref:System.Windows.Forms.Control.Click> Ereignis gebunden, um die einzelnen Ereignishandler. Weitere Informationen finden Sie unter [Vorgehensweise: Verbinden mehrerer Ereignisse mit einem einzelnen Ereignishandler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen von Ereignishandlern in Windows Forms](creating-event-handlers-in-windows-forms.md)
- [Übersicht über Ereignisse](events-overview-windows-forms.md)

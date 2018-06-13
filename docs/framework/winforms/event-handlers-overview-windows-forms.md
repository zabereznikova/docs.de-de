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
ms.openlocfilehash: 2970cf0f83339fe86faf4af7da80bb17bd25acfc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538155"
---
# <a name="event-handlers-overview-windows-forms"></a>Übersicht über Ereignishandler (Windows Forms)
Ein Ereignishandler ist eine Methode, die auf ein Ereignis gebunden ist. Wenn das Ereignis ausgelöst wird, wird der Code im Ereignishandler ausgeführt. Jeder Ereignishandler bietet zwei Parameter, mit die das Ereignis ordnungsgemäß verarbeiten können. Das folgende Beispiel zeigt einen Ereignishandler für ein <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Click> Ereignis.  
  
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
  
 Der erste Parameter`sender`, stellt einen Verweis auf das Objekt, das das Ereignis ausgelöst hat. Der zweite Parameter `e`, im obigen Beispiel übergibt ein spezifisches Objekt auf das Ereignis, das behandelt wird. Durch Verweisen auf die Eigenschaften des Objekts (und in einigen Fällen, deren Methoden), erhalten Sie Informationen wie z. B. die Position des Mauszeigers für Mausereignisse oder in den Drag & Drop-Ereignissen übertragenen Daten.  
  
 Jedes Ereignis erzeugt in der Regel einen Ereignishandler mit einem anderen Ereignisobjekt-Typ für den zweiten Parameter. Einige Ereignishandler, etwa solche für die <xref:System.Windows.Forms.Control.MouseDown> und <xref:System.Windows.Forms.Control.MouseUp> Ereignisse weisen denselben Objekttyp für ihre zweiten Parameter. Den gleiche Ereignishandler können Sie für diese Typen von Ereignissen um beide Ereignisse zu behandeln.  
  
 Den gleiche Ereignishandler können auch um das gleiche Ereignis für verschiedene Steuerelemente zu behandeln. Angenommen, Sie haben eine Gruppe von <xref:System.Windows.Forms.RadioButton> Steuerelemente eines Formulars, konnte für einen einzelnen Ereignishandler erstellt die <xref:System.Windows.Forms.Control.Click> Ereignis und jedes Steuerelement <xref:System.Windows.Forms.Control.Click> Ereignis gebunden, um die einzelnen Ereignishandler. Weitere Informationen finden Sie unter [Vorgehensweise: Verbinden mehrerer Ereignisse mit einem einzelnen Ereignishandler in Windows Forms](../../../docs/framework/winforms/how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Ereignishandlern in Windows Forms](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [Übersicht über Ereignisse](../../../docs/framework/winforms/events-overview-windows-forms.md)

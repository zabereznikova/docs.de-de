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
ms.openlocfilehash: ffec8a9f8e080dec78152e62e00e2dceefbdaab0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141691"
---
# <a name="event-handlers-overview-windows-forms"></a>Übersicht über Ereignishandler (Windows Forms)
Ein Ereignishandler ist eine Methode, die an ein Ereignis gebunden ist. Wenn das Ereignis ausgelöst wird, wird der Code innerhalb des Ereignishandlers ausgeführt. Jeder Ereignishandler stellt zwei Parameter bereit, mit denen Sie das Ereignis ordnungsgemäß behandeln können. Das folgende Beispiel zeigt einen <xref:System.Windows.Forms.Button> Ereignishandler <xref:System.Windows.Forms.Control.Click> für das Ereignis eines Steuerelements.  
  
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
  
 Der erste`sender`Parameter , stellt einen Verweis auf das Objekt bereit, das das Ereignis ausgelöst hat. Der zweite `e`Parameter, im obigen Beispiel, übergibt ein Objekt, das für das behandelte Ereignis spezifisch ist. Durch Verweisen auf die Eigenschaften des Objekts (und manchmal auch auf seine Methoden) können Sie Informationen wie die Position der Maus für Mausereignisse oder Daten abrufen, die in Drag-and-Drop-Ereignissen übertragen werden.  
  
 In der Regel erzeugt jedes Ereignis einen Ereignishandler mit einem anderen Ereignisobjekttyp für den zweiten Parameter. Einige Ereignishandler, z. B. für die <xref:System.Windows.Forms.Control.MouseDown> und-Ereignisse, <xref:System.Windows.Forms.Control.MouseUp> haben denselben Objekttyp für ihren zweiten Parameter. Für diese Ereignistypen können Sie denselben Ereignishandler verwenden, um beide Ereignisse zu behandeln.  
  
 Sie können auch denselben Ereignishandler verwenden, um dasselbe Ereignis für verschiedene Steuerelemente zu behandeln. Wenn Sie z. B. <xref:System.Windows.Forms.RadioButton> über eine Gruppe von Steuerelementen in <xref:System.Windows.Forms.Control.Click> einem Formular verfügen, <xref:System.Windows.Forms.Control.Click> können Sie einen einzelnen Ereignishandler für das Ereignis erstellen und das Ereignis jedes Steuerelements an den einzelnen Ereignishandler binden lassen. Weitere Informationen finden Sie unter [Gewusst wie: Verbinden mehrerer Ereignisse mit einem einzelnen Ereignishandler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Erstellen von Ereignishandlern in Windows Forms](creating-event-handlers-in-windows-forms.md)
- [Übersicht über Ereignisse](events-overview-windows-forms.md)

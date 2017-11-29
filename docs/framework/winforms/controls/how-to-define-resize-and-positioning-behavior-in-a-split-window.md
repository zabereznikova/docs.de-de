---
title: "Gewusst wie: Definieren des Verhaltens bei Größen- und Positionsänderungen in einem geteilten Fenster"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- split windows [Windows Forms], resizing
- splitter windows [Windows Forms], resizing
- SplitContainer control [Windows Forms], resizing
ms.assetid: 9bf73f36-ed2d-4a02-b15a-0770eff4fdfa
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: db4a99c7dae7783e8ea51f43ad51fcd2214997e5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-resize-and-positioning-behavior-in-a-split-window"></a>Gewusst wie: Definieren des Verhaltens bei Größen- und Positionsänderungen in einem geteilten Fenster
Die Bereiche von den <xref:System.Windows.Forms.SplitContainer> Steuerelement eignen sich gut für wird ein, angepasst und von Benutzern bearbeitet. Es werden jedoch Situationen wird den Splitter programmgesteuert –, wo es positioniert ist, und in welchem Maß sie verschoben werden kann.  
  
 Die <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> -Eigenschaft und die anderen Eigenschaften auf die <xref:System.Windows.Forms.SplitContainer> steuern das Verhalten der Benutzeroberfläche an Ihre Bedürfnisse genaue zu steuern. Diese Eigenschaften sind in der folgenden Tabelle aufgeführt.  
  
|Name|Beschreibung|  
|----------|-----------------|  
|<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>-Eigenschaft|Bestimmt, ob der Splitter mithilfe der Tastatur oder Maus verschiebbar ist.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A>-Eigenschaft|Legt den Abstand in Pixel vom linken oder oberen Rand auf die Splitterleiste verschiebbar.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>-Eigenschaft|Bestimmt die minimale Entfernung in Pixel, dass der Splitter vom Benutzer verschoben werden kann.|  
  
 Im folgenden Beispiel ändert die <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> Eigenschaft zum Erstellen eines Effekts "Andocken Splitter"; der Benutzer des Splitters inkrementiert in Schritten von 10 Pixel anstatt der Standardeinstellung 1.  
  
### <a name="to-define-splitcontainer-resize-behavior"></a>SplitContainer-Resize-Verhalten definieren  
  
1.  Legen Sie in einer Prozedur, die <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> Eigenschaft auf die gewünschte Größe, damit das Verhalten "andocken" des Splitters erreicht wird.  
  
     Im folgenden Codebeispiel wird innerhalb des Formulars <xref:System.Windows.Forms.Form.Load> Ereignis, das der Splitter innerhalb der <xref:System.Windows.Forms.SplitContainer> Steuerelements springen 10 Pixel beim gezogen festgelegt ist.  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, _  
        ByVal e As System.EventArgs) Handles MyBase.Load  
        Dim splitSnapper as new SplitContainer()  
        splitSnapper.SplitterIncrement = 10  
        splitSnapper.Dock = DockStyle.Fill  
        splitSnapper.Parent = me  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_Load(System.Object sender, System.EventArgs e)  
    {  
        SplitContainer splitSnapper = new SplitContainer();  
        splitSnapper.SplitterIncrement = 10;  
        splitSnapper.Dock = DockStyle.Fill;  
        splitSnapper.Parent = this;  
    }  
    ```  
  
     ([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]) Fügen Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
     Den Splitter etwas nach links oder rechts verschieben, müssen keine messbaren Auswirkungen; Wenn der Mauszeiger die Form 10 Pixel in beide Richtungen ist, wird der Splitter an die neue Position ausrichten.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.SplitContainer>  
 <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>

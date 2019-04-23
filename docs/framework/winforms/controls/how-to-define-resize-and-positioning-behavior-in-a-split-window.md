---
title: 'Vorgehensweise: Definieren des Verhaltens bei Größen- und Positionsänderungen in einem geteilten Fenster'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- split windows [Windows Forms], resizing
- splitter windows [Windows Forms], resizing
- SplitContainer control [Windows Forms], resizing
ms.assetid: 9bf73f36-ed2d-4a02-b15a-0770eff4fdfa
ms.openlocfilehash: 8cdcfdfaa135a92ed6a6e96d4a72de2c97f2493d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59328672"
---
# <a name="how-to-define-resize-and-positioning-behavior-in-a-split-window"></a>Vorgehensweise: Definieren des Verhaltens bei Größen- und Positionsänderungen in einem geteilten Fenster
Die Bereiche von den <xref:System.Windows.Forms.SplitContainer> Steuerelement eignen sich gut für das wird ein, angepasst und die vom Benutzer bearbeitet. Es werden jedoch Situationen wird den Splitter programmgesteuert –, wo es positioniert ist und in welchem Ausmaß verschoben werden.  
  
 Die <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> -Eigenschaft und die anderen Eigenschaften auf der <xref:System.Windows.Forms.SplitContainer> -Steuerelement bietet eine präzise Kontrolle über das Verhalten der Benutzeroberfläche an Ihre Anforderungen anpassen. Diese Eigenschaften sind in der folgenden Tabelle aufgeführt.  
  
|Name|Beschreibung|  
|----------|-----------------|  
|<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> -Eigenschaft|Bestimmt, ob der Splitter mithilfe der Tastatur oder Maus verschoben ist.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> -Eigenschaft|Legt den Abstand in Pixel vom linken oder oberen Rand auf die Splitterleiste verschiebbar.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> -Eigenschaft|Bestimmt die minimale Entfernung in Pixeln, des Splitters vom Benutzer verschoben werden kann.|  
  
 Im folgenden Beispiel ändert die <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> Eigenschaft, um einen Effekt "Andocken Splitter"; zu erstellen, wenn der Benutzer den Splitter zieht, inkrementiert in Einheiten von 10 Pixel und nicht der Standardwert 1.  
  
### <a name="to-define-splitcontainer-resize-behavior"></a>Verhalten bei Größenänderung SplitContainer definieren  
  
1. Legen Sie in einer Prozedur die <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> Eigenschaft, um die gewünschte Größe, damit der "springende" Verhalten des Splitters erreicht wird.  
  
     Das folgende Codebeispiel zeigt, innerhalb des Formulars <xref:System.Windows.Forms.Form.Load> Ereignis, das der Splitter innerhalb der <xref:System.Windows.Forms.SplitContainer> -Steuerelement so eingestellt ist, dass 10 Pixel beim gezogen.  
  
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
  
     (Visual C#) Platzieren Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
     Den Splitter etwas nach links oder rechts verschieben, wird keine erkennbaren Auswirkungen haben; Wenn der Mauszeiger über 10 Pixel in beide Richtungen überschreitet, wird der Splitter jedoch auf die neue Position ausrichten.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>

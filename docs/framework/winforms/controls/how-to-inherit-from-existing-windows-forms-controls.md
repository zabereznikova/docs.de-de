---
title: 'Gewusst wie: Erben von vorhandenen Windows Forms-Steuerelementen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- custom controls [Windows Forms], inheritance
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
ms.openlocfilehash: f19b207c840994ffa3aa364135583b5daeb26827
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43890459"
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a>Gewusst wie: Erben von vorhandenen Windows Forms-Steuerelementen
Wenn Sie die Funktionalität eines vorhandenen Steuerelements erweitern möchten, können Sie ein Steuerelement erstellen, dass durch Vererbung von einem vorhandenen Steuerelement abgeleitet ist. Beim Erben von einem vorhandenen Steuerelement erben Sie die gesamte Funktionalität und die visuellen Eigenschaften dieses Steuerelements. Angenommen, Sie ein Steuerelement erstellt haben, die von geerbt <xref:System.Windows.Forms.Button>, das neue Steuerelement sieht und Act, genau wie ein standardmäßiges <xref:System.Windows.Forms.Button> Steuerelement. Sie können die Funktionalität Ihres neuen Steuerelements durch Implementieren von benutzerdefinierten Methoden und Eigenschaften erweitern oder ändern. Bei einigen Steuerelementen können Sie auch die visuelle Darstellung des geerbten Steuerelements ändern, indem Sie überschreiben die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-an-inherited-control"></a>So erstellen Sie ein geerbtes Steuerelement  
  
1.  Erstellen Sie ein neues **Windows Forms-Anwendungsprojekt**.  
  
2.  Wählen Sie im Menü **Projekt** die Option **Neues Element hinzufügen** aus.  
  
     Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.  
  
3.  Doppelklicken Sie im Dialogfeld **Neues Element hinzufügen** auf **Benutzerdefiniertes Steuerelement**.  
  
     Ein neues benutzerdefiniertes Steuerelement wird zu Ihrem Projekt hinzugefügt.  
  
4.  Wenn Sie Visual Basic verwenden, klicken Sie am Anfang des **Projektmappen-Explorers** auf **Alle Dateien anzeigen**. Erweitern Sie „CustomControl1.vb“ und öffnen Sie „CustomControl1.Designer.vb“ im Code-Editor.  
  
5.  Wenn Sie C# verwenden, öffnen Sie „CustomControl1.cs“ im Code-Editor.  
  
6.  Suchen Sie die Klassendeklaration, die von erbt <xref:System.Windows.Forms.Control>.  
  
7.  Ändern Sie die Basisklasse in das Steuerelement, von dem Sie erben möchten.  
  
     Wenn Sie erben möchten z. B. <xref:System.Windows.Forms.Button>, ändern Sie die Klassendeklaration in Folgendes:  
  
    ```vb  
    Partial Class CustomControl1  
        Inherits System.Windows.Forms.Button  
    ```  
  
    ```csharp  
    public partial class CustomControl1 : System.Windows.Forms.Button  
    ```  
  
8.  Wenn Sie Visual Basic verwenden, speichern und schließen Sie „CustomControl1.Designer.vb“. Öffnen Sie „CustomControl1.vb“ im Code-Editor.  
  
9. Implementieren Sie alle benutzerdefinierten Methoden oder Eigenschaften, die in das Steuerelement eingebunden werden sollen.  
  
10. Wenn Sie die grafische Darstellung des Steuerelements ändern möchten, überschreiben die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode.  
  
    > [!NOTE]
    >  Überschreiben von <xref:System.Windows.Forms.Control.OnPaint%2A> nicht können Sie die Darstellung aller Steuerelemente ändern. Diese Steuerelemente, die alle vollständig von Windows gezeichnet werden (z. B. <xref:System.Windows.Forms.TextBox>) niemals aufrufen ihre <xref:System.Windows.Forms.Control.OnPaint%2A> -Methode, und verwenden daher nie verwenden den benutzerdefinierten Code. Finden Sie in der Hilfedokumentation für das bestimme Steuerelement, das Sie ändern, finden Sie unter möchten den <xref:System.Windows.Forms.Control.OnPaint%2A> Methode verfügbar ist. Eine Liste aller Windows Form-Steuerelemente finden Sie unter [Steuerelemente für Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md). Wenn ein Steuerelement keinen <xref:System.Windows.Forms.Control.OnPaint%2A> als Membermethode aufgelistet, Sie können nicht geändert werden seine Darstellung durch diese Methode überschreiben. Weitere Informationen über benutzerdefinierte Darstellung finden Sie unter [Zeichnen und Ausgeben von benutzerdefinierten Steuerelementen](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).  
  
    ```vb  
    Protected Overrides Sub OnPaint(ByVal e As _  
       System.Windows.Forms.PaintEventArgs)  
       MyBase.OnPaint(e)  
       ' Insert code to do custom painting.   
       ' If you want to completely change the appearance of your control,  
       ' do not call MyBase.OnPaint(e).  
    End Sub  
    ```  
  
    ```csharp  
    protected override void OnPaint(PaintEventArgs pe)  
    {  
       base.OnPaint(pe);  
       // Insert code to do custom painting.  
       // If you want to completely change the appearance of your control,  
       // do not call base.OnPaint(pe).  
    }  
    ```  
  
11. Speichern und testen Sie das Steuerelement.  
  
## <a name="see-also"></a>Siehe auch  
 [Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 [Vorgehensweise: Erben von der Control-Klasse](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)  
 [Vorgehensweise: Erben von der UserControl-Klasse](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 [Vorgehensweise: Erstellen von Steuerelementen für Windows Forms](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 [Problembehandlung für geerbte Ereignishandler in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 [Exemplarische Vorgehensweise: Vererben eines Windows Forms-Steuerelements mit Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 [Exemplarische Vorgehensweise: Vererben von einem Windows Forms-Steuerelement mit Visual C#](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)

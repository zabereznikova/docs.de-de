---
title: "Gewusst wie: Hinzuf&#252;gen von Steuerelementen ohne Benutzeroberfl&#228;che zu Windows&#160;Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "NonVisualSelection"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Steuerelemente [Windows Forms], Nicht sichtbar"
  - "Unsichtbare Steuerelemente"
  - "Nicht sichtbare Steuerelemente"
  - "Windows Forms-Steuerelemente, Hinzufügen zum Formular"
  - "Windows Forms-Steuerelemente, Nicht sichtbar"
ms.assetid: 52134d9c-cff6-4eed-8e2b-3d5eb3bd494e
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Hinzuf&#252;gen von Steuerelementen ohne Benutzeroberfl&#228;che zu Windows&#160;Forms
Durch ein nicht sichtbares Steuerelement \(bzw. eine Komponente\) werden der Anwendung Funktionen hinzugefügt.  Komponenten stellen dem Benutzer im Gegensatz zu anderen Steuerelementen keine Benutzeroberfläche bereit und müssen daher auch nicht auf der Oberfläche des Windows Forms\-Designers angezeigt werden.  Wenn einem Formular eine Komponente hinzugefügt wird, wird im Windows Forms\-Designer im unteren Formularbereich eine Leiste mit veränderbarer Größe angezeigt, in der alle Komponenten angezeigt werden.  Nachdem ein Steuerelement der Komponentenleiste hinzugefügt wurde, können Sie die Komponente auswählen und ihre Eigenschaften genauso wie für jedes andere Steuerelement im Formular festlegen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So fügen Sie Windows Forms eine Komponente hinzu  
  
1.  Öffnen Sie das Formular.  Ausführliche Informationen finden Sie unter [How to: Display Windows Forms in the Designer](http://msdn.microsoft.com/de-de/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).  
  
2.  Klicken Sie in der **Toolbox** auf eine Komponente, und ziehen Sie sie in das Formular.  
  
     Die Komponente wird auf der Komponentenleiste angezeigt.  
  
 Komponenten können einem Formular auch zur Laufzeit hinzugefügt werden.  Dies ist ein häufiges Szenario, besonders weil Komponenten im Gegensatz zu Steuerelementen, die über eine Benutzeroberfläche verfügen, keinen visuellen Ausdruck besitzen.  Im nachstehenden Beispiel wird eine <xref:System.Windows.Forms.Timer>\-Komponente zur Laufzeit hinzugefügt.  \(Beachten Sie hierbei, dass [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] eine Reihe unterschiedlicher Zeitgeber enthält. In diesem Fall verwenden Sie eine <xref:System.Windows.Forms.Timer>\-Komponente von Windows Forms.  Weitere Informationen über die verschiedenen Zeitgeber in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] finden Sie unter [Introduction to Server\-Based Timers](http://msdn.microsoft.com/de-de/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).\)  
  
> [!CAUTION]
>  Komponenten haben häufig steuerelementspezifische Eigenschaften, die festgelegt werden müssen, um ein effektives Arbeiten der Komponente zu gewährleisten.  Für die nachfolgend verwendete <xref:System.Windows.Forms.Timer>\-Komponente muss die `Interval`\-Eigenschaft festgelegt werden.  Achten Sie darauf, die für die jeweilige Komponente erforderlichen Eigenschaften festzulegen, wenn Sie dem Projekt Komponenten hinzufügen.  
  
#### So fügen Sie Windows Forms eine Komponente programmgesteuert hinzu  
  
1.  Erstellen Sie im Code eine Instanz der <xref:System.Windows.Forms.Timer>\-Klasse.  
  
2.  Legen Sie die `Interval`\-Eigenschaft fest, um die Zeit zwischen den Teilstrichen des Zeitgebers zu bestimmen.  
  
3.  Konfigurieren Sie beliebige andere Eigenschaften für die Komponente.  
  
     Der folgende Code zeigt die Erstellung eines <xref:System.Windows.Forms.Timer> mit festgelegter `Interval`\-Eigenschaft.  
  
    ```vb  
    Public Sub CreateTimer()  
       Dim timerKeepTrack As New System.Windows.Forms.Timer  
       timerKeepTrack.Interval = 1000  
    End Sub  
  
    ```  
  
    ```csharp  
    public void createTimer()  
    {  
       System.Windows.Forms.Timer timerKeepTrack = new  
           System.Windows.Forms.Timer();  
       timerKeepTrack.Interval = 1000;  
    }  
  
    ```  
  
    ```cpp  
    public:  
       void createTimer()  
       {  
          System::Windows::Forms::Timer^ timerKeepTrack = gcnew  
             System::Windows::Forms::Timer();  
          timerKeepTrack->Interval = 1000;  
       }  
    ```  
  
    > [!IMPORTANT]
    >  Möglicherweise setzen Sie den lokalen Computer über das Netzwerk einem Sicherheitsrisiko aus, indem auf ein bösartiges UserControl verwiesen wird.  Allerdings ist dies nur dann ein Problem, wenn ein böswilliger Benutzer ein schädliches benutzerdefiniertes Steuerelement erstellt, das Sie versehentlich zu dem Projekt hinzufügen.  
  
## Siehe auch  
 [Windows Forms\-Steuerelemente](../../../../docs/framework/winforms/controls/index.md)   
 [Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)   
 [Gewusst wie: Hinzufügen von ActiveX\-Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)   
 [Gewusst wie: Kopieren von Steuerelementen zwischen Windows Forms](../../../../docs/framework/winforms/controls/how-to-copy-controls-between-windows-forms.md)   
 [Einfügen von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)   
 [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)   
 [Steuerelemente für Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [Windows Forms\-Steuerelemente nach Funktion](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
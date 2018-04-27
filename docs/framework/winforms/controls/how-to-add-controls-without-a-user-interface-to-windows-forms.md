---
title: 'Gewusst wie: Hinzufügen von Steuerelementen ohne Benutzeroberfläche zu Windows Forms'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- NonVisualSelection
helpviewer_keywords:
- invisible controls [Windows Forms]
- Windows Forms controls, adding to form
- controls [Windows Forms], nonvisual
- Windows Forms controls, nonvisual
- nonvisual controls [Windows Forms]
ms.assetid: 52134d9c-cff6-4eed-8e2b-3d5eb3bd494e
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e900c1c34f69531a14cfa11803ef5a6afb4783c6
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a>Gewusst wie: Hinzufügen von Steuerelementen ohne Benutzeroberfläche zu Windows Forms
Nicht sichtbare Steuerelement (bzw. eine Komponente) bietet Funktionen für Ihre Anwendung. Im Gegensatz zu anderen Steuerelementen Komponenten bieten eine Benutzeroberfläche für dem Benutzer keine und müssen daher nicht auf der Windows Forms-Designer-Oberfläche angezeigt werden. Wenn eine Komponente zu einem Formular hinzugefügt wird, zeigt Windows Forms-Designer ein veränderbarer am unteren Rand der Form, in dem alle Komponenten angezeigt werden. Sobald ein Steuerelement auf der Komponentenleiste hinzugefügt wurde, können Sie wählen Sie die Komponente und seine Eigenschaften festlegen, wie jedem anderen Steuerelement im Formular.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-add-a-component-to-a-windows-form"></a>Hinzufügen eine Komponente zu einem Windows Form  
  
1.  Öffnen Sie das Formular. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von Windows Forms im Designer](http://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).  
  
2.  In der **Toolbox**, klicken Sie auf eine Komponente, und ziehen Sie es in Ihr Formular.  
  
     Die Komponente wird auf der Komponentenleiste angezeigt.  
  
 Darüber hinaus können Komponenten zu einem Formular zur Laufzeit hinzugefügt werden. Dies ist ein gängiges Szenario, vor allem, da Komponenten nicht visuellen Ausdruck, im Gegensatz zu Steuerelemente verfügen, die über eine Benutzeroberfläche verfügen. Im folgenden Beispiel wird eine <xref:System.Windows.Forms.Timer> Komponente zur Laufzeit hinzugefügt wird. (Beachten Sie, dass Visual Studio eine Anzahl von verschiedenen Zeitgeber enthält; in diesem Fall verwenden Sie eine Windows Forms <xref:System.Windows.Forms.Timer> Komponente. Weitere Informationen über die verschiedenen Zeitgeber in Visual Studio finden Sie unter [Einführung in serverbasierte Zeitgeber](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).)  
  
> [!CAUTION]
>  Komponenten haben häufig steuerelementspezifischen Eigenschaften, die für die Komponente, für die effiziente Ausführung festgelegt werden müssen. Im Fall von der <xref:System.Windows.Forms.Timer> folgenden Komponente, legen Sie die `Interval` Eigenschaft. Achten Sie darauf, beim Komponenten Ihrem Projekt hinzufügen, Sie die Eigenschaften für die jeweilige Komponente erforderlich legen.  
  
#### <a name="to-add-a-component-to-a-windows-form-programmatically"></a>So fügen Sie eine Komponente zu einem Windows Form programmgesteuert hinzu  
  
1.  Erstellen Sie eine Instanz von der <xref:System.Windows.Forms.Timer> -Klasse im Code.  
  
2.  Legen Sie die `Interval` Eigenschaft, um die Zeit zwischen den Teilstrichen des Zeitgebers zu bestimmen.  
  
3.  Konfigurieren Sie alle anderen erforderlichen Eigenschaften für die Komponente.  
  
     Der folgende Code zeigt die Erstellung einer <xref:System.Windows.Forms.Timer> mit seiner `Interval` Eigenschaftensatz.  
  
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
    >  Sie können den lokalen Computer über das Netzwerk ein Sicherheitsrisiko durch Verweisen auf ein bösartiges UserControl verfügbar machen. Dies ist nur relevant, wenn ein böswilliger Benutzer, erstellen ein schädliches benutzerdefiniertes Steuerelement, indem Sie versehentlich zu Ihrem Projekt hinzufügen.  
  
## <a name="see-also"></a>Siehe auch  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/index.md)  
 [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [Gewusst wie: Hinzufügen von ActiveX-Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)  
 [Gewusst wie: Kopieren von Steuerelementen zwischen Windows Forms](../../../../docs/framework/winforms/controls/how-to-copy-controls-between-windows-forms.md)  
 [Einfügen von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)  
 [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Windows Forms-Steuerelemente nach Funktion](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)

---
title: 'Gewusst wie: Testen des Laufzeitverhaltens eines UserControl'
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], testing
- user controls [Windows Forms], testing
- composite controls [Windows Forms], testing
- UserControl Test Container
- UserControl class [Windows Forms], run-time behavior
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
ms.openlocfilehash: ac846840f7d420da63f6bfe3db3772d7bf6cc730
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a>Gewusst wie: Testen des Laufzeitverhaltens eines UserControl
Bei der Entwicklung einer <xref:System.Windows.Forms.UserControl>, müssen Sie dessen Laufzeitverhalten zu testen. Sie können eine separate Windows-basiertes Anwendungsprojekt erstellen und platzieren Sie das Steuerelement auf einen Testformular, aber dieses Verfahren ist. Eine Möglichkeit schnellere und einfachere, ist die Verwendung der **UserControl-Testcontainer** von Visual Studio bereitgestellt werden. Dieser Testcontainer wird direkt aus Ihrem Windows-Steuerelementbibliothek-Projekt gestartet.  
  
> [!IMPORTANT]
>  Für den Testcontainer laden Ihre <xref:System.Windows.Forms.UserControl>, das Steuerelement muss über mindestens einen öffentlichen Konstruktor verfügen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
> [!NOTE]
>  Ein Visual C++-Steuerelement kann nicht getestet werden, mithilfe der **UserControl-Testcontainer**.  
  
### <a name="to-test-the-run-time-behavior-of-a-usercontrol"></a>Zum Testen des Laufzeitverhaltens eines UserControl  
  
1.  Erstellen Sie eine Windows-Steuerelementbibliothek-Projekt namens **TestContainerExample**. Weitere Informationen finden Sie unter [Vorlage für Windows-Steuerelementbibliothek](http://msdn.microsoft.com/library/722f4e2d-1310-4ed5-8f33-593337ab66b4).  
  
2.  In der **Windows Forms-Designer**, ziehen Sie eine <xref:System.Windows.Forms.Label> -Steuerelement aus der **Toolbox** auf das Steuerelement-Entwurfsoberfläche.  
  
3.  Drücken Sie F5, um das Projekt erstellen und Ausführen der **UserControl-Testcontainer**. Der Testcontainer wird mit Ihrem <xref:System.Windows.Forms.UserControl> in der **Vorschau** Bereich.  
  
4.  Wählen Sie die <xref:System.Windows.Forms.Control.BackColor%2A> angezeigten Eigenschaft der <xref:System.Windows.Forms.PropertyGrid> Steuerelement rechts neben der **Vorschau** Bereich. Ändern Sie dessen Wert in `ControlDark`. Beachten Sie, dass das Steuerelement in einer dunkleren Farbe ändert. Wiederholen Sie den anderen Eigenschaftswerte ändern, und beobachten Sie die Auswirkung auf das Steuerelement.  
  
5.  Klicken Sie auf die **Fill-Benutzersteuerelement andocken** Kontrollkästchen unten die **Vorschau** Bereich. Beachten Sie, dass das Steuerelement skaliert wird, um den Bereich zu füllen. Die Größe des Testcontainers und beachten Sie, dass das Steuerelement mit dem Bereich angepasst wird.  
  
6.  Schließen Sie den Testcontainer an.  
  
7.  Fügen Sie ein anderes Benutzersteuerelement, das **TestContainerExample** Projekt. Einzelheiten finden Sie in [NIB: Vorgehensweise: Hinzufügen von vorhandenen Elementen zu einem Projekt](http://msdn.microsoft.com/library/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).  
  
8.  In der **Windows Forms-Designer**, ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das Steuerelement-Entwurfsoberfläche.  
  
9. Drücken Sie F5, um das Projekt erstellen, und führen Sie den Testcontainer aus.  
  
10. Klicken Sie auf die **Benutzersteuerelement auswählen** <xref:System.Windows.Forms.ComboBox> Wechsel zwischen den beiden Benutzersteuerelemente.  
  
## <a name="testing-user-controls-from-another-project"></a>Benutzersteuerelemente aus einem anderen Projekt testen  
 Sie können die Benutzersteuerelemente als andere Projekte in Ihrem aktuellen Projekt Testcontainer testen.  
  
#### <a name="to-test-user-controls-from-another-project"></a>So testen Sie Benutzersteuerelemente aus einem anderen Projekt  
  
1.  Erstellen Sie eine Windows-Steuerelementbibliothek-Projekt namens **TestContainerExample2**. Weitere Informationen finden Sie unter [Vorlage für Windows-Steuerelementbibliothek](http://msdn.microsoft.com/library/722f4e2d-1310-4ed5-8f33-593337ab66b4).  
  
2.  In der **Windows Forms-Designer**, ziehen Sie eine <xref:System.Windows.Forms.RadioButton> -Steuerelement aus der **Toolbox** auf das Steuerelement-Entwurfsoberfläche.  
  
3.  Drücken Sie F5, um das Projekt erstellen, und führen Sie den Testcontainer aus. Der Testcontainer wird mit Ihrem <xref:System.Windows.Forms.UserControl> in der **Vorschau** Bereich.  
  
4.  Klicken Sie auf die **laden** Schaltfläche.  
  
5.  In der **öffnen** Dialogfeld Feld, navigieren Sie zu **TestContainerExample**.dll, die Sie im vorherigen Verfahren erstellt haben. Wählen Sie **TestContainerExample**DLL-Datei, und klicken Sie auf die **öffnen** Schaltfläche, um die Benutzersteuerelemente zu laden.  
  
6.  Verwenden der **Benutzersteuerelement auswählen** <xref:System.Windows.Forms.ComboBox> So wechseln Sie zwischen die beiden Benutzersteuerelemente aus der **TestContainerExample** Projekt.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.UserControl>  
 [Vorgehensweise: Erstellen von zusammengesetzten Steuerelementen](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)  
 [Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 [Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual C#](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 [Benutzersteuerelement-Designer](http://msdn.microsoft.com/library/2abb9eec-ba32-45cb-b73d-8b52a8bd6bf1)

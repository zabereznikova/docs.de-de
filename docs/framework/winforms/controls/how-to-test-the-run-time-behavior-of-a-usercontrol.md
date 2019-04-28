---
title: 'Vorgehensweise: Testen des Laufzeitverhaltens eines UserControl'
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], testing
- user controls [Windows Forms], testing
- composite controls [Windows Forms], testing
- UserControl Test Container
- UserControl class [Windows Forms], run-time behavior
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
ms.openlocfilehash: 15b37c71e6643b588c0378510965a9a3e7cb56e9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61672574"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a>Vorgehensweise: Testen des Laufzeitverhaltens eines UserControl
Bei der Entwicklung einer <xref:System.Windows.Forms.UserControl>, müssen Sie dessen Laufzeitverhalten zu testen. Können einen separaten Windows-basiertes Anwendungsprojekt zu erstellen und das Steuerelement auf einem Testformular, aber dieses Verfahren ist unpraktisch. Eine schnellere und einfachere Möglichkeit ist die Verwendung der **UserControl-Testcontainer** von Visual Studio bereitgestellt. Dieser Testcontainer, die direkt über das Windows-Steuerelementbibliothek-Projekt wird gestartet.  
  
> [!IMPORTANT]
>  Für den Testcontainer beim Laden Ihrer <xref:System.Windows.Forms.UserControl>, muss das Steuerelement über mindestens einen öffentlichen Konstruktor haben.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
> [!NOTE]
>  Ein Visual C++-Steuerelement kann nicht getestet werden, mithilfe der **UserControl-Testcontainer**.  
  
### <a name="to-test-the-run-time-behavior-of-a-usercontrol"></a>So testen Sie das Laufzeitverhalten eines UserControl  
  
1. Erstellen Sie ein Windows-Steuerelementbibliothek-Projekt namens **TestContainerExample**. Weitere Informationen finden Sie unter [Vorlage für Windows-Steuerelementbibliothek](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).  
  
2. In der **Windows Forms-Designer**, ziehen Sie eine <xref:System.Windows.Forms.Label> -Steuerelement aus der **Toolbox** auf der Entwurfsoberfläche des Steuerelements.  
  
3. Drücken Sie F5, um das Projekt erstellen und Ausführen der **UserControl-Testcontainer**. Der Testcontainer wird mit Ihrem <xref:System.Windows.Forms.UserControl> in die **Vorschau** Bereich.  
  
4. Wählen Sie die <xref:System.Windows.Forms.Control.BackColor%2A> angezeigten Eigenschaft der <xref:System.Windows.Forms.PropertyGrid> Steuerelement rechts neben der **Vorschau** Bereich. Ändern Sie seinen Wert auf `ControlDark`. Beachten Sie, dass das Steuerelement zu einer dunkleren Farbe geändert. Versuchen Sie es anderen Eigenschaftswerte ändern, und beobachten die Auswirkungen auf das Steuerelement.  
  
5. Klicken Sie auf die **Fill-Benutzersteuerelement andocken** Kontrollkästchen unten die **Vorschau** Bereich. Beachten Sie, dass das Steuerelement skaliert wird, um den Bereich zu füllen. Ändern der Größe des Testcontainers, und beobachten Sie, dass das Steuerelement mit dem Bereich angepasst wird.  
  
6. Schließen Sie den Testcontainer.  
  
7. Fügen Sie einen anderen benutzerdefinierten Steuerelements, sodass die **TestContainerExample** Projekt. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen vorhandener Elemente zu einem Projekt](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100)).  
  
8. In der **Windows Forms-Designer**, ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf der Entwurfsoberfläche des Steuerelements.  
  
9. Drücken Sie F5, um das Projekt erstellen, und führen Sie den Testcontainer aus.  
  
10. Klicken Sie auf die **Benutzersteuerelement auswählen** <xref:System.Windows.Forms.ComboBox> zwischen den beiden Steuerelementen wechseln.  
  
## <a name="testing-user-controls-from-another-project"></a>Testen von Benutzersteuerelementen aus einem anderen Projekt  
 Sie können Steuerelemente aus anderen Projekten in Test-Container des aktuellen Projekts testen.  
  
#### <a name="to-test-user-controls-from-another-project"></a>Um Steuerelemente aus einem anderen Projekt zu testen.  
  
1. Erstellen Sie ein Windows-Steuerelementbibliothek-Projekt namens **TestContainerExample2**. Weitere Informationen finden Sie unter [Vorlage für Windows-Steuerelementbibliothek](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).  
  
2. In der **Windows Forms-Designer**, ziehen Sie eine <xref:System.Windows.Forms.RadioButton> -Steuerelement aus der **Toolbox** auf der Entwurfsoberfläche des Steuerelements.  
  
3. Drücken Sie F5, um das Projekt erstellen, und führen Sie den Testcontainer aus. Der Testcontainer wird mit Ihrem <xref:System.Windows.Forms.UserControl> in die **Vorschau** Bereich.  
  
4. Klicken Sie auf die **Load** Schaltfläche.  
  
5. In der **öffnen** Dialogfeld zu **TestContainerExample**DLL-Datei, die Sie in der vorherigen Prozedur erstellt. Wählen Sie **TestContainerExample**DLL-Datei, und klicken Sie auf die **öffnen** Schaltfläche, um die Steuerelemente zu laden.  
  
6. Verwenden der **Benutzersteuerelement auswählen** <xref:System.Windows.Forms.ComboBox> zum Wechseln zwischen den beiden Steuerelementen aus der **TestContainerExample** Projekt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.UserControl>
- [Vorgehensweise: Erstellen von zusammengesetzten Steuerelementen](how-to-author-composite-controls.md)
- [Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual Basic](walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit visuellen ElementC#](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- [Benutzersteuerelement-Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))

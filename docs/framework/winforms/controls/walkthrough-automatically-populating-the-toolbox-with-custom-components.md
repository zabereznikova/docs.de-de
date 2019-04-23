---
title: 'Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten'
ms.date: 03/30/2017
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
ms.openlocfilehash: 6ecf69350b8337dc6049b73251809192b47dc2fb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59338097"
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a>Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten
Wenn die Komponenten von einem Projekt in der aktuell geöffneten Projektmappe definiert sind, werden sie automatisch in angezeigt der **Toolbox**, keine Aktion erforderlich. Sie können auch manuell Auffüllen der **Toolbox** mit den benutzerdefinierten Komponenten mithilfe der [Choose Toolbox Items Dialog Box (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100)), aber die **Toolbox** berücksichtigt der Elemente in der Projektmappe Buildausgaben Sie mit folgenden Merkmalen:  
  
-   Implementiert <xref:System.ComponentModel.IComponent>;  
  
-   Keine <xref:System.ComponentModel.ToolboxItemAttribute> festgelegt `false`;  
  
-   Keine <xref:System.ComponentModel.DesignTimeVisibleAttribute> festgelegt `false`.  
  
> [!NOTE]
>  Die **Toolbox** Verweisketten, werden nicht befolgt werden, damit es keine Elemente angezeigt werden, die von einem Projekt in der Projektmappe nicht erstellt werden.  
  
 In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie eine benutzerdefinierte Komponente automatisch in angezeigt wird der **Toolbox** , nachdem die Komponente erstellt wird. In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen ein Windows Forms-Projekt.  
  
-   Erstellen eine benutzerdefinierte Komponente an.  
  
-   Erstellen einer Instanz einer benutzerdefinierten Komponente.  
  
-   Entladen und das erneute Laden einer benutzerdefinierten Komponente.  
  
 Wenn Sie fertig sind, sehen Sie, den **Toolbox** wird aufgefüllt, mit einer Komponente, die Sie erstellt haben.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="creating-the-project"></a>Erstellen des Projekts  
 Im ersten Schritt wird das Projekt erstellt und das Formular eingerichtet.  
  
#### <a name="to-create-the-project"></a>So erstellen Sie das Projekt  
  
1. Erstellen Sie ein Windows-basierten Anwendung mit dem Namen `ToolboxExample` (**Datei** > **neu** > **Projekt**  >  **Visual C#-** oder **Visual Basic** > **Klassischer Desktop** > **Windows Forms-Anwendung**).  
  
2. Fügen Sie dem Projekt eine neue Komponente hinzu. Geben Sie ihm den Namen `DemoComponent`.  
  
     Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen neuer Projektelemente](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).  
  
3. Erstellen Sie das Projekt.  
  
4. Von der **Tools** Menü klicken Sie auf die **Optionen** Element. Klicken Sie auf **allgemeine** unter der **Windows Forms-Designer** Element aus, und stellen sicher, dass die **AutoToolboxPopulate** Option wird festgelegt, um **"true"**.  
  
## <a name="creating-an-instance-of-a-custom-component"></a>Erstellen einer Instanz einer benutzerdefinierten Komponente  
 Der nächste Schritt ist eine Instanz der benutzerdefinierten Komponente auf dem Formular zu erstellen. Da die **Toolbox** automatisch Konten für die neue Komponente, dies ist so einfach wie das Erstellen einer anderen Komponente oder Steuerelement.  
  
#### <a name="to-create-an-instance-of-a-custom-component"></a>Zum Erstellen einer Instanz einer benutzerdefinierten Komponente  
  
1. Öffnen Sie das Formular des Projekts in der **Formulardesigner**.  
  
2. In der **Toolbox**, klicken Sie auf die neue Registerkarte **ToolboxExample-Komponenten**.  
  
     Sobald Sie die Registerkarte klicken, wird Ihnen **DemoComponent**.  
  
    > [!NOTE]
    >  Aus Leistungsgründen Komponenten in den automatisch ausgefüllten Bereich des der **Toolbox** zeigen keine benutzerdefinierten Bitmaps, und die <xref:System.Drawing.ToolboxBitmapAttribute> wird nicht unterstützt. Zum Anzeigen eines Symbols für eine benutzerdefinierte Komponente in der **Toolbox**, verwenden Sie die **Toolboxelemente auswählen** (Dialogfeld), laden Sie die Komponente.  
  
3. Ziehen Sie die Komponente auf das Formular.  
  
     Eine Instanz der Komponente erstellt und hinzugefügt werden, um die **Komponentenleiste**.  
  
## <a name="unloading-and-reloading-a-custom-component"></a>Entladen und Neuladen einer benutzerdefinierten Komponente  
 Die **Toolbox** berücksichtigt die Komponenten in jedem geladenen Projekt, und wenn ein Projekt entladen wird, entfernt Verweise auf das Projekt die Komponenten.  
  
#### <a name="to-experiment-with-the-effect-on-the-toolbox-of-unloading-and-reloading-components"></a>Experimentieren Sie mit dem Effekt in der Toolbox entladen und Neuladen von Komponenten  
  
1. Entladen Sie das Projekt aus der Projektmappe.  
  
     Weitere Informationen zum Entladen von Projekten finden Sie unter [Vorgehensweise: Entladen und Laden von Projekten](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/tt479x1t(v=vs.100)). Wenn Sie aufgefordert werden, um zu speichern, wählen Sie **Ja**.  
  
2. Fügen Sie einen neuen **Windows-Anwendung** Projekt der Projektmappe. Öffnen Sie das Formular in der **Designer**.  
  
     Die **ToolboxExample-Komponenten** Registerkarte aus dem vorherigen Projekt ist jetzt nicht mehr vorhanden.  
  
3. Erneutes Laden der `ToolboxExample` Projekt.  
  
     Die **ToolboxExample-Komponenten** Registerkarte wird wieder angezeigt.  
  
## <a name="next-steps"></a>Nächste Schritte  
 In dieser exemplarischen Vorgehensweise wird veranschaulicht, dass die **Toolbox** berücksichtigt Komponenten eines Projekts, aber die **Toolbox** ist auch Steuerelemente. Experimentieren Sie mit Ihren eigenen benutzerdefinierten Steuerelementen durch Hinzufügen und Entfernen von Projekten aus Ihrer Projektmappe.  
  
## <a name="see-also"></a>Siehe auch

- [Allgemein, Windows Forms-Designer, Optionen (Dialogfeld)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))
- [Vorgehensweise: Ändern Sie Toolbox-Registerkarten](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/66kwe227(v=vs.100))
- [Dialogfeld „Toolboxelemente auswählen“ (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))
- [Einfügen von Steuerelementen in Windows Forms](putting-controls-on-windows-forms.md)

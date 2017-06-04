---
title: "Gewusst wie: Testen des Laufzeitverhaltens eines UserControl | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Zusammengesetzte Steuerelemente, Testen"
  - "Benutzersteuerelemente [Windows Forms], Testen"
  - "UserControl-Klasse, Laufzeitverhalten"
  - "UserControl-Klasse, Testen"
  - "UserControl-Testcontainer"
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Testen des Laufzeitverhaltens eines UserControl
Wenn Sie ein <xref:System.Windows.Forms.UserControl> entwickeln, müssen Sie sein Laufzeitverhalten testen.  Hierfür können Sie ein separates Windows\-basiertes Anwendungsprojekt erstellen und das Steuerelement in ein Testformular einfügen. Diese Vorgehensweise ist jedoch nicht empfehlenswert.  Eine schnellere und einfachere Möglichkeit bietet der von Visual Studio bereitgestellte **UserControl\-Testcontainer**.  Dieser Testcontainer wird direkt in Ihrem Windows\-Steuerelementbibliothek\-Projekt gestartet.  
  
> [!IMPORTANT]
>  Damit der Testcontainer das <xref:System.Windows.Forms.UserControl> lädt, muss das Steuerelement mindestens über einen öffentlichen Konstruktor verfügen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
> [!NOTE]
>  Ein Visual C\+\+\-Steuerelement kann nicht mit dem **UserControl\-Testcontainer** getestet werden.  
  
### So testen Sie das Laufzeitverhalten eines UserControl\-Steuerelements  
  
1.  Erstellen Sie ein Windows\-Steuerelementbibliothek\-Projekt mit dem Namen TestContainerExample.  Ausführliche Informationen finden Sie unter [Windows Control Library Template](http://msdn.microsoft.com/de-de/722f4e2d-1310-4ed5-8f33-593337ab66b4).  
  
2.  Ziehen Sie im **Windows Forms\-Designer** ein <xref:System.Windows.Forms.Label>\-Steuerelement aus der **Toolbox** auf die Entwurfsoberfläche des Steuerelements.  
  
3.  Drücken Sie F5, um das Projekt zu erstellen und den **UserControl\-Testcontainer** auszuführen.  Der Testcontainer wird mit dem <xref:System.Windows.Forms.UserControl> im Bereich **Vorschau** angezeigt.  
  
4.  Wählen Sie die <xref:System.Windows.Forms.Control.BackColor%2A>\-Eigenschaft aus, die im <xref:System.Windows.Forms.PropertyGrid>\-Steuerelement rechts neben dem Bereich **Vorschau** angezeigt wird.  Ändern Sie ihren Wert in `ControlDark`.  Beachten Sie, dass die Farbe des Steuerelements dunkler wird.  Versuchen Sie, weitere Eigenschaftswerte zu ändern, und beobachten Sie die Auswirkung auf das Steuerelement.  
  
5.  Klicken Sie auf das Kontrollkästchen **Fill\-Benutzersteuerelement andocken** unter dem Bereich **Vorschau**.  Beachten Sie, dass die Größe des Steuerelements an den Bereich angepasst wird.  Ändern Sie die Größe des Testcontainers, und beachten Sie, wie das Steuerelement an den Bereich angepasst wird.  
  
6.  Schließen Sie den Testcontainer.  
  
7.  Fügen Sie dem TestContainerExample\-Projekt ein weiteres Benutzersteuerelement hinzu.  Ausführliche Informationen finden Sie unter [NIB:How to: Add Existing Items to a Project](http://msdn.microsoft.com/de-de/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).  
  
8.  Ziehen Sie im **Windows Forms\-Designer** ein <xref:System.Windows.Forms.Button>\-Steuerelement aus der **Toolbox** auf die Entwurfsoberfläche des Steuerelements.  
  
9. Drücken Sie F5, um das Projekt zu erstellen und den Testcontainer auszuführen.  
  
10. Klicken Sie auf die <xref:System.Windows.Forms.ComboBox> **Benutzersteuerelement auswählen**, um zwischen den beiden Benutzersteuerelementen zu wechseln.  
  
## Testen von Benutzersteuerelementen aus einem anderen Projekt  
 Sie können Benutzersteuerelemente aus anderen Projekten im Testcontainer des aktuellen Projekts testen.  
  
#### So testen Sie Benutzersteuerelemente aus einem anderen Projekt  
  
1.  Erstellen Sie ein Windows\-Steuerelementbibliothek\-Projekt mit dem Namen TestContainerExample2.  Ausführliche Informationen finden Sie unter [Windows Control Library Template](http://msdn.microsoft.com/de-de/722f4e2d-1310-4ed5-8f33-593337ab66b4).  
  
2.  Ziehen Sie im **Windows Forms\-Designer** ein <xref:System.Windows.Forms.RadioButton>\-Steuerelement aus der **Toolbox** auf die Entwurfsoberfläche des Steuerelements.  
  
3.  Drücken Sie F5, um das Projekt zu erstellen und den Testcontainer auszuführen.  Der Testcontainer wird mit dem <xref:System.Windows.Forms.UserControl> im Bereich **Vorschau** angezeigt.  
  
4.  Klicken Sie auf die Schaltfläche **Laden**.  
  
5.  Navigieren Sie im Dialogfeld **Öffnen** zur Datei TestContainerExample.dll, die Sie in der vorherigen Prozedur erstellt haben.  Wählen Sie TestContainerExample.dll aus, und klicken Sie auf die Schaltfläche **Öffnen**, um die Benutzersteuerelemente zu laden.  
  
6.  Wechseln Sie mit dem <xref:System.Windows.Forms.ComboBox> **Benutzersteuerelement auswählen** zwischen den beiden Benutzersteuerelementen aus dem TestContainerExample\-Projekt.  
  
## Siehe auch  
 <xref:System.Windows.Forms.UserControl>   
 [Gewusst wie: Erstellen von zusammengesetzten Steuerelementen](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)   
 [Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)   
 [Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual C\#](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)   
 [User Control Designer](http://msdn.microsoft.com/de-de/2abb9eec-ba32-45cb-b73d-8b52a8bd6bf1)
---
title: 'Vorgehensweise: Erstellen von Steuerelementen für Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], creating
- UserControl class [Windows Forms], Windows Forms
- custom controls [Windows Forms], creating
ms.assetid: 7570e982-545b-4c3a-a7c7-55581d313400
ms.openlocfilehash: a6ea57dda8f034684e8590ce4c3b6d37ab01230e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54579523"
---
# <a name="how-to-author-controls-for-windows-forms"></a>Vorgehensweise: Erstellen von Steuerelementen für Windows Forms
Ein Steuerelement stellt eine grafische Verknüpfung zwischen dem Benutzer und der Anwendung dar. Ein Steuerelement kann Daten bereitstellen oder verarbeiten, Benutzereingaben akzeptieren, auf Ereignisse reagieren oder eine beliebige Anzahl von anderen Funktionen ausführen, die eine Verbindung zwischen dem Benutzer und der Anwendung herstellen. Da es sich bei einem Steuerelement im Wesentlichen um eine Komponente mit grafischer Schnittstelle handelt, kann sie den gleichen Zwecken dienen wie eine Komponente, sowie Benutzerinteraktion bereitstellen. Steuerelemente werden erstellt, um bestimmte Zwecke zu erfüllen, und das Erstellen von Steuerelementen ist einfach eine weitere Aufgabe als Programmierer. Vor diesem Hintergrund bieten die folgenden Schritte einen Überblick über das Erstellen von Steuerelementen. Links bieten zusätzliche Informationen zu den einzelnen Schritten.  
  
> [!NOTE]
>  Wenn Sie ein benutzerdefiniertes Steuerelement erstellen möchten, das in Web Forms verwendet werden soll, sollten Sie [Entwickeln von benutzerdefinierten ASP.NET-Serversteuerelementen](https://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef) lesen.  
>   
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-author-a-control"></a>So erstellen Sie ein Steuerelement  
  
1.  Bestimmen Sie, was Sie mit dem Steuerelement erreichen möchten bzw. welche Rolle es in Ihrer Anwendung spielen soll. Zu berücksichtigende Faktoren sind:  
  
    -   Welche Art grafische Benutzeroberfläche benötigen Sie?  
  
    -   Welche besonderen Benutzerinteraktionen werden von diesem Steuerelement behandelt?  
  
    -   Wird die benötigte Funktionalität von vorhandenen Steuerelementen bereitgestellt?  
  
    -   Erhalten Sie die Funktionalität, die Sie benötigen, durch Kombinieren mehrerer Windows Forms-Steuerelemente?  
  
2.  Bestimmen Sie, wenn Sie ein Objektmodell für das Steuerelement benötigen, wie die Funktionalität im Objektmodell verteilt wird, und teilen Sie die Funktionalität zwischen dem Steuerelement und beliebigen Unterobjekten auf. Ein Objektmodell kann nützlich sein, wenn Sie ein komplexes Steuerelement planen oder mehrere Funktionen eingebunden werden soll.  
  
3.  Bestimmen Sie, welchen Typ des Steuerelements (z.B. Benutzersteuerelement, benutzerdefiniertes Steuerelement, geerbtes Windows Forms-Steuerelement) Sie benötigen. Weitere Informationen finden Sie unter [Empfehlungen zum Typ von Steuerelementen](../../../../docs/framework/winforms/controls/control-type-recommendations.md) und [Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md).  
  
4.  Drücken Sie die Funktionalität als Eigenschaften, Methoden und Ereignisse des Steuerelements und seiner Unterobjekte oder untergeordneten Strukturen aus, und weisen Sie entsprechende Zugriffsebenen zu (z.B. öffentlich, geschützt und so weiter).  
  
5.  Wenn Sie eine benutzerdefinierte Darstellung Ihres Steuerelements benötigen, fügen Sie entsprechenden Code hinzu. Weitere Informationen finden Sie unter [Zeichnen und Ausgeben benutzerdefinierter Steuerelemente](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).  
  
6.  Wenn das Steuerelement erbt <xref:System.Windows.Forms.UserControl>, Sie können das Laufzeitverhalten testen, indem Sie das Projekt erstellen und in der **UserControl-Testcontainer**. Weitere Informationen finden Sie unter [Vorgehensweise: Testen Sie das Laufzeitverhalten eines UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
7.  Sie können Ihr Steuerelement auch testen und debuggen, indem Sie ein neues Projekt erstellen, z.B. eine Windows-Anwendung, und es in einem Container platzieren. Dieser Prozess wird als Teil des veranschaulicht [Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md).  
  
8.  Fügen Sie jedes Mal, wenn Sie die Funktionen hinzufügen, auch Funktionen zum Testprojekt hinzu, um die neue Funktionalität auszuführen.  
  
9. Wiederholen Sie die Schritte, um den Entwurf zu verbessern.  
  
10. Verpacken Sie das Steuerelement, und stellen Sie es bereit. Weitere Informationen finden Sie unter [Bereitstellen von Anwendungen, Diensten und Komponenten](https://msdn.microsoft.com/library/wtzawcsz).  
  
## <a name="see-also"></a>Siehe auch
- [Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [Exemplarische Vorgehensweise: Vererben eines Windows Forms-Steuerelements mit Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)
- [Vorgehensweise: Erben von der UserControl-Klasse](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)
- [Vorgehensweise: Erben von der Control-Klasse](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)
- [Vorgehensweise: Erben von vorhandenen Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)
- [Vorgehensweise: Testen Sie das Laufzeitverhalten eines UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)
- [Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)

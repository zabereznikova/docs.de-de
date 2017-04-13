---
title: "Gewusst wie: Erben von der UserControl-Klasse | Microsoft Docs"
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
  - "Zusammengesetzte Steuerelemente, Erstellen"
  - "Vererbung, Benutzerdefinierte Windows Forms-Steuerelemente"
  - "Benutzersteuerelemente [Windows Forms], Erstellen"
  - "UserControl-Klasse, Erben von"
ms.assetid: 67713625-e2e4-4f6a-bce7-0855ee5043d9
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Erben von der UserControl-Klasse
Um die Funktionalität eines oder mehrerer Windows Forms\-Steuerelemente mit benutzerdefiniertem Code zu kombinieren, können Sie ein *Benutzersteuerelement* erstellen.  Mithilfe von Benutzersteuerelementen kann die schnelle Entwicklung von Steuerelementen mit der Funktionalität von Windows Forms\-Standardsteuerelementen und der Vielseitigkeit von benutzerdefinierten Eigenschaften und Methoden kombiniert werden.  Sobald ein Benutzersteuerelement erstellt wird, wird ein sichtbarer Designer angezeigt, auf dem Windows Forms\-Standardsteuerelemente positioniert werden können.  Diese Steuerelemente behalten sowohl ihre inhärente Funktionalität als auch das Aussehen und Verhalten von Standardsteuerelementen bei.  Wenn sie jedoch einmal in das Benutzersteuerelement integriert sind, sind sie für den Entwickler über Code nicht länger verfügbar.  Vom Benutzersteuerelement wird sowohl das eigene Zeichnen als auch die gesamte grundlegende Funktionalität behandelt, die mit Steuerelementen verbunden ist.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So erstellen Sie ein Benutzersteuerelement  
  
1.  Erstellen Sie ein neues **Windows\-Steuerelementbibliothek**\-Projekt.  
  
     Ein neues Projekt wird mit einem leeren Benutzersteuerelement erstellt.  
  
2.  Ziehen Sie Steuerelemente von der Registerkarte **Windows Forms** der **Toolbox** auf den Designer.  
  
3.  Die Steuerelemente sollten so positioniert und entworfen werden, wie sie im fertig gestellten Steuerelement angezeigt werden sollen.  Wenn Entwickler in der Lage sein sollen, auf die konstituierenden Steuerelemente zuzugreifen, müssen diese als öffentlich deklariert werden. Wahlweise müssen Eigenschaften des konstituierenden Steuerelements selektiv verfügbar gemacht werden.  Ausführliche Informationen finden Sie unter [Gewusst wie: Verfügbarmachen der Eigenschaften konstituierender Steuerelemente](../../../../docs/framework/winforms/controls/how-to-expose-properties-of-constituent-controls.md).  
  
4.  Implementieren Sie alle benutzerdefinierten Methoden oder Eigenschaften, die in das Steuerelement eingebunden werden.  
  
5.  Drücken Sie F5, um das Projekt zu erstellen und das Steuerelement im **UserControl\-Testcontainer** auszuführen.  Weitere Informationen finden Sie unter [Gewusst wie: Testen des Laufzeitverhaltens eines UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
## Siehe auch  
 [Arten von benutzerdefinierten Steuerelementen](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)   
 [Gewusst wie: Erben von der Control\-Klasse](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)   
 [Gewusst wie: Erben von vorhandenen Windows Forms\-Steuerelementen](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)   
 [Gewusst wie: Erstellen von Steuerelementen für Windows Forms](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)   
 [Troubleshooting Inherited Event Handlers in Visual Basic](../Topic/Troubleshooting%20Inherited%20Event%20Handlers%20in%20Visual%20Basic.md)   
 [Gewusst wie: Testen des Laufzeitverhaltens eines UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)
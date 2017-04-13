---
title: "Gewusst wie: Erstellen von Steuerelementen f&#252;r Windows&#160;Forms | Microsoft Docs"
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
  - "Steuerelemente [Windows Forms], Erstellen"
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Erstellen"
  - "UserControl-Klasse, Windows Forms"
ms.assetid: 7570e982-545b-4c3a-a7c7-55581d313400
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Erstellen von Steuerelementen f&#252;r Windows&#160;Forms
Ein Steuerelement repräsentiert einen grafischen Link zwischen Benutzer und Programm.  Mit ihm können Daten bereitgestellt oder verarbeitet, Benutzereingaben angenommen und auf Ereignisse reagiert werden. Außerdem kann eine beliebige Anzahl weiterer Funktionen ausgeführt werden, die Benutzer und Anwendung miteinander verbinden.  Da ein Steuerelement im Wesentlichen eine Komponente mit grafischer Oberfläche darstellt, kann es wie eine Komponente jede Funktion zur Verfügung stellen. Benutzerinteraktion wird ebenfalls ermöglicht.  Steuerelemente werden erstellt, um bestimmte Aufgaben zu erfüllen. Daher handelt es sich beim Erstellen von Steuerelementen lediglich um eine weitere Programmieraufgabe.  Die folgenden Schritte repräsentieren entsprechend eine Übersicht über den Vorgang des Erstellens eines Steuerelements.  Über Links werden zusätzliche Informationen zu den einzelnen Schritten geboten.  
  
> [!NOTE]
>  Informationen über das Erstellen eines benutzerdefinierten Steuerelements zur Verwendung in Web Forms finden Sie unter [Developing Custom ASP.NET Server Controls](../Topic/Developing%20Custom%20ASP.NET%20Server%20Controls.md).  
>   
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So erstellen Sie ein Steuerelement  
  
1.  Legen Sie fest, welche Ziele Sie mit dem Steuerelement erreichen möchten oder welchen Teil der Anwendung es darstellen soll.  Es folgt eine Liste der Faktoren, die zu berücksichtigen sind:  
  
    -   Welche Art von grafischer Oberfläche wird benötigt?  
  
    -   Welche besonderen Benutzerinteraktionen werden von diesem Steuerelement behandelt?  
  
    -   Wird die benötigte Funktionalität schon von vorhandenen Steuerelementen bereitgestellt?  
  
    -   Kann die benötigte Funktionalität durch Kombinieren mehrerer Windows Forms\-Steuerelemente erzielt werden?  
  
2.  Wenn Sie ein Objektmodell für das Steuerelement benötigen, legen Sie fest, welche Funktionalität über das Objektmodell verteilt werden soll. Teilen Sie die Funktionalität anschließend zwischen dem Steuerelement und beliebigen Unterobjekten auf.  Ein Objektmodell kann hilfreich sein, wenn ein komplexes Steuerelement geplant wird oder mehrere Funktionalitäten eingebunden werden sollen.  
  
3.  Legen Sie den Steuerelementtyp entsprechend Ihren Anforderungen fest, z. B. Benutzersteuerelement, benutzerdefiniertes Steuerelement oder geerbtes Windows Forms\-Steuerelement.  Ausführliche Informationen zu diesem Thema finden Sie unter [Empfehlungen zum Typ von Steuerelementen](../../../../docs/framework/winforms/controls/control-type-recommendations.md) und [Arten von benutzerdefinierten Steuerelementen](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md).  
  
4.  Stellen Sie die Funktionalität als Eigenschaften, Methoden und Ereignisse des Steuerelements dar. Weisen Sie außerdem die geeigneten Zugriffsebenen \(z. B. public\) zu.  
  
5.  Wenn Sie für das Steuerelement benutzerdefiniertes Zeichnen benötigen, fügen Sie entsprechenden Code hinzu.  Ausführliche Informationen finden Sie unter [Zeichnen und Ausgeben von benutzerdefinierten Steuerelementen](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).  
  
6.  Wenn das Steuerelement von <xref:System.Windows.Forms.UserControl> erbt, können Sie sein Laufzeitverhalten testen, indem Sie das Steuerelementprojekt erstellen und im **UserControl\-Testcontainer** ausführen.  Weitere Informationen finden Sie unter [Gewusst wie: Testen des Laufzeitverhaltens eines UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
7.  Sie können das Steuerelement auch testen und debuggen, indem Sie ein neues Projekt erstellen, z. B. eine Windows\-Anwendung, und in einem Container platzieren.  Dieser Prozess wird im Thema [Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md) veranschaulicht.  
  
8.  So wie Sie einzelne Features hinzugefügt haben, fügen Sie nun Features zu dem Testprojekt hinzu, um die neue Funktionalität zu überprüfen.  
  
9. Wiederholen Sie die Schritte, während Sie den Entwurf verfeinern.  
  
10. Packen und verteilen Sie das Steuerelement.  Ausführliche Informationen finden Sie unter [Bereitstellen von Anwendungen, Diensten und Komponenten](../Topic/Deploying%20Applications,%20Services,%20and%20Components.md).  
  
## Siehe auch  
 [Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)   
 [Exemplarische Vorgehensweise: Vererben eines Windows Forms\-Steuerelements mit Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)   
 [Gewusst wie: Erben von der UserControl\-Klasse](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)   
 [Gewusst wie: Erben von der Control\-Klasse](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)   
 [Gewusst wie: Erben von vorhandenen Windows Forms\-Steuerelementen](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)   
 [Gewusst wie: Testen des Laufzeitverhaltens eines UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)   
 [Arten von benutzerdefinierten Steuerelementen](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
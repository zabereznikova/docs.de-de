---
title: "Problembehandlung beim Erstellen von Komponenten und Steuerelementen | Microsoft Docs"
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
  - "Komponenten [Windows Forms], Problembehandlung"
  - "Steuerelemente [Windows Forms], Problembehandlung"
  - "Problembehandlung bei Komponenten"
  - "Problembehandlung bei Steuerelementen"
  - "Windows Forms-Steuerelemente, Debuggen"
ms.assetid: e9c8c099-2271-4737-882f-50f336c7a55e
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# Problembehandlung beim Erstellen von Komponenten und Steuerelementen
Unter diesem Thema sind die folgenden Probleme aufgeführt, die bei der Entwicklung von Komponenten und Steuerelementen häufig auftreten.  Weitere Informationen finden Sie unter [Programming with Components](../Topic/Programming%20with%20Components.md).  
  
-   Hinzufügen eines Steuerelements zu einer Toolbox nicht möglich  
  
-   Debuggen des Windows Forms\-Benutzersteuerelements bzw. einer Komponente nicht möglich  
  
-   Ereignis wird im geerbten Steuerelement bzw. in der geerbten Komponente zweimal ausgelöst  
  
-   Entwurfszeitfehler: "Fehler beim Erstellen der Komponente '*Komponentenname*'"  
  
-   STAThreadAttribute  
  
-   Komponentensymbol wird nicht in der Toolbox angezeigt.  
  
## Hinzufügen eines Steuerelements zu einer Toolbox nicht möglich  
 Wenn Sie in die **Toolbox** ein benutzerdefiniertes Steuerelement, das Sie in einem anderen Projekt erstellt haben, bzw. ein Steuerelement von Drittanbieter aufnehmen möchten, müssen Sie diesen Vorgang manuell durchführen.  Wenn das Steuerelement oder die Komponente im aktuellen Projekt enthalten ist, sollte es bzw. sie automatisch in der **Toolbox** angezeigt werden.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).  
  
#### So fügen Sie der Toolbox ein Steuerelement hinzu  
  
1.  Klicken Sie mit der rechten Maustaste auf die **Toolbox**, und wählen Sie im Kontextmenü die Option **Elemente auswählen** aus.  
  
2.  Fügen Sie im Dialogfeld **Toolboxelemente auswählen** die Komponente hinzu:  
  
    -   Wenn Sie eine .NET Framework\-Komponente bzw. ein entsprechendes Steuerelement hinzufügen möchten, klicken Sie auf die Registerkarte **.NET Framework\-Komponenten**.  
  
         – oder –  
  
    -   Wenn Sie eine COM\-Komponente bzw. ein ActiveX\-Steuerelement hinzufügen möchten, klicken Sie auf die Registerkarte **COM\-Komponenten**.  
  
3.  Wenn das Steuerelement im Dialogfeld aufgeführt ist, stellen Sie sicher, dass es ausgewählt ist. Klicken Sie anschließend auf **OK**.  
  
     Das Steuerelement wird der **Toolbox** hinzugefügt.  
  
4.  Wenn das gewünschte Steuerelement nicht im Dialogfeld aufgeführt ist, gehen Sie wie folgt vor:  
  
    1.  Klicken Sie auf die Schaltfläche **Durchsuchen**.  
  
    2.  Wechseln Sie in den Ordner mit der DLL\-Datei, die das Steuerelement enthält.  
  
    3.  Wählen Sie die DLL\-Datei aus, und klicken Sie auf **Öffnen**.  
  
         Das Steuerelement wird im Dialogfeld angezeigt.  
  
    4.  Stellen Sie sicher, dass das Steuerelement ausgewählt ist, und klicken Sie dann auf **OK**.  
  
         Das Steuerelement wird der **Toolbox** hinzugefügt.  
  
## Debuggen des Windows Forms\-Benutzersteuerelements bzw. einer Komponente nicht möglich  
 Wenn sich das Steuerelement von der <xref:System.Windows.Forms.UserControl>\-Klasse ableitet, können Sie sein Laufzeitverhalten mit dem Testcontainer debuggen.  Weitere Informationen finden Sie unter [Gewusst wie: Testen des Laufzeitverhaltens eines UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
 Andere benutzerdefinierte Steuerelemente und Komponenten sind keine eigenständigen Projekte.  Sie müssen von einer Anwendung, z. B. einem Windows Forms\-Projekt, gehostet werden.  Für das Debuggen eines Steuerelements oder einer Komponente müssen Sie es\/sie einem Windows Forms\-Projekt hinzufügen.  
  
#### So debuggen Sie ein Steuerelement bzw. eine Komponente  
  
1.  Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.  
  
2.  Wählen Sie im Menü **Datei** die Option **Hinzufügen** und anschließend **Neues Projekt**, um der Anwendung ein Testprojekt hinzuzufügen.  
  
3.  Wählen Sie im Dialogfeld **Neues Projekt hinzufügen** die Option **Windows\-Anwendung** für den Projekttyp.  
  
4.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf den Knoten **Verweise** für das neue Projekt.  Klicken Sie im Kontextmenü auf **Verweis hinzufügen**, um dem Projekt mit dem Steuerelement oder der Komponente einen Verweis hinzuzufügen.  
  
5.  Erstellen Sie eine Instanz des Steuerelements bzw. der Komponente im Testprojekt.  Wenn sich die Komponente in der **Toolbox** befindet, können Sie sie auf die Designeroberfläche ziehen. Wahlweise können Sie die Instanz auch wie im nächsten Codebeispiel gezeigt programmgesteuert erstellen:  
  
    ```vb  
    Dim Component1 As New MyNeatComponent()  
    ```  
  
    ```csharp  
    MyNeatComponent Component1 = new MyNeatComponent();  
    ```  
  
     Jetzt können Sie das Steuerelement bzw. die Komponente wie gewohnt debuggen.  
  
 Weitere Informationen zum Debuggen finden Sie unter [Debuggen in Visual Studio](../Topic/Debugging%20in%20Visual%20Studio.md) und [Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms\-Steuerelementen zur Entwurfszeit](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).  
  
## Ereignis wird im geerbten Steuerelement bzw. in der geerbten Komponente zweimal ausgelöst  
 Ursache dafür ist mit großer Wahrscheinlichkeit eine doppelt vorliegende `Handles`\-Klausel.  Weitere Informationen finden Sie unter [Troubleshooting Inherited Event Handlers in Visual Basic](../Topic/Troubleshooting%20Inherited%20Event%20Handlers%20in%20Visual%20Basic.md).  
  
## Entwurfszeitfehler: "Fehler beim Erstellen der Komponente 'Komponentenname'"  
 Die Komponente oder das Steuerelement muss einen Standardkonstruktor ohne Parameter bereitstellen.  Wenn die Entwurfsumgebung eine Instanz des Steuerelements oder der Komponente erstellt, versucht sie nicht, Parameter für Konstruktorüberladungen bereitzustellen, die Parameter enthalten.  
  
## STAThreadAttribute  
 Das <xref:System.STAThreadAttribute> informiert die Common Language Runtime \(CLR\), dass Windows Forms das Singlethread\-Apartmentmodell verwendet.  Wenn Sie dieses Attribut nicht auf die `Main`\-Methode der Windows Forms\-Anwendung anwenden, kann es zu unerwartetem Verhalten kommen.  Zum Beispiel werden Hintergrundbilder möglicherweise für Steuerelemente wie <xref:System.Windows.Forms.ListView> nicht angezeigt.  Einige Steuerelemente benötigen dieses Attribut möglicherweise auch zur ordnungsgemäßen automatischen Vervollständigung und für das Drag & Drop\-Verhalten.  
  
## Komponentensymbol wird nicht in der Toolbox angezeigt.  
 Wenn Sie <xref:System.Drawing.ToolboxBitmapAttribute> zum Verknüpfen eines Symbols mit der benutzerdefinierten Komponente verwenden, wird in der Toolbox für automatisch erstellte Komponenten keine Bitmap angezeigt.  Damit die Bitmap angezeigt wird, müssen Sie das Steuerelement über das Dialogfeld **Toolboxelemente auswählen** neu laden.  Weitere Informationen finden Sie unter [Gewusst wie: Bereitstellen einer Toolboxbitmap für ein Steuerelement](../../../../docs/framework/winforms/controls/how-to-provide-a-toolbox-bitmap-for-a-control.md).  
  
## Siehe auch  
 [Entwickeln von Windows Forms\-Steuerelementen zur Entwurfszeit](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)   
 [Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)   
 [Gewusst wie: Testen des Laufzeitverhaltens eines UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)   
 [Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms\-Steuerelementen zur Entwurfszeit](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)   
 [Component Authoring](../Topic/Component%20Authoring.md)   
 [Troubleshooting Design\-Time Development](../Topic/Troubleshooting%20Design-Time%20Development.md)   
 [Programming with Components](../Topic/Programming%20with%20Components.md)
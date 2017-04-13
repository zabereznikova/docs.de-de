---
title: "Exemplarische Vorgehensweise: Demonstrieren der visuellen Vererbung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Formularvererbung, Exemplarische Vorgehensweisen"
  - "Vererbung, Exemplarische Vorgehensweisen"
  - "Visuelle Vererbung"
  - "Exemplarische Vorgehensweisen [Windows Forms], Visuelle Vererbung"
  - "Windows Forms, Vererbung"
ms.assetid: 01966086-3142-450e-8210-3fd4cb33f591
caps.latest.revision: 24
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# Exemplarische Vorgehensweise: Demonstrieren der visuellen Vererbung
Mit visueller Vererbung können Sie die Steuerelemente auf dem Basisformular anzeigen und neue Steuerelemente hinzufügen.  In dieser exemplarischen Vorgehensweise erstellen Sie ein Basisformular und kompilieren es in eine Klassenbibliothek.  Sie importieren diese Klassenbibliothek in ein anderes Projekt und erstellen ein neues Formular, das vom Basisformular erbt.  Bei dieser exemplarischen Vorgehensweise lernen Sie Folgendes:  
  
-   Erstellen eines Klassenbibliotheksprojekts, das ein Basisformular enthält.  
  
-   Hinzufügen einer Schaltfläche mit Eigenschaften, die abgeleitete Klassen des Basisformulars ändern können.  
  
-   Hinzufügen einer Schaltfläche, die von Erben des Basisformulars nicht geändert werden kann.  
  
-   Erstellen eines Projekts, das ein Formular enthält, das von `BaseForm` erbt.  
  
 Schließlich wird in dieser exemplarischen Vorgehensweise der Unterschied zwischen privaten und geschützten Steuerelementen in einem geerbten Formular gezeigt.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren**, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
> [!CAUTION]
>  Nicht alle Steuerelemente unterstützen visuelle Vererbung von einem Basisformular.  Die folgenden Steuerelemente unterstützen das in dieser exemplarischen Vorgehensweise beschriebene Szenario nicht:  
>   
>  <xref:System.Windows.Forms.WebBrowser>  
>   
>  <xref:System.Windows.Forms.ToolStrip>  
>   
>  <xref:System.Windows.Forms.ToolStripPanel>  
>   
>  <xref:System.Windows.Forms.TableLayoutPanel>  
>   
>  <xref:System.Windows.Forms.FlowLayoutPanel>  
>   
>  <xref:System.Windows.Forms.DataGridView>  
>   
>  Diese Steuerelemente im geerbten Formular sind immer schreibgeschützt, unabhängig von den verwendeten Modifizierern \(`private`, `protected` oder `public`\).  
  
## Szenarioschritte  
 Der erste Schritt ist das Erstellen des Basisformulars.  
  
#### So erstellen Sie ein Klassenbibliotheksprojekt, das ein Basisformular enthält  
  
1.  Wählen Sie im Menü **Datei** den Befehl **Neu** aus, und wählen Sie dann **Projekt** aus, um das Dialogfeld **Neues Projekt** zu öffnen.  
  
2.  Erstellen Sie eine Windows Forms\-Anwendung namens `BaseFormLibrary`.  
  
3.  Um eine Klassenbibliothek anstelle einer Windows Forms\-Standardanwendung zu erstellen, klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf den Projektknoten **BaseFormLibrary**, und wählen Sie dann **Eigenschaften** aus.  
  
4.  Ändern Sie in den Eigenschaften für das Projekt **Ausgabetyp** von **Windows\-Anwendung** in **Klassenbibliothek**.  
  
5.  Wählen Sie im Menü **Datei** die Option **Alle speichern** aus, um das Projekt und die Dateien am Standardspeicherort zu speichern.  
  
 Mit den nächsten zwei Verfahren werden dem Basisformular Schaltflächen hinzugefügt.  Zur Demonstration der visuellen Vererbung weisen Sie den Schaltflächen verschiedene Zugriffsebenen zu, indem Sie ihre `Modifiers`Eigenschaften festlegen.  
  
#### So fügen Sie eine Schaltfläche hinzu, die von Erben des Basisformulars geändert werden kann  
  
1.  Öffnen Sie **Form1** im Designer.  
  
2.  Auf der Registerkarte **Alle Windows Forms** der **Toolbox** doppelklicken Sie auf **Schaltfläche**, um dem Formular eine Schaltfläche hinzuzufügen.  Verwenden Sie die Maus, um die Position und Größe der Schaltfläche anzupassen.  
  
3.  Legen Sie im "Eigenschaftenfenster" die folgenden Eigenschaften der Schaltfläche fest:  
  
    -   Legen Sie die Eigenschaft **Text** auf **Say Hello** fest.  
  
    -   Legen Sie die Eigenschaft **Name** auf **btnProtected** fest.  
  
    -   Legen Sie die Eigenschaft **Modifizierer** auf **Protected** fest.  Hierdurch können Formulare, die von **Form1** erben, die Eigenschaften von **btnProtected** ändern.  
  
4.  Doppelklicken Sie auf die Schaltfläche **Say Hello**, um einen Ereignishandler für das Ereignis **Click** hinzuzufügen.  
  
5.  Fügen Sie dem Ereignishandler folgende Codezeile hinzu:  
  
    ```vb  
    MessageBox.Show("Hello, World!")  
    ```  
  
    ```csharp  
    MessageBox.Show("Hello, World!");  
    ```  
  
#### So fügen Sie eine Schaltfläche hinzu, die von Erben des Basisformulars nicht geändert werden kann  
  
1.  Wechseln Sie in die Entwurfsansicht, indem Sie über dem Code\-Editor auf die Registerkarte **Form1.vb \[Design\], Form1.cs \[Design\] oder Form1.jsl \[Design\]** klicken, oder drücken Sie F7.  
  
2.  Fügen Sie eine zweite Schaltfläche hinzu, und legen Sie deren Eigenschaften wie folgt fest:  
  
    -   Legen Sie die Eigenschaft **Text** auf **Say Goodbye** fest.  
  
    -   Legen Sie die Eigenschaft **\(Name\)** auf **btnPrivate** fest.  
  
    -   Legen Sie die Eigenschaft **Modifizierer** auf **Private** fest.  Hierdurch können Formulare, die von **Form1** erben, die Eigenschaften von **btnPrivate** nicht ändern.  
  
3.  Doppelklicken Sie auf die Schaltfläche **Say Goodbye**, um einen Ereignishandler für das Ereignis **Click** hinzuzufügen.  Platzieren Sie die folgende Codezeile in der Ereignisprozedur:  
  
    ```vb  
    MessageBox.Show("Goodbye!")  
    ```  
  
    ```csharp  
    MessageBox.Show("Goodbye!");  
    ```  
  
4.  Wählen Sie im Menü **Erstellen** **BaseForm\-Bibliothek erstellen** aus, um die Klassenbibliothek zu erstellen.  
  
     Nachdem die Bibliothek erstellt wurde, können Sie ein neues Projekt erstellen, das von dem Formular erbt, das Sie gerade erstellt haben.  
  
#### So erstellen Sie ein Projekt, das ein Formular enthält, das vom Basisformular erbt  
  
1.  Wählen Sie im Menü **Datei** den Befehl **Hinzufügen** aus, und wählen Sie dann **Neues Projekt** aus, um das Dialogfeld **Neues Projekt hinzufügen** zu öffnen.  
  
2.  Erstellen Sie eine Windows Forms\-Anwendung namens `InheritanceTest`.  
  
#### So fügen Sie ein geerbtes Formular hinzu  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf das Projekt **InheritanceTest**, wählen Sie **Hinzufügen** aus und dann **Neues Element**.  
  
2.  Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Kategorie **Windows Forms** aus \(wenn Sie eine Liste mit Kategorien haben\), und wählen Sie dann die Vorlage **Geerbtes Formular** aus.  
  
3.  Übernehmen Sie den Standardnamen `Form2`, und klicken Sie auf **Hinzufügen**.  
  
4.  Wählen Sie im Dialogfeld **Vererbungsauswahl** im Projekt **BaseFormLibrary** als Formular, von dem geerbt werden soll, **Form1** aus, und klicken Sie auf **OK**.  
  
     Hierdurch wird ein Formular im Projekt **InheritanceTest** erstellt, das von dem Formular in **BaseFormLibrary** abgeleitet wird.  
  
5.  Öffnen Sie das geerbte Formular \(**Form2**\) im Designer, indem Sie darauf doppelklicken, wenn es nicht bereits geöffnet ist.  
  
     Im Designer haben die geerbten Schaltflächen ein Symbol \(![VisualBasicInheritanceSymbol&#45;Bildschirmabbildung](../../../../docs/framework/winforms/advanced/media/vbinheritanceglyph.png "vbInheritanceGlyph")\) in der oberen Ecke, das anzeigt, dass sie geerbt sind.  
  
6.  Wählen Sie die Schaltfläche **Say Hello** aus, und beachten Sie die Ziehpunkte zur Größenänderung.  Da diese Schaltfläche geschützt ist, können die Erben sie verschieben, ihre Größe ändern, ihre Beschriftung ändern und andere Änderungen vornehmen.  
  
7.  Wählen Sie die private Schaltfläche **Say Goodbye** aus, und beachten Sie, dass sie über keine Ziehpunkte zur Größenänderung verfügt.  Darüber hinaus sind im Fenster **Eigenschaften** die Eigenschaften dieser Schaltfläche abgeblendet, um anzuzeigen, dass sie nicht geändert werden können.  
  
8.  Bei Verwendung von [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]:  
  
    1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste im Projekt **InheritanceTest** auf **Form1**, und wählen Sie dann **Löschen** aus.  Klicken Sie in dem angezeigten Meldungsfeld auf **OK**, um den Löschvorgang zu bestätigen.  
  
    2.  Öffnen Sie die Datei "Program.cs", und ändern Sie die Zeile `Application.Run(new Form1());` in `Application.Run(new Form2());`.  
  
9. Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf das Projekt **InheritanceTest**, und wählen Sie **Als Startprojekt festlegen** aus.  
  
10. Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf das Projekt **InheritanceTest**, und wählen Sie **Eigenschaften** aus.  
  
11. Legen Sie auf den **InheritanceTest**\-Eigenschaftenseiten für das **Startobjekt** fest, dass es das geerbte Formular sein soll \(**Form2**\).  
  
12. Drücken Sie F5, um die Anwendung auszuführen, und beobachten Sie das Verhalten des geerbten Formulars.  
  
## Nächste Schritte  
 Die Vererbung bei Benutzersteuerelementen funktioniert größtenteils auf die gleiche Weise.  Öffnen Sie ein neues Klassenbibliotheksprojekt, und fügen Sie ein Benutzersteuerelement hinzu.  Platzieren Sie konstituierende Steuerelemente darauf, und kompilieren Sie das Projekt.  Öffnen Sie ein weiteres, neues Klassenbibliotheksprojekt, und fügen Sie einen Verweis auf die kompilierte Klassenbibliothek hinzu.  Versuchen Sie außerdem, dem Projekt ein geerbtes Steuerelement hinzuzufügen \(über das Dialogfeld **Neue Elemente hinzufügen**\) sowie die **Vererbungsauswahl** zu verwenden.  Fügen Sie ein Benutzersteuerelement hinzu, und ändern Sie die `Inherits`\-Anweisung \(`:` in [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]\).  Weitere Informationen finden Sie unter [Gewusst wie: Erben von Windows Forms](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md).  
  
## Siehe auch  
 [Gewusst wie: Erben von Windows Forms](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)   
 [Visuelle Vererbung in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)   
 [Windows Forms](../../../../docs/framework/winforms/index.md)
---
title: "Exemplarische Vorgehensweise: Vererben von einem Windows&#160;Forms-Steuerelement mit Visual&#160;C# | Microsoft Docs"
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
  - "Benutzerdefinierte Steuerelemente [Windows Forms], Vererbung"
  - "Vererbung, Steuerelement"
  - "Vererbung, Benutzerdefinierte Steuerelemente"
  - "Vererbung, Exemplarische Vorgehensweisen"
  - "Windows Forms-Steuerelemente, Vererbung"
ms.assetid: 09476da0-8d4c-4a4c-b969-649519dfb438
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Exemplarische Vorgehensweise: Vererben von einem Windows&#160;Forms-Steuerelement mit Visual&#160;C# #
Mit [!INCLUDE[csprcslong](../../../../includes/csprcslong-md.md)] können Sie leistungsstarke benutzerdefinierte Steuerelemente durch *Vererbung* erstellen.  Durch Vererbung können Sie Steuerelemente mit der gesamten Funktionalität von standardmäßigen Windows Forms\-Steuerelementen erstellen, die zusätzlich über benutzerdefinierte Funktionalität verfügen.  In dieser exemplarischen Vorgehensweise erstellen Sie ein einfaches geerbtes Steuerelement mit der Bezeichnung `ValueButton`.  Diese Schaltfläche erbt die Funktionalität des standardmäßigen Windows Forms\-Steuerelements <xref:System.Windows.Forms.Button> und macht eine benutzerdefinierte Eigenschaft mit der Bezeichnung `ButtonValue` verfügbar.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Erstellen des Projekts  
 Wenn Sie ein neues Projekt erstellen, geben Sie dessen Namen an, um Stammnamespace, Assemblyname und Projektname einzurichten und sicherzustellen, dass die Standardkomponente sich im richtigen Namespace befindet.  
  
#### So erstellen Sie die ValueButtonLib\-Steuerelementbibliothek und das ValueButton\-Steuerelement  
  
1.  Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**, um das Dialogfeld **Neues Projekt** zu öffnen.  
  
2.  Wählen Sie in der Liste der [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]\-Projekte die Projektvorlage **Windows Forms\-Steuerelementbibliothek** aus, und geben Sie im Feld **Name** die Zeichenfolge `ValueButtonLib` ein.  
  
     Der Projektname `ValueButtonLib` wird standardmäßig auch dem Stammnamespace zugewiesen.  Der Stammnamespace wird dazu verwendet, die Namen der Komponenten in der Assembly zu qualifizieren.  Wenn beispielsweise zwei Assemblys Komponenten mit der Bezeichnung `ValueButton` bereitstellen, können Sie die zu verwendende `ValueButton`\-Komponente mit `ValueButtonLib.ValueButton` spezifizieren.  Weitere Informationen finden Sie unter [Namespaces](../Topic/Namespaces%20\(C%23%20Programming%20Guide\).md).  
  
3.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf **UserControl1.cs**, und wählen Sie im Kontextmenü **Umbenennen** aus.  Ändern Sie den Dateinamen in `ValueButton.cs`.  Klicken Sie auf die Schaltfläche **Ja**, wenn Sie gefragt werden, ob Sie alle Verweise auf das Codeelement '`UserControl1`' umbenennen möchten.  
  
4.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf **ValueButton.cs**, und wählen Sie **Code anzeigen** aus.  
  
5.  Suchen Sie die `class`\-Anweisungszeile `public partial class ValueButton`, und ändern Sie den Typ, von dem dieses Steuerelement von <xref:System.Windows.Forms.UserControl> erbt, in <xref:System.Windows.Forms.Button>.  Dadurch kann das geerbte Steuerelement die gesamte Funktionalität des <xref:System.Windows.Forms.Button>\-Steuerelements erben.  
  
6.  Öffnen Sie im **Projektmappen\-Explorer** den Knoten **ValueButton.cs**, um die vom Designer generierte Codedatei **ValueButton.Designer.cs** anzuzeigen.  Öffnen Sie diese Datei im **Code\-Editor**.  
  
7.  Suchen Sie die `InitializeComponent`\-Methode, und entfernen Sie die Zeile, die die <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A>\-Eigenschaft zuweist.  Diese Eigenschaft ist im <xref:System.Windows.Forms.Button>\-Steuerelement nicht vorhanden.  
  
8.  Klicken Sie im Menü **Datei** auf **Alle speichern**, um das Projekt zu speichern.  
  
    > [!NOTE]
    >  Ein visueller Designer ist nicht mehr verfügbar.  Da sich das <xref:System.Windows.Forms.Button>\-Steuerelement selbst zeichnet, können Sie dessen Darstellung im Designer nicht ändern.  Die visuelle Darstellung des Steuerelements entspricht genau der Klasse, von der es erbt \(in diesem Fall <xref:System.Windows.Forms.Button>\), sofern im Code keine Änderung vorgenommen wurde.  Sie können weiterhin Komponenten, die über keine Benutzeroberflächenelemente verfügen, der Entwurfsoberfläche hinzufügen.  
  
## Hinzufügen einer Eigenschaft zum geerbten Steuerelement  
 Eine Möglichkeit, geerbte Windows Forms\-Steuerelemente zu verwenden, besteht darin, Steuerelemente zu erstellen, die in Art und Aussehen mit den standardmäßigen Windows Forms\-Steuerelementen identisch sind, dabei aber benutzerdefinierte Eigenschaften verfügbar machen.  In diesem Abschnitt fügen Sie dem Steuerelement eine Eigenschaft mit der Bezeichnung `ButtonValue` hinzu.  
  
#### So fügen Sie die Value\-Eigenschaft hinzu  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf **ValueButton.cs**, und klicken Sie dann im Kontextmenü auf **Code anzeigen**.  
  
2.  Suchen Sie die `class`\-Anweisung.  Fügen Sie direkt nach der geschweiften Klammer \(`{`\) den folgenden Code ein:  
  
     \[C\#\]  
  
    ```  
    // Creates the private variable that will store the value of your   
    // property.  
    private int varValue;  
    // Declares the property.  
    public int ButtonValue  
    {  
       // Sets the method for retrieving the value of your property.  
       get  
       {  
          return varValue;  
       }  
       // Sets the method for setting the value of your property.  
       set  
       {  
          varValue = value;  
       }  
    }  
    ```  
  
     Durch diesen Code werden die Methoden festgelegt, mit denen die `ButtonValue`\-Eigenschaft gespeichert und abgerufen wird.  Die `get`\-Anweisung legt den Wert fest, der für den in der privaten Variable `varValue` gespeicherten Wert zurückgegeben wird, und die `set`\-Anweisung legt den Wert der privaten Variable mithilfe des `value`\-Schlüsselworts fest.  
  
3.  Klicken Sie im Menü **Datei** auf **Alle speichern**, um das Projekt zu speichern.  
  
## Testen des Steuerelements  
 Steuerelemente sind keine eigenständigen Projekte und müssen daher in einem Container untergebracht werden.  Zum Testen des Steuerelements müssen Sie ein Testprojekt erstellen, in dem das Steuerelement ausgeführt wird.  Außerdem müssen Sie das Steuerelement für das Testprojekt zugänglich machen, indem Sie es erstellen \(kompilieren\).  In diesem Abschnitt erstellen Sie das Steuerelement und testen es in einem Windows Form.  
  
#### So erstellen Sie das Steuerelement  
  
1.  Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.  
  
     Das Build sollte erfolgreich und ohne Compilerfehler oder \-warnungen abgeschlossen werden.  
  
#### So erstellen Sie ein Testprojekt  
  
1.  Zeigen Sie im Menü **Datei** auf **Hinzufügen**, und klicken Sie auf **Neues Projekt**, um das Dialogfeld **Neues Projekt hinzufügen** zu öffnen.  
  
2.  Wählen Sie den Knoten **Windows** unter dem Knoten **Visual C\#** aus, und klicken Sie auf **Windows Forms\-Anwendung**.  
  
3.  Geben Sie im Feld **Name** die Zeichenfolge `Test` ein.  
  
4.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf den Knoten **Verweise** für das Testprojekt, und klicken Sie im Kontextmenü auf **Verweis hinzufügen**, um das Dialogfeld **Verweis hinzufügen** anzuzeigen.  
  
5.  Klicken Sie auf die Registerkarte **Projekte**.  Das `ValueButtonLib`\-Projekt wird unter **Projektname** aufgeführt.  Doppelklicken Sie auf das Projekt, um dem Testprojekt den Verweis hinzuzufügen.  
  
6.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf **Test**, und wählen Sie **Erstellen** aus.  
  
#### So fügen Sie das Steuerelement dem Formular hinzu  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf **Form1.cs**, und wählen Sie im Kontextmenü **Designer anzeigen** aus.  
  
2.  Klicken Sie in der **Toolbox** auf **ValueButtonLib Components**.  Doppelklicken Sie auf **ValueButton**.  
  
     In dem Formular wird ein **ValueButton** angezeigt.  
  
3.  Klicken Sie mit der rechten Maustaste auf **ValueButton**, und wählen Sie im Kontextmenü **Eigenschaften** aus.  
  
4.  Prüfen Sie im **Eigenschaftenfenster** die Eigenschaften des Steuerelements.  Beachten Sie, dass diese mit Ausnahme einer Eigenschaft \(der `ButtonValue`\-Eigenschaft\) mit den durch eine standardmäßige Schaltfläche verfügbar gemachten Eigenschaften übereinstimmen.  
  
5.  Legen Sie für die `ButtonValue`\-Eigenschaft `5` fest.  
  
6.  Doppelklicken Sie auf der Registerkarte **Alle Windows Forms** der **Toolbox** auf **Label**, um dem Formular ein <xref:System.Windows.Forms.Label>\-Steuerelement hinzuzufügen.  
  
7.  Verschieben Sie das Label\-Steuerelement in die Mitte des Formulars.  
  
8.  Doppelklicken Sie auf `valueButton1`.  
  
     Der **Code\-Editor** wird geöffnet und springt zum `valueButton1_Click`\-Ereignis.  
  
9. Geben Sie folgende Codezeile ein.  
  
     \[C\#\]  
  
    ```  
    label1.Text = valueButton1.ButtonValue.ToString();  
    ```  
  
10. Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf **Test**, und wählen Sie im Kontextmenü **Als Startprojekt festlegen**.  
  
11. Wählen Sie im Menü **Debuggen** die Option **Debuggen starten**.  
  
     `Form1` wird angezeigt.  
  
12. Klicken Sie auf `valueButton1`.  
  
     In `label1` wird die Zahl '5' angezeigt, was darauf hinweist, dass die `ButtonValue`\-Eigenschaft des geerbten Steuerelements mithilfe der `valueButton1_Click`\-Methode an `label1` übergeben wurde.  Somit erbt das `ValueButton`\-Steuerelement alle Funktionen der Windows Forms\-Standardschaltfläche, macht jedoch eine zusätzliche benutzerdefinierte Eigenschaft verfügbar.  
  
## Siehe auch  
 [Programming with Components](../Topic/Programming%20with%20Components.md)   
 [Component Authoring Walkthroughs](../Topic/Component%20Authoring%20Walkthroughs.md)   
 [Gewusst wie: Anzeigen eines Steuerelements im Dialogfeld "Toolboxelemente auswählen"](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)   
 [Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual C\#](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)
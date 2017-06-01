---
title: "Exemplarische Vorgehensweise: Serialisieren der Auflistungen von Standardtypen mit dem DesignerSerializationVisibilityAttribute | Microsoft Docs"
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
  - "Auflistungen, Serialisieren"
  - "Auflistungen, Standardtypen"
  - "DesiginerSerializationVisibilityAttribute-Klasse"
  - "Serialisierung, Auflistungen"
  - "Standardtypen, Auflistungen"
ms.assetid: 020c9df4-fdc5-4dae-815a-963ecae5668c
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Exemplarische Vorgehensweise: Serialisieren der Auflistungen von Standardtypen mit dem DesignerSerializationVisibilityAttribute
Die benutzerdefinierten Steuerelemente machen manchmal eine Auflistung als Eigenschaft verfügbar.  Diese exemplarische Vorgehensweise veranschaulicht, wie Sie mit der <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>\-Klasse steuern können, wie eine Auflistung zur Entwurfszeit serialisiert wird.  Wenn Sie den <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content>\-Wert auf die Auflistungseigenschaft anwenden, ist gewährleistet, dass die Eigenschaft serialisiert wird.  
  
 Informationen zum Kopieren des Codes in diesem Thema als einzelne Auflistung finden Sie unter [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](../Topic/How%20to:%20Serialize%20Collections%20of%20Standard%20Types%20with%20the%20DesignerSerializationVisibilityAttribute.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Vorbereitungsmaßnahmen  
 Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:  
  
-   Ausreichende Berechtigungen zum Erstellen und Ausführen von Windows Forms\-Anwendungsprojekten auf dem Computer, auf dem Visual Studio installiert ist.  
  
## Erstellen eines Steuerelements, das über eine serialisierbare Auflistung verfügt  
 Der erste Schritt besteht darin, ein Steuerelement zu erstellen, das über eine serialisierbare Auflistung als Eigenschaft verfügt.  Sie können den Inhalt dieser Auflistung mithilfe des **Auflistungs\-Editors** bearbeiten, den Sie über das **Eigenschaftenfenster** aufrufen können.  
  
#### So erstellen Sie ein Steuerelement, das über eine serialisierbare Auflistung verfügt  
  
1.  Erstellen Sie ein Windows\-Steuerelementbibliothek\-Projekt mit dem Namen `SerializationDemoControlLib`.  Weitere Informationen finden Sie unter [Windows Control Library Template](http://msdn.microsoft.com/de-de/722f4e2d-1310-4ed5-8f33-593337ab66b4).  
  
2.  Benennen Sie `UserControl1` in `SerializationDemoControl` um.  Weitere Informationen finden Sie unter [How to: Rename Identifiers](http://msdn.microsoft.com/de-de/2430f732-2b70-4516-8cf6-a7bb71cc9724).  
  
3.  Legen Sie im Fenster **Eigenschaften** den Wert der <xref:System.Windows.Forms.Padding.All%2A?displayProperty=fullName>\-Eigenschaft auf `10` fest.  
  
4.  Fügen Sie ein <xref:System.Windows.Forms.TextBox>\-Steuerelement in das `SerializationDemoControl` ein.  
  
5.  Wählen Sie das <xref:System.Windows.Forms.TextBox>\-Steuerelement aus.  Legen Sie im **Eigenschaftenfenster** die folgenden Eigenschaften fest.  
  
    |Property|Ändern in|  
    |--------------|---------------|  
    |**Multiline**|`true`|  
    |**Dock**|<xref:System.Windows.Forms.DockStyle>|  
    |**ScrollBars**|<xref:System.Windows.Forms.ScrollBars>|  
    |**ReadOnly**|`true`|  
  
6.  Deklarieren Sie im **Code\-Editor** ein Zeichenfolgenarrayfeld mit dem Namen `stringsValue` im `SerializationDemoControl`.  
  
     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]  
  
7.  Definieren Sie die `Strings`\-Eigenschaft für das `SerializationDemoControl`.  
  
> [!NOTE]
>  Der <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content>\-Wert wird verwendet, um die Serialisierung der Auflistung zu ermöglichen.  
  
 [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
 [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
 [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]  
  
1.  Drücken Sie F5, um das Projekt zu erstellen und das Steuerelement im **UserControl\-Testcontainer** auszuführen.  
  
2.  Suchen Sie die `Strings`\-Eigenschaft im <xref:System.Windows.Forms.PropertyGrid> **UserControl\-Testcontainer**.  Klicken Sie auf die `Strings`\-Eigenschaft und anschließend auf die Schaltfläche mit den Auslassungszeichen \(![VisualStudioEllipsesButton&#45;Bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\), um den **Zeichenfolgen\-Editor** zu öffnen.  
  
3.  Geben Sie mehrere Zeichenfolgen in den **Zeichenfolgen\-Editor** ein.  Trennen Sie sie, indem Sie am Ende jeder Zeichenfolge die EINGABETASTE drücken.  Klicken Sie auf **OK**, wenn Sie alle Zeichenfolgen eingegeben haben.  
  
> [!NOTE]
>  Die von Ihnen eingegebenen Zeichenfolgen werden in der <xref:System.Windows.Forms.TextBox> des `SerializationDemoControl` angezeigt.  
  
## Serialisieren einer Auflistungseigenschaft  
 Um das Serialisierungsverhalten des Steuerelements zu testen, fügen Sie es auf einem Formular ein und ändern den Inhalt der Auflistung mit dem **Auflistungs\-Editor**.  Sie können den Zustand der serialisierten Auflistung anhand einer speziellen Designer\-Datei erkennen, in die der **Windows Forms\-Designer** Code ausgibt.  
  
#### So serialisieren Sie eine Auflistung  
  
1.  Fügen Sie der Projektmappe ein neues Windows\-Anwendungsprojekt hinzu.  Geben Sie dem Projekt die Bezeichnung `SerializationDemoControlTest`.  
  
2.  Suchen Sie in der **Toolbox** die Registerkarte mit dem Namen **SerializationDemoControlLib Components**.  Auf dieser Registerkarte befindet sich das `SerializationDemoControl`.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).  
  
3.  Fügen Sie ein `SerializationDemoControl` auf dem Formular ein.  
  
4.  Suchen Sie die `Strings`\-Eigenschaft im **Eigenschaftenfenster**.  Klicken Sie auf die `Strings`\-Eigenschaft und anschließend auf die Schaltfläche mit den Auslassungszeichen \(![VisualStudioEllipsesButton&#45;Bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\), um den **Zeichenfolgen\-Editor** zu öffnen.  
  
5.  Geben Sie mehrere Zeichenfolgen in den **Zeichenfolgen\-Editor** ein.  Trennen Sie sie, indem Sie am Ende jeder Zeichenfolge die EINGABETASTE drücken.  Klicken Sie auf **OK**, wenn Sie alle Zeichenfolgen eingegeben haben.  
  
> [!NOTE]
>  Die von Ihnen eingegebenen Zeichenfolgen werden in der <xref:System.Windows.Forms.TextBox> des `SerializationDemoControl` angezeigt.  
  
1.  Klicken Sie im **Projektmappen\-Explorer** auf die Schaltfläche **Alle Dateien anzeigen**.  
  
2.  Öffnen Sie den Knoten **Form1**.  Darunter befindet sich eine Datei mit dem Namen **Form1.Designer.cs** oder **Form1.Designer.vb**.  Dies ist die Datei, in die der **Windows Forms\-Designer** Code ausgibt, der den Zustand des Formulars und dessen untergeordneten Steuerelemente zur Entwurfszeit wiedergibt.  Öffnen Sie diese Datei im **Code\-Editor**.  
  
3.  Öffnen Sie den Bereich **Vom Windows Form\-Designer generierter Code**, und suchen Sie den Abschnitt **serializationDemoControl1**.  Unter dieser Bezeichnung befindet sich der Code, der dem serialisierten Zustand des Steuerelements entspricht.  Die Zeichenfolgen, die Sie in Schritt 5 eingegeben haben, werden in einer Zuweisung zur `Strings`\-Eigenschaft angezeigt.  Der Code im folgenden Beispiel entspricht in etwa dem Code, der angezeigt würde, wenn Sie die Zeichenfolgen "red", "orange" und "yellow" eingegeben hätten.  
  
4.  \[Visual Basic\]  
  
    ```  
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}  
    ```  
  
5.  \[C\#\]  
  
    ```  
    this.serializationDemoControl1.Strings = new string[] {  
            "red",  
            "orange",  
            "yellow"};  
    ```  
  
6.  Ändern Sie im **Code\-Editor** in der `Strings`\-Eigenschaft den Wert von <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> auf <xref:System.ComponentModel.DesignerSerializationVisibility>.  
  
7.  \[Visual Basic\]  
  
    ```  
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _  
    ```  
  
8.  \[C\#\]  
  
    ```  
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]  
    ```  
  
9. Erstellen Sie die Projektmappe neu, und wiederholen Sie die Schritte 4 bis 8.  
  
> [!NOTE]
>  In diesem Fall gibt der **Windows Forms\-Designer** keine Zuweisung zur `Strings`\-Eigenschaft aus.  
  
## Nächste Schritte  
 Nachdem Sie wissen, wie Sie eine Auflistung von Standardtypen serialisieren können, sollten Sie es in Erwägung ziehen, Ihre benutzerdefinierten Steuerelemente stärker in die Entwurfszeitumgebung zu integrieren.  In den folgenden Themen wird beschrieben, wie Sie die Entwurfszeitintegrierung der benutzerdefinierten Steuerelemente verbessern können:  
  
-   [Design\-Time Architecture](../Topic/Design-Time%20Architecture.md)  
  
-   [Attribute in Windows Forms\-Steuerelementen](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
  
-   [Designer Serialization Overview](../Topic/Designer%20Serialization%20Overview.md)  
  
-   [Exemplarische Vorgehensweise: Erstellen eines Windows Forms\-Steuerelements, das Visual Studio\-Entwurfszeitfeatures nutzt](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
  
## Siehe auch  
 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>   
 [Designer Serialization Overview](../Topic/Designer%20Serialization%20Overview.md)   
 [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](../Topic/How%20to:%20Serialize%20Collections%20of%20Standard%20Types%20with%20the%20DesignerSerializationVisibilityAttribute.md)   
 [Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
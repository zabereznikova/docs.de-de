---
title: 'Exemplarische Vorgehensweise: Serialisieren der Auflistungen von Standardtypen mit dem DesignerSerializationVisibilityAttribute'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- serialization [Windows Forms], collections
- standard types [Windows Forms], collections
- collections [Windows Forms], serializing
- collections [Windows Forms], standard types
ms.assetid: 020c9df4-fdc5-4dae-815a-963ecae5668c
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9efad2da27f4003632b643b9f5f0602be0d55480
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-serializing-collections-of-standard-types-with-the-designerserializationvisibilityattribute"></a>Exemplarische Vorgehensweise: Serialisieren der Auflistungen von Standardtypen mit dem DesignerSerializationVisibilityAttribute
Der benutzerdefinierten Steuerelemente werden manchmal eine Auflistung als Eigenschaft verfügbar machen. Diese exemplarische Vorgehensweise veranschaulicht, wie die <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> Klasse steuern, wie eine Auflistung zur Entwurfszeit serialisiert wird. Anwenden der <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> Wert auf die Auflistungseigenschaft wird sichergestellt, dass die Eigenschaft serialisiert wird.  
  
 Um den Code in diesem Thema als einzelne Auflistung kopieren zu können, finden Sie unter [wie: Serialisieren Auflistungen von Standardtypen mit dem DesignerSerializationVisibilityAttribute](http://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:  
  
-   Ausreichende Berechtigungen zum Erstellen und Ausführen von Windows Forms-Anwendungsprojekten auf dem Computer, auf dem Visual Studio installiert ist.  
  
## <a name="creating-a-control-that-has-a-serializable-collection"></a>Erstellen eines Steuerelements, verfügt über eine serialisierbare Auflistung  
 Der erste Schritt besteht darin ein Steuerelement zu erstellen, die eine serialisierbare Auflistung als Eigenschaft verfügt. Können Sie den Inhalt dieser Auflistung mit Bearbeiten der **Auflistungs-Editor**, das Sie zugreifen können, aus der **Eigenschaften** Fenster.  
  
#### <a name="to-create-a-control-with-a-serializable-collection"></a>So erstellen Sie ein Steuerelement über eine serialisierbare Auflistung  
  
1.  Erstellen Sie ein Windows-Steuerelementbibliothek-Projekt aufgerufen `SerializationDemoControlLib`. Weitere Informationen finden Sie unter [Vorlage für Windows-Steuerelementbibliothek](http://msdn.microsoft.com/en-us/722f4e2d-1310-4ed5-8f33-593337ab66b4).  
  
2.  Benennen Sie `UserControl1` auf `SerializationDemoControl`. Weitere Informationen finden Sie unter [Vorgehensweise: Umbenennen von Bezeichnern](http://msdn.microsoft.com/en-us/2430f732-2b70-4516-8cf6-a7bb71cc9724).  
  
3.  In der **Eigenschaften** Fenster, legen Sie den Wert von der <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> Eigenschaft `10`.  
  
4.  Stelle eine <xref:System.Windows.Forms.TextBox> steuern, der `SerializationDemoControl`.  
  
5.  Wählen Sie das <xref:System.Windows.Forms.TextBox>-Steuerelement. In der **Eigenschaften** die folgenden Eigenschaften fest.  
  
    |Eigenschaft|Ändern in|  
    |--------------|---------------|  
    |**Multiline**|`true`|  
    |**Andocken**|<xref:System.Windows.Forms.DockStyle.Fill>|  
    |**Bildlaufleisten**|<xref:System.Windows.Forms.ScrollBars.Vertical>|  
    |**ReadOnly**|`true`|  
  
6.  In der **Code-Editor**, deklarieren Sie ein Array, mit dem Namen Zeichenfolgenfeld `stringsValue` in `SerializationDemoControl`.  
  
     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]  
  
7.  Definieren der `Strings` Eigenschaft auf die `SerializationDemoControl`.  
  
> [!NOTE]
>  Die <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> Wert wird verwendet, um die Serialisierung der Auflistung zu aktivieren.  
  
 [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
 [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
 [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]  
  
1.  Drücken Sie F5, um das Projekt zu erstellen, und führen Sie das Steuerelement im **UserControl-Testcontainer** aus.  
  
2.  Suchen der `Strings` Eigenschaft in der <xref:System.Windows.Forms.PropertyGrid> von der **UserControl-Testcontainer**. Klicken Sie auf die `Strings` -Eigenschaft, klicken Sie dann auf die Auslassungspunkte (![von VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton")) die Schaltfläche, um die **Zeichenfolgen-Editor**.  
  
3.  Geben Sie mehrere Zeichenfolgen in die **Zeichenfolgen-Editor**. Trennen sie durch Drücken der EINGABETASTE am Ende einer Zeichenfolge. Klicken Sie auf **OK** , wenn Sie alle Zeichenfolgen eingegeben haben.  
  
> [!NOTE]
>  Die eingegebene Zeichenfolgen angezeigt, der <xref:System.Windows.Forms.TextBox> von der `SerializationDemoControl`.  
  
## <a name="serializing-a-collection-property"></a>Serialisieren einer Auflistungseigenschaft  
 Um die Serialisierung des Verhaltens eines Steuerelements zu testen, werden Sie ihn in einem Formular platzieren und ändern Sie den Inhalt der Auflistung mit den **Auflistungs-Editor**. Sehen Sie den Zustand der serialisierten Auflistung durch einen Blick auf eine spezielle-Designer-Datei, in dem die **Windows Forms-Designer** Code ausgibt.  
  
#### <a name="to-serialize-a-collection"></a>Um eine Auflistung zu serialisieren.  
  
1.  Fügen Sie der Projektmappe ein Windows-Anwendungsprojekt. Benennen Sie das Projekt mit `SerializationDemoControlTest`.  
  
2.  In der **Toolbox**, suchen Sie die Registerkarte mit dem Namen **SerializationDemoControlLib Components**. Auf dieser Registerkarte finden Sie die `SerializationDemoControl`. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).  
  
3.  Stelle eine `SerializationDemoControl` auf dem Formular.  
  
4.  Suchen der `Strings` Eigenschaft in der **Eigenschaften** Fenster. Klicken Sie auf die `Strings` -Eigenschaft, klicken Sie dann auf die Auslassungspunkte (![von VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton")) die Schaltfläche, um die **Zeichenfolgen-Editor**.  
  
5.  Geben Sie mehrere Zeichenfolgen in die **Zeichenfolgen-Editor**. Trennen sie durch Drücken der EINGABETASTE am Ende einer Zeichenfolge. Klicken Sie auf **OK** , wenn Sie alle Zeichenfolgen eingegeben haben.  
  
> [!NOTE]
>  Die eingegebene Zeichenfolgen angezeigt, der <xref:System.Windows.Forms.TextBox> von der `SerializationDemoControl`.  
  
1.  Klicken Sie im **Projektmappen-Explorer** auf die Schaltfläche **Alle Dateien anzeigen**.  
  
2.  Öffnen der **Form1** Knoten. Darunter befindet sich eine Datei namens **Form1.Designer.cs** oder **Form1.Designer.vb**. Dies ist die Datei in dem die **Windows Forms-Designer** gibt Code aus, das den Entwurfszeitzustand des Formulars und seiner untergeordneten Steuerelemente darstellt. Öffnen Sie diese Datei im **Code-Editor**.  
  
3.  Öffnen Sie den Bereich **Windows Form Designer generierter Code** und suchen Sie den Abschnitt mit der Bezeichnung **serializationDemoControl1**. Unter dieser Bezeichnung befindet sich der Code, der serialisierten Zustand des Steuerelements darstellt. Die Zeichenfolgen, die in Schritt 5 eingegebene angezeigt werden, in einer Zuordnung zu den `Strings` Eigenschaft. Die folgenden Codebeispiele in c# und Visual Basic-Code anzeigen ähnelt, was Sie sehen, wenn Sie die Zeichenfolgen "Red", "orange" und "Gelb" eingegeben haben.  
  
    ```csharp  
    this.serializationDemoControl1.Strings = new string[] {  
            "red",  
            "orange",  
            "yellow"};  
    ```  
    
    ```vb  
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}  
    ```
  
4.  In der **Code-Editor**, ändern Sie den Wert von der <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> auf die `Strings` Eigenschaft <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.  
  
    ```csharp  
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]  
    ```  
    ```vb  
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _  
    ```  
  
5. Erneutes Erstellen von Projektmappen und wiederholen Sie die Schritte 3 und 4.  
  
> [!NOTE]
>  In diesem Fall die **Windows Forms-Designer** gibt keine Zuweisung zur der `Strings` Eigenschaft.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Sobald Sie wissen, wie eine Auflistung von standardmäßigen Typen serialisieren, sollten Sie besser Integrieren von benutzerdefinierten Steuerelementen in der entwurfszeitumgebung. In den folgenden Themen wird beschrieben, wie die während der Entwurfszeit-Integration von der benutzerdefinierten Steuerelemente zu verbessern:  
  
-   [Architektur zur Entwurfszeit](http://msdn.microsoft.com/library/4881917b-628f-4689-b872-472e4f8a4e3a)  
  
-   [Attribute in Windows Forms-Steuerelementen](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
  
-   [Übersicht über die Designer-Serialisierung](http://msdn.microsoft.com/library/c342635a-aa5f-4281-915b-b013738af15a)  
  
-   [Exemplarische Vorgehensweise: Erstellen eines Windows Forms-Steuerelements, das Visual Studio-Entwurfszeitfunktion nutzt](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>  
 [Übersicht über die Designer-Serialisierung](http://msdn.microsoft.com/library/c342635a-aa5f-4281-915b-b013738af15a)  
 [Vorgehensweise: Serialisieren der Auflistungen von Standardtypen mit dem DesignerSerializationVisibilityAttribute](http://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9)  
 [Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)

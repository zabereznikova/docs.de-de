---
title: 'Exemplarische Vorgehensweise: Serialisieren der Auflistungen von Standardtypen mit dem DesignerSerializationVisibilityAttribute'
ms.date: 03/30/2017
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
ms.openlocfilehash: 791b2ea1497b8b884d066894e925785fd1bb6f7d
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59305207"
---
# <a name="walkthrough-serializing-collections-of-standard-types-with-the-designerserializationvisibilityattribute"></a>Exemplarische Vorgehensweise: Serialisieren der Auflistungen von Standardtypen mit dem DesignerSerializationVisibilityAttribute
Ihre benutzerdefinierten Steuerelemente werden manchmal eine Auflistung als Eigenschaft verfügbar machen. In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie mit der <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> Klasse, um zu steuern, wie eine Auflistung zur Entwurfszeit serialisiert wird. Anwenden der <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> Wert, der die Auflistungseigenschaft wird sichergestellt, dass die Eigenschaft serialisiert wird.  
  
 Zum Kopieren des Codes in diesem Thema als einzelne Auflistung lesen Sie [Vorgehensweise: Serialisieren der Auflistungen von Standardtypen mit dem DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="prerequisites"></a>Vorraussetzungen  
 Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:  
  
-   Berechtigt sind, können zum Erstellen und Ausführen von Windows Forms-Anwendungsprojekten auf dem Computer, auf dem Visual Studio installiert ist.  
  
## <a name="creating-a-control-that-has-a-serializable-collection"></a>Erstellen eines Steuerelements, verfügt über eine serialisierbare Auflistung  
 Der erste Schritt ist zum Erstellen eines Steuerelements, das eine serialisierbare Auflistung als Eigenschaft verfügt. Sie können den Inhalt dieser Sammlung mit Bearbeiten der **Auflistungs-Editor**, die Sie zugreifen können die **Eigenschaften** Fenster.  
  
#### <a name="to-create-a-control-with-a-serializable-collection"></a>So erstellen Sie ein Steuerelement über eine serialisierbare Auflistung  
  
1. Erstellen Sie ein Windows-Steuerelementbibliothek-Projekt namens `SerializationDemoControlLib`. Weitere Informationen finden Sie unter [Vorlage für Windows-Steuerelementbibliothek](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).  
  
2. Benennen Sie `UserControl1` zu `SerializationDemoControl`. Weitere Informationen finden Sie unter [Umbenennen eines Codesymbols](/visualstudio/ide/reference/rename).  
  
3. In der **Eigenschaften** legen den Wert des der <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> Eigenschaft `10`.  
  
4. Stelle eine <xref:System.Windows.Forms.TextBox> steuern, der `SerializationDemoControl`.  
  
5. Wählen Sie das <xref:System.Windows.Forms.TextBox>-Steuerelement. In der **Eigenschaften** Fenster die folgenden Eigenschaften festlegen.  
  
    |Eigenschaft|Ändern in|  
    |--------------|---------------|  
    |**Multiline**|`true`|  
    |**Andocken**|<xref:System.Windows.Forms.DockStyle.Fill>|  
    |**ScrollBars**|<xref:System.Windows.Forms.ScrollBars.Vertical>|  
    |**ReadOnly**|`true`|  
  
6. In der **Code-Editor**, deklarieren Sie einen Zeichenfolgen-Arrayfeld mit dem Namen `stringsValue` in `SerializationDemoControl`.  
  
     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]  
  
7. Definieren der `Strings` Eigenschaft für die `SerializationDemoControl`.  
  
> [!NOTE]
>  Die <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> Wert wird verwendet, um die Serialisierung der Auflistung zu ermöglichen.  
  
 [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
 [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
 [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]  
  
1. Drücken Sie F5, um das Projekt zu erstellen, und führen Sie das Steuerelement im **UserControl-Testcontainer** aus.  
  
2. Suchen der `Strings` -Eigenschaft in der <xref:System.Windows.Forms.PropertyGrid> von der **UserControl-Testcontainer**. Klicken Sie auf die `Strings` -Eigenschaft, klicken Sie dann auf die Auslassungspunkte (![VisualStudioEllipsesButton-bildschirmabbildung](../media/vbellipsesbutton.png "VbEllipsesButton")) die Schaltfläche, um die **Zeichenfolgen-Editor**.  
  
3. Geben Sie mehrere Zeichenfolgen in die **Zeichenfolgen-Editor**. Trennen sie durch Drücken der EINGABETASTE am Ende einer Zeichenfolge. Klicken Sie auf **OK** , wenn Sie Zeichenfolgen eingegeben haben.  
  
> [!NOTE]
>  Die eingegebene Zeichenfolgen angezeigt werden, der <xref:System.Windows.Forms.TextBox> von der `SerializationDemoControl`.  
  
## <a name="serializing-a-collection-property"></a>Eine Auflistungseigenschaft serialisiert  
 Um das Serialisierungsverhalten des Steuerelements zu testen, werden Sie ihn in einem Formular zu platzieren und ändern Sie den Inhalt der Auflistung mit den **Auflistungs-Editor**. Sie sehen den Status für die serialisierte Auflistung anhand einer speziellen Designer-Datei, in dem die **Windows Forms-Designer** Code ausgibt.  
  
#### <a name="to-serialize-a-collection"></a>Um eine Auflistung zu serialisieren.  
  
1. Fügen Sie ein Windows-Anwendungsprojekt mit der Lösung. Benennen Sie das Projekt mit `SerializationDemoControlTest`.  
  
2. In der **Toolbox**, suchen Sie die Registerkarte mit dem Namen **SerializationDemoControlLib Components**. In dieser Registerkarte finden Sie die `SerializationDemoControl`. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).  
  
3. Stelle eine `SerializationDemoControl` in Ihrem Formular.  
  
4. Suchen der `Strings` -Eigenschaft in der **Eigenschaften** Fenster. Klicken Sie auf die `Strings` -Eigenschaft, klicken Sie dann auf die Auslassungspunkte (![VisualStudioEllipsesButton-bildschirmabbildung](../media/vbellipsesbutton.png "VbEllipsesButton")) die Schaltfläche, um die **Zeichenfolgen-Editor**.  
  
5. Geben Sie mehrere Zeichenfolgen in die **Zeichenfolgen-Editor**. Trennen sie durch Drücken der EINGABETASTE am Ende einer Zeichenfolge. Klicken Sie auf **OK** , wenn Sie Zeichenfolgen eingegeben haben.  
  
> [!NOTE]
>  Die eingegebene Zeichenfolgen angezeigt werden, der <xref:System.Windows.Forms.TextBox> von der `SerializationDemoControl`.  
  
1. Klicken Sie im **Projektmappen-Explorer** auf die Schaltfläche **Alle Dateien anzeigen**.  
  
2. Öffnen der **Form1** Knoten. Darunter befindet sich eine Datei namens **Form1.Designer.cs** oder **Form1.Designer.vb**. Dies ist die Datei in dem die **Windows Forms-Designer** gibt Code aus, das den Entwurfszeitzustand des Formulars und seiner untergeordneten Steuerelemente darstellt. Öffnen Sie diese Datei im **Code-Editor**.  
  
3. Öffnen Sie den Bereich **Windows Form Designer generierter Code** und suchen Sie den Abschnitt mit der Bezeichnung **serializationDemoControl1**. Unter diesen Label befindet sich der Code, der den serialisierten Zustand des Steuerelements darstellt. Die Zeichenfolgen, die in Schritt 5 eingegebenen angezeigt werden, in einer Zuweisung auf die `Strings` Eigenschaft. Die folgenden Codebeispiele in c# und Visual Basic-Code anzeigen ähnelt, wird angezeigt, wenn Sie die Zeichenfolgen "Rot", "orange" und "Gelb" eingegeben.  
  
    ```csharp  
    this.serializationDemoControl1.Strings = new string[] {  
            "red",  
            "orange",  
            "yellow"};  
    ```  
    
    ```vb  
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}  
    ```
  
4. In der **Code-Editor**, ändern Sie den Wert von der <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> auf die `Strings` Eigenschaft <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.  
  
    ```csharp  
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]  
    ```  
    ```vb  
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _  
    ```  
  
5. Erneutes Erstellen von Projektmappen und wiederholen Sie die Schritte 3 und 4.  
  
> [!NOTE]
>  In diesem Fall die **Windows Forms-Designer** gibt keine Zuweisung, die `Strings` Eigenschaft.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Sobald Sie wissen wie eine Auflistung von standardmäßigen Typen serialisieren, sollten Sie Ihre benutzerdefinierten Steuerelemente besser in der Entwurfszeit-Umgebung integrieren. In den folgenden Themen wird beschrieben, wie die während der Entwurfszeit-Integration von benutzerdefinierten Steuerelementen zu verbessern:  
  
-   [Architektur der Entwurfszeit](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))  
  
-   [Attribute in Windows Forms-Steuerelementen](attributes-in-windows-forms-controls.md)  
  
-   [Übersicht über die Designerserialisierung](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))  
  
-   [Exemplarische Vorgehensweise: Erstellen eines Windows Forms-Steuerelements, das Visual Studio-Entwurfszeitfunktionen nutzt](creating-a-wf-control-design-time-features.md)  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>
- [Übersicht über die Designerserialisierung](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))
- [Vorgehensweise: Serialisieren der Auflistungen von Standardtypen mit dem DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))
- [Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)

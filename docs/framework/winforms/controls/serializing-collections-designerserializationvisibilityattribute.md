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
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 297a7080b0c34fa10f976cbbbfb48d8c35786aca
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458077"
---
# <a name="walkthrough-serialize-collections-of-standard-types"></a>Exemplarische Vorgehensweise: Serialisieren von Auflistungen von Standardtypen

Die benutzerdefinierten Steuerelemente machen manchmal eine Auflistung als Eigenschaft verfügbar. In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie mit der <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>-Klasse gesteuert wird, wie eine Auflistung zur Entwurfszeit serialisiert wird. Wenn Sie den <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> Wert auf Ihre Auflistungs Eigenschaft anwenden, wird sichergestellt, dass die Eigenschaft serialisiert wird.

Informationen zum Kopieren des Codes in diesem Thema als einzelne Auflistung finden Sie unter Gewusst [wie: Serialisieren von Auflistungen von Standard Typen mit dem DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).

## <a name="prerequisites"></a>Erforderliche Voraussetzungen

Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.

## <a name="create-a-control-with-a-serializable-collection"></a>Erstellen eines Steuer Elements mit einer serialisierbaren Sammlung

Der erste Schritt besteht darin, ein Steuerelement zu erstellen, das über eine serialisierbare Auflistung als Eigenschaft verfügt. Sie können den Inhalt dieser Sammlung mit dem Auflistungs- **Editor**bearbeiten, auf den Sie über das **Eigenschaften** Fenster zugreifen können.

1. Erstellen Sie in Visual Studio ein Windows-Steuerelement Bibliothek-Projekt, und nennen Sie es " **SerializationDemoControlLib**".

2. Benennen Sie `UserControl1` in `SerializationDemoControl`um. Weitere Informationen finden Sie unter [Umbenennen einer Code Symbol Umgestaltung](/visualstudio/ide/reference/rename).

3. Legen Sie im Fenster **Eigenschaften** den Wert der <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType>-Eigenschaft auf **10**fest.

4. Platzieren Sie ein <xref:System.Windows.Forms.TextBox>-Steuerelement in der `SerializationDemoControl`.

5. Wählen Sie das <xref:System.Windows.Forms.TextBox>-Steuerelement. Legen Sie im **Eigenschaften** Fenster die folgenden Eigenschaften fest.

    |property|Ändern in|
    |--------------|---------------|
    |**Multiline**|`true`|
    |**Andocken**|<xref:System.Windows.Forms.DockStyle.Fill>|
    |**ScrollBars**|<xref:System.Windows.Forms.ScrollBars.Vertical>|
    |**ReadOnly**|`true`|

6. Deklarieren Sie im **Code-Editor**ein Zeichen folgen Array Feld mit dem Namen `stringsValue` in `SerializationDemoControl`.

     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]

7. Definieren Sie die `Strings`-Eigenschaft für die `SerializationDemoControl`.

   > [!NOTE]
   > Der <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content>-Wert wird verwendet, um die Serialisierung der Auflistung zu aktivieren.

   [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
   [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
   [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]

8. Drücken Sie **F5** , um das Projekt zu erstellen, und führen Sie das Steuerelement im **UserControl-Test Container**aus.

9. Suchen Sie die Eigenschaft **Strings** in der <xref:System.Windows.Forms.PropertyGrid> des **UserControl-Test Containers**. Wählen Sie die Eigenschaft **Strings** aus, und wählen Sie dann die Auslassungs Punkte (![der Schaltfläche mit den Auslassungs Punkten (...) in der Eigenschaftenfenster von Visual Studio](./media/visual-studio-ellipsis-button.png)), um den Editor für die **Zeichen**folgen Auflistung zu öffnen

10. Geben Sie im Zeichen folgen- **Sammlungs-Editor mehrere Zeichen**folgen ein. Trennen Sie diese durch Drücken der **Eingabe** Taste am Ende der einzelnen Zeichen folgen. Klicken Sie auf **OK** , wenn die Eingabe von Zeichen folgen abgeschlossen ist.

   > [!NOTE]
   > Die eingegebenen Zeichen folgen werden in der <xref:System.Windows.Forms.TextBox> der `SerializationDemoControl`angezeigt.

## <a name="serialize-a-collection-property"></a>Serialisieren einer Sammlungs Eigenschaft

Um das Serialisierungsverhalten Ihres Steuer Elements zu testen, platzieren Sie es in einem Formular, und ändern Sie den Inhalt der Auflistung mit dem Auflistungs- **Editor**. Sie können den serialisierten Auflistungs Status anzeigen, indem Sie eine spezielle Designer-Datei betrachten, in der die **Windows Forms-Designer** Code ausgibt.

1. Fügen Sie der Projekt Mappe ein Windows-Anwendungsprojekt hinzu. Benennen Sie das Projekt mit `SerializationDemoControlTest`.

2. Suchen Sie in der **Toolbox**die Registerkarte mit dem Namen **SerializationDemoControlLib Components**. Auf dieser Registerkarte finden Sie die `SerializationDemoControl`. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).

3. Legen Sie eine `SerializationDemoControl` in das Formular ein.

4. Suchen Sie die `Strings`-Eigenschaft im **Eigenschaften** Fenster. Klicken Sie auf die `Strings`-Eigenschaft, und klicken Sie dann auf die Auslassungs Punkte (![der Schaltfläche mit den Auslassungs Punkten (...) in der Eigenschaftenfenster von Visual Studio.](./media/visual-studio-ellipsis-button.png)), um den Editor für die **Zeichen**folgen Auflistung

5. Geben Sie im Zeichen folgen- **Sammlungs-Editor mehrere Zeichen**folgen ein. Trennen Sie diese durch Drücken der **Eingabe** Taste am Ende jeder Zeichenfolge. Klicken Sie auf **OK** , wenn die Eingabe von Zeichen folgen abgeschlossen ist.

    > [!NOTE]
    > Die eingegebenen Zeichen folgen werden in der <xref:System.Windows.Forms.TextBox> der `SerializationDemoControl`angezeigt.

6. Klicken Sie im **Projektmappen-Explorer** auf die Schaltfläche **Alle Dateien anzeigen**.

7. Öffnen Sie den Knoten **Form1** . Darunter befindet sich eine Datei mit dem Namen **Form1.Designer.cs** oder **Form1. Designer. vb**. Dies ist die Datei, in die der **Windows Forms-Designer** Code ausgibt, der den Entwurfszeit Zustand des Formulars und seiner untergeordneten Steuerelemente darstellt. Öffnen Sie diese Datei im **Code-Editor**.

8. Öffnen Sie die Region namens **Windows Form-Designer generierter Code** , und suchen Sie den Abschnitt mit der Bezeichnung **serializationDemoControl1**. Unterhalb dieser Bezeichnung befindet sich der Code, der den serialisierten Zustand des Steuer Elements darstellt. Die Zeichen folgen, die Sie in Schritt 5 eingegeben haben, werden in einer Zuweisung zur `Strings`-Eigenschaft angezeigt. Die folgenden Codebeispiele in C# und Visual Basic zeigen Code ähnlich dem, was Sie sehen werden, wenn Sie die Zeichen folgen "Red", "Orange" und "Yellow" eingegeben haben.

    ```csharp
    this.serializationDemoControl1.Strings = new string[] {
            "red",
            "orange",
            "yellow"};
    ```

    ```vb
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}
    ```

9. Ändern Sie im **Code-Editor**den Wert des <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> für die Eigenschaft `Strings` in <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.

    ```csharp
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]
    ```

    ```vb
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _
    ```

10. Erstellen Sie die Lösung neu, und wiederholen Sie die Schritte 3 und 4

> [!NOTE]
> In diesem Fall gibt der **Windows Forms-Designer** keine Zuweisung zur `Strings`-Eigenschaft aus.

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie wissen, wie eine Auflistung von Standardtypen serialisiert werden soll, sollten Sie in Erwägung gezogen werden, die benutzerdefinierten Steuerelemente tiefer in die Entwurfszeit Umgebung zu integrieren. In den folgenden Themen wird beschrieben, wie Sie die Entwurfszeit Integration Ihrer benutzerdefinierten Steuerelemente verbessern:

- [Entwurfszeit Architektur](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))

- [Attribute in Windows Forms-Steuerelementen](attributes-in-windows-forms-controls.md)

- [Übersicht über die Designer-Serialisierung](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))

- [Exemplarische Vorgehensweise: Erstellen eines Windows Forms-Steuerelements, das Visual Studio-Entwurfszeitfunktion nutzt](creating-a-wf-control-design-time-features.md)

## <a name="see-also"></a>Siehe auch

- <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>
- [Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)

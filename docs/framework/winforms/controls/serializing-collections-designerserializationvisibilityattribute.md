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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 2fbb0715d148b443b1eca8f400e4ad43eb51fa43
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015736"
---
# <a name="walkthrough-serialize-collections-of-standard-types"></a>Exemplarische Vorgehensweise: Serialisieren von Auflistungen von Standardtypen

Die benutzerdefinierten Steuerelemente machen manchmal eine Auflistung als Eigenschaft verfügbar. Diese exemplarische Vorgehensweise veranschaulicht die Verwendung <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> der-Klasse, um zu steuern, wie eine Auflistung zur Entwurfszeit serialisiert wird. Wenn Sie <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> den Wert auf Ihre Auflistungs Eigenschaft anwenden, wird sichergestellt, dass die Eigenschaft serialisiert wird.

Zum Kopieren des Codes in diesem Thema als einzelne Auflistung lesen Sie [Vorgehensweise: Serialisieren Sie Auflistungen von Standard Typen mit dem DesignerSerializationVisibilityAttribute](/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).

## <a name="prerequisites"></a>Vorraussetzungen

Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.

## <a name="create-a-control-with-a-serializable-collection"></a>Erstellen eines Steuer Elements mit einer serialisierbaren Sammlung

Der erste Schritt besteht darin, ein Steuerelement zu erstellen, das über eine serialisierbare Auflistung als Eigenschaft verfügt. Sie können den Inhalt dieser Sammlung mit dem Auflistungs- **Editor**bearbeiten, auf den Sie über das **Eigenschaften** Fenster zugreifen können.

1. Erstellen Sie in Visual Studio ein Windows-Steuerelement Bibliothek-Projekt, und nennen Sie es " **SerializationDemoControlLib**".

2. Benennen `UserControl1` Sie `SerializationDemoControl`in um. Weitere Informationen finden Sie unter [Umbenennen einer Code Symbol Umgestaltung](/visualstudio/ide/reference/rename).

3. Legen Sie im Fenster **Eigenschaften** den Wert <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> der-Eigenschaft auf **10**fest.

4. Platzieren Sie <xref:System.Windows.Forms.TextBox> ein-Steuer `SerializationDemoControl`Element in der.

5. Wählen Sie das <xref:System.Windows.Forms.TextBox>-Steuerelement. Legen Sie im **Eigenschaften** Fenster die folgenden Eigenschaften fest.

    |Eigenschaft|Ändern in|
    |--------------|---------------|
    |**Multiline**|`true`|
    |**Dock**|<xref:System.Windows.Forms.DockStyle.Fill>|
    |**ScrollBars**|<xref:System.Windows.Forms.ScrollBars.Vertical>|
    |**ReadOnly**|`true`|

6. Deklarieren Sie im **Code-Editor**ein Zeichen folgen Array `stringsValue` Feld `SerializationDemoControl`mit dem Namen in.

     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]

7. Definieren Sie `Strings` die-Eigenschaft `SerializationDemoControl`auf dem.

   > [!NOTE]
   > Der <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> -Wert wird verwendet, um die Serialisierung der Auflistung zu aktivieren.

   [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
   [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
   [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]

8. Drücken Sie **F5** , um das Projekt zu erstellen, und führen Sie das Steuerelement im **UserControl-Test Container**aus.

9. Suchen Sie die Eigenschaft **Strings** in <xref:System.Windows.Forms.PropertyGrid> der des **UserControl-Test Containers**. Wählen Sie die Eigenschaft **Strings** aus, und wählen Sie dann![die Auslassungs Punkte (die Schaltfläche mit den Auslassungs Punkten (.](./media/visual-studio-ellipsis-button.png)..) in der Eigenschaftenfenster von Visual Studio) aus, um den Editor für die **Zeichen**folgen Auflistung

10. Geben Sie im Zeichen folgen- **Sammlungs-Editor mehrere Zeichen**folgen ein. Trennen Sie diese durch Drücken der **Eingabe** Taste am Ende der einzelnen Zeichen folgen. Klicken Sie auf **OK** , wenn die Eingabe von Zeichen folgen abgeschlossen ist.

   > [!NOTE]
   > Die Zeichen folgen, die Sie eingegeben <xref:System.Windows.Forms.TextBox> haben, `SerializationDemoControl`werden in der von angezeigt.

## <a name="serialize-a-collection-property"></a>Serialisieren einer Sammlungs Eigenschaft

Um das Serialisierungsverhalten Ihres Steuer Elements zu testen, platzieren Sie es in einem Formular, und ändern Sie den Inhalt der Auflistung mit dem Auflistungs- **Editor**. Sie können den serialisierten Auflistungs Status anzeigen, indem Sie eine spezielle Designer-Datei betrachten, in der die **Windows Forms-Designer** Code ausgibt.

1. Fügen Sie der Projekt Mappe ein Windows-Anwendungsprojekt hinzu. Benennen Sie das Projekt mit `SerializationDemoControlTest`.

2. Suchen Sie in der **Toolbox**die Registerkarte mit dem Namen **SerializationDemoControlLib Components**. Auf dieser Registerkarte finden Sie die `SerializationDemoControl`. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Automatisches Auffüllen der Toolbox mit benutzerdefinierten Komponenten](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).

3. Platzieren Sie `SerializationDemoControl` einen auf dem Formular.

4. Suchen Sie `Strings` die-Eigenschaft im **Eigenschaften** Fenster. Klicken Sie `Strings` auf die-Eigenschaft, und klicken Sie![dann auf die Auslassungs Punkte (die Schaltfläche mit den Auslassungs Punkten (](./media/visual-studio-ellipsis-button.png)...) inder Eigenschaftenfenster von Visual Studio.

5. Geben Sie im Zeichen folgen- **Sammlungs-Editor mehrere Zeichen**folgen ein. Trennen Sie diese durch Drücken der **Eingabe** Taste am Ende jeder Zeichenfolge. Klicken Sie auf **OK** , wenn die Eingabe von Zeichen folgen abgeschlossen ist.

> [!NOTE]
> Die Zeichen folgen, die Sie eingegeben <xref:System.Windows.Forms.TextBox> haben, `SerializationDemoControl`werden in der von angezeigt.

6. Klicken Sie im **Projektmappen-Explorer** auf die Schaltfläche **Alle Dateien anzeigen**.

7. Öffnen Sie den Knoten **Form1** . Darunter befindet sich eine Datei mit dem Namen **Form1.Designer.cs** oder **Form1. Designer. vb**. Dies ist die Datei, in die der **Windows Forms-Designer** Code ausgibt, der den Entwurfszeit Zustand des Formulars und seiner untergeordneten Steuerelemente darstellt. Öffnen Sie diese Datei im **Code-Editor**.

8. Öffnen Sie die Region namens **Windows Form-Designer generierter Code** , und suchen Sie den Abschnitt mit der Bezeichnung **serializationDemoControl1**. Unterhalb dieser Bezeichnung befindet sich der Code, der den serialisierten Zustand des Steuer Elements darstellt. Die Zeichen folgen, die Sie in Schritt 5 eingegeben haben, werden `Strings` in einer Zuweisung zur-Eigenschaft angezeigt. Die folgenden Codebeispiele in C# und Visual Basic zeigen Code ähnlich dem, was Sie sehen werden, wenn Sie die Zeichen folgen "Red", "Orange" und "Yellow" eingegeben haben.

    ```csharp
    this.serializationDemoControl1.Strings = new string[] {
            "red",
            "orange",
            "yellow"};
    ```

    ```vb
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}
    ```

9. Ändern Sie `Strings` <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> im<xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>Code- **Editor**den Wert von für die-Eigenschaft in.

    ```csharp
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]
    ```

    ```vb
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _
    ```

10. Erstellen Sie die Lösung neu, und wiederholen Sie die Schritte 3 und 4

> [!NOTE]
> In diesem Fall gibt der **Windows Forms-Designer** keine Zuweisung zur `Strings` -Eigenschaft aus.

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie wissen, wie eine Auflistung von Standardtypen serialisiert werden soll, sollten Sie in Erwägung gezogen werden, die benutzerdefinierten Steuerelemente tiefer in die Entwurfszeit Umgebung zu integrieren. In den folgenden Themen wird beschrieben, wie Sie die Entwurfszeit Integration Ihrer benutzerdefinierten Steuerelemente verbessern:

- [Entwurfszeit Architektur](/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))

- [Attribute in Windows Forms-Steuerelementen](attributes-in-windows-forms-controls.md)

- [Übersicht über die Designer-Serialisierung](/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))

- [Exemplarische Vorgehensweise: Erstellen eines Windows Forms-Steuer Elements, das Visual Studio-Entwurfszeit Funktionen nutzt](creating-a-wf-control-design-time-features.md)

## <a name="see-also"></a>Siehe auch

- <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>
- [Exemplarische Vorgehensweise: Automatisches Auffüllen der Toolbox mit benutzerdefinierten Komponenten](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)

---
title: 'Exemplarische Vorgehensweise: Demonstrieren der visuellen Vererbung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- form inheritance [Windows Forms], walkthroughs
- visual inheritance
- inheritance [Windows Forms], walkthroughs
- walkthroughs [Windows Forms], visual inheritance
- Windows Forms, inheritance
ms.assetid: 01966086-3142-450e-8210-3fd4cb33f591
ms.openlocfilehash: 32df98852b28963ffb748895156f7d9977c74b92
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046151"
---
# <a name="walkthrough-demonstrating-visual-inheritance"></a>Exemplarische Vorgehensweise: Demonstrieren der visuellen Vererbung

Mit visueller Vererbung können Sie die Steuerelemente auf dem Basisformular anzeigen und neue Steuerelemente hinzufügen. In dieser exemplarischen Vorgehensweise erstellen Sie ein Basisformular und kompilieren es in eine Klassenbibliothek. Sie importieren diese Klassenbibliothek in ein anderes Projekt und erstellen ein neues Formular, das vom Basisformular erbt. Bei dieser exemplarischen Vorgehensweise lernen Sie Folgendes:

- Erstellen eines Klassenbibliotheksprojekts, das ein Basisformular enthält.

- Hinzufügen einer Schaltfläche mit Eigenschaften, die abgeleitete Klassen des Basisformulars ändern können.

- Hinzufügen einer Schaltfläche, die von Erben des Basisformulars nicht geändert werden kann.

- Erstellen eines Projekts, das ein Formular enthält, das von `BaseForm` erbt.

Schließlich wird in dieser exemplarischen Vorgehensweise der Unterschied zwischen privaten und geschützten Steuerelementen in einem geerbten Formular gezeigt.

> [!CAUTION]
> Nicht alle Steuerelemente unterstützen visuelle Vererbung von einem Basisformular. Die folgenden Steuerelemente unterstützen das in dieser exemplarischen Vorgehensweise beschriebene Szenario nicht:
>
> - <xref:System.Windows.Forms.WebBrowser>
>
> - <xref:System.Windows.Forms.ToolStrip>
>
> - <xref:System.Windows.Forms.ToolStripPanel>
>
> - <xref:System.Windows.Forms.TableLayoutPanel>
>
> - <xref:System.Windows.Forms.FlowLayoutPanel>
>
> - <xref:System.Windows.Forms.DataGridView>
>
> Diese Steuerelemente im geerbten Formular sind immer schreibgeschützt, unabhängig von den verwendeten Modifizierern (`private`, `protected` oder `public`).

## <a name="create-a-class-library-project-containing-a-base-form"></a>Erstellen eines Klassen Bibliotheks Projekts, das ein Basis Formular enthält

1. Wählen Sie in Visual Studio im Menü **Datei** die Option **Neues** > **Projekt** aus, um das Dialogfeld **Neues Projekt** zu öffnen.

2. Erstellen Sie eine Windows Forms Anwendung `BaseFormLibrary`mit dem Namen.

3. Um eine Klassenbibliothek anstelle einer Standard Windows Forms Anwendung zu erstellen, klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf den Projekt Knoten **BaseFormLibrary** , und wählen Sie dann **Eigenschaften**aus.

4. Ändern Sie in den Eigenschaften für das Projekt den **Ausgabetyp** aus der **Windows-Anwendung** in die **Klassenbibliothek**.

5. Wählen Sie im Menü **Datei** die Option **Alle speichern** aus, um das Projekt und die Dateien am Standard Speicherort zu speichern.

Mit den nächsten zwei Verfahren werden dem Basisformular Schaltflächen hinzugefügt. Zur Demonstration der visuellen Vererbung weisen Sie den Schaltflächen verschiedene Zugriffsebenen zu, indem Sie ihre `Modifiers`Eigenschaften festlegen.

## <a name="add-a-button-that-inheritors-of-the-base-form-can-modify"></a>Fügen Sie eine Schaltfläche hinzu, die von Vererbung des Basis Formulars geändert werden kann.

1. Öffnen Sie **Form1** im Designer.

2. Doppelklicken Sie auf der Registerkarte **alle Windows Forms** der **Toolbox**auf die **Schaltfläche** , um dem Formular eine Schaltfläche hinzuzufügen. Verwenden Sie die Maus, um die Position und Größe der Schaltfläche anzupassen.

3. Legen Sie im "Eigenschaftenfenster" die folgenden Eigenschaften der Schaltfläche fest:

    - Legen Sie die **Text** -Eigenschaft auf **Hello**fest.

    - Legen Sie die Eigenschaft **(Name)** auf **btnProtected**fest.

    - Legen Sie die **modifizierereigenschaft** auf **Protected**fest. Dadurch können Formulare, die von **Form1** erben, die Eigenschaften von **btnProtected**ändern.

4. Doppelklicken Sie auf die Schaltfläche " **Say Hello** ", um einen Ereignishandler für das **Click** -Ereignis hinzuzufügen.

5. Fügen Sie dem Ereignishandler folgende Codezeile hinzu:

    ```vb
    MessageBox.Show("Hello, World!")
    ```

    ```csharp
    MessageBox.Show("Hello, World!");
    ```

## <a name="add-a-button-that-cannot-be-modified-by-inheritors-of-the-base-form"></a>Hinzufügen einer Schaltfläche, die von Vererber des Basis Formulars nicht geändert werden kann

1. Wechseln Sie zur Entwurfs Ansicht, indem Sie über dem Code-Editor auf die Registerkarte **Form1. vb [Entwurf], Form1.cs [Entwurf] oder Form1. jsl [Design]** klicken, oder indem Sie F7 drücken.

2. Fügen Sie eine zweite Schaltfläche hinzu, und legen Sie deren Eigenschaften wie folgt fest:

    - Legen Sie die **Text** -Eigenschaft auf " **Goodbye**" fest.

    - Legen Sie die Eigenschaft **(Name)** auf **btnPrivate**fest.

    - Legen Sie die **modifizierereigenschaft** auf **Privat**fest. Dies macht es für Formulare, die von **Form1** erben, nicht möglich, die Eigenschaften von **btnPrivate**zu ändern.

3. Doppelklicken Sie auf die Schaltfläche " **Say Goodbye** ", um einen Ereignishandler für das **Click** -Ereignis hinzuzufügen. Platzieren Sie die folgende Codezeile in der Ereignisprozedur:

    ```vb
    MessageBox.Show("Goodbye!")
    ```

    ```csharp
    MessageBox.Show("Goodbye!");
    ```

4. Wählen Sie im Menü **Erstellen** die Option **BaseForm-Bibliothek erstellen** aus, um die Klassenbibliothek zu erstellen.

     Nachdem die Bibliothek erstellt wurde, können Sie ein neues Projekt erstellen, das von dem Formular erbt, das Sie gerade erstellt haben.

## <a name="create-a-project-containing-a-form-that-inherits-from-the-base-form"></a>Erstellen Sie ein Projekt, das ein Formular enthält, das vom Basis Formular erbt.

1. Wählen Sie im Menü **Datei** die Option **Hinzufügen** und dann **Neues Projekt** aus, um das Dialogfeld **Neues Projekt hinzufügen** zu öffnen.

2. Erstellen Sie eine Windows Forms Anwendung `InheritanceTest`mit dem Namen.

## <a name="add-an-inherited-form"></a>Ein geerbtes Formular hinzufügen

1. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt " **vererancetest** ", und wählen Sie **Hinzufügen**und dann **Neues Element**aus.

2. Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Kategorie **Windows Forms** aus (wenn Sie eine Liste mit Kategorien haben), und wählen Sie dann die Vorlage **geerbte Formulare aus** .

3. Belassen Sie den Standardnamen `Form2` von, und klicken Sie dann auf **Hinzufügen**.

4. Wählen Sie im Dialogfeld **Vererbungs** Auswahl die Option **Form1** aus dem **BaseFormLibrary** -Projekt als Formular aus, von dem geerbt werden soll, und klicken Sie auf **OK**.

     Dadurch wird ein Formular im **vererancetest** -Projekt erstellt, das aus dem Formular in **BaseFormLibrary**abgeleitet ist.

5. Öffnen Sie das geerbte Formular (**Form2**) im Designer, indem Sie darauf doppelklicken, wenn es nicht bereits geöffnet ist.

    Im Designer verfügen die geerbten Schaltflächen über ein Symbol (![Screenshot des Visual Basic Vererbungs Symbols](./media/walkthrough-demonstrating-visual-inheritance/visual-basic-inheritance-glyph.gif)) in der oberen Ecke, das angibt, dass Sie geerbt werden.

6. Wählen Sie die Schaltfläche "Hello" ( **Hallo** ) aus, und beobachten Sie die Handles Da diese Schaltfläche geschützt ist, können die Erben sie verschieben, ihre Größe ändern, ihre Beschriftung ändern und andere Änderungen vornehmen.

7. Wählen Sie die private Schaltfläche " **Goodbye** " aus, und beachten Sie, dass Sie keine Handles zur Größenänderung hat. Außerdem sind im **Eigenschaften** Fenster die Eigenschaften dieser Schaltfläche ausgegraut, um anzugeben, dass Sie nicht geändert werden können.

8. Bei Verwendung von Visual C#:

    1. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste im Projekt " **vererancetest** " auf **Form1** , und wählen Sie dann **Löschen**aus. Klicken Sie im angezeigten Meldungs Feld auf **OK** , um den Löschvorgang zu bestätigen.

    2. Öffnen Sie die Datei "Program.cs", und ändern Sie die Zeile `Application.Run(new Form1());` in `Application.Run(new Form2());`.

9. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt **vererancetest** , und wählen Sie **als Startprojekt festlegen**aus.

10. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt **vererancetest** , und wählen Sie **Eigenschaften**aus.

11. Legen Sie auf den Eigenschaften Seiten von **vererancetest** das **Start Objekt** auf das geerbte Formular (**Form2**) fest.

12. Drücken Sie **F5** , um die Anwendung auszuführen, und beobachten Sie das Verhalten des geerbten Formulars.

## <a name="next-steps"></a>Nächste Schritte

Die Vererbung bei Benutzersteuerelementen funktioniert größtenteils auf die gleiche Weise. Öffnen Sie ein neues Klassenbibliotheksprojekt, und fügen Sie ein Benutzersteuerelement hinzu. Platzieren Sie konstituierende Steuerelemente darauf, und kompilieren Sie das Projekt. Öffnen Sie ein weiteres, neues Klassenbibliotheksprojekt, und fügen Sie einen Verweis auf die kompilierte Klassenbibliothek hinzu. Fügen Sie dem Projekt außerdem ein geerbtes Steuerelement (über das Dialogfeld **neue Elemente hinzufügen** ) hinzu, und verwenden Sie die **Vererbungs**Auswahl. Fügen Sie ein Benutzer Steuerelement hinzu, `Inherits` und`:` ändern Sie C#die-Anweisung (in Visual). Weitere Informationen finden Sie unter [Vorgehensweise: Erben Sie](how-to-inherit-windows-forms.md)Windows Forms.

## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Windows Forms erben](how-to-inherit-windows-forms.md)
- [Visuelle Vererbung in Windows Forms](windows-forms-visual-inheritance.md)
- [Windows Forms](../index.md)

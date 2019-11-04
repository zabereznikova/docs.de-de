---
title: Problembehandlung beim Erstellen von Komponenten und Steuerelementen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- troubleshooting components
- troubleshooting controls [Windows Forms]
- controls [Windows Forms], troubleshooting
- components [Windows Forms], troubleshooting
- Windows Forms controls, debugging
ms.assetid: e9c8c099-2271-4737-882f-50f336c7a55e
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 9ee9df41e6f0a4e37164760a2e40740e31530121
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459076"
---
# <a name="troubleshoot-control-and-component-authoring"></a>Problembehandlung beim Erstellen von Steuerelementen und Komponenten

In diesem Thema werden die folgenden allgemeinen Probleme aufgelistet, die beim Entwickeln von Komponenten und Steuerelementen auftreten:

- Steuerelement kann nicht zur Toolbox hinzugefügt werden

- Windows Forms-Benutzersteuerelement oder Komponente kann nicht debuggt werden

- Ereignis wird im geerbten Steuerelement oder der Komponente zweimal ausgelöst

- Entwurfszeitfehler: „Failed to Create Component '*Component Name*'“ („Fehler beim Erstellen der Komponente ‚Komponentenname‘“)

- STAThreadAttribute

- Symbol „Komponente“ wird nicht in der Toolbox angezeigt

## <a name="cannot-add-control-to-toolbox"></a>Steuerelement kann nicht zur Toolbox hinzugefügt werden

Wenn Sie ein benutzerdefiniertes Steuerelement, das Sie in einem anderen Projekt erstellt haben, oder ein Drittanbieter-Steuerelement zur **Toolbox** hinzufügen möchten, müssen Sie dies manuell vornehmen. Wenn das aktuelle Projekt ein Steuerelement oder eine Komponente enthält, sollte es automatisch in der **Toolbox** angezeigt werden. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).

### <a name="to-add-a-control-to-the-toolbox"></a>So fügen Sie der Toolbox ein Steuerelement hinzu

1. Klicken Sie mit der rechten Maustaste auf **Toolbox**, und wählen Sie im Kontextmenü **Elemente auswählen** aus.

2. Fügen Sie im Dialogfeld **Toolboxelemente auswählen** die Komponente hinzu:

    - Wenn Sie eine .NET Framework-Komponente oder ein -Steuerelement hinzufügen möchten, klicken Sie auf die Registerkarte **.NET Framework-Komponenten**.

         – oder –

    - Wenn Sie eine COM-Komponente oder ein ActiveX-Steuerelement hinzufügen möchten, klicken Sie auf die Registerkarte **COM-Steuerelemente**.

3. Wenn das Steuerelement im Dialogfeld aufgelistet ist, bestätigen Sie die Auswahl, und klicken Sie auf **OK**.

     Das Steuerelement wird zur **Toolbox** hinzugefügt.

4. Wenn Ihr Steuerelement nicht im Dialogfeld aufgelistet ist, führen Sie folgende Schritte aus:

    1. Klicken Sie auf die Schaltfläche **Durchsuchen**.

    2. Navigieren Sie zum Ordner mit der DLL-Datei, die Ihr Steuerelement enthält.

    3. Wählen Sie die DLL-Datei aus, und klicken Sie auf **Öffnen**.

         Das Steuerelement wird im Dialogfeld angezeigt.

    4. Bestätigen Sie die Auswahl des Steuerelements, und klicken Sie dann auf **OK**.

         Ihr Steuerelement wird zur **Toolbox** hinzugefügt.

## <a name="cannot-debug-the-windows-forms-user-control-or-component"></a>Windows Forms-Benutzersteuerelement oder Komponente kann nicht debuggt werden

Wenn das Steuerelement von der <xref:System.Windows.Forms.UserControl>-Klasse abgeleitet ist, können Sie das Laufzeitverhalten mit dem Test Container Debuggen. Weitere Informationen finden Sie unter [Vorgehensweise: Testen des Laufzeitverhaltens eines UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).

Andere benutzerdefinierte Steuerelemente und Komponenten sind keine eigenständigen Projekte. Sie müssen von einer Anwendung wie einem Windows Forms-Projekt gehostet werden. Zum Debuggen eines Steuerelements oder einer Komponente müssen Sie sie zu einem Windows Forms-Projekt hinzufügen.

### <a name="to-debug-a-control-or-component"></a>So debuggen Sie ein Steuerelement oder eine Komponente

1. Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**, um eine Projektmappe zu erstellen.

2. Wählen Sie im Menü **Datei** **Hinzufügen** und dann **Neues Projekt** aus, um ein Testprojekt zu Ihrer Anwendung hinzuzufügen.

3. Wählen Sie im Dialogfeld **Neues Projekt hinzufügen** für den Projekttyp **Windows-Anwendung** aus.

4. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Knoten **Verweise** für das neue Projekt. Klicken Sie im Kontextmenü auf **Verweis hinzufügen**, um einen Verweis auf das Projekt mit dem Steuerelement oder der Komponente hinzuzufügen.

5. Erstellen Sie eine Instanz des Steuerelements oder der Komponente im Testprojekt. Wenn sich Ihre Komponente in der **Toolbox** befindet, können Sie sie auf die Oberfläche des Designers ziehen, oder die Instanz programmgesteuert erstellen, wie im folgenden Codebeispiel gezeigt wird.

    ```vb
    Dim Component1 As New MyNeatComponent()
    ```

    ```csharp
    MyNeatComponent Component1 = new MyNeatComponent();
    ```

   Sie können jetzt das Steuerelement oder die Komponente wie gewohnt debuggen.

Weitere Informationen zum Debuggen finden Sie unter [Debuggen in Visual Studio](/visualstudio/debugger/debugger-feature-tour) und [Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms-Steuerelementen zur Entwurfszeit](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).

## <a name="event-is-raised-twice-in-inherited-control-or-component"></a>Ereignis wird im geerbten Steuerelement oder der Komponente zweimal ausgelöst

Dies liegt wahrscheinlich an einer doppelten `Handles`-Klausel. Weitere Informationen finden Sie unter [Problembehandlung für geerbte Ereignishandler in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).

## <a name="design-time-error-failed-to-create-component-component-name"></a>Entwurfszeitfehler: „Failed to Create Component 'Component Name'“ („Fehler beim Erstellen der Komponente ‚Komponentenname‘“)

Die Komponente oder das Steuerelement muss einen Parameter losen Konstruktor ohne Parameter bereitstellen. Wenn die Entwurfsumgebung eine Instanz der Komponente oder des Steuerelements erstellt, versucht sie nicht, Parameter auf Konstruktorüberladungen bereitzustellen, die Parameter annehmen.

## <a name="stathreadattribute"></a>STAThreadAttribute

Der <xref:System.STAThreadAttribute> informiert den Common Language Runtime (CLR), dass Windows Forms das Single Thread-Apartment Modell verwendet. Möglicherweise kommt es zu unbeabsichtigtem Verhalten, wenn Sie dieses Attribut nicht auf die `Main`-Methode Ihrer Windows Forms Anwendung anwenden. Beispielsweise können Hintergrundbilder für Steuerelemente wie <xref:System.Windows.Forms.ListView>nicht angezeigt werden. Einige Steuerelemente benötigen dieses Attribut möglicherweise für korrektes AutoComplete- und Drag & Drop-Verhalten.

## <a name="component-icon-does-not-appear-in-toolbox"></a>Symbol „Komponente“ wird nicht in der Toolbox angezeigt

Wenn Sie <xref:System.Drawing.ToolboxBitmapAttribute> verwenden, um der benutzerdefinierten Komponente ein Symbol zuzuordnen, wird die Bitmap für automatisch generierte Komponenten nicht in der Toolbox angezeigt. Laden Sie das Steuerelement mithilfe des Dialogfelds **Toolboxelemente auswählen** neu, um die Bitmap anzuzeigen. Weitere Informationen finden Sie unter [Vorgehensweise: Bereitstellen einer Toolboxbitmap für ein Steuerelement](how-to-provide-a-toolbox-bitmap-for-a-control.md).

## <a name="see-also"></a>Siehe auch

- [Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit](developing-windows-forms-controls-at-design-time.md)
- [Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
- [Vorgehensweise: Testen des Laufzeitverhaltens eines UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)
- [Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms-Steuerelementen zur Entwurfszeit](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)

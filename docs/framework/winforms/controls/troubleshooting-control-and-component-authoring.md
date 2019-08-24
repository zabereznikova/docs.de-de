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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 2e0b98107ac5f43c80aad6cb5ea61e6f4e1e28d3
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015709"
---
# <a name="troubleshoot-control-and-component-authoring"></a>Problembehandlung bei der Erstellung von Steuerelementen und Komponenten

In diesem Thema werden die folgenden allgemeinen Probleme aufgelistet, die beim Entwickeln von Komponenten und Steuerelementen auftreten:

- Steuerelement kann nicht zur Toolbox hinzugefügt werden

- Windows Forms-Benutzersteuerelement oder Komponente kann nicht debuggt werden

- Ereignis wird im geerbten Steuerelement oder der Komponente zweimal ausgelöst

- Entwurfs Zeitfehler: "Fehler beim Erstellen der Komponente '*Komponenten Name*'".

- STAThreadAttribute

- Symbol „Komponente“ wird nicht in der Toolbox angezeigt

## <a name="cannot-add-control-to-toolbox"></a>Steuerelement kann nicht zur Toolbox hinzugefügt werden

Wenn Sie ein benutzerdefiniertes Steuerelement, das Sie in einem anderen Projekt erstellt haben, oder ein Drittanbieter-Steuerelement zur **Toolbox** hinzufügen möchten, müssen Sie dies manuell vornehmen. Wenn das aktuelle Projekt ein Steuerelement oder eine Komponente enthält, sollte es automatisch in der **Toolbox** angezeigt werden. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Automatisches Auffüllen der Toolbox mit benutzerdefinierten Komponenten](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).

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

Wenn das Steuerelement von der <xref:System.Windows.Forms.UserControl> -Klasse abgeleitet ist, können Sie das Laufzeitverhalten mit dem Test Container Debuggen. Weitere Informationen finden Sie unter [Vorgehensweise: Testen Sie das Laufzeitverhalten eines UserControl-](how-to-test-the-run-time-behavior-of-a-usercontrol.md)Steuer Elements.

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

Weitere Informationen zum Debuggen finden Sie unter [Debuggen in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio) und [Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)Steuerelementen zur Entwurfszeit

## <a name="event-is-raised-twice-in-inherited-control-or-component"></a>Ereignis wird im geerbten Steuerelement oder der Komponente zweimal ausgelöst

Dies liegt wahrscheinlich an einer doppelten `Handles`-Klausel. Weitere Informationen finden Sie unter [Problembehandlung für geerbte Ereignishandler in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).

## <a name="design-time-error-failed-to-create-component-component-name"></a>Entwurfs Zeitfehler: "Fehler beim Erstellen der Komponente ' Komponenten Name '".

Die Komponente oder das Steuerelement muss einen Parameter losen Konstruktor ohne Parameter bereitstellen. Wenn die Entwurfsumgebung eine Instanz der Komponente oder des Steuerelements erstellt, versucht sie nicht, Parameter auf Konstruktorüberladungen bereitzustellen, die Parameter annehmen.

## <a name="stathreadattribute"></a>STAThreadAttribute

Der <xref:System.STAThreadAttribute> informiert den Common Language Runtime (CLR), dass Windows Forms das Single Thread-Apartment Modell verwendet. Möglicherweise kommt es zu unbeabsichtigtem Verhalten, wenn Sie dieses Attribut nicht auf die `Main`-Methode Ihrer Windows Forms Anwendung anwenden. Beispielsweise können Hintergrundbilder für Steuerelemente wie <xref:System.Windows.Forms.ListView>nicht angezeigt werden. Einige Steuerelemente benötigen dieses Attribut möglicherweise für korrektes AutoComplete- und Drag & Drop-Verhalten.

## <a name="component-icon-does-not-appear-in-toolbox"></a>Symbol „Komponente“ wird nicht in der Toolbox angezeigt

Wenn Sie verwenden <xref:System.Drawing.ToolboxBitmapAttribute> , um der benutzerdefinierten Komponente ein Symbol zuzuordnen, wird die Bitmap für automatisch generierte Komponenten nicht in der Toolbox angezeigt. Laden Sie das Steuerelement mithilfe des Dialogfelds **Toolboxelemente auswählen** neu, um die Bitmap anzuzeigen. Weitere Informationen finden Sie unter [Vorgehensweise: Stellen Sie eine Toolbox Bitmap für ein](how-to-provide-a-toolbox-bitmap-for-a-control.md)Steuerelement bereit.

## <a name="see-also"></a>Siehe auch

- [Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit](developing-windows-forms-controls-at-design-time.md)
- [Exemplarische Vorgehensweise: Automatisches Auffüllen der Toolbox mit benutzerdefinierten Komponenten](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
- [Vorgehensweise: Testen des Lauf Zeit Verhaltens eines UserControl-Steuer Elements](how-to-test-the-run-time-behavior-of-a-usercontrol.md)
- [Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms-Steuerelementen zur Entwurfszeit](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)

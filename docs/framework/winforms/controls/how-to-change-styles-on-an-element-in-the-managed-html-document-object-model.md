---
title: 'Vorgehensweise: Ändern von Formaten eines Elements im verwalteten HTML-Dokumentobjektmodell'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- managed HTML DOM [Windows Forms], changing styles on elements
ms.assetid: 154e8d9f-3e2d-4e8b-a6f3-c85a070e9cc1
ms.openlocfilehash: ad91f7591e2fa07605fe4f7ac026b7c969ab7ef0
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2019
ms.locfileid: "57678930"
---
# <a name="how-to-change-styles-on-an-element-in-the-managed-html-document-object-model"></a>Vorgehensweise: Ändern von Formaten eines Elements im verwalteten HTML-Dokumentobjektmodell

Stile können in HTML-Code Sie die Darstellung eines Dokuments und seine Elemente steuern. <xref:System.Windows.Forms.HtmlDocument> und <xref:System.Windows.Forms.HtmlElement> unterstützen <xref:System.Windows.Forms.HtmlElement.Style%2A> Eigenschaften, die Formatzeichenfolgen im folgenden Format verwenden:

`name1:value1;...;nameN:valueN;`

Hier ist ein `DIV` mit einer Formatzeichenfolge, die die Schriftart auf Arial und den Text fett formatiert festlegt:

`<DIV style="font-face:arial;font-weight:bold;">`

`Hello, world!`

`</DIV>`

Das Problem mit dem Bearbeiten von Stilen mithilfe der <xref:System.Windows.Forms.HtmlElement.Style%2A> Eigenschaft ist, dass es mühsam, hinzufügen und Entfernen von einzelnen stileinstellungen aus der Zeichenfolge nachweisen kann. Beispielsweise würde es eine komplexe Prozedur für die Sie vom vorangehenden Text in Kursivdruck rendern, wenn der Benutzer den Cursor über positioniert werden die `DIV`, und kursiv deaktiviert, wenn der Cursor verlässt die `DIV`. Wenn Sie eine große Anzahl von Formaten auf diese Weise bearbeiten müssen würde ein Problem dar.

Das folgende Verfahren enthält Code, mit denen Sie problemlos Formate für HTML-Dokumente und Elemente bearbeiten. Die Prozedur erfordert, dass Sie wissen, wie Sie grundlegende Aufgaben in Windows Forms, z. B. Erstellen eines neuen Projekts und Hinzufügen eines Steuerelements zu einem Formular.

### <a name="to-process-style-changes-in-a-windows-forms-application"></a>Verarbeiten von Änderungen an Formatvorlagen in Windows Forms-Anwendungen

1. Erstellen Sie ein neues Windows Forms-Projekt.

2. Erstellen Sie eine neue Klassendatei, die mit der Erweiterung, die für Ihre bevorzugte Programmiersprache geeignet.

3. Kopieren der `StyleGenerator` -Klassencode im Beispielabschnitt dieses Themas in die Klassendatei, und speichern Sie den Code.

4. Speichern Sie die folgenden HTML-Code in eine Datei namens Test.htm.

    ```html
    <HTML>
        <BODY>

            <DIV style="font-face:arial;font-weight:bold;">
                Hello, world!
            </DIV><P>

            <DIV>
                Hello again, world!
            </DIV><P>

        </BODY>
    </HTML>
    ```

5. Hinzufügen einer <xref:System.Windows.Forms.WebBrowser> Steuerelement mit dem Namen `webBrowser1` zum Hauptformular Ihres Projekts.

6. Fügen Sie den folgenden Code, Code-Datei des Projekts hinzu.

    > [!IMPORTANT]
    > Sicherstellen, dass die `webBrowser1_DocumentCompleted` Ereignishandler als konfiguriert ist, einen Listener für die <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> Ereignis. Doppelklicken Sie im Visual Studio auf die <xref:System.Windows.Forms.WebBrowser> steuern; in einem Text-Editor, konfigurieren Sie den Listener programmgesteuert.

    [!code-csharp[ManagedDOMStyles#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/Form1.cs#2)]
    [!code-vb[ManagedDOMStyles#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/Form1.vb#2)]

7. Führen Sie das Projekt aus. Führen Sie den Cursor über der ersten `DIV` um die Auswirkungen des Codes zu beobachten.

## <a name="example"></a>Beispiel

Das folgende Codebeispiel zeigt den vollständigen Code für die `StyleGenerator` -Klasse, die einen vorhandenen Stilwert analysiert wird, unterstützt das Hinzufügen, ändern und Entfernen von formatiert und einen neuen Style-Wert, mit der angeforderten Änderungen zurückgibt.

[!code-csharp[ManagedDOMStyles#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/StyleGenerator.cs#1)]
[!code-vb[ManagedDOMStyles#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/StyleGenerator.vb#1)]

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.HtmlElement>

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
# <a name="how-to-change-styles-on-an-element-in-the-managed-html-document-object-model"></a><span data-ttu-id="871b9-102">Vorgehensweise: Ändern von Formaten eines Elements im verwalteten HTML-Dokumentobjektmodell</span><span class="sxs-lookup"><span data-stu-id="871b9-102">How to: Change Styles on an Element in the Managed HTML Document Object Model</span></span>

<span data-ttu-id="871b9-103">Stile können in HTML-Code Sie die Darstellung eines Dokuments und seine Elemente steuern.</span><span class="sxs-lookup"><span data-stu-id="871b9-103">You can use styles in HTML to control the appearance of a document and its elements.</span></span> <span data-ttu-id="871b9-104"><xref:System.Windows.Forms.HtmlDocument> und <xref:System.Windows.Forms.HtmlElement> unterstützen <xref:System.Windows.Forms.HtmlElement.Style%2A> Eigenschaften, die Formatzeichenfolgen im folgenden Format verwenden:</span><span class="sxs-lookup"><span data-stu-id="871b9-104"><xref:System.Windows.Forms.HtmlDocument> and <xref:System.Windows.Forms.HtmlElement> support <xref:System.Windows.Forms.HtmlElement.Style%2A> properties that take style strings of the following format:</span></span>

`name1:value1;...;nameN:valueN;`

<span data-ttu-id="871b9-105">Hier ist ein `DIV` mit einer Formatzeichenfolge, die die Schriftart auf Arial und den Text fett formatiert festlegt:</span><span class="sxs-lookup"><span data-stu-id="871b9-105">Here is a `DIV` with a style string that sets the font to Arial and all text to bold:</span></span>

`<DIV style="font-face:arial;font-weight:bold;">`

`Hello, world!`

`</DIV>`

<span data-ttu-id="871b9-106">Das Problem mit dem Bearbeiten von Stilen mithilfe der <xref:System.Windows.Forms.HtmlElement.Style%2A> Eigenschaft ist, dass es mühsam, hinzufügen und Entfernen von einzelnen stileinstellungen aus der Zeichenfolge nachweisen kann.</span><span class="sxs-lookup"><span data-stu-id="871b9-106">The problem with manipulating styles using the <xref:System.Windows.Forms.HtmlElement.Style%2A> property is that it can prove cumbersome to add to and remove individual style settings from the string.</span></span> <span data-ttu-id="871b9-107">Beispielsweise würde es eine komplexe Prozedur für die Sie vom vorangehenden Text in Kursivdruck rendern, wenn der Benutzer den Cursor über positioniert werden die `DIV`, und kursiv deaktiviert, wenn der Cursor verlässt die `DIV`.</span><span class="sxs-lookup"><span data-stu-id="871b9-107">For example, it would become a complex procedure for you to render the previous text in italics whenever the user positions the cursor over the `DIV`, and take italics off when the cursor leaves the `DIV`.</span></span> <span data-ttu-id="871b9-108">Wenn Sie eine große Anzahl von Formaten auf diese Weise bearbeiten müssen würde ein Problem dar.</span><span class="sxs-lookup"><span data-stu-id="871b9-108">Time would become an issue if you need to manipulate a large number of styles in this manner.</span></span>

<span data-ttu-id="871b9-109">Das folgende Verfahren enthält Code, mit denen Sie problemlos Formate für HTML-Dokumente und Elemente bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="871b9-109">The following procedure contains code that you can use to easily manipulate styles on HTML documents and elements.</span></span> <span data-ttu-id="871b9-110">Die Prozedur erfordert, dass Sie wissen, wie Sie grundlegende Aufgaben in Windows Forms, z. B. Erstellen eines neuen Projekts und Hinzufügen eines Steuerelements zu einem Formular.</span><span class="sxs-lookup"><span data-stu-id="871b9-110">The procedure requires that you know how to perform basic tasks in Windows Forms, such as creating a new project and adding a control to a form.</span></span>

### <a name="to-process-style-changes-in-a-windows-forms-application"></a><span data-ttu-id="871b9-111">Verarbeiten von Änderungen an Formatvorlagen in Windows Forms-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="871b9-111">To process style changes in a Windows Forms application</span></span>

1. <span data-ttu-id="871b9-112">Erstellen Sie ein neues Windows Forms-Projekt.</span><span class="sxs-lookup"><span data-stu-id="871b9-112">Create a new Windows Forms project.</span></span>

2. <span data-ttu-id="871b9-113">Erstellen Sie eine neue Klassendatei, die mit der Erweiterung, die für Ihre bevorzugte Programmiersprache geeignet.</span><span class="sxs-lookup"><span data-stu-id="871b9-113">Create a new class file ending in the extension appropriate for your programming language.</span></span>

3. <span data-ttu-id="871b9-114">Kopieren der `StyleGenerator` -Klassencode im Beispielabschnitt dieses Themas in die Klassendatei, und speichern Sie den Code.</span><span class="sxs-lookup"><span data-stu-id="871b9-114">Copy the `StyleGenerator` class code in the Example section of this topic into the class file, and save the code.</span></span>

4. <span data-ttu-id="871b9-115">Speichern Sie die folgenden HTML-Code in eine Datei namens Test.htm.</span><span class="sxs-lookup"><span data-stu-id="871b9-115">Save the following HTML to a file named Test.htm.</span></span>

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

5. <span data-ttu-id="871b9-116">Hinzufügen einer <xref:System.Windows.Forms.WebBrowser> Steuerelement mit dem Namen `webBrowser1` zum Hauptformular Ihres Projekts.</span><span class="sxs-lookup"><span data-stu-id="871b9-116">Add a <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1` to the main form of your project.</span></span>

6. <span data-ttu-id="871b9-117">Fügen Sie den folgenden Code, Code-Datei des Projekts hinzu.</span><span class="sxs-lookup"><span data-stu-id="871b9-117">Add the following code to your project's code file.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="871b9-118">Sicherstellen, dass die `webBrowser1_DocumentCompleted` Ereignishandler als konfiguriert ist, einen Listener für die <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="871b9-118">Ensure that the `webBrowser1_DocumentCompleted` event handler is configured as a listener for the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="871b9-119">Doppelklicken Sie im Visual Studio auf die <xref:System.Windows.Forms.WebBrowser> steuern; in einem Text-Editor, konfigurieren Sie den Listener programmgesteuert.</span><span class="sxs-lookup"><span data-stu-id="871b9-119">In Visual Studio, double-click on the <xref:System.Windows.Forms.WebBrowser> control; in a text editor, configure the listener programmatically.</span></span>

    [!code-csharp[ManagedDOMStyles#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/Form1.cs#2)]
    [!code-vb[ManagedDOMStyles#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/Form1.vb#2)]

7. <span data-ttu-id="871b9-120">Führen Sie das Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="871b9-120">Run the project.</span></span> <span data-ttu-id="871b9-121">Führen Sie den Cursor über der ersten `DIV` um die Auswirkungen des Codes zu beobachten.</span><span class="sxs-lookup"><span data-stu-id="871b9-121">Run your cursor over the first `DIV` to observe the effects of the code.</span></span>

## <a name="example"></a><span data-ttu-id="871b9-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="871b9-122">Example</span></span>

<span data-ttu-id="871b9-123">Das folgende Codebeispiel zeigt den vollständigen Code für die `StyleGenerator` -Klasse, die einen vorhandenen Stilwert analysiert wird, unterstützt das Hinzufügen, ändern und Entfernen von formatiert und einen neuen Style-Wert, mit der angeforderten Änderungen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="871b9-123">The following code example shows the full code for the `StyleGenerator` class, which parses an existing style value, supports adding, changing, and removing styles, and returns a new style value with the requested changes.</span></span>

[!code-csharp[ManagedDOMStyles#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ManagedDOMStyles/CS/StyleGenerator.cs#1)]
[!code-vb[ManagedDOMStyles#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ManagedDOMStyles/VB/StyleGenerator.vb#1)]

## <a name="see-also"></a><span data-ttu-id="871b9-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="871b9-124">See also</span></span>

- <xref:System.Windows.Forms.HtmlElement>

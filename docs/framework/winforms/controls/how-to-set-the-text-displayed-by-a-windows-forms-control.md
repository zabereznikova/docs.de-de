---
title: Festlegen des von einem Steuerelement angezeigten Texts
description: Erfahren Sie, wie Sie den Text festlegen, der von einem Windows Forms Steuerelement angezeigt wird. Legen Sie den Text mithilfe der Text-Eigenschaft fest oder geben Sie ihn zurück, oder ändern Sie die Schriftart mithilfe der Font-Eigenschaft.
ms.date: 08/20/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, captions
- Button control [Windows Forms], button text
- StdFont object and CommandButton caption
- captions [Windows Forms], Windows Forms controls
- Text property [Windows Forms], Windows Forms control
- Button control [Windows Forms], text display
- labels [Windows Forms], adding to CommandButton control
- buttons [Windows Forms], text
- captions [Windows Forms], setting
- text
- examples [Windows Forms], controls
- text [Windows Forms], Windows Forms controls
- controls [Windows Forms], captions
- forms [Windows Forms], captions
ms.assetid: 36b95bff-8780-479d-b86a-f1a0673653aa
ms.openlocfilehash: 35bae5830bfee8ab91f7b6c7b9dcc6d6b8db00ca
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622847"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control"></a><span data-ttu-id="c567f-104">Gewusst wie: Festlegen des von einem Windows Forms-Steuerelement angezeigten Texts</span><span class="sxs-lookup"><span data-stu-id="c567f-104">How to: Set the text displayed by a Windows Forms control</span></span>

<span data-ttu-id="c567f-105">Windows Forms Steuerelemente zeigen normalerweise Text an, der mit der primären Funktion des Steuer Elements verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="c567f-105">Windows Forms controls usually display some text that's related to the primary function of the control.</span></span> <span data-ttu-id="c567f-106">Ein Steuerelement zeigt beispielsweise <xref:System.Windows.Forms.Button> in der Regel eine Beschriftung an, die angibt, welche Aktion ausgeführt wird, wenn auf die Schaltfläche geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="c567f-106">For example, a <xref:System.Windows.Forms.Button> control usually displays a caption indicating what action will be performed if the button is clicked.</span></span> <span data-ttu-id="c567f-107">Bei allen Steuerelementen können Sie den Text mithilfe der <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft festlegen oder zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="c567f-107">For all controls, you can set or return the text by using the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="c567f-108">Sie können die Schriftart ändern, indem Sie die <xref:System.Windows.Forms.Control.Font%2A>-Eigenschaft verwenden.</span><span class="sxs-lookup"><span data-stu-id="c567f-108">You can change the font by using the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span>

<span data-ttu-id="c567f-109">Sie können den Text auch mit dem- [Designer](#designer)festlegen.</span><span class="sxs-lookup"><span data-stu-id="c567f-109">You can also set the text by using the [designer](#designer).</span></span>

## <a name="programmatic"></a><span data-ttu-id="c567f-110">Programmgesteuert</span><span class="sxs-lookup"><span data-stu-id="c567f-110">Programmatic</span></span>

1. <span data-ttu-id="c567f-111">Legen Sie für die <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft eine Zeichenfolge fest.</span><span class="sxs-lookup"><span data-stu-id="c567f-111">Set the <xref:System.Windows.Forms.Control.Text%2A> property to a string.</span></span>

   <span data-ttu-id="c567f-112">Zum Erstellen einer unterstrichenen Zugriffstaste enthält ein kaufmännisches und-(&) vor dem Buchstaben, der als Zugriffstaste verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c567f-112">To create an underlined access key, includes an ampersand (&) before the letter that will be the access key.</span></span>

2. <span data-ttu-id="c567f-113">Legen Sie die <xref:System.Windows.Forms.Control.Font%2A>-Eigenschaft auf ein Objekt des Typs <xref:System.Drawing.Font> fest.</span><span class="sxs-lookup"><span data-stu-id="c567f-113">Set the <xref:System.Windows.Forms.Control.Font%2A> property to an object of type <xref:System.Drawing.Font>.</span></span>

    ```vb
    Button1.Text = "Click here to save changes"
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)
    ```

    ```csharp
    button1.Text = "Click here to save changes";
    button1.Font = new Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point);
    ```

    ```cpp
    button1->Text = "Click here to save changes";
    button1->Font = new System::Drawing::Font("Arial", 10, FontStyle::Bold, GraphicsUnit::Point);
    ```

    > [!NOTE]
    > <span data-ttu-id="c567f-114">Mit einem Escapezeichen können Sie ein Sonderzeichen in Benutzeroberflächenelementen anzeigen, das diese normalerweise anders interpretieren würde, z. B. Menüelemente.</span><span class="sxs-lookup"><span data-stu-id="c567f-114">You can use an escape character to display a special character in user-interface elements that would normally interpret them differently, such as menu items.</span></span> <span data-ttu-id="c567f-115">Mit der folgenden Codezeile wird z. b. der Text des Menü Elements so festgelegt, dass der Text "& jetzt für etwas unterschiedliches Element" lautet:</span><span class="sxs-lookup"><span data-stu-id="c567f-115">For example, the following line of code sets the menu item's text to read "& Now For Something Completely Different":</span></span>

    ```vb
    MPMenuItem.Text = "&& Now For Something Completely Different"
    ```

    ```csharp
    mpMenuItem.Text = "&& Now For Something Completely Different";
    ```

    ```cpp
    mpMenuItem->Text = "&& Now For Something Completely Different";
    ```

## <a name="designer"></a><span data-ttu-id="c567f-116">Designer</span><span class="sxs-lookup"><span data-stu-id="c567f-116">Designer</span></span>

1. <span data-ttu-id="c567f-117">Legen Sie im **Eigenschaften** Fenster von Visual Studio die **Text** -Eigenschaft des-Steuer Elements auf eine entsprechende Zeichenfolge fest.</span><span class="sxs-lookup"><span data-stu-id="c567f-117">In the **Properties** window in Visual Studio, set the **Text** property of the control to an appropriate string.</span></span>

   <span data-ttu-id="c567f-118">Zum Erstellen einer unterstrichenen Tastenkombination enthält ein kaufmännisches und-(&) vor dem Buchstaben, der als Tastenkombination verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c567f-118">To create an underlined shortcut key, includes an ampersand (&) before the letter that will be the shortcut key.</span></span>

2. <span data-ttu-id="c567f-119">Wählen Sie im Fenster **Eigenschaften** die Schaltfläche mit den Auslassungs Punkten (Auslassungs Zeichen ![ (...) im Eigenschaftenfenster von Visual Studio ](./media/visual-studio-ellipsis-button.png) ) neben der Eigenschaft **Schriftart** aus.</span><span class="sxs-lookup"><span data-stu-id="c567f-119">In the **Properties** window, select the ellipsis button (![Ellipsis button (...) in the Properties window of Visual Studio](./media/visual-studio-ellipsis-button.png)) next to the **Font** property.</span></span>

   <span data-ttu-id="c567f-120">Wählen Sie im Dialogfeld Standard Schriftart die Schriftart, den Schrift Schnitt, die Größe, die Effekte (z. b. durchgestrichen oder unterstreichen) und das gewünschte Skript aus.</span><span class="sxs-lookup"><span data-stu-id="c567f-120">In the standard font dialog box, select the font, font style, size, effects (such as strikeout or underline), and script that you want.</span></span>

## <a name="see-also"></a><span data-ttu-id="c567f-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c567f-121">See also</span></span>

- <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>
- [<span data-ttu-id="c567f-122">Gewusst wie: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="c567f-122">How to: Create Access Keys for Windows Forms Controls</span></span>](how-to-create-access-keys-for-windows-forms-controls.md)
- [<span data-ttu-id="c567f-123">Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c567f-123">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)

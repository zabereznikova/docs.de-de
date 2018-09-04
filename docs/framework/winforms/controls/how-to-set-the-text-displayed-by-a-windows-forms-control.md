---
title: 'Gewusst wie: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Textes'
ms.date: 03/30/2017
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
ms.openlocfilehash: d9c9bea26cfc3d5b2cfc4484173a7680ff2fc34d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43525034"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control"></a><span data-ttu-id="c1e1d-102">Gewusst wie: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Textes</span><span class="sxs-lookup"><span data-stu-id="c1e1d-102">How to: Set the Text Displayed by a Windows Forms Control</span></span>
<span data-ttu-id="c1e1d-103">Windows Forms-Steuerelemente zeigen in der Regel Text an, der mit der Hauptfunktion des Steuerelements zusammenhängt.</span><span class="sxs-lookup"><span data-stu-id="c1e1d-103">Windows Forms controls usually display some text that is related to the primary function of the control.</span></span> <span data-ttu-id="c1e1d-104">Beispielsweise verfügt ein <xref:System.Windows.Forms.Button>-Steuerelement üblicherweise über eine Beschriftung, die auf die beim Klicken der Schaltfläche ausgeführte Aktion hinweist.</span><span class="sxs-lookup"><span data-stu-id="c1e1d-104">For example, a <xref:System.Windows.Forms.Button> control usually displays a caption indicating what action will be performed when the button is clicked.</span></span> <span data-ttu-id="c1e1d-105">Bei allen Steuerelementen können Sie den Text mithilfe der <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft festlegen oder zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="c1e1d-105">For all controls, you can set or return the text by using the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="c1e1d-106">Sie können die Schriftart ändern, indem Sie die <xref:System.Windows.Forms.Control.Font%2A>-Eigenschaft verwenden.</span><span class="sxs-lookup"><span data-stu-id="c1e1d-106">You can change the font by using the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span> <span data-ttu-id="c1e1d-107">Sie können den Text aber auch mithilfe des Designers festlegen. </span><span class="sxs-lookup"><span data-stu-id="c1e1d-107">You can also set the text using the designer.</span></span>  <span data-ttu-id="c1e1d-108">Siehe auch [wie: Erstellen Access Keys für Windows Forms-Steuerelemente mithilfe des Designers](how-to-create-access-keys-for-windows-forms-controls-using-the-designer.md), [wie: Festlegen der Text angezeigt, die ein Windows Forms-Steuerelement mithilfe den Designer](how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer.md), [wie: Festlegen des Images Angezeigt wird, indem Sie eine Windows Forms-Steuerelement mithilfe des Designers](how-to-set-the-image-displayed-by-a-windows-forms-control-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="c1e1d-108">Also see [How to: Create Access Keys for Windows Forms Controls Using the Designer](how-to-create-access-keys-for-windows-forms-controls-using-the-designer.md), [How to: Set the Text Displayed by a Windows Forms Control Using the Designer](how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer.md), [How to: Set the Image Displayed by a Windows Forms Control Using the Designer](how-to-set-the-image-displayed-by-a-windows-forms-control-using-the-designer.md).</span></span>  
  
### <a name="to-set-the-text-displayed-by-a-control-programmatically"></a><span data-ttu-id="c1e1d-109">So legen Sie den von einem Steuerelement angezeigten Text programmgesteuert fest</span><span class="sxs-lookup"><span data-stu-id="c1e1d-109">To set the text displayed by a control programmatically</span></span>  
  
1.  <span data-ttu-id="c1e1d-110">Legen Sie für die <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft eine Zeichenfolge fest.</span><span class="sxs-lookup"><span data-stu-id="c1e1d-110">Set the <xref:System.Windows.Forms.Control.Text%2A> property to a string.</span></span>  
  
     <span data-ttu-id="c1e1d-111">Wenn Sie eine unterstrichene Zugriffstaste erstellen möchten, setzen Sie ein kaufmännisches Und-Zeichen (&) vor den Buchstaben der Zugriffstaste.</span><span class="sxs-lookup"><span data-stu-id="c1e1d-111">To create an underlined access key, includes an ampersand (&) before the letter that will be the access key.</span></span>  
  
2.  <span data-ttu-id="c1e1d-112">Legen Sie die <xref:System.Windows.Forms.Control.Font%2A>-Eigenschaft auf ein Objekt des Typs <xref:System.Drawing.Font> fest.</span><span class="sxs-lookup"><span data-stu-id="c1e1d-112">Set the <xref:System.Windows.Forms.Control.Font%2A> property to an object of type <xref:System.Drawing.Font>.</span></span>  
  
    ```vb  
    Button1.Text = "Click here to save changes"  
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)  
    ```  
  
    ```csharp  
    button1.Text = "Click here to save changes";  
    button1.Font = new Font("Arial", 10, FontStyle.Bold,  
       GraphicsUnit.Point);  
    ```  
  
    ```cpp  
    button1->Text = "Click here to save changes";  
    button1->Font = new System::Drawing::Font("Arial",  
       10, FontStyle::Bold, GraphicsUnit::Point);  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="c1e1d-113">Mit einem Escapezeichen können Sie ein Sonderzeichen in Benutzeroberflächenelementen anzeigen, das diese normalerweise anders interpretieren würde, z. B. Menüelemente.</span><span class="sxs-lookup"><span data-stu-id="c1e1d-113">You can use an escape character to display a special character in user-interface elements that would normally interpret them differently, such as menu items.</span></span> <span data-ttu-id="c1e1d-114">Mit der folgenden Codezeile wird der Text des Menüelements beispielsweise wie folgt festgelegt: "& Now For Something Completely Different":</span><span class="sxs-lookup"><span data-stu-id="c1e1d-114">For example, the following line of code sets the menu item's text to read "& Now For Something Completely Different":</span></span>  
  
    ```vb  
    MPMenuItem.Text = "&& Now For Something Completely Different"  
    ```  
  
    ```csharp  
    mpMenuItem.Text = "&& Now For Something Completely Different";  
    ```  
  
    ```cpp  
    mpMenuItem->Text = "&& Now For Something Completely Different";  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c1e1d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1e1d-115">See Also</span></span>  
 <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="c1e1d-116">Gewusst wie: Erstellen von Zugriffstasten für Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="c1e1d-116">How to: Create Access Keys for Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)  
 [<span data-ttu-id="c1e1d-117">Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c1e1d-117">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)

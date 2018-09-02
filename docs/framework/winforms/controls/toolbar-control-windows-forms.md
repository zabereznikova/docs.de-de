---
title: ToolBar-Steuerelement (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolBar control [Windows Forms]
ms.assetid: 6b40e9ce-6a7a-4784-bfc9-7f1d36b7462e
ms.openlocfilehash: 8162dfc898f7965d65de918d2a5b1f7afbfdf9b2
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43400848"
---
# <a name="toolbar-control-windows-forms"></a><span data-ttu-id="8c746-102">ToolBar-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="8c746-102">ToolBar Control (Windows Forms)</span></span>
> [!NOTE]
>  <span data-ttu-id="8c746-103">Obwohl das <xref:System.Windows.Forms.ToolStrip>-Steuerelement das `ToolBar`-Steuerelement ersetzt und funktionell erweitert, wird das `ToolBar`-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="8c746-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the `ToolBar` control; however, the `ToolBar` control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="8c746-104">Das `ToolBar`-Steuerelement von Windows Forms wird in Formularen als eine Steuerleiste verwendet, auf der eine Zeile aus Dropdownmenüs und Bitmapschaltflächen angezeigt wird, die Befehle aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8c746-104">The Windows Forms `ToolBar` control is used on forms as a control bar that displays a row of drop-down menus and bitmapped buttons that activate commands.</span></span> <span data-ttu-id="8c746-105">Daher ist ein Klicken auf eine Symbolleistenschaltfläche mit dem Auswählen eines Menübefehls identisch.</span><span class="sxs-lookup"><span data-stu-id="8c746-105">Thus, clicking a toolbar button is equivalent to choosing a menu command.</span></span> <span data-ttu-id="8c746-106">Die Schaltflächen können so konfiguriert werden, dass sie so angezeigt werden und sich so verhalten wie Schaltflächen, Dropdownmenüs oder Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="8c746-106">The buttons can be configured to appear and behave as push buttons, drop-down menus, or separators.</span></span> <span data-ttu-id="8c746-107">In der Regel enthält eine Symbolleiste Schaltflächen und Menüs, die Elementen in der Menüstruktur einer Anwendung entsprechen. Dadurch wird schneller Zugriff auf die am häufigsten verwendeten Funktionen und Befehle einer Anwendung ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="8c746-107">Typically, a toolbar contains buttons and menus that correspond to items in an application's menu structure, providing quick access to an application's most frequently used functions and commands.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c746-108">Die <xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A>-Eigenschaft des `ToolBar`-Steuerelements übernimmt eine Instanz der <xref:System.Windows.Forms.ContextMenu>-Klasse als Verweis.</span><span class="sxs-lookup"><span data-stu-id="8c746-108">The `ToolBar` control's <xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A> property takes an instance of the <xref:System.Windows.Forms.ContextMenu> class as a reference.</span></span> <span data-ttu-id="8c746-109">Wenn Sie diese Art von Schaltfläche auf einer Symbolleiste in Ihrer Anwendung implementieren, sollten Sie sorgfältig auf den Verweis achten, den Sie übergeben, denn die Eigenschaft akzeptiert jedes Objekt, das von der <xref:System.Windows.Forms.Menu>-Klasse erbt.</span><span class="sxs-lookup"><span data-stu-id="8c746-109">Carefully consider the reference you pass when implementing this sort of button on toolbars in your application, as the property will accept any object that inherits from the <xref:System.Windows.Forms.Menu> class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8c746-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8c746-110">In This Section</span></span>  
 [<span data-ttu-id="8c746-111">Übersicht über das ToolBar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="8c746-111">ToolBar Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolbar-control-overview-windows-forms.md)  
 <span data-ttu-id="8c746-112">Stellt die allgemeinen Konzepte des `ToolBar`-Steuerelements vor, mit dem Sie benutzerdefinierte Symbolleisten entwerfen können, mit denen Benutzer arbeiten können.</span><span class="sxs-lookup"><span data-stu-id="8c746-112">Introduces the general concepts of the `ToolBar` control, which allows you to design custom toolbars that your users can work with.</span></span>  
  
 [<span data-ttu-id="8c746-113">Gewusst wie: Hinzufügen von Schaltflächen zu einem ToolBar-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="8c746-113">How to: Add Buttons to a ToolBar Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md)  
 <span data-ttu-id="8c746-114">Beschreibt, wie ein `ToolBar`-Steuerelement hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="8c746-114">Describes how to add buttons to a `ToolBar` control.</span></span>  
  
 [<span data-ttu-id="8c746-115">Gewusst wie: Definieren eines Symbols für eine Symbolleistenschaltfläche</span><span class="sxs-lookup"><span data-stu-id="8c746-115">How to: Define an Icon for a ToolBar Button</span></span>](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)  
 <span data-ttu-id="8c746-116">Beschreibt, wie Symbole auf den Schaltflächen eines `ToolBar`-Steuerelements angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8c746-116">Describes how to display icons within a `ToolBar` control's buttons.</span></span>  
  
 [<span data-ttu-id="8c746-117">Gewusst wie: Auslösen von Menüereignissen für Symbolleistenschaltflächen</span><span class="sxs-lookup"><span data-stu-id="8c746-117">How to: Trigger Menu Events for Toolbar Buttons</span></span>](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)  
 <span data-ttu-id="8c746-118">Bietet Anweisungen zum Schreiben von Code, in dem interpretiert wird, auf welche Schaltfläche ein Benutzer in einem `ToolBar`-Steuerelement geklickt hat.</span><span class="sxs-lookup"><span data-stu-id="8c746-118">Gives directions on writing code to interpret which button the user clicks in a `ToolBar` control.</span></span>  
  
 <span data-ttu-id="8c746-119">Siehe auch [wie: Definieren eines Symbols für eine Symbolleisten-Schaltfläche mithilfe der Designer](how-to-define-an-icon-for-a-toolbar-button-using-the-designer.md), [Vorgehensweise: Hinzufügen von Schaltflächen zu einem ToolBar-Steuerelement mithilfe der Designer](how-to-add-buttons-to-a-toolbar-control-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="8c746-119">Also see [How to: Define an Icon for a ToolBar Button Using the Designer](how-to-define-an-icon-for-a-toolbar-button-using-the-designer.md), [How to: Add Buttons to a ToolBar Control Using the Designer](how-to-add-buttons-to-a-toolbar-control-using-the-designer.md).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8c746-120">Referenz</span><span class="sxs-lookup"><span data-stu-id="8c746-120">Reference</span></span>  
 <span data-ttu-id="8c746-121"><xref:System.Windows.Forms.ToolBar>-Klasse</span><span class="sxs-lookup"><span data-stu-id="8c746-121"><xref:System.Windows.Forms.ToolBar> class</span></span>  
 <span data-ttu-id="8c746-122">Enthält Referenzinformationen zur Klasse und zu ihren Membern.</span><span class="sxs-lookup"><span data-stu-id="8c746-122">Provides reference information on the class and its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8c746-123">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="8c746-123">Related Sections</span></span>  
 [<span data-ttu-id="8c746-124">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="8c746-124">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="8c746-125">Enthält eine vollständige Liste der Windows Forms-Steuerelemente mit Links zu Informationen zur jeweiligen Verwendung.</span><span class="sxs-lookup"><span data-stu-id="8c746-125">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>  
  
 [<span data-ttu-id="8c746-126">ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="8c746-126">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)  
 <span data-ttu-id="8c746-127">Beschreibt Symbolleisten, die Menüs, Steuerelemente und Benutzersteuerelemente in Windows Forms-Anwendungen enthalten können.</span><span class="sxs-lookup"><span data-stu-id="8c746-127">Describes toolbars that can host menus, controls, and user controls in Windows Forms applications.</span></span>

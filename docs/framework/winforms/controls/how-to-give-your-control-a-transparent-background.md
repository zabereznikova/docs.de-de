---
title: 'Vorgehensweise: Verwenden eines transparenten Hintergrunds für ein Steuerelement'
ms.date: 03/30/2017
helpviewer_keywords:
- transparent backgrounds [Windows Forms], custom controls
- custom controls [Windows Forms], transparent background
- transparency [Windows Forms], Windows Forms custom controls
ms.assetid: 32433e63-f4e9-4305-9857-6de3edeb944a
ms.openlocfilehash: 671075973793d7fbf0b70ce77428a0a632305b9c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206095"
---
# <a name="how-to-give-your-control-a-transparent-background"></a><span data-ttu-id="b7c0e-102">Vorgehensweise: Verwenden eines transparenten Hintergrunds für ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b7c0e-102">How to: Give Your Control a Transparent Background</span></span>
<span data-ttu-id="b7c0e-103">In früheren Versionen von .NET Framework wird für Steuerelemente ein Festlegen auf transparente Hintergrundfarben nur dann unterstützt, wenn zunächst die <xref:System.Windows.Forms.Control.SetStyle%2A> -Methode im Konstruktor der Formulare festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="b7c0e-103">In earlier versions of the .NET Framework, controls didn't support setting transparent backcolors without first setting the <xref:System.Windows.Forms.Control.SetStyle%2A> method in the forms's constructor.</span></span> <span data-ttu-id="b7c0e-104">In der aktuellen Framework-Version kann die Hintergrundfarbe für die meisten Steuerelemente zur Entwurfszeit im Fenster <xref:System.Drawing.Color.Transparent%2A> Eigenschaften **oder in Code im Konstruktor des Formulars auf** festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="b7c0e-104">In the current framework version, the backcolor for most controls can be set to <xref:System.Drawing.Color.Transparent%2A> in the **Properties** window at design time, or in code in the form's constructor.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7c0e-105">Windows Forms-Steuerelemente unterstützen keine echte Transparenz.</span><span class="sxs-lookup"><span data-stu-id="b7c0e-105">Windows Forms controls do not support true transparency.</span></span> <span data-ttu-id="b7c0e-106">Der Hintergrund eines transparenten Windows Forms-Steuerelements wird von seinem übergeordneten Element gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="b7c0e-106">The background of a transparent Windows Forms control is painted by its parent.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7c0e-107">Das <xref:System.Windows.Controls.Button> -Steuerelement unterstützt keine transparente Hintergrundfarbe, selbst wenn die <xref:System.Windows.Forms.ButtonBase.BackColor%2A> -Eigenschaft auf <xref:System.Drawing.Color.Transparent%2A>festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b7c0e-107">The <xref:System.Windows.Controls.Button> control doesn't support a transparent backcolor even when the <xref:System.Windows.Forms.ButtonBase.BackColor%2A> property is set to <xref:System.Drawing.Color.Transparent%2A>.</span></span>  
  
### <a name="to-give-your-control-a-transparent-backcolor"></a><span data-ttu-id="b7c0e-108">So weisen Sie dem Steuerelement eine transparente Hintergrundfarbe zu</span><span class="sxs-lookup"><span data-stu-id="b7c0e-108">To give your control a transparent backcolor</span></span>  
  
-   <span data-ttu-id="b7c0e-109">Wählen Sie im Fenster Eigenschaften die <xref:System.Windows.Forms.ButtonBase.BackColor%2A> Eigenschaft, und legen Sie ihn auf</span><span class="sxs-lookup"><span data-stu-id="b7c0e-109">In the Properties window, choose the <xref:System.Windows.Forms.ButtonBase.BackColor%2A> property and set it to</span></span> <xref:System.Drawing.Color.Transparent%2A>  
  
## <a name="see-also"></a><span data-ttu-id="b7c0e-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7c0e-110">See also</span></span>

- <xref:System.Drawing.Color.FromArgb%2A>
- [<span data-ttu-id="b7c0e-111">Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b7c0e-111">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="b7c0e-112">Verwenden von verwalteten Grafikklassen</span><span class="sxs-lookup"><span data-stu-id="b7c0e-112">Using Managed Graphics Classes</span></span>](../advanced/using-managed-graphics-classes.md)
- [<span data-ttu-id="b7c0e-113">Vorgehensweise: Zeichnen deckender und halbtransparenter Linien</span><span class="sxs-lookup"><span data-stu-id="b7c0e-113">How to: Draw Opaque and Semitransparent Lines</span></span>](../advanced/how-to-draw-opaque-and-semitransparent-lines.md)

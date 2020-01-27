---
title: Übersicht über die FontDialog-Komponente
ms.date: 03/30/2017
f1_keywords:
- FontDialog
helpviewer_keywords:
- Font dialog box [Windows Forms], Windows Forms
- Font dialog box
- FontDialog component [Windows Forms], about FontDialog component
ms.assetid: daf46e57-1b4b-4b7a-bad0-b50ca7ba75dc
ms.openlocfilehash: 664b756dc068ca283e4f43edbdd0f3266f5d1142
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745708"
---
# <a name="fontdialog-component-overview-windows-forms"></a><span data-ttu-id="335f0-102">Übersicht über die FontDialog-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="335f0-102">FontDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="335f0-103">Bei der Windows Forms <xref:System.Windows.Forms.FontDialog> Komponente handelt es sich um ein vorkonfiguriertes Dialogfeld, bei dem es sich um das Standard Dialogfeld für Windows- **Schriftart** handelt</span><span class="sxs-lookup"><span data-stu-id="335f0-103">The Windows Forms <xref:System.Windows.Forms.FontDialog> component is a pre-configured dialog box, which is the standard Windows **Font** dialog box used to expose the fonts that are currently installed on the system.</span></span> <span data-ttu-id="335f0-104">Verwenden Sie es in Ihrer Windows-basierten Anwendung als einfache Lösung für die Schriftart Auswahl, anstatt ein eigenes Dialogfeld zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="335f0-104">Use it within your Windows-based application as a simple solution for font selection in lieu of configuring your own dialog box.</span></span>  
  
 <span data-ttu-id="335f0-105">Standardmäßig werden im Dialogfeld Listenfelder für Schriftart, Schriftart Stil und Größe angezeigt. Kontrollkästchen für Effekte wie "Strikeout" und "Unterstreichung" eine Dropdown Liste für das Skript. und ein Beispiel, wie die Schriftart angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="335f0-105">By default, the dialog box shows list boxes for Font, Font style, and Size; check boxes for effects like Strikeout and Underline; a drop-down list for Script; and a sample of how the font will appear.</span></span> <span data-ttu-id="335f0-106">(Das Skript bezieht sich auf verschiedene Zeichen Skripts, die für eine bestimmte Schriftart verfügbar sind, z. b. Hebräisch oder Japanisch.) Um das Dialogfeld Schriftart anzuzeigen, müssen Sie die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="335f0-106">(Script refers to different character scripts that are available for a given font, for example, Hebrew or Japanese.) To display the font dialog box, call the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="335f0-107">Schlüsseleigenschaften</span><span class="sxs-lookup"><span data-stu-id="335f0-107">Key Properties</span></span>  
 <span data-ttu-id="335f0-108">Die Komponente verfügt über eine Reihe von Eigenschaften, die ihre Darstellung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="335f0-108">The component has a number of properties that configure its appearance.</span></span> <span data-ttu-id="335f0-109">Die Eigenschaften, die die Auswahl des Dialog Felds festlegen, sind <xref:System.Windows.Forms.FontDialog.Font%2A> und <xref:System.Windows.Forms.FontDialog.Color%2A>.</span><span class="sxs-lookup"><span data-stu-id="335f0-109">The properties that set the dialog-box selections are <xref:System.Windows.Forms.FontDialog.Font%2A> and <xref:System.Windows.Forms.FontDialog.Color%2A>.</span></span> <span data-ttu-id="335f0-110">Die <xref:System.Windows.Forms.FontDialog.Font%2A>-Eigenschaft legt die Schriftart, den Stil, die Größe, das Skript und die Effekte fest. beispielsweise `Arial, 10pt, style=Italic, Strikeout`.</span><span class="sxs-lookup"><span data-stu-id="335f0-110">The <xref:System.Windows.Forms.FontDialog.Font%2A> property sets the font, style, size, script, and effects; for example, `Arial, 10pt, style=Italic, Strikeout`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="335f0-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="335f0-111">See also</span></span>

- <xref:System.Windows.Forms.FontDialog>
- [<span data-ttu-id="335f0-112">FontDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="335f0-112">FontDialog Component</span></span>](fontdialog-component-windows-forms.md)

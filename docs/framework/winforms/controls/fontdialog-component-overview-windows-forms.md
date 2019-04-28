---
title: Übersicht über die FontDialog-Komponente (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- FontDialog
helpviewer_keywords:
- Font dialog box [Windows Forms], Windows Forms
- Font dialog box
- FontDialog component [Windows Forms], about FontDialog component
ms.assetid: daf46e57-1b4b-4b7a-bad0-b50ca7ba75dc
ms.openlocfilehash: 7f140807bf4b42e530302190042e729c59248e7f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789310"
---
# <a name="fontdialog-component-overview-windows-forms"></a><span data-ttu-id="63084-102">Übersicht über die FontDialog-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="63084-102">FontDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="63084-103">Die Windows-Formulare <xref:System.Windows.Forms.FontDialog> Komponente ist ein vorkonfiguriertes Dialogfeld, wird die standardmäßige Windows **Schriftart** Dialogfeld verwendet, um die Schriftarten verfügbar zu machen, die derzeit auf dem System installiert sind.</span><span class="sxs-lookup"><span data-stu-id="63084-103">The Windows Forms <xref:System.Windows.Forms.FontDialog> component is a pre-configured dialog box, which is the standard Windows **Font** dialog box used to expose the fonts that are currently installed on the system.</span></span> <span data-ttu-id="63084-104">Verwenden Sie es in Ihrer Windows-basierten Anwendung als einfache Lösung für die Schriftartauswahl, anstatt ein eigenes Dialogfeld zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="63084-104">Use it within your Windows-based application as a simple solution for font selection in lieu of configuring your own dialog box.</span></span>  
  
 <span data-ttu-id="63084-105">Standardmäßig zeigt das Dialogfeld Listenfelder für Schriftart, Schriftschnitt und Größe Aktivieren Sie die Kontrollkästchen für die Effekte wie durchgestrichen und unterstrichen; ein Dropdown-Liste für Skripts; und ein Beispiel, wie die Schriftart angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="63084-105">By default, the dialog box shows list boxes for Font, Font style, and Size; check boxes for effects like Strikeout and Underline; a drop-down list for Script; and a sample of how the font will appear.</span></span> <span data-ttu-id="63084-106">(Skript bezieht sich auf verschiedene Zeichensätze-Skripts, die für eine angegebene Schriftart, verfügbar sind z. B. Hebräisch oder Japanisch.) Um das Dialogfeld "Schriftart" anzuzeigen, rufen die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="63084-106">(Script refers to different character scripts that are available for a given font, for example, Hebrew or Japanese.) To display the font dialog box, call the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="63084-107">Schlüsseleigenschaften</span><span class="sxs-lookup"><span data-stu-id="63084-107">Key Properties</span></span>  
 <span data-ttu-id="63084-108">Die Komponente muss es sich um eine Reihe von Eigenschaften, die die Darstellung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="63084-108">The component has a number of properties that configure its appearance.</span></span> <span data-ttu-id="63084-109">Die Eigenschaften, die im Dialogfeld Optionen festgelegt, werden <xref:System.Windows.Forms.FontDialog.Font%2A> und <xref:System.Windows.Forms.FontDialog.Color%2A>.</span><span class="sxs-lookup"><span data-stu-id="63084-109">The properties that set the dialog-box selections are <xref:System.Windows.Forms.FontDialog.Font%2A> and <xref:System.Windows.Forms.FontDialog.Color%2A>.</span></span> <span data-ttu-id="63084-110">Die <xref:System.Windows.Forms.FontDialog.Font%2A> Eigenschaft legt fest, die Schriftart, Stil, Größe, Skripts und Effekte; z. B. `Arial, 10pt, style=Italic, Strikeout`.</span><span class="sxs-lookup"><span data-stu-id="63084-110">The <xref:System.Windows.Forms.FontDialog.Font%2A> property sets the font, style, size, script, and effects; for example, `Arial, 10pt, style=Italic, Strikeout`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63084-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63084-111">See also</span></span>

- <xref:System.Windows.Forms.FontDialog>
- [<span data-ttu-id="63084-112">FontDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="63084-112">FontDialog Component</span></span>](fontdialog-component-windows-forms.md)

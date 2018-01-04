---
title: "Übersicht über die FontDialog-Komponente (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: FontDialog
helpviewer_keywords:
- Font dialog box [Windows Forms], Windows Forms
- Font dialog box
- FontDialog component [Windows Forms], about FontDialog component
ms.assetid: daf46e57-1b4b-4b7a-bad0-b50ca7ba75dc
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b9e3018d024254adb249860f7736399e7f2da72a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="fontdialog-component-overview-windows-forms"></a><span data-ttu-id="b05a9-102">Übersicht über die FontDialog-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="b05a9-102">FontDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="b05a9-103">Windows Forms <xref:System.Windows.Forms.FontDialog> Komponente ist ein vorkonfiguriertes Dialogfeld, das Windows-Standarddialogfeld also **Schriftart** Dialogfeld verwendet, um die Schriftarten verfügbar machen, die zurzeit auf dem System installiert sind.</span><span class="sxs-lookup"><span data-stu-id="b05a9-103">The Windows Forms <xref:System.Windows.Forms.FontDialog> component is a pre-configured dialog box, which is the standard Windows **Font** dialog box used to expose the fonts that are currently installed on the system.</span></span> <span data-ttu-id="b05a9-104">Verwenden Sie es in Ihrer Windows basierenden Anwendung als einfache Lösung für eine Schriftartauswahl anstatt ein eigenes Dialogfeld zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b05a9-104">Use it within your Windows-based application as a simple solution for font selection in lieu of configuring your own dialog box.</span></span>  
  
 <span data-ttu-id="b05a9-105">Standardmäßig zeigt das Dialogfeld Listenfelder für Schriftart, Schriftschnitt und-Grad; Kontrollkästchen für Effekte wie durchgestrichen und unterstrichen; eine Dropdown-Liste für Skripts; und ein Beispiel für die Anzeige der Schriftartformats.</span><span class="sxs-lookup"><span data-stu-id="b05a9-105">By default, the dialog box shows list boxes for Font, Font style, and Size; check boxes for effects like Strikeout and Underline; a drop-down list for Script; and a sample of how the font will appear.</span></span> <span data-ttu-id="b05a9-106">(Skript bezieht sich auf verschiedene Zeichenskripts, die für eine angegebene Schriftart verfügbar sind z. B. Hebräisch oder Japanisch.) Um das Dialogfeld "Schriftart" anzuzeigen, rufen die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="b05a9-106">(Script refers to different character scripts that are available for a given font, for example, Hebrew or Japanese.) To display the font dialog box, call the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="b05a9-107">Wichtige Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b05a9-107">Key Properties</span></span>  
 <span data-ttu-id="b05a9-108">Die Komponente muss es sich um eine Reihe von Eigenschaften, die ihre Darstellung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b05a9-108">The component has a number of properties that configure its appearance.</span></span> <span data-ttu-id="b05a9-109">Die Eigenschaften, die im Dialogfeld Optionen festgelegt, werden <xref:System.Windows.Forms.FontDialog.Font%2A> und <xref:System.Windows.Forms.FontDialog.Color%2A>.</span><span class="sxs-lookup"><span data-stu-id="b05a9-109">The properties that set the dialog-box selections are <xref:System.Windows.Forms.FontDialog.Font%2A> and <xref:System.Windows.Forms.FontDialog.Color%2A>.</span></span> <span data-ttu-id="b05a9-110">Die <xref:System.Windows.Forms.FontDialog.Font%2A> Eigenschaft legt fest, die Schriftart, Stil, Größe, Skript und Effekte; z. B. `Arial, 10pt, style=Italic, Strikeout`.</span><span class="sxs-lookup"><span data-stu-id="b05a9-110">The <xref:System.Windows.Forms.FontDialog.Font%2A> property sets the font, style, size, script, and effects; for example, `Arial, 10pt, style=Italic, Strikeout`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b05a9-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b05a9-111">See Also</span></span>  
 <xref:System.Windows.Forms.FontDialog>  
 [<span data-ttu-id="b05a9-112">FontDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="b05a9-112">FontDialog Component</span></span>](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md)

---
title: Hilfesysteme in Windows Forms-Anwendungen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Help [Windows Forms], adding to Windows applications
- Windows applications [Windows Forms], providing Help systems
- What's This? Help
- Help [Windows Forms], Windows Forms
- HelpProvider component [Windows Forms], providing Help in Windows applications
ms.assetid: 2a96a278-432c-41fc-9e3c-5bfedf5e1267
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 45d3385d008f823050f213252fdc2e1851cf422b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="help-systems-in-windows-forms-applications"></a><span data-ttu-id="b8983-102">Hilfesysteme in Windows Forms-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="b8983-102">Help Systems in Windows Forms Applications</span></span>
<span data-ttu-id="b8983-103">Einer der wichtigsten Zusatzfunktionen Sie, wie ein Entwickler von Anwendungen, können Ihre Benutzer mit Dokumentationselement ist ein zuständigen Hilfesystem.</span><span class="sxs-lookup"><span data-stu-id="b8983-103">One of the most important courtesies you, as a developer of applications, can furnish your users with is a competent Help system.</span></span> <span data-ttu-id="b8983-104">Dies ist, in dem sie aktivieren wird, wenn sie verwechselt oder disoriented werden.</span><span class="sxs-lookup"><span data-stu-id="b8983-104">This is where they will turn when they become confused or disoriented.</span></span> <span data-ttu-id="b8983-105">Ein Hilfesystem in einer Windows-basierten Anwendung erfolgt einfach mithilfe der [HelpProvider-Komponente](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="b8983-105">Providing a Help system in a Windows-based application is easily done by using the [HelpProvider Component](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md).</span></span>  
  
## <a name="different-types-of-help"></a><span data-ttu-id="b8983-106">Verschiedene Arten von Hilfe</span><span class="sxs-lookup"><span data-stu-id="b8983-106">Different Types of Help</span></span>  
 <span data-ttu-id="b8983-107">Die <xref:System.Windows.Forms.HelpProvider>-Komponente von Windows Forms wird verwendet, um eine HTML Help 1.x-Hilfedatei (entweder eine mit HTML Help Workshop erstellte CHM-Datei oder eine HTM-Datei) mit einer Windows-basierten Anwendung zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="b8983-107">The Windows Forms <xref:System.Windows.Forms.HelpProvider> component is used to associate an HTML Help 1.x Help file (either a .chm file, produced with the HTML Help Workshop, or an .htm file) with your Windows-based application.</span></span> <span data-ttu-id="b8983-108">Die <xref:System.Windows.Forms.HelpProvider> Komponente kann verwendet werden, um kontextbezogene Hilfe für Steuerelemente in Windows Forms oder bestimmte Steuerelemente bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b8983-108">The <xref:System.Windows.Forms.HelpProvider> component can be used to provide context-sensitive Help for controls on Windows Forms or specific controls.</span></span> <span data-ttu-id="b8983-109">Darüber hinaus die <xref:System.Windows.Forms.HelpProvider> Komponente eine Hilfedatei zu bestimmten Bereichen, z. B. die Hauptseite der eine Tabelle mit Inhalt, einen Index oder eine Suchfunktion öffnen kann.</span><span class="sxs-lookup"><span data-stu-id="b8983-109">Additionally, the <xref:System.Windows.Forms.HelpProvider> component can open a Help file to specific areas, such as the main page of a table of contents, an index, or a search function.</span></span> <span data-ttu-id="b8983-110">Allgemeine Informationen zu den <xref:System.Windows.Forms.HelpProvider> Komponente finden Sie unter [Übersicht über die HelpProvider-Komponente](../../../../docs/framework/winforms/controls/helpprovider-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="b8983-110">For general information about the <xref:System.Windows.Forms.HelpProvider> component, see [HelpProvider Component Overview](../../../../docs/framework/winforms/controls/helpprovider-component-overview-windows-forms.md).</span></span> <span data-ttu-id="b8983-111">Informationen zum Verwenden der <xref:System.Windows.Forms.HelpProvider> Komponente zum Anzeigen der Hilfe in Windows Forms finden Sie unter [wie: Anzeigen kontextbezogener Hilfe](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md).</span><span class="sxs-lookup"><span data-stu-id="b8983-111">For information on how to use the <xref:System.Windows.Forms.HelpProvider> component to show pop-up Help on Windows Forms, see [How to: Display Pop-up Help](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md).</span></span> <span data-ttu-id="b8983-112">Weitere Informationen zum Verwenden der <xref:System.Windows.Forms.ToolTip> Komponente zum Anzeigen der Hilfe für das Steuerelement spezifische finden Sie unter [Steuerelement können mithilfe von QuickInfos](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md).</span><span class="sxs-lookup"><span data-stu-id="b8983-112">For information on using the <xref:System.Windows.Forms.ToolTip> component to show control-specific Help, see [Control Help Using ToolTips](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md).</span></span>  
  
 <span data-ttu-id="b8983-113">Sie können HTML Help 1.x-Dateien mit HTML Help Workshop generieren.</span><span class="sxs-lookup"><span data-stu-id="b8983-113">You can generate HTML Help 1.x files with the HTML Help Workshop.</span></span> <span data-ttu-id="b8983-114">Weitere Informationen zur HTML-Hilfe finden Sie unter "HTML Help Workshop" oder andere "HTML" Hilfethemen im MSDN.</span><span class="sxs-lookup"><span data-stu-id="b8983-114">For more information on HTML Help, see the "HTML Help Workshop" or the other "HTML Help" topics in MSDN.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8983-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8983-115">See Also</span></span>  
 [<span data-ttu-id="b8983-116">Integrieren von Benutzerhilfe in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b8983-116">Integrating User Help in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)  
 [<span data-ttu-id="b8983-117">HelpProvider-Komponente</span><span class="sxs-lookup"><span data-stu-id="b8983-117">HelpProvider Component</span></span>](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md)  
 [<span data-ttu-id="b8983-118">ToolTip-Komponente</span><span class="sxs-lookup"><span data-stu-id="b8983-118">ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)  
 [<span data-ttu-id="b8983-119">Übersicht über Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b8983-119">Windows Forms Overview</span></span>](../../../../docs/framework/winforms/windows-forms-overview.md)  
 [<span data-ttu-id="b8983-120">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b8983-120">Windows Forms</span></span>](../../../../docs/framework/winforms/index.md)

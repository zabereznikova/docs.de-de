---
title: "Codierung und die Globalisierung von Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView control [Windows Forms], lack of Unicode support
- DateTimePicker control [Windows Forms], lack of Unicode support
- TrackBar control [Windows Forms], lack of Unicode support
- ImageList component [Windows Forms], lack of Unicode support
- Unicode [Windows Forms]
- ToolBar control [Windows Forms], lack of Unicode support
- international applications [Windows Forms], character display
- StatusBar control [Windows Forms], lack of Unicode support
- MonthCalendar control [Windows Forms], lack of Unicode support
- international characters
- TabControl control [Windows Forms], lack of Unicode support
- Windows Forms, encoding
- TreeView control [Windows Forms], lack of Unicode support
- ProgressBar control [Windows Forms], Unicode-enabled forms
- localization [Windows Forms], character sets
- globalization [Windows Forms], character sets
ms.assetid: 22e8965d-a712-42b3-8167-3ee346bd70f9
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f25f4f7206b68e961f3c09a488af643ad5d0a4fd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="encoding-and-windows-forms-globalization"></a><span data-ttu-id="52fd6-102">Codierung und die Globalisierung von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="52fd6-102">Encoding and Windows Forms Globalization</span></span>
<span data-ttu-id="52fd6-103">Windows Forms-Anwendungen sind vollständig Unicode-aktiviert, was bedeutet, dass jedes Zeichen durch eine eindeutige Nummer, unabhängig von Plattform, Programm oder Sprache, dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="52fd6-103">Windows Forms applications are entirely Unicode-enabled, meaning that each character is represented by a unique number, no matter what the platform, program, or language.</span></span> <span data-ttu-id="52fd6-104">Weitere Informationen zu Unicode finden Sie unter der [Website des Unicode Consortium](http://www.unicode.org).</span><span class="sxs-lookup"><span data-stu-id="52fd6-104">For more information about Unicode, see the [Unicode consortium Web site](http://www.unicode.org).</span></span>  
  
## <a name="benefits-of-unicode"></a><span data-ttu-id="52fd6-105">Vorteile von Unicode</span><span class="sxs-lookup"><span data-stu-id="52fd6-105">Benefits of Unicode</span></span>  
 <span data-ttu-id="52fd6-106">Zu den Vorteilen von Unicode-aktivierten Formularen zählt die Möglichkeit, mit Skripts zu arbeiten, die nur aus Unicode bestehen, z. B. Hindi.</span><span class="sxs-lookup"><span data-stu-id="52fd6-106">The benefits of Unicode-enabled forms include the ability to work with scripts that are Unicode-only, such as Hindi.</span></span> <span data-ttu-id="52fd6-107">Außerdem können Sie in einem Formular mehrere Sprachen verwenden.</span><span class="sxs-lookup"><span data-stu-id="52fd6-107">In addition, you can use multiple languages on a single form.</span></span> <span data-ttu-id="52fd6-108">In Unicode sind alle Zeichen zwei Byte lang. Doppelbyte-Zeichen können also ohne besonderen Aufwand dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="52fd6-108">In Unicode, all characters are two bytes long, so no special effort is needed to represent double-byte characters.</span></span> <span data-ttu-id="52fd6-109">Sie können zudem einen einzigen Codesatz schreiben, der auf allen Plattformen funktioniert.</span><span class="sxs-lookup"><span data-stu-id="52fd6-109">You can also write a single set of code that will work on all platforms.</span></span> <span data-ttu-id="52fd6-110">Dies ist eine Änderung gegenüber früheren Versionen von [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], die unterschiedlichen Code für unterschiedliche Plattformen (z. B. Windows NT und [!INCLUDE[win98](../../../../includes/win98-md.md)]) voraussetzten.</span><span class="sxs-lookup"><span data-stu-id="52fd6-110">This is a change from previous versions of [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], in which you had to write different code for different platforms, such as Windows NT and [!INCLUDE[win98](../../../../includes/win98-md.md)].</span></span>  
  
 <span data-ttu-id="52fd6-111">Bestimmte Steuerelemente unterstützen jedoch Unicode in [!INCLUDE[win98](../../../../includes/win98-md.md)] und Windows Millennium Edition nicht.</span><span class="sxs-lookup"><span data-stu-id="52fd6-111">However, certain controls do not support Unicode in [!INCLUDE[win98](../../../../includes/win98-md.md)] and Windows Millennium Edition.</span></span> <span data-ttu-id="52fd6-112">Diese Steuerelemente, die allesamt dem allgemeinen Steuerelement untergeordnet sind, verarbeiten Daten mit den Windows-Codepages als [!INCLUDE[vcpransi](../../../../includes/vcpransi-md.md)].</span><span class="sxs-lookup"><span data-stu-id="52fd6-112">These controls, all of which inherit from the common control, will process data with the Windows code pages, as [!INCLUDE[vcpransi](../../../../includes/vcpransi-md.md)].</span></span> <span data-ttu-id="52fd6-113">Diese Steuerelemente sind: <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.DateTimePicker>, <xref:System.Windows.Forms.MonthCalendar>, <xref:System.Windows.Forms.TrackBar>, <xref:System.Windows.Forms.ProgressBar>, <xref:System.Windows.Forms.ImageList>, <xref:System.Windows.Forms.ToolBar> und <xref:System.Windows.Forms.StatusBar>.</span><span class="sxs-lookup"><span data-stu-id="52fd6-113">These controls are: <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.DateTimePicker>, <xref:System.Windows.Forms.MonthCalendar>, <xref:System.Windows.Forms.TrackBar>, <xref:System.Windows.Forms.ProgressBar>, <xref:System.Windows.Forms.ImageList>, <xref:System.Windows.Forms.ToolBar>, and <xref:System.Windows.Forms.StatusBar>.</span></span> <span data-ttu-id="52fd6-114">Sie können daher in diesen Steuerelementen auf den aufgeführten Plattformen keine Unicode-Daten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="52fd6-114">As a result, you cannot display Unicode data in these controls on the listed platforms.</span></span> <span data-ttu-id="52fd6-115">Sie können z. B. japanische Zeichen nicht auf einem englischen [!INCLUDE[win98](../../../../includes/win98-md.md)]-Betriebssystem anzeigen.</span><span class="sxs-lookup"><span data-stu-id="52fd6-115">For example, you cannot display Japanese characters on an English [!INCLUDE[win98](../../../../includes/win98-md.md)] operating system.</span></span>  
  
 <span data-ttu-id="52fd6-116">Unicode-kompatible Alternativen zu den <xref:System.Windows.Forms.ToolBar>- und <xref:System.Windows.Forms.StatusBar>-Steuerelementen stellen die <xref:System.Windows.Forms.ToolStrip>- und <xref:System.Windows.Forms.StatusStrip>-Steuerelemente dar, die diese älteren Steuerelemente ersetzen.</span><span class="sxs-lookup"><span data-stu-id="52fd6-116">For Unicode-aware alternatives to the <xref:System.Windows.Forms.ToolBar> and <xref:System.Windows.Forms.StatusBar> controls, use the <xref:System.Windows.Forms.ToolStrip> and <xref:System.Windows.Forms.StatusStrip> controls, which replace these older controls.</span></span> <span data-ttu-id="52fd6-117">Um ein ähnliches Erscheinungsbild der visuellen Elemente in der Anwendung zu gewährleisten, verwenden Sie anstelle des <xref:System.Windows.Forms.MainMenu>-Steuerelements das <xref:System.Windows.Forms.MenuStrip>-Steuerelement zum Rendern von Menüs.</span><span class="sxs-lookup"><span data-stu-id="52fd6-117">To maintain a similar look and feel between visual elements in your application, use the <xref:System.Windows.Forms.MenuStrip> control for rendering menus instead of <xref:System.Windows.Forms.MainMenu>.</span></span> <span data-ttu-id="52fd6-118">Wie <xref:System.Windows.Forms.ToolStrip> und <xref:System.Windows.Forms.StatusStrip> kann auch <xref:System.Windows.Forms.MenuStrip> Unicode-Zeichen verarbeiten und anzeigen.</span><span class="sxs-lookup"><span data-stu-id="52fd6-118">Like <xref:System.Windows.Forms.ToolStrip> and <xref:System.Windows.Forms.StatusStrip>, <xref:System.Windows.Forms.MenuStrip> can also process and display Unicode characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52fd6-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52fd6-119">See Also</span></span>  
 [<span data-ttu-id="52fd6-120">Globalisieren von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="52fd6-120">Globalizing Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/globalizing-windows-forms.md)

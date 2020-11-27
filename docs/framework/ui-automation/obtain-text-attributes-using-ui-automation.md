---
title: Abrufen von Textattributen mithilfe der Benutzeroberflächenautomatisierung
description: Erfahren Sie, wie Sie mithilfe der Benutzeroberflächen Automatisierung Text Attribute erhalten. Ein Codebeispiel, in dem Text Attribute aus einem Textbereich abgerufen werden, finden Sie unter.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting, text attributes
- UI Automation, getting text attributes
- text attributes, getting
ms.assetid: fdefc6c3-b836-4cfe-8dec-1484bfdc5551
ms.openlocfilehash: 2c59c42e2ba6b67381ab9f70da51bd51ad4330c9
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96282326"
---
# <a name="obtain-text-attributes-using-ui-automation"></a><span data-ttu-id="cfc3d-104">Abrufen von Textattributen mithilfe der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="cfc3d-104">Obtain Text Attributes Using UI Automation</span></span>

> [!NOTE]
> <span data-ttu-id="cfc3d-105">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="cfc3d-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="cfc3d-106">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="cfc3d-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="cfc3d-107">In diesem Thema wird gezeigt, wie mit [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Textattribute aus einem Textbereich abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="cfc3d-107">This topic shows how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to obtain text attributes from a text range.</span></span> <span data-ttu-id="cfc3d-108">Ein Textbereich kann der aktuellen Position der Einfügemarke (oder der degenerierten Auswahl) in einem Dokument, einer zusammenhängenden Auswahl von Text, einer Reihe nicht zusammenhängender ausgewählter Textstellen oder dem gesamten Text eines Dokuments entsprechen.</span><span class="sxs-lookup"><span data-stu-id="cfc3d-108">A text range can correspond to the current location of the caret (or degenerate selection) within a document, a contiguous selection of text, a collection of disjoint text selections, or the entire textual content of a document.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfc3d-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cfc3d-109">Example</span></span>  

 <span data-ttu-id="cfc3d-110">Im folgenden Codebeispiel wird veranschaulicht, wie <xref:System.Windows.Automation.TextPattern.FontNameAttribute> aus einem Textbereich abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="cfc3d-110">The following code example demonstrates how to obtain the <xref:System.Windows.Automation.TextPattern.FontNameAttribute> from a text range.</span></span>  
  
 [!code-csharp[UIATextPattern_snip#StartTarget](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#starttarget)]
 [!code-vb[UIATextPattern_snip#StartTarget](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#starttarget)]  
[!code-csharp[UIATextPattern_snip#GetTextElement](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#gettextelement)]
[!code-vb[UIATextPattern_snip#GetTextElement](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#gettextelement)]  
[!code-csharp[UIATextPattern_snip#FontName](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#fontname)]
[!code-vb[UIATextPattern_snip#FontName](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#fontname)]  
  
 <span data-ttu-id="cfc3d-111">Das <xref:System.Windows.Automation.TextPattern> -Steuerelementmuster unterstützt zusammen mit der <xref:System.Windows.Automation.Text.TextPatternRange> -Klasse grundlegende Textattribute, Eigenschaften und Methoden.</span><span class="sxs-lookup"><span data-stu-id="cfc3d-111">The <xref:System.Windows.Automation.TextPattern> control pattern, in tandem with the <xref:System.Windows.Automation.Text.TextPatternRange> class, supports basic text attributes, properties, and methods.</span></span> <span data-ttu-id="cfc3d-112">Für steuerelementspezifische Funktionalität, die von <xref:System.Windows.Automation.TextPattern> oder <xref:System.Windows.Automation.Text.TextPatternRange> nicht unterstützt wird, stellt die <xref:System.Windows.Automation.AutomationElement>-Klasse Methoden für einen Benutzeroberflächenautomatisierungs-Client zur Verfügung, um auf das entsprechende systemeigene Objektmodell zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="cfc3d-112">For control-specific functionality that is not supported by <xref:System.Windows.Automation.TextPattern> or <xref:System.Windows.Automation.Text.TextPatternRange> the <xref:System.Windows.Automation.AutomationElement>, class provides methods for a UI Automation client to access the corresponding native object model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfc3d-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cfc3d-113">See also</span></span>

- [<span data-ttu-id="cfc3d-114">Übersicht über TextPattern für die Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="cfc3d-114">UI Automation TextPattern Overview</span></span>](ui-automation-textpattern-overview.md)
- [<span data-ttu-id="cfc3d-115">Hinzufügen von Inhalt in einem Textfeld mithilfe von Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="cfc3d-115">Add Content to a Text Box Using UI Automation</span></span>](add-content-to-a-text-box-using-ui-automation.md)
- [<span data-ttu-id="cfc3d-116">Suchen und Hervorheben von Text durch Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="cfc3d-116">Find and Highlight Text Using UI Automation</span></span>](find-and-highlight-text-using-ui-automation.md)
- [<span data-ttu-id="cfc3d-117">Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="cfc3d-117">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="cfc3d-118">Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients</span><span class="sxs-lookup"><span data-stu-id="cfc3d-118">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="cfc3d-119">Abrufen verschiedener Textattributdetails mithilfe der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="cfc3d-119">Obtain Mixed Text Attribute Details Using UI Automation</span></span>](obtain-mixed-text-attribute-details-using-ui-automation.md)

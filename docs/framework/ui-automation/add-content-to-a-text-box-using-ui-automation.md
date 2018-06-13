---
title: Hinzufügen von Inhalt in einem Textfeld mithilfe von Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adding content to text boxes
- text boxes, adding content
- UI Automation, adding content to text boxes
ms.assetid: 8bdd1a73-1ecb-4a05-a891-a7827ebb767f
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 4b3179333119d1ff516c6176298fa25514a9ba66
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33409775"
---
# <a name="add-content-to-a-text-box-using-ui-automation"></a><span data-ttu-id="d0009-102">Hinzufügen von Inhalt in einem Textfeld mithilfe von Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="d0009-102">Add Content to a Text Box Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="d0009-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="d0009-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="d0009-104">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="d0009-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="d0009-105">Dieses Thema enthält Beispielcode, der veranschaulicht [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] zum Einfügen von Text in einem einzeiligen Textfeld.</span><span class="sxs-lookup"><span data-stu-id="d0009-105">This topic contains example code that demonstrates how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to insert text into a single-line text box.</span></span> <span data-ttu-id="d0009-106">Eine alternative Methode für mehrzeilige und rich-Text-Steuerelemente bereitgestellt wird, in dem [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ist nicht anwendbar.</span><span class="sxs-lookup"><span data-stu-id="d0009-106">An alternate method is provided for multi-line and rich text controls where [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] is not applicable.</span></span> <span data-ttu-id="d0009-107">Für Vergleichszwecke können veranschaulicht das Beispiel auch Win32-Methoden verwenden, um die gleichen Ergebnisse zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="d0009-107">For comparison purposes, the example also demonstrates how to use Win32 methods to accomplish the same results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0009-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d0009-108">Example</span></span>  
 <span data-ttu-id="d0009-109">Im folgenden Beispiel Durchlaufen einer Sequenz von Textsteuerelementen eine Zielanwendung.</span><span class="sxs-lookup"><span data-stu-id="d0009-109">The following example steps through a sequence of text controls in a target application.</span></span> <span data-ttu-id="d0009-110">Jedes Textfeld-Steuerelement wird daraufhin überprüft, ob eine <xref:System.Windows.Automation.ValuePattern> -Objekt abgerufen werden kann, mithilfe der <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="d0009-110">Each text control is tested to see if a <xref:System.Windows.Automation.ValuePattern> object can be obtained from it using the <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> method.</span></span> <span data-ttu-id="d0009-111">Wenn im Textsteuerelement ein unterstützt <xref:System.Windows.Automation.ValuePattern>die <xref:System.Windows.Automation.ValuePattern.SetValue%2A> Methode wird verwendet, um eine benutzerdefinierte Zeichenfolge in das Textfeld-Steuerelement einfügen.</span><span class="sxs-lookup"><span data-stu-id="d0009-111">If the text control does support <xref:System.Windows.Automation.ValuePattern>, the <xref:System.Windows.Automation.ValuePattern.SetValue%2A> method is used to insert a user-defined string into the text control.</span></span> <span data-ttu-id="d0009-112">Andernfalls die <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> Methode wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="d0009-112">Otherwise, the <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> method is used.</span></span>  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## <a name="see-also"></a><span data-ttu-id="d0009-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0009-113">See Also</span></span>  
 [<span data-ttu-id="d0009-114">Einfügen von TextPattern-Text (Beispiel)</span><span class="sxs-lookup"><span data-stu-id="d0009-114">TextPattern Insert Text Sample</span></span>](http://msdn.microsoft.com/library/67353f93-7ee2-42f2-ab76-5c078cf6ca16)

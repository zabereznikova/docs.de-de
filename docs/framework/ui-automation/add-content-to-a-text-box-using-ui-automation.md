---
title: Hinzufügen von Inhalt in einem Textfeld mithilfe von Benutzeroberflächenautomatisierung
description: Ein Beispiel zum Hinzufügen von Inhalt zu einem einzeiligen Textfeld finden Sie unter Verwenden der Microsoft-Benutzeroberflächen Automatisierung in .net.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adding content to text boxes
- text boxes, adding content
- UI Automation, adding content to text boxes
ms.assetid: 8bdd1a73-1ecb-4a05-a891-a7827ebb767f
ms.openlocfilehash: 9108cb586700474f7f855751000944212a3cef29
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96235726"
---
# <a name="add-content-to-a-text-box-using-ui-automation"></a><span data-ttu-id="dfb02-103">Hinzufügen von Inhalt in einem Textfeld mithilfe von Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="dfb02-103">Add Content to a Text Box Using UI Automation</span></span>

> [!NOTE]
> <span data-ttu-id="dfb02-104">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="dfb02-104">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="dfb02-105">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="dfb02-105">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="dfb02-106">Dieses Thema enthält Beispielcode, der veranschaulicht, wie verwendet wird, [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] um Text in ein einzeilige Textfeld einzufügen.</span><span class="sxs-lookup"><span data-stu-id="dfb02-106">This topic contains example code that demonstrates how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to insert text into a single-line text box.</span></span> <span data-ttu-id="dfb02-107">Eine alternative Methode wird für mehrzeilige und Rich-Text-Steuerelemente bereitgestellt, bei denen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] nicht anwendbar ist.</span><span class="sxs-lookup"><span data-stu-id="dfb02-107">An alternate method is provided for multi-line and rich text controls where [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] is not applicable.</span></span> <span data-ttu-id="dfb02-108">Zu Vergleichszwecken veranschaulicht das Beispiel auch, wie Win32-Methoden verwendet werden, um die gleichen Ergebnisse zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="dfb02-108">For comparison purposes, the example also demonstrates how to use Win32 methods to accomplish the same results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dfb02-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dfb02-109">Example</span></span>  

 <span data-ttu-id="dfb02-110">Im folgenden Beispiel wird eine Sequenz von Text Steuerelementen in einer Zielanwendung durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="dfb02-110">The following example steps through a sequence of text controls in a target application.</span></span> <span data-ttu-id="dfb02-111">Jedes Text Steuerelement wird getestet, um zu überprüfen, ob ein- <xref:System.Windows.Automation.ValuePattern> Objekt mithilfe der-Methode abgerufen werden kann <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> .</span><span class="sxs-lookup"><span data-stu-id="dfb02-111">Each text control is tested to see if a <xref:System.Windows.Automation.ValuePattern> object can be obtained from it using the <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> method.</span></span> <span data-ttu-id="dfb02-112">Wenn das Text Steuerelement unterstützt <xref:System.Windows.Automation.ValuePattern> , <xref:System.Windows.Automation.ValuePattern.SetValue%2A> wird die-Methode verwendet, um eine benutzerdefinierte Zeichenfolge in das Text Steuerelement einzufügen.</span><span class="sxs-lookup"><span data-stu-id="dfb02-112">If the text control does support <xref:System.Windows.Automation.ValuePattern>, the <xref:System.Windows.Automation.ValuePattern.SetValue%2A> method is used to insert a user-defined string into the text control.</span></span> <span data-ttu-id="dfb02-113">Andernfalls wird die- <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="dfb02-113">Otherwise, the <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> method is used.</span></span>  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## <a name="see-also"></a><span data-ttu-id="dfb02-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dfb02-114">See also</span></span>

- <span data-ttu-id="dfb02-115">[TextPattern-Textbeispiel einfügen](/previous-versions/dotnet/netframework-3.5/ms771478(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="dfb02-115">[TextPattern Insert Text Sample](/previous-versions/dotnet/netframework-3.5/ms771478(v=vs.90))</span></span>

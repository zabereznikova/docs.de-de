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
ms.openlocfilehash: fdc52d0b94ce500b6560b60419d409f5cbd73b55
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932648"
---
# <a name="add-content-to-a-text-box-using-ui-automation"></a><span data-ttu-id="07d54-102">Hinzufügen von Inhalt in einem Textfeld mithilfe von Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="07d54-102">Add Content to a Text Box Using UI Automation</span></span>
> [!NOTE]
> <span data-ttu-id="07d54-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="07d54-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="07d54-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden [Sie unter Windows Automation-API: Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746)der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="07d54-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="07d54-105">Dieses Thema enthält Beispielcode, der veranschaulicht, wie [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] verwendet wird, um Text in ein einzeilige Textfeld einzufügen.</span><span class="sxs-lookup"><span data-stu-id="07d54-105">This topic contains example code that demonstrates how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to insert text into a single-line text box.</span></span> <span data-ttu-id="07d54-106">Eine alternative Methode wird für mehrzeilige und Rich-Text-Steuer [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Elemente bereitgestellt, bei denen nicht anwendbar ist.</span><span class="sxs-lookup"><span data-stu-id="07d54-106">An alternate method is provided for multi-line and rich text controls where [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] is not applicable.</span></span> <span data-ttu-id="07d54-107">Zu Vergleichszwecken veranschaulicht das Beispiel auch, wie Win32-Methoden verwendet werden, um die gleichen Ergebnisse zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="07d54-107">For comparison purposes, the example also demonstrates how to use Win32 methods to accomplish the same results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07d54-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07d54-108">Example</span></span>  
 <span data-ttu-id="07d54-109">Im folgenden Beispiel wird eine Sequenz von Text Steuerelementen in einer Zielanwendung durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="07d54-109">The following example steps through a sequence of text controls in a target application.</span></span> <span data-ttu-id="07d54-110">Jedes Text Steuerelement wird getestet, um zu <xref:System.Windows.Automation.ValuePattern> überprüfen, ob ein-Objekt mithilfe <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> der-Methode abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="07d54-110">Each text control is tested to see if a <xref:System.Windows.Automation.ValuePattern> object can be obtained from it using the <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> method.</span></span> <span data-ttu-id="07d54-111">Wenn das Text Steuerelement unter <xref:System.Windows.Automation.ValuePattern>stützt, <xref:System.Windows.Automation.ValuePattern.SetValue%2A> wird die-Methode verwendet, um eine benutzerdefinierte Zeichenfolge in das Text Steuerelement einzufügen.</span><span class="sxs-lookup"><span data-stu-id="07d54-111">If the text control does support <xref:System.Windows.Automation.ValuePattern>, the <xref:System.Windows.Automation.ValuePattern.SetValue%2A> method is used to insert a user-defined string into the text control.</span></span> <span data-ttu-id="07d54-112">Andernfalls wird die <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> -Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="07d54-112">Otherwise, the <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> method is used.</span></span>  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## <a name="see-also"></a><span data-ttu-id="07d54-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07d54-113">See also</span></span>

- <span data-ttu-id="07d54-114">[TextPattern-Textbeispiel einfügen](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771478(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="07d54-114">[TextPattern Insert Text Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771478(v=vs.90))</span></span>

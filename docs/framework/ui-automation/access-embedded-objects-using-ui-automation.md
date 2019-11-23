---
title: Zugreifen auf eingebettete Objekte mit Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- embedded objects, accessing
- accessing embedded objects
- UI Automation, accessing embedded objects
ms.assetid: a5b513ec-7fa6-4460-869f-c18ff04f7cf2
ms.openlocfilehash: 75c63360eab2cde95698bdaded5c5249a3ca89fd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447266"
---
# <a name="access-embedded-objects-using-ui-automation"></a><span data-ttu-id="94407-102">Zugreifen auf eingebettete Objekte mit Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="94407-102">Access Embedded Objects Using UI Automation</span></span>
> [!NOTE]
> <span data-ttu-id="94407-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="94407-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="94407-104">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="94407-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="94407-105">In diesem Thema wird gezeigt, wie Sie mithilfe von [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Objekte verfügbar machen können, die im Inhalt eines Textsteuerelements eingebettet sind.</span><span class="sxs-lookup"><span data-stu-id="94407-105">This topic shows how [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] can be used to expose objects embedded within the content of a text control.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="94407-106">Bei eingebetteten Objekten kann es sich um Bilder, Links, Schaltflächen, Tabellen oder ActiveX-Steuerelemente handeln.</span><span class="sxs-lookup"><span data-stu-id="94407-106">Embedded objects can include images, hyperlinks, buttons, tables, or ActiveX controls.</span></span>  
  
 <span data-ttu-id="94407-107">Eingebettete Objekte werden als untergeordnete Elemente des [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Textanbieters angesehen</span><span class="sxs-lookup"><span data-stu-id="94407-107">Embedded objects are considered children of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] text provider.</span></span> <span data-ttu-id="94407-108">Dadurch können sie über dieselbe Benutzeroberflächenautomatisierungs-Struktur wie alle anderen [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] -Elemente verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="94407-108">This allows them to be exposed through the same UI Automation tree structure as all other [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] elements.</span></span> <span data-ttu-id="94407-109">Funktionen werden dagegen über die Steuerelementmuster verfügbar gemacht, die üblicherweise für den Steuerelementtyp der eingebetteten Objekte erforderlich sind (Links sind beispielsweise textbasiert und unterstützen daher <xref:System.Windows.Automation.TextPattern>).</span><span class="sxs-lookup"><span data-stu-id="94407-109">Functionality, in turn, is exposed through the control patterns typically required by the embedded objects control type (for example, since hyperlinks are text-based they will support <xref:System.Windows.Automation.TextPattern>).</span></span>  
  
 <span data-ttu-id="94407-110">![Embedded objects in a text container.](./media/uia-textpattern-embeddedobjects.PNG "UIA_TextPattern_EmbeddedObjects")</span><span class="sxs-lookup"><span data-stu-id="94407-110">![Embedded objects in a text container.](./media/uia-textpattern-embeddedobjects.PNG "UIA_TextPattern_EmbeddedObjects")</span></span>  
<span data-ttu-id="94407-111">A sample document with textual content, ("Did You Know?"…) and two embedded objects (a picture of a whale and a text hyperlink), used as a target for the code examples.</span><span class="sxs-lookup"><span data-stu-id="94407-111">A sample document with textual content, ("Did You Know?"…) and two embedded objects (a picture of a whale and a text hyperlink), used as a target for the code examples.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94407-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="94407-112">Example</span></span>  
 <span data-ttu-id="94407-113">Mit dem folgenden Beispielcode wird veranschaulicht, wie eine Auflistung eingebetteter Objekte aus einem [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Textanbieter abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="94407-113">The following code example demonstrates how to retrieve a collection of embedded objects from within a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] text provider.</span></span> <span data-ttu-id="94407-114">Wenn Sie das Beispieldokument aus der Einführung verwenden, werden zwei Objekte zurückgegeben (ein Bild- und ein Textelement).</span><span class="sxs-lookup"><span data-stu-id="94407-114">For the sample document provided in the introduction, two objects would be returned (an image element and a text element).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="94407-115">Das Bildelement sollte ihm zugeordneten Text haben, der das Bild beschreibt und üblicherweise in der <xref:System.Windows.Automation.AutomationElement.NameProperty> des Bildelements (z. B. „Ein blauer Wal“) steht.</span><span class="sxs-lookup"><span data-stu-id="94407-115">The image element should have some intrinsic text associated with it that describes the image, typically in its <xref:System.Windows.Automation.AutomationElement.NameProperty> (for example, "A blue whale.").</span></span> <span data-ttu-id="94407-116">Wenn jedoch ein Textbereich abgerufen wird, der das Bildobjekt umfasst, werden weder das Bild noch dieser beschreibende Text im Textstream zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="94407-116">However, when a text range spanning the image object is obtained, neither the image nor this descriptive text is returned in the text stream.</span></span>  
  
[!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
[!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#GetChildren](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#getchildren)]
[!code-vb[FindText#GetChildren](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#getchildren)]  
  
## <a name="example"></a><span data-ttu-id="94407-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="94407-117">Example</span></span>  
 <span data-ttu-id="94407-118">Mit dem folgenden Beispielcode wird veranschaulicht, wie ein Textbereich aus einem eingebetteten Objekt in einem [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Textanbieter abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="94407-118">The following code example demonstrates how to obtain a text range from an embedded object within a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] text provider.</span></span> <span data-ttu-id="94407-119">Der abgerufene Textbereich ist ein leerer Bereich, dessen Startpunkt auf das Leerzeichen in „…</span><span class="sxs-lookup"><span data-stu-id="94407-119">The text range retrieved is an empty range where the starting endpoint follows "…</span></span> <span data-ttu-id="94407-120">ocean.(Leerzeichen)" folgt und dessen Endpunkt vor dem abschließenden "." positioniert ist und der den eingebetteten Link darstellt (siehe Abbildung in der Einführung).</span><span class="sxs-lookup"><span data-stu-id="94407-120">ocean.(space)" and the ending endpoint precedes the closing "." representing the embedded hyperlink (as shown by the image provided in the introduction).</span></span> <span data-ttu-id="94407-121">Obwohl dies ein leerer Bereich ist, wird er nicht als degenerierter Bereich angesehen, da er eine Spanne ungleich null hat.</span><span class="sxs-lookup"><span data-stu-id="94407-121">Even though this is an empty range, it is not considered a degenerate range because it has a non-zero span.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="94407-122"><xref:System.Windows.Automation.TextPattern> kann ein eingebettetes Textobjekt, etwa einen Link, abrufen. Allerdings muss ein sekundäres <xref:System.Windows.Automation.TextPattern> aus dem eingebetteten Objekt abgerufen werden, um dessen gesamte Funktionalität verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="94407-122"><xref:System.Windows.Automation.TextPattern> can retrieve a text-based embedded object such as a hyperlink; however, a secondary <xref:System.Windows.Automation.TextPattern> will have to be obtained from the embedded object to expose its full functionality.</span></span>  
  
 [!code-csharp[UIATextPattern_snip#GetRangeFromChild](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#getrangefromchild)]
 [!code-vb[UIATextPattern_snip#GetRangeFromChild](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#getrangefromchild)]  
  
## <a name="see-also"></a><span data-ttu-id="94407-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94407-123">See also</span></span>

- [<span data-ttu-id="94407-124">Übersicht über TextPattern für die Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="94407-124">UI Automation TextPattern Overview</span></span>](ui-automation-textpattern-overview.md)
- [<span data-ttu-id="94407-125">Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="94407-125">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="94407-126">Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients</span><span class="sxs-lookup"><span data-stu-id="94407-126">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="94407-127">Hinzufügen von Inhalt in einem Textfeld mithilfe von Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="94407-127">Add Content to a Text Box Using UI Automation</span></span>](add-content-to-a-text-box-using-ui-automation.md)
- [<span data-ttu-id="94407-128">Suchen und Hervorheben von Text durch Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="94407-128">Find and Highlight Text Using UI Automation</span></span>](find-and-highlight-text-using-ui-automation.md)

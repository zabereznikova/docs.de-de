---
title: 'Vorgehensweise: Aktivieren der Textverkürzung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], trimming
- documents [WPF], trimming text
- trimming text [WPF]
ms.assetid: dd8c9191-d2be-45fd-9fb4-3c75b65578c5
ms.openlocfilehash: 25fff566868e792004a915fee195485c4a1f385f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776126"
---
# <a name="how-to-enable-text-trimming"></a><span data-ttu-id="74de3-102">Vorgehensweise: Aktivieren der Textverkürzung</span><span class="sxs-lookup"><span data-stu-id="74de3-102">How to: Enable Text Trimming</span></span>

<span data-ttu-id="74de3-103">Dieses Beispiel zeigt die Verwendung und die Werte zur Verfügung, in der <xref:System.Windows.TextTrimming> Enumeration.</span><span class="sxs-lookup"><span data-stu-id="74de3-103">This example demonstrates the usage and effects of the values available in the <xref:System.Windows.TextTrimming> enumeration.</span></span>

## <a name="example"></a><span data-ttu-id="74de3-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="74de3-104">Example</span></span>

<span data-ttu-id="74de3-105">Das folgende Beispiel definiert eine <xref:System.Windows.Controls.TextBlock> -Element mit dem <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> -Attribut festgelegt.</span><span class="sxs-lookup"><span data-stu-id="74de3-105">The following example defines a <xref:System.Windows.Controls.TextBlock> element with the <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> attribute set.</span></span>

[!code-xaml[TextTrimmingSnippets#_TextTrimmingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml#_texttrimmingxaml)]

<span data-ttu-id="74de3-106">Festlegen der entsprechenden <xref:System.Windows.TextTrimming> Eigenschaft im Code wird unten gezeigt.</span><span class="sxs-lookup"><span data-stu-id="74de3-106">Setting the corresponding <xref:System.Windows.TextTrimming> property in code is demonstrated below.</span></span>

[!code-csharp[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml.cs#_texttrimmingsettexttrimming)]
[!code-vb[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextTrimmingSnippets/VisualBasic/Window1.xaml.vb#_texttrimmingsettexttrimming)]

<span data-ttu-id="74de3-107">Es gibt derzeit drei Optionen zum Verkürzen von Text aus: **CharacterEllipsis**, **WordEllipsis**, und **keine**.</span><span class="sxs-lookup"><span data-stu-id="74de3-107">There are currently three options for trimming text: **CharacterEllipsis**, **WordEllipsis**, and **None**.</span></span>

<span data-ttu-id="74de3-108">Wenn <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> nastaven NA hodnotu **CharacterEllipsis**, Text gekürzt und mit einer Ellipse am nächsten Kante Zeichen fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="74de3-108">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **CharacterEllipsis**, text is trimmed and continued with an ellipsis at the character closest to the trimming edge.</span></span>  <span data-ttu-id="74de3-109">Diese Einstellung tendiert dazu, den Text zu kürzen, damit dieser besser an die Kürzungsgrenze passt. Dies kann jedoch dazu führen, dass Wörter teilweise abgeschnitten werden.</span><span class="sxs-lookup"><span data-stu-id="74de3-109">This setting tends to trim text to fit more closely to the trimming boundary, but may result in words being partially trimmed.</span></span>  <span data-ttu-id="74de3-110">Die folgende Abbildung zeigt die Auswirkung dieser Einstellung auf einen <xref:System.Windows.Controls.TextBlock> ähnlich der oben definierten.</span><span class="sxs-lookup"><span data-stu-id="74de3-110">The following figure shows the effect of this setting on a <xref:System.Windows.Controls.TextBlock> similar to the one defined above.</span></span>

<span data-ttu-id="74de3-111">![Anpassen von mit VSTU TextTrimming.CharacterEllipsis](./media/texttrimming-character.png "TextTrimming_Character")</span><span class="sxs-lookup"><span data-stu-id="74de3-111">![Example: TextTrimming.CharacterEllipsis](./media/texttrimming-character.png "TextTrimming_Character")</span></span>

<span data-ttu-id="74de3-112">Wenn <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> nastaven NA hodnotu **WordEllipsis**, Text gekürzt und mit einer Ellipse am Ende des nächsten Kante ersten vollständigen Worts fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="74de3-112">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **WordEllipsis**, text is trimmed and continued with an ellipsis at the end of the first full word closest to the trimming edge.</span></span>  <span data-ttu-id="74de3-113">Mit dieser Einstellung werden keine teilweise verkürzten Wörter angezeigt, aber meist nicht so weit zu Kante als Text zu kürzen der **CharacterEllipsis** festlegen.</span><span class="sxs-lookup"><span data-stu-id="74de3-113">This setting will not show partially trimmed words, but tends not to trim text as closely to the trimming edge as the **CharacterEllipsis** setting.</span></span>  <span data-ttu-id="74de3-114">Die folgende Abbildung zeigt die Auswirkung dieser Einstellung auf die <xref:System.Windows.Controls.TextBlock> oben definierten.</span><span class="sxs-lookup"><span data-stu-id="74de3-114">The following figure shows the effect of this setting on the <xref:System.Windows.Controls.TextBlock> defined above.</span></span>

<span data-ttu-id="74de3-115">![Anpassen von mit VSTU TextTrimming.WordEllipsis](./media/texttrimming-word.png "TextTrimming_Word")</span><span class="sxs-lookup"><span data-stu-id="74de3-115">![Example: TextTrimming.WordEllipsis](./media/texttrimming-word.png "TextTrimming_Word")</span></span>

<span data-ttu-id="74de3-116">Wenn <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> nastaven NA hodnotu **keine**, es wird keine textkürzung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="74de3-116">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **None**, no text trimming is performed.</span></span>  <span data-ttu-id="74de3-117">In diesem Fall wird Text einfach an der Begrenzung des übergeordneten Textcontainers zugeschnitten.</span><span class="sxs-lookup"><span data-stu-id="74de3-117">In this case, text is simply cropped to the boundary of the parent text container.</span></span>  <span data-ttu-id="74de3-118">Die folgende Abbildung zeigt die Auswirkung dieser Einstellung auf einen <xref:System.Windows.Controls.TextBlock> ähnlich der oben definierten.</span><span class="sxs-lookup"><span data-stu-id="74de3-118">The following figure shows the effect of this setting on a <xref:System.Windows.Controls.TextBlock> similar to the one defined above.</span></span>

<span data-ttu-id="74de3-119">![Anpassen von mit VSTU TextTrimming.None](./media/texttrimming-none.png "TextTrimming_None")</span><span class="sxs-lookup"><span data-stu-id="74de3-119">![Example: TextTrimming.None](./media/texttrimming-none.png "TextTrimming_None")</span></span>

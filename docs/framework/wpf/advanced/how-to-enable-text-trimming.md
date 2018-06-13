---
title: 'Gewusst wie: Aktivieren der Textverkürzung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], trimming
- documents [WPF], trimmng text
- trimmng text [WPF]
ms.assetid: dd8c9191-d2be-45fd-9fb4-3c75b65578c5
ms.openlocfilehash: 97bc88b298500892fcc7d26e61f8052a05d9e593
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543539"
---
# <a name="how-to-enable-text-trimming"></a><span data-ttu-id="7e7cc-102">Gewusst wie: Aktivieren der Textverkürzung</span><span class="sxs-lookup"><span data-stu-id="7e7cc-102">How to: Enable Text Trimming</span></span>
<span data-ttu-id="7e7cc-103">Dieses Beispiel veranschaulicht die Verwendung und die Auswirkungen der Werte zur Verfügung, in der <xref:System.Windows.TextTrimming> Enumeration.</span><span class="sxs-lookup"><span data-stu-id="7e7cc-103">This example demonstrates the usage and effects of the values available in the <xref:System.Windows.TextTrimming> enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e7cc-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7e7cc-104">Example</span></span>  
 <span data-ttu-id="7e7cc-105">Das folgende Beispiel definiert eine <xref:System.Windows.Controls.TextBlock> Element mit dem <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> -Attribut festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7e7cc-105">The following example defines a <xref:System.Windows.Controls.TextBlock> element with the <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> attribute set.</span></span>  
  
 [!code-xaml[TextTrimmingSnippets#_TextTrimmingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml#_texttrimmingxaml)]  
  
## <a name="example"></a><span data-ttu-id="7e7cc-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7e7cc-106">Example</span></span>  
 <span data-ttu-id="7e7cc-107">Festlegen der entsprechenden <xref:System.Windows.TextTrimming> -Eigenschaft im Code wird unten veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="7e7cc-107">Setting the corresponding <xref:System.Windows.TextTrimming> property in code is demonstrated below.</span></span>  
  
 [!code-csharp[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml.cs#_texttrimmingsettexttrimming)]
 [!code-vb[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextTrimmingSnippets/VisualBasic/Window1.xaml.vb#_texttrimmingsettexttrimming)]  
  
 <span data-ttu-id="7e7cc-108">Es gibt derzeit drei Optionen zum Verkürzen von Text: **CharacterEllipsis**, **WordEllipsis**, und **keine**.</span><span class="sxs-lookup"><span data-stu-id="7e7cc-108">There are currently three options for trimming text: **CharacterEllipsis**, **WordEllipsis**, and **None**.</span></span>  
  
 <span data-ttu-id="7e7cc-109">Wenn <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> festgelegt ist, um **CharacterEllipsis**, Text gekürzt und mit einem Auslassungszeichen mit dem Zeichen, die dem Kürzen Rand am nächsten fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="7e7cc-109">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **CharacterEllipsis**, text is trimmed and continued with an ellipsis at the character closest to the trimming edge.</span></span>  <span data-ttu-id="7e7cc-110">Diese Einstellung tendiert dazu, den Text zu kürzen, damit dieser besser an die Kürzungsgrenze passt. Dies kann jedoch dazu führen, dass Wörter teilweise abgeschnitten werden.</span><span class="sxs-lookup"><span data-stu-id="7e7cc-110">This setting tends to trim text to fit more closely to the trimming boundary, but may result in words being partially trimmed.</span></span>  <span data-ttu-id="7e7cc-111">Die folgende Abbildung zeigt die Auswirkungen dieser Einstellung auf einen <xref:System.Windows.Controls.TextBlock> oben definierten ähnelt.</span><span class="sxs-lookup"><span data-stu-id="7e7cc-111">The following figure shows the effect of this setting on a <xref:System.Windows.Controls.TextBlock> similar to the one defined above.</span></span>  
  
 <span data-ttu-id="7e7cc-112">![Beispiel: TextTrimming.CharacterEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-character.png "TextTrimming_Character")</span><span class="sxs-lookup"><span data-stu-id="7e7cc-112">![Example: TextTrimming.CharacterEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-character.png "TextTrimming_Character")</span></span>  
  
 <span data-ttu-id="7e7cc-113">Wenn <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> festgelegt ist, um **WordEllipsis**, Text gekürzt und mit einem Auslassungszeichen am Ende der ersten vollständigen Worts am nächsten an den Rand verkürzen fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="7e7cc-113">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **WordEllipsis**, text is trimmed and continued with an ellipsis at the end of the first full word closest to the trimming edge.</span></span>  <span data-ttu-id="7e7cc-114">Diese Einstellung wird teilweise verkürzten Wörter nicht angezeigt, aber ist nicht so genau zu dem Kürzen Rand als Text Kürzen der **CharacterEllipsis** Einstellung.</span><span class="sxs-lookup"><span data-stu-id="7e7cc-114">This setting will not show partially trimmed words, but tends not to trim text as closely to the trimming edge as the **CharacterEllipsis** setting.</span></span>  <span data-ttu-id="7e7cc-115">Die folgende Abbildung zeigt die Auswirkungen dieser Einstellung auf die <xref:System.Windows.Controls.TextBlock> oben definiert.</span><span class="sxs-lookup"><span data-stu-id="7e7cc-115">The following figure shows the effect of this setting on the <xref:System.Windows.Controls.TextBlock> defined above.</span></span>  
  
 <span data-ttu-id="7e7cc-116">![Beispiel: TextTrimming.WordEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-word.png "TextTrimming_Word")</span><span class="sxs-lookup"><span data-stu-id="7e7cc-116">![Example: TextTrimming.WordEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-word.png "TextTrimming_Word")</span></span>  
  
 <span data-ttu-id="7e7cc-117">Wenn <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> festgelegt ist, um **keine**, kein Text verkürzt wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7e7cc-117">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **None**, no text trimming is performed.</span></span>  <span data-ttu-id="7e7cc-118">In diesem Fall wird Text einfach an der Begrenzung des übergeordneten Textcontainers zugeschnitten.</span><span class="sxs-lookup"><span data-stu-id="7e7cc-118">In this case, text is simply cropped to the boundary of the parent text container.</span></span>  <span data-ttu-id="7e7cc-119">Die folgende Abbildung zeigt die Auswirkungen dieser Einstellung auf einen <xref:System.Windows.Controls.TextBlock> oben definierten ähnelt.</span><span class="sxs-lookup"><span data-stu-id="7e7cc-119">The following figure shows the effect of this setting on a <xref:System.Windows.Controls.TextBlock> similar to the one defined above.</span></span>  
  
 <span data-ttu-id="7e7cc-120">![Beispiel: TextTrimming.None](../../../../docs/framework/wpf/advanced/media/texttrimming-none.png "TextTrimming_None")</span><span class="sxs-lookup"><span data-stu-id="7e7cc-120">![Example: TextTrimming.None](../../../../docs/framework/wpf/advanced/media/texttrimming-none.png "TextTrimming_None")</span></span>

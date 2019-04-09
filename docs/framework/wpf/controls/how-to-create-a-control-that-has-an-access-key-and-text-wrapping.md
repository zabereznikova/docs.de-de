---
title: 'Vorgehensweise: Erstellen eines Steuerelements, das über eine Tastenkombination und Textumbruch verfügt'
ms.date: 03/30/2017
helpviewer_keywords:
- access keys [WPF], control for
- controls [WPF], text wrapping
- wrapping text [WPF]
- keys [WPF], control for
- controls [WPF], access keys
- text wrapping [WPF]
ms.assetid: 205099d9-2551-4302-a25e-a15af9f67e04
ms.openlocfilehash: 48e439719afa2426b5d8f822c621080cdc32514e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59174043"
---
# <a name="how-to-create-a-control-that-has-an-access-key-and-text-wrapping"></a><span data-ttu-id="e6a46-102">Vorgehensweise: Erstellen eines Steuerelements, das über eine Tastenkombination und Textumbruch verfügt</span><span class="sxs-lookup"><span data-stu-id="e6a46-102">How to: Create a Control That Has an Access Key and Text Wrapping</span></span>
<span data-ttu-id="e6a46-103">Diese Beispiel veranschaulicht, wie Sie ein Steuerelement erstellen, das über eine Tastenkombination verfügt und das Umbrechen von Text unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e6a46-103">This example shows how to create a control that has an access key and supports text wrapping.</span></span> <span data-ttu-id="e6a46-104">Im Beispiel wird eine <xref:System.Windows.Controls.Label> Steuerelement zur Veranschaulichung dieser Konzepte.</span><span class="sxs-lookup"><span data-stu-id="e6a46-104">The example uses a <xref:System.Windows.Controls.Label> control to illustrate these concepts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6a46-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e6a46-105">Example</span></span>  
 **<span data-ttu-id="e6a46-106">Umbrechen von Text zur Bezeichnung hinzufügen</span><span class="sxs-lookup"><span data-stu-id="e6a46-106">Add Text Wrapping to Your Label</span></span>**  
  
 <span data-ttu-id="e6a46-107">Die <xref:System.Windows.Controls.Label> Umbrechen von Text-Steuerelement nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e6a46-107">The <xref:System.Windows.Controls.Label> control does not support text wrapping.</span></span> <span data-ttu-id="e6a46-108">Wenn sich eine Bezeichnung über mehrere Zeilen erstrecken soll, können Sie ein anderes Element verschachteln, das das Umbrechen von Text unterstützt, und es innerhalb der Bezeichnung platzieren.</span><span class="sxs-lookup"><span data-stu-id="e6a46-108">If you need a label that wraps across multiple lines, you can nest another element that does support text wrapping and put the element inside the label.</span></span> <span data-ttu-id="e6a46-109">Das folgende Beispiel zeigt, wie Sie mit einem <xref:System.Windows.Controls.TextBlock> um eine Bezeichnung zu erstellen, die mehrere Zeilen Text umbrochen wird.</span><span class="sxs-lookup"><span data-stu-id="e6a46-109">The following example shows how to use a <xref:System.Windows.Controls.TextBlock> to make a label that wraps several lines of text.</span></span>  
  
 [!code-xaml[LabelSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#5)]  
  
 **<span data-ttu-id="e6a46-110">Fügen Sie eine Tastenkombination und Textumbruch zu einer Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="e6a46-110">Add an Access Key and Text Wrapping to Your Label</span></span>**  
  
 <span data-ttu-id="e6a46-111">Bei Bedarf eine <xref:System.Windows.Controls.Label> , die über eine Tastenkombination (mnemonisches Zeichen) verfügt, verwenden Sie die <xref:System.Windows.Controls.AccessText> Elements in der <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="e6a46-111">If you need a <xref:System.Windows.Controls.Label> that has an access key (mnemonic), use the <xref:System.Windows.Controls.AccessText> element that is inside the <xref:System.Windows.Controls.Label>.</span></span>  
  
 <span data-ttu-id="e6a46-112">Steuert, wie z. B. <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.Expander>, und <xref:System.Windows.Controls.GroupBox> haben Sie die Standard-Steuerelementvorlagen.</span><span class="sxs-lookup"><span data-stu-id="e6a46-112">Controls such as <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.Expander>, and <xref:System.Windows.Controls.GroupBox> have default control templates.</span></span> <span data-ttu-id="e6a46-113">Diese Vorlagen enthalten ein <xref:System.Windows.Controls.ContentPresenter>.</span><span class="sxs-lookup"><span data-stu-id="e6a46-113">These templates contain a <xref:System.Windows.Controls.ContentPresenter>.</span></span> <span data-ttu-id="e6a46-114">Eine der Eigenschaften, die Sie auf festlegen, können die <xref:System.Windows.Controls.ContentPresenter> ist <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A>= "true", damit können Sie eine Zugriffstaste für das Steuerelement an.</span><span class="sxs-lookup"><span data-stu-id="e6a46-114">One of the properties that you can set on the <xref:System.Windows.Controls.ContentPresenter> is <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A>="true", which you can use to specify an access key for the control.</span></span>  
  
 <span data-ttu-id="e6a46-115">Das folgende Beispiel zeigt, wie Sie erstellen eine <xref:System.Windows.Controls.Label> , die über eine Tastenkombination verfügt und Umbrechen von Text unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e6a46-115">The following example shows how to create a <xref:System.Windows.Controls.Label> that has an access key and supports text wrapping.</span></span> <span data-ttu-id="e6a46-116">So aktivieren Sie den Textumbruch, im Beispiel wird die <xref:System.Windows.Controls.AccessText.TextWrapping%2A> -Eigenschaft und verwendet ein Unterstrich-Zeichen um den Zugriffsschlüssel angeben.</span><span class="sxs-lookup"><span data-stu-id="e6a46-116">To enable text wrapping, the example sets the <xref:System.Windows.Controls.AccessText.TextWrapping%2A> property and uses an underline character to specify the access key.</span></span> <span data-ttu-id="e6a46-117">(Das Zeichen, das unmittelbar auf den Unterstrich folgt, ist die Tastenkombination.)</span><span class="sxs-lookup"><span data-stu-id="e6a46-117">(The character that immediately follows the underline character is the access key.)</span></span>  
  
 [!code-xaml[LabelSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="e6a46-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6a46-118">See also</span></span>

- [<span data-ttu-id="e6a46-119">Vorgehensweise: Festlegen der Zieleigenschaft einer Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="e6a46-119">How to: Set the Target Property of a Label</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752101(v=vs.90))

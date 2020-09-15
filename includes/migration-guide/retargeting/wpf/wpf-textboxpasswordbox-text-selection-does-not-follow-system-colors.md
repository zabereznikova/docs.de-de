---
ms.openlocfilehash: 7c2e80669d9ef27f87cde9442d8eeab0ee31a524
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614624"
---
### <a name="wpf-textboxpasswordbox-text-selection-does-not-follow-system-colors"></a><span data-ttu-id="40cd0-101">TextBox-/PasswordBox-Textauswahl von WPF folgt nicht den Systemfarben</span><span class="sxs-lookup"><span data-stu-id="40cd0-101">WPF TextBox/PasswordBox Text Selection Does Not Follow System Colors</span></span>

#### <a name="details"></a><span data-ttu-id="40cd0-102">Details</span><span class="sxs-lookup"><span data-stu-id="40cd0-102">Details</span></span>

<span data-ttu-id="40cd0-103">In .NET Framework 4.7.1 und früheren Versionen konnten `System.Windows.Controls.TextBox` und `System.Windows.Controls.PasswordBox` von WPF nur eine Textauswahl aus der Adorner-Ebene rendern.</span><span class="sxs-lookup"><span data-stu-id="40cd0-103">In .NET Framework 4.7.1 and earlier versions, WPF `System.Windows.Controls.TextBox` and `System.Windows.Controls.PasswordBox` could only render a text selection in the Adorner layer.</span></span> <span data-ttu-id="40cd0-104">In einigen Systemdesigns verdeckte dies Text, wodurch die Lesbarkeit erschwert wurde.</span><span class="sxs-lookup"><span data-stu-id="40cd0-104">In some system themes this would occlude text, making it hard to read.</span></span>  <span data-ttu-id="40cd0-105">In .NET Framework 4.7.2 und höher besteht für Entwickler eine Option, ein nicht auf Adorner basierendes Auswahlrenderingschema zu aktivieren, das dieses Problem behebt.</span><span class="sxs-lookup"><span data-stu-id="40cd0-105">In .NET Framework 4.7.2 and later, developers have an option of enabling a non-Adorner-based selection rendering scheme that alleviates this issue.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="40cd0-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="40cd0-106">Suggestion</span></span>

<span data-ttu-id="40cd0-107">Ein Entwickler, die diese Änderung nutzen möchte, muss das folgende AppContext-Flag entsprechend festlegen.</span><span class="sxs-lookup"><span data-stu-id="40cd0-107">A developer who wants to utilize this change must set the following AppContext flag appropriately.</span></span>  <span data-ttu-id="40cd0-108">Um dieses Feature nutzen zu können, muss die installierte Version von .NET Framework 4.7.2 oder höher sein. Um die nicht auf Adorner basierende Auswahl zu aktivieren, verwenden Sie das folgenden AppContext-Flag.</span><span class="sxs-lookup"><span data-stu-id="40cd0-108">To utilize this feature, the installed .NET Framework version must be 4.7.2 or greater.To enabled the non-adorner-based selection, use the following AppContext flag.</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Text.UseAdornerForTextboxSelectionRendering=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="40cd0-109">name</span><span class="sxs-lookup"><span data-stu-id="40cd0-109">Name</span></span>    | <span data-ttu-id="40cd0-110">Wert</span><span class="sxs-lookup"><span data-stu-id="40cd0-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="40cd0-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="40cd0-111">Scope</span></span>   | <span data-ttu-id="40cd0-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="40cd0-112">Edge</span></span>        |
| <span data-ttu-id="40cd0-113">Version</span><span class="sxs-lookup"><span data-stu-id="40cd0-113">Version</span></span> | <span data-ttu-id="40cd0-114">4.7.2</span><span class="sxs-lookup"><span data-stu-id="40cd0-114">4.7.2</span></span>       |
| <span data-ttu-id="40cd0-115">Typ</span><span class="sxs-lookup"><span data-stu-id="40cd0-115">Type</span></span>    | <span data-ttu-id="40cd0-116">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="40cd0-116">Retargeting</span></span> |

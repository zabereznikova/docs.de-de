---
ms.openlocfilehash: a9d0fe3516ade04bc38b804268a9d989f6891d80
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643880"
---
### <a name="switchsystemwindowsformsdonotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported"></a><span data-ttu-id="7c592-101">Kompatibilitätsswitch „Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox“ wird nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="7c592-101">Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>

<span data-ttu-id="7c592-102">Der mit .NET Framework 4.6.1 eingeführte Kompatibilitätsswitch `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` wird in Windows Forms unter .NET Core 3.0 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7c592-102">The `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` compatibility switch, which was introduced in .NET Framework 4.6.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="7c592-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="7c592-103">Change description</span></span>

<span data-ttu-id="7c592-104">Ab .NET Framework 4.6.1 wird mit der Tastenkombination <kbd>STRG</kbd> + <kbd>A</kbd> in einem <xref:System.Windows.Forms.TextBox>-Steuerelement der gesamte Text ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="7c592-104">Starting with .NET Framework 4.6.1, selecting the <kbd>Ctrl</kbd> + <kbd>A</kbd> shortcut key in a <xref:System.Windows.Forms.TextBox> control selected all text.</span></span> <span data-ttu-id="7c592-105">In .NET Framework 4.6 und früheren Versionen konnte mit der Tastenkombination <kbd>STRG</kbd> + <kbd>A</kbd> nicht der gesamte Text ausgewählt werden, wenn die beiden Eigenschaften [Textbox.ShortcutsEnabled](xref:System.Windows.Forms.TextBoxBase.ShortcutsEnabled) und <xref:System.Windows.Forms.TextBox.Multiline?displayProperty=nameWithType> auf `true` festgelegt waren.</span><span class="sxs-lookup"><span data-stu-id="7c592-105">In .NET Framework 4.6 and previous versions, selecting the <kbd>Ctrl</kbd> + <kbd>A</kbd> shortcut key failed to select all text if the [Textbox.ShortcutsEnabled](xref:System.Windows.Forms.TextBoxBase.ShortcutsEnabled) and <xref:System.Windows.Forms.TextBox.Multiline?displayProperty=nameWithType> properties were both set to `true`.</span></span> <span data-ttu-id="7c592-106">Der Kompatibilitätsswitch `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` wurde in .NET Framework 4.6.1 eingeführt, um das ursprüngliche Verhalten beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="7c592-106">The `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` compatibility switch was introduced in .NET Framework 4.6.1 to retain the original behavior.</span></span> <span data-ttu-id="7c592-107">Weitere Informationen finden Sie unter <xref:System.Windows.Forms.TextBox.ProcessCmdKey%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7c592-107">For more information see <xref:System.Windows.Forms.TextBox.ProcessCmdKey%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="7c592-108">In .NET Core wird der Switch `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7c592-108">In .NET Core, the `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="7c592-109">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="7c592-109">Version introduced</span></span>

<span data-ttu-id="7c592-110">3.0 Vorschau 9</span><span class="sxs-lookup"><span data-stu-id="7c592-110">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="7c592-111">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="7c592-111">Recommended action</span></span>

<span data-ttu-id="7c592-112">Entfernen Sie den Switch.</span><span class="sxs-lookup"><span data-stu-id="7c592-112">Remove the switch.</span></span> <span data-ttu-id="7c592-113">Der Switch wird nicht unterstützt, und es ist keine alternative Funktionalität verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7c592-113">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="7c592-114">Kategorie</span><span class="sxs-lookup"><span data-stu-id="7c592-114">Category</span></span>

<span data-ttu-id="7c592-115">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7c592-115">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7c592-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="7c592-116">Affected APIs</span></span>

- <span data-ttu-id="7c592-117">Keine</span><span class="sxs-lookup"><span data-stu-id="7c592-117">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->

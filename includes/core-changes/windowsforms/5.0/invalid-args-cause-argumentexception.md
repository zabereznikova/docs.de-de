---
ms.openlocfilehash: aab7d8538c875e35c832acc2a6c64beb84d4fb47
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2020
ms.locfileid: "84702438"
---
### <a name="winforms-methods-now-throw-argumentexception"></a><span data-ttu-id="6b322-101">WinForms-Methoden lösen jetzt ArgumentException aus.</span><span class="sxs-lookup"><span data-stu-id="6b322-101">WinForms methods now throw ArgumentException</span></span>

<span data-ttu-id="6b322-102">Einige Windows Forms-Methoden lösen nun eine <xref:System.ArgumentException> für ungültige Argumente aus, was zuvor nicht der Fall war.</span><span class="sxs-lookup"><span data-stu-id="6b322-102">Some Windows Forms methods now throw an <xref:System.ArgumentException> for invalid arguments, where previously they did not.</span></span>

#### <a name="change-description"></a><span data-ttu-id="6b322-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="6b322-103">Change description</span></span>

<span data-ttu-id="6b322-104">Zuvor führte das Übergeben von Argumenten eines unerwarteten oder falschen Typs an bestimmte Windows Forms-Methoden zu einem unbestimmten Zustand.</span><span class="sxs-lookup"><span data-stu-id="6b322-104">Previously, passing arguments of an unexpected or incorrect type to certain Windows Forms methods would result in an indeterminate state.</span></span> <span data-ttu-id="6b322-105">Ab .NET 5.0 lösen diese Methoden stattdessen eine <xref:System.ArgumentException> aus, wenn ungültige Argumente übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="6b322-105">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentException> when passed invalid arguments.</span></span>

<span data-ttu-id="6b322-106">Das Auslösen einer <xref:System.ArgumentException>-Ausnahme entspricht dem Verhalten der .NET Runtime.</span><span class="sxs-lookup"><span data-stu-id="6b322-106">Throwing an <xref:System.ArgumentException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="6b322-107">Außerdem wird die Debugfunktion verbessert, indem ausdrücklich kommuniziert wird, welches Argument ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="6b322-107">It also improves the debugging experience by clearly communicating which argument is invalid.</span></span>

<span data-ttu-id="6b322-108">In der folgenden Tabelle sind die betroffenen Methoden und Parameter aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="6b322-108">The following table lists the affected methods and parameters:</span></span>

| <span data-ttu-id="6b322-109">Methode</span><span class="sxs-lookup"><span data-stu-id="6b322-109">Method</span></span> | <span data-ttu-id="6b322-110">Parametername</span><span class="sxs-lookup"><span data-stu-id="6b322-110">Parameter name</span></span> | <span data-ttu-id="6b322-111">Bedingung</span><span class="sxs-lookup"><span data-stu-id="6b322-111">Condition</span></span> | <span data-ttu-id="6b322-112">Hinzugefügte Version</span><span class="sxs-lookup"><span data-stu-id="6b322-112">Version added</span></span> |
|-|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | <span data-ttu-id="6b322-113">Das Argument ist nicht vom Typ <xref:System.Windows.Forms.TabPage>.</span><span class="sxs-lookup"><span data-stu-id="6b322-113">Argument is not of type <xref:System.Windows.Forms.TabPage>.</span></span> | <span data-ttu-id="6b322-114">5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="6b322-114">5.0 Preview 1</span></span> |
| <xref:System.Windows.Forms.DataFormats.GetFormat(System.String)?displayProperty=fullName> | `format` | <span data-ttu-id="6b322-115">Das Argument ist `null`, <xref:System.String.Empty?displayProperty=nameWithType> oder Leerraum.</span><span class="sxs-lookup"><span data-stu-id="6b322-115">Argument is `null`, <xref:System.String.Empty?displayProperty=nameWithType>, or white space.</span></span> | <span data-ttu-id="6b322-116">5.0 Vorschau 5</span><span class="sxs-lookup"><span data-stu-id="6b322-116">5.0 Preview 5</span></span> |

#### <a name="version-introduced"></a><span data-ttu-id="6b322-117">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="6b322-117">Version introduced</span></span>

<span data-ttu-id="6b322-118">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="6b322-118">.NET 5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="6b322-119">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="6b322-119">Recommended action</span></span>

- <span data-ttu-id="6b322-120">Aktualisieren Sie den Code, um das Übergeben ungültiger Argumente zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="6b322-120">Update the code to prevent passing invalid arguments.</span></span>
- <span data-ttu-id="6b322-121">Verarbeiten Sie falls erforderlich eine <xref:System.ArgumentException>, wenn Sie die Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="6b322-121">If necessary, handle an <xref:System.ArgumentException> when calling the method.</span></span>

#### <a name="category"></a><span data-ttu-id="6b322-122">Kategorie</span><span class="sxs-lookup"><span data-stu-id="6b322-122">Category</span></span>

<span data-ttu-id="6b322-123">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6b322-123">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6b322-124">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="6b322-124">Affected APIs</span></span>

- <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName>
- <xref:System.Windows.Forms.DataFormats.GetFormat(System.String)?displayProperty=fullName>

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`
- `M:System.Windows.Forms.DataFormats.GetFormat(System.String)`

-->

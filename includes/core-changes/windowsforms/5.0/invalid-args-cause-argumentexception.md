---
ms.openlocfilehash: f1fc70075ef09a4f036c69788342c07ee51d72ce
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702476"
---
### <a name="winforms-methods-now-throw-argumentexception"></a><span data-ttu-id="8a9c8-101">WinForms-Methoden lösen jetzt ArgumentException aus.</span><span class="sxs-lookup"><span data-stu-id="8a9c8-101">WinForms methods now throw ArgumentException</span></span>

<span data-ttu-id="8a9c8-102">Einige Windows Forms-Methoden lösen nun eine <xref:System.ArgumentException> für ungültige Argumente aus, was zuvor nicht der Fall war.</span><span class="sxs-lookup"><span data-stu-id="8a9c8-102">Some Windows Forms methods now throw an <xref:System.ArgumentException> for invalid arguments, where previously they did not.</span></span>

#### <a name="change-description"></a><span data-ttu-id="8a9c8-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="8a9c8-103">Change description</span></span>

<span data-ttu-id="8a9c8-104">Zuvor führte das Übergeben von Argumenten eines unerwarteten oder falschen Typs an bestimmte Windows Forms-Methoden zu einem unbestimmten Zustand.</span><span class="sxs-lookup"><span data-stu-id="8a9c8-104">Previously, passing arguments of an unexpected or incorrect type to certain Windows Forms methods would result in an indeterminate state.</span></span> <span data-ttu-id="8a9c8-105">Ab .NET 5.0 lösen diese Methoden stattdessen eine <xref:System.ArgumentException> aus, wenn ungültige Argumente übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="8a9c8-105">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentException> when passed invalid arguments.</span></span>

<span data-ttu-id="8a9c8-106">Das Auslösen einer <xref:System.ArgumentException>-Ausnahme entspricht dem Verhalten der .NET Runtime.</span><span class="sxs-lookup"><span data-stu-id="8a9c8-106">Throwing an <xref:System.ArgumentException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="8a9c8-107">Außerdem wird die Debugfunktion verbessert, indem ausdrücklich kommuniziert wird, welches Argument ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="8a9c8-107">It also improves the debugging experience by clearly communicating which argument is invalid.</span></span>

<span data-ttu-id="8a9c8-108">In der folgenden Tabelle sind die betroffenen Methoden und Parameter aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="8a9c8-108">The following table lists the affected methods and parameters:</span></span>

| <span data-ttu-id="8a9c8-109">Methode</span><span class="sxs-lookup"><span data-stu-id="8a9c8-109">Method</span></span> | <span data-ttu-id="8a9c8-110">Parametername</span><span class="sxs-lookup"><span data-stu-id="8a9c8-110">Parameter name</span></span> | <span data-ttu-id="8a9c8-111">Bedingung</span><span class="sxs-lookup"><span data-stu-id="8a9c8-111">Condition</span></span> | <span data-ttu-id="8a9c8-112">Hinzugefügte Version</span><span class="sxs-lookup"><span data-stu-id="8a9c8-112">Version added</span></span> |
|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | <span data-ttu-id="8a9c8-113">Das Argument ist nicht vom Typ <xref:System.Windows.Forms.TabPage>.</span><span class="sxs-lookup"><span data-stu-id="8a9c8-113">Argument is not of type <xref:System.Windows.Forms.TabPage>.</span></span> | <span data-ttu-id="8a9c8-114">5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="8a9c8-114">5.0 Preview 1</span></span> |

#### <a name="version-introduced"></a><span data-ttu-id="8a9c8-115">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="8a9c8-115">Version introduced</span></span>

<span data-ttu-id="8a9c8-116">.NET 5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="8a9c8-116">.NET 5.0 Preview 1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8a9c8-117">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="8a9c8-117">Recommended action</span></span>

- <span data-ttu-id="8a9c8-118">Aktualisieren Sie den Code, um das Übergeben ungültiger Argumente zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="8a9c8-118">Update the code to prevent passing invalid arguments.</span></span>
- <span data-ttu-id="8a9c8-119">Verarbeiten Sie falls erforderlich eine <xref:System.ArgumentException>, wenn Sie die Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8a9c8-119">If necessary, handle an <xref:System.ArgumentException> when calling the method.</span></span>

#### <a name="category"></a><span data-ttu-id="8a9c8-120">Kategorie</span><span class="sxs-lookup"><span data-stu-id="8a9c8-120">Category</span></span>

<span data-ttu-id="8a9c8-121">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8a9c8-121">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8a9c8-122">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="8a9c8-122">Affected APIs</span></span>

- <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName>

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`

-->

---
ms.openlocfilehash: 9f6703c77e17ac9376aee944b891f4635dc7632e
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309145"
---
### <a name="winforms-methods-now-throw-argumentexception"></a><span data-ttu-id="18356-101">WinForms-Methoden lösen jetzt ArgumentException aus.</span><span class="sxs-lookup"><span data-stu-id="18356-101">WinForms methods now throw ArgumentException</span></span>

<span data-ttu-id="18356-102">Einige Windows Forms-Methoden lösen nun eine <xref:System.ArgumentException> für ungültige Argumente aus, was zuvor nicht der Fall war.</span><span class="sxs-lookup"><span data-stu-id="18356-102">Some Windows Forms methods now throw an <xref:System.ArgumentException> for invalid arguments, where previously they did not.</span></span>

#### <a name="change-description"></a><span data-ttu-id="18356-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="18356-103">Change description</span></span>

<span data-ttu-id="18356-104">Zuvor führte das Übergeben von Argumenten eines unerwarteten oder falschen Typs an bestimmte Windows Forms-Methoden zu einem unbestimmten Zustand.</span><span class="sxs-lookup"><span data-stu-id="18356-104">Previously, passing arguments of an unexpected or incorrect type to certain Windows Forms methods would result in an indeterminate state.</span></span> <span data-ttu-id="18356-105">Ab .NET 5.0 lösen diese Methoden stattdessen eine <xref:System.ArgumentException> aus, wenn ungültige Argumente übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="18356-105">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentException> when passed invalid arguments.</span></span>

<span data-ttu-id="18356-106">Das Auslösen einer <xref:System.ArgumentException>-Ausnahme entspricht dem Verhalten der .NET Runtime.</span><span class="sxs-lookup"><span data-stu-id="18356-106">Throwing an <xref:System.ArgumentException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="18356-107">Außerdem wird die Debugfunktion verbessert, indem ausdrücklich kommuniziert wird, welches Argument ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="18356-107">It also improves the debugging experience by clearly communicating which argument is invalid.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="18356-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="18356-108">Version introduced</span></span>

<span data-ttu-id="18356-109">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="18356-109">.NET 5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="18356-110">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="18356-110">Recommended action</span></span>

- <span data-ttu-id="18356-111">Aktualisieren Sie den Code, um das Übergeben ungültiger Argumente zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="18356-111">Update the code to prevent passing invalid arguments.</span></span>
- <span data-ttu-id="18356-112">Verarbeiten Sie falls erforderlich eine <xref:System.ArgumentException>, wenn Sie die Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="18356-112">If necessary, handle an <xref:System.ArgumentException> when calling the method.</span></span>

#### <a name="category"></a><span data-ttu-id="18356-113">Kategorie</span><span class="sxs-lookup"><span data-stu-id="18356-113">Category</span></span>

<span data-ttu-id="18356-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="18356-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="18356-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="18356-115">Affected APIs</span></span>

<span data-ttu-id="18356-116">In der folgenden Tabelle sind die betroffenen Methoden und Parameter aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="18356-116">The following table lists the affected methods and parameters:</span></span>

| <span data-ttu-id="18356-117">Methode</span><span class="sxs-lookup"><span data-stu-id="18356-117">Method</span></span> | <span data-ttu-id="18356-118">Parametername</span><span class="sxs-lookup"><span data-stu-id="18356-118">Parameter name</span></span> | <span data-ttu-id="18356-119">Bedingung</span><span class="sxs-lookup"><span data-stu-id="18356-119">Condition</span></span> | <span data-ttu-id="18356-120">Hinzugefügte Version</span><span class="sxs-lookup"><span data-stu-id="18356-120">Version added</span></span> |
|-|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | <span data-ttu-id="18356-121">Das Argument ist nicht vom Typ <xref:System.Windows.Forms.TabPage>.</span><span class="sxs-lookup"><span data-stu-id="18356-121">Argument is not of type <xref:System.Windows.Forms.TabPage>.</span></span> | <span data-ttu-id="18356-122">Vorschauversion 1</span><span class="sxs-lookup"><span data-stu-id="18356-122">Preview 1</span></span> |
| <xref:System.Windows.Forms.DataFormats.GetFormat(System.String)?displayProperty=fullName> | `format` | <span data-ttu-id="18356-123">Das Argument ist `null`, <xref:System.String.Empty?displayProperty=nameWithType> oder Leerraum.</span><span class="sxs-lookup"><span data-stu-id="18356-123">Argument is `null`, <xref:System.String.Empty?displayProperty=nameWithType>, or white space.</span></span> | <span data-ttu-id="18356-124">Preview 5</span><span class="sxs-lookup"><span data-stu-id="18356-124">Preview 5</span></span> |
| <xref:System.Windows.Forms.InputLanguageChangedEventArgs.%23ctor(System.Globalization.CultureInfo,System.Byte)> | `culture` | <span data-ttu-id="18356-125">`InputLanguage` kann für die angegebene Kultur nicht abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="18356-125">Unable to retrieve an `InputLanguage` for the specified culture.</span></span> | <span data-ttu-id="18356-126">Preview 7</span><span class="sxs-lookup"><span data-stu-id="18356-126">Preview 7</span></span> |

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`
- `M:System.Windows.Forms.DataFormats.GetFormat(System.String)`
- `M:System.Windows.Forms.InputLanguageChangedEventArgs.%23ctor(System.Globalization.CultureInfo,System.Byte)`

-->

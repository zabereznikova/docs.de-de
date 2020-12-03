---
title: 'Breaking Change: WinForms-Methoden lösen jetzt ArgumentException aus.'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, durch den einige Windows Forms-Methoden nun eine ArgumentException-Ausnahme für ungültige Argumente auslösen.
ms.date: 07/18/2020
ms.openlocfilehash: 46fe3f3b1208a5cd676e1b7546507bed36a850f2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759564"
---
# <a name="winforms-methods-now-throw-argumentexception"></a><span data-ttu-id="5e2ef-103">WinForms-Methoden lösen jetzt ArgumentException aus.</span><span class="sxs-lookup"><span data-stu-id="5e2ef-103">WinForms methods now throw ArgumentException</span></span>

<span data-ttu-id="5e2ef-104">Einige Windows Forms-Methoden lösen nun eine <xref:System.ArgumentException> für ungültige Argumente aus, was zuvor nicht der Fall war.</span><span class="sxs-lookup"><span data-stu-id="5e2ef-104">Some Windows Forms methods now throw an <xref:System.ArgumentException> for invalid arguments, where previously they did not.</span></span>

## <a name="change-description"></a><span data-ttu-id="5e2ef-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="5e2ef-105">Change description</span></span>

<span data-ttu-id="5e2ef-106">Zuvor führte das Übergeben von Argumenten eines unerwarteten oder falschen Typs an bestimmte Windows Forms-Methoden zu einem unbestimmten Zustand.</span><span class="sxs-lookup"><span data-stu-id="5e2ef-106">Previously, passing arguments of an unexpected or incorrect type to certain Windows Forms methods would result in an indeterminate state.</span></span> <span data-ttu-id="5e2ef-107">Ab .NET 5.0 lösen diese Methoden stattdessen eine <xref:System.ArgumentException> aus, wenn ungültige Argumente übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="5e2ef-107">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentException> when passed invalid arguments.</span></span>

<span data-ttu-id="5e2ef-108">Das Auslösen einer <xref:System.ArgumentException>-Ausnahme entspricht dem Verhalten der .NET Runtime.</span><span class="sxs-lookup"><span data-stu-id="5e2ef-108">Throwing an <xref:System.ArgumentException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="5e2ef-109">Außerdem wird die Debugfunktion verbessert, indem ausdrücklich kommuniziert wird, welches Argument ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="5e2ef-109">It also improves the debugging experience by clearly communicating which argument is invalid.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="5e2ef-110">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="5e2ef-110">Version introduced</span></span>

<span data-ttu-id="5e2ef-111">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="5e2ef-111">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="5e2ef-112">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="5e2ef-112">Recommended action</span></span>

- <span data-ttu-id="5e2ef-113">Aktualisieren Sie den Code, um das Übergeben ungültiger Argumente zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="5e2ef-113">Update the code to prevent passing invalid arguments.</span></span>
- <span data-ttu-id="5e2ef-114">Verarbeiten Sie falls erforderlich eine <xref:System.ArgumentException>, wenn Sie die Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="5e2ef-114">If necessary, handle an <xref:System.ArgumentException> when calling the method.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="5e2ef-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="5e2ef-115">Affected APIs</span></span>

<span data-ttu-id="5e2ef-116">In der folgenden Tabelle sind die betroffenen Methoden und Parameter aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="5e2ef-116">The following table lists the affected methods and parameters:</span></span>

| <span data-ttu-id="5e2ef-117">Methode</span><span class="sxs-lookup"><span data-stu-id="5e2ef-117">Method</span></span> | <span data-ttu-id="5e2ef-118">Parametername</span><span class="sxs-lookup"><span data-stu-id="5e2ef-118">Parameter name</span></span> | <span data-ttu-id="5e2ef-119">Bedingung</span><span class="sxs-lookup"><span data-stu-id="5e2ef-119">Condition</span></span> | <span data-ttu-id="5e2ef-120">Hinzugefügte Version</span><span class="sxs-lookup"><span data-stu-id="5e2ef-120">Version added</span></span> |
|-|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | <span data-ttu-id="5e2ef-121">Das Argument ist nicht vom Typ <xref:System.Windows.Forms.TabPage>.</span><span class="sxs-lookup"><span data-stu-id="5e2ef-121">Argument is not of type <xref:System.Windows.Forms.TabPage>.</span></span> | <span data-ttu-id="5e2ef-122">Vorschauversion 1</span><span class="sxs-lookup"><span data-stu-id="5e2ef-122">Preview 1</span></span> |
| <xref:System.Windows.Forms.DataFormats.GetFormat(System.String)?displayProperty=fullName> | `format` | <span data-ttu-id="5e2ef-123">Das Argument ist `null`, <xref:System.String.Empty?displayProperty=nameWithType> oder Leerraum.</span><span class="sxs-lookup"><span data-stu-id="5e2ef-123">Argument is `null`, <xref:System.String.Empty?displayProperty=nameWithType>, or white space.</span></span> | <span data-ttu-id="5e2ef-124">Preview 5</span><span class="sxs-lookup"><span data-stu-id="5e2ef-124">Preview 5</span></span> |
| <xref:System.Windows.Forms.InputLanguageChangedEventArgs.%23ctor(System.Globalization.CultureInfo,System.Byte)> | `culture` | <span data-ttu-id="5e2ef-125">`InputLanguage` kann für die angegebene Kultur nicht abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5e2ef-125">Unable to retrieve an `InputLanguage` for the specified culture.</span></span> | <span data-ttu-id="5e2ef-126">Preview 7</span><span class="sxs-lookup"><span data-stu-id="5e2ef-126">Preview 7</span></span> |

<!--

### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`
- `M:System.Windows.Forms.DataFormats.GetFormat(System.String)`
- `M:System.Windows.Forms.InputLanguageChangedEventArgs.%23ctor(System.Globalization.CultureInfo,System.Byte)`

### Category

Windows Forms

-->

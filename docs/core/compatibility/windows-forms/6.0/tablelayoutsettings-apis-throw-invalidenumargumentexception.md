---
title: 'Breaking Change: Einige TableLayoutSettings-Eigenschaften, die eine InvalidEnumArgumentException-Ausnahme auslösen'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 6.0, durch den einige TableLayoutSettings-APIs nun eine InvalidEnumArgumentException-Ausnahme für ungültige Argumente auslösen.
ms.date: 01/18/2021
ms.openlocfilehash: 8397952e4647347718f11597a100c5d764e7186b
ms.sourcegitcommit: f8cd3ef517ee177c99feed944824c27d208cc0d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2021
ms.locfileid: "98570239"
---
# <a name="selected-tablelayoutsettings-properties-throw-invalidenumargumentexception"></a><span data-ttu-id="0f631-103">Ausgewählten TableLayoutSettings-Eigenschaften, die eine InvalidEnumArgumentException-Ausnahme auslösen</span><span class="sxs-lookup"><span data-stu-id="0f631-103">Selected TableLayoutSettings properties throw InvalidEnumArgumentException</span></span>

<span data-ttu-id="0f631-104">Ausgewählte <xref:System.Windows.Forms.TableLayoutSettings>-Eigenschaften lösen jetzt eine <xref:System.ComponentModel.InvalidEnumArgumentException> aus, wenn Sie versuchen, einen falschen Wert zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="0f631-104">Selected <xref:System.Windows.Forms.TableLayoutSettings> properties now throw an <xref:System.ComponentModel.InvalidEnumArgumentException> if you attempt to assign an incorrect value.</span></span>

## <a name="change-description"></a><span data-ttu-id="0f631-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="0f631-105">Change description</span></span>

<span data-ttu-id="0f631-106">In früheren Versionen von .NET haben diese Eigenschaften eine <xref:System.ArgumentOutOfRangeException> ausgelöst, wenn versucht wurde, einen falschen Wert zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="0f631-106">In previous .NET versions, these properties throw an <xref:System.ArgumentOutOfRangeException> if you attempt to assign an incorrect value.</span></span> <span data-ttu-id="0f631-107">Ab .NET 6.0 lösen diese Eigenschaften in solchen Fällen eine <xref:System.ComponentModel.InvalidEnumArgumentException> aus.</span><span class="sxs-lookup"><span data-stu-id="0f631-107">Starting in .NET 6.0, these properties throw an <xref:System.ComponentModel.InvalidEnumArgumentException> in such cases.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="0f631-108">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="0f631-108">Reason for change</span></span>

<span data-ttu-id="0f631-109">Das Auslösen von <xref:System.ComponentModel.InvalidEnumArgumentException> ist in ähnlichen Situationen mit der vorhandenen Windows Forms-API identisch.</span><span class="sxs-lookup"><span data-stu-id="0f631-109">Throwing <xref:System.ComponentModel.InvalidEnumArgumentException> is in line with the existing Windows Forms API in similar situations.</span></span> <span data-ttu-id="0f631-110">Durch das Auslösen dieser Ausnahme wird für Entwickler auch das Debuggen verbessert.</span><span class="sxs-lookup"><span data-stu-id="0f631-110">Throwing this exception also provides developers with a better debug experience.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="0f631-111">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="0f631-111">Version introduced</span></span>

<span data-ttu-id="0f631-112">.NET 6.0</span><span class="sxs-lookup"><span data-stu-id="0f631-112">.NET 6.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="0f631-113">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="0f631-113">Recommended action</span></span>

- <span data-ttu-id="0f631-114">Aktualisieren Sie den Code, um zu verhindern, dass falsche Werte zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="0f631-114">Update the code to prevent assigning incorrect values.</span></span>
- <span data-ttu-id="0f631-115">Verarbeiten Sie ggf. eine <xref:System.ComponentModel.InvalidEnumArgumentException>, wenn Sie auf diese APIs zugreifen.</span><span class="sxs-lookup"><span data-stu-id="0f631-115">If necessary, handle an <xref:System.ComponentModel.InvalidEnumArgumentException> when accessing these APIs.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="0f631-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="0f631-116">Affected APIs</span></span>

<span data-ttu-id="0f631-117">In der folgenden Tabelle sind die betroffenen Eigenschaften aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="0f631-117">The following table lists the affected properties:</span></span>

| <span data-ttu-id="0f631-118">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="0f631-118">Property</span></span> | <span data-ttu-id="0f631-119">Version geändert</span><span class="sxs-lookup"><span data-stu-id="0f631-119">Version changed</span></span> |
|-|-|-|-|
| <xref:System.Windows.Forms.TableLayoutPanel.CellBorderStyle?displayProperty=fullName> | <span data-ttu-id="0f631-120">Vorschauversion 1</span><span class="sxs-lookup"><span data-stu-id="0f631-120">Preview 1</span></span> |
| <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle?displayProperty=fullName> | <span data-ttu-id="0f631-121">Vorschauversion 1</span><span class="sxs-lookup"><span data-stu-id="0f631-121">Preview 1</span></span> |

<!--

### Affected APIs

- `P:System.Windows.Forms.TableLayoutPanel.CellBorderStyle`
- `P:System.Windows.Forms.TableLayoutPanel.GrowStyle`

### Category

Windows Forms

-->

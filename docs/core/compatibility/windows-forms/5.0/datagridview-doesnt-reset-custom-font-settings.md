---
title: 'Breaking Change: DataGridView setzt Schriftarten für angepasste Zelltypen nicht mehr zurück'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, durch den DataGridView Standardschriftarten in Zellenstilen nicht mehr so zurücksetzt, dass sie mit der Umgebungsschriftart übereinstimmen, wenn die Schriftart des Zellenstils angepasst wurde.
ms.date: 10/18/2020
ms.openlocfilehash: 708b12ba1305681f5c38eb605861d02e3b2c8eb1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759565"
---
# <a name="datagridview-no-longer-resets-fonts-for-customized-cell-styles"></a><span data-ttu-id="79f92-103">DataGridView setzt Schriftarten für angepasste Zelltypen nicht mehr zurück</span><span class="sxs-lookup"><span data-stu-id="79f92-103">DataGridView no longer resets fonts for customized cell styles</span></span>

<span data-ttu-id="79f92-104">Wenn die Umgebungsschriftart geändert wird, setzt <xref:System.Windows.Forms.DataGridViewElement.DataGridView> Standardschriftarten für Zelltypen nicht mehr so zurück, dass die Schriftarten übereinstimmen, wenn die Schriftart des Zellenstils angepasst wurde.</span><span class="sxs-lookup"><span data-stu-id="79f92-104">When the ambient font changes, <xref:System.Windows.Forms.DataGridViewElement.DataGridView> no longer resets default cell style fonts to match the ambient font if the cell style font has been customized.</span></span>

## <a name="change-description"></a><span data-ttu-id="79f92-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="79f92-105">Change description</span></span>

<span data-ttu-id="79f92-106">Wenn in früheren .NET-Versionen die Umgebungsschriftart geändert wurde, wurden benutzerdefinierte Schriftarten in den Eigenschaften <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle> und <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> von <xref:System.Windows.Forms.DataGridViewElement.DataGridView> zurückgesetzt und überschrieben.</span><span class="sxs-lookup"><span data-stu-id="79f92-106">In previous .NET versions, if the ambient font changes, <xref:System.Windows.Forms.DataGridViewElement.DataGridView> resets and overrides user-defined fonts in the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle>, and <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> properties.</span></span>

<span data-ttu-id="79f92-107">Wenn Sie Schriftarteinstellungen in den Eigenschaften <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle> oder <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> ab .NET 5.0 konfigurieren, werden diese Eigenschaften beibehalten, auch wenn die Umgebungsschriftart geändert wird.</span><span class="sxs-lookup"><span data-stu-id="79f92-107">Starting in .NET 5.0, if you configure font settings in the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle>, or <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> properties, those settings are retained even when the ambient font changes.</span></span> <span data-ttu-id="79f92-108">Bei allen diesen Eigenschaften, deren Schriftart Sie nicht anpassen, wird die Schriftart so geändert, dass sie mit den Einstellungen der Umgebungsschriftart übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="79f92-108">For any of these properties that you don't customize the font, the font will change to match the ambient font settings.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="79f92-109">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="79f92-109">Reason for change</span></span>

<span data-ttu-id="79f92-110">Zusammen mit der [Änderung der Standardschriftart in .NET Core 3.0](../../winforms.md#default-control-font-changed-to-segoe-ui-9-pt) wurden die Standardschriftarteinstellungen für die verschiedenen Zellstile ebenfalls geändert.</span><span class="sxs-lookup"><span data-stu-id="79f92-110">With the [change of the default font in .NET Core 3.0](../../winforms.md#default-control-font-changed-to-segoe-ui-9-pt), the default font settings for the various cell styles also changed.</span></span> <span data-ttu-id="79f92-111">Dieses Verhalten ist für Apps jedoch nicht wünschenswert, bei denen der Stil der <xref:System.Windows.Forms.DataGridViewElement.DataGridView>-Steuerelemente benutzerdefiniert festgelegt wird. Außerdem wurde die Migration dieser Apps vom .NET Framework zu .NET 5.0 dadurch behindert.</span><span class="sxs-lookup"><span data-stu-id="79f92-111">This behavior is undesirable for apps that rely on custom styling in their <xref:System.Windows.Forms.DataGridViewElement.DataGridView> controls, and impeded the migration of these apps from .NET Framework to .NET 5.0.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="79f92-112">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="79f92-112">Version introduced</span></span>

<span data-ttu-id="79f92-113">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="79f92-113">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="79f92-114">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="79f92-114">Recommended action</span></span>

<span data-ttu-id="79f92-115">Ihrerseits müssen Sie nichts tun.</span><span class="sxs-lookup"><span data-stu-id="79f92-115">No action is required on your part.</span></span> <span data-ttu-id="79f92-116">Wenn Sie die Schriftart in den Eigenschaften <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle> oder <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> jedoch angepasst haben und möchten, dass die Schriftart mit der Umgebungsschriftart übereinstimmt, legen Sie für jede der Eigenschaften <xref:System.Windows.Forms.DataGridViewCellStyle.Font?displayProperty=nameWithType> auf `null` fest.</span><span class="sxs-lookup"><span data-stu-id="79f92-116">However, if you've customized the font in the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle>, or <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> properties and want the font to match the ambient font, set <xref:System.Windows.Forms.DataGridViewCellStyle.Font?displayProperty=nameWithType> to `null` for each property.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="79f92-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="79f92-117">Affected APIs</span></span>

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle?displayProperty=fullName>

<!--

### Affected APIs

- `P:System.Windows.Forms.DataGridView.DefaultCellStyle`
- `P:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle`
- `P:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle`

### Category

- Windows Forms

-->

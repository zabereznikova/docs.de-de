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
# <a name="datagridview-no-longer-resets-fonts-for-customized-cell-styles"></a>DataGridView setzt Schriftarten für angepasste Zelltypen nicht mehr zurück

Wenn die Umgebungsschriftart geändert wird, setzt <xref:System.Windows.Forms.DataGridViewElement.DataGridView> Standardschriftarten für Zelltypen nicht mehr so zurück, dass die Schriftarten übereinstimmen, wenn die Schriftart des Zellenstils angepasst wurde.

## <a name="change-description"></a>Änderungsbeschreibung

Wenn in früheren .NET-Versionen die Umgebungsschriftart geändert wurde, wurden benutzerdefinierte Schriftarten in den Eigenschaften <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle> und <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> von <xref:System.Windows.Forms.DataGridViewElement.DataGridView> zurückgesetzt und überschrieben.

Wenn Sie Schriftarteinstellungen in den Eigenschaften <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle> oder <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> ab .NET 5.0 konfigurieren, werden diese Eigenschaften beibehalten, auch wenn die Umgebungsschriftart geändert wird. Bei allen diesen Eigenschaften, deren Schriftart Sie nicht anpassen, wird die Schriftart so geändert, dass sie mit den Einstellungen der Umgebungsschriftart übereinstimmt.

## <a name="reason-for-change"></a>Grund für die Änderung

Zusammen mit der [Änderung der Standardschriftart in .NET Core 3.0](../../winforms.md#default-control-font-changed-to-segoe-ui-9-pt) wurden die Standardschriftarteinstellungen für die verschiedenen Zellstile ebenfalls geändert. Dieses Verhalten ist für Apps jedoch nicht wünschenswert, bei denen der Stil der <xref:System.Windows.Forms.DataGridViewElement.DataGridView>-Steuerelemente benutzerdefiniert festgelegt wird. Außerdem wurde die Migration dieser Apps vom .NET Framework zu .NET 5.0 dadurch behindert.

## <a name="version-introduced"></a>Eingeführt in Version

.NET 5.0

## <a name="recommended-action"></a>Empfohlene Maßnahme

Ihrerseits müssen Sie nichts tun. Wenn Sie die Schriftart in den Eigenschaften <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle> oder <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> jedoch angepasst haben und möchten, dass die Schriftart mit der Umgebungsschriftart übereinstimmt, legen Sie für jede der Eigenschaften <xref:System.Windows.Forms.DataGridViewCellStyle.Font?displayProperty=nameWithType> auf `null` fest.

## <a name="affected-apis"></a>Betroffene APIs

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

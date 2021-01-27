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
# <a name="selected-tablelayoutsettings-properties-throw-invalidenumargumentexception"></a>Ausgewählten TableLayoutSettings-Eigenschaften, die eine InvalidEnumArgumentException-Ausnahme auslösen

Ausgewählte <xref:System.Windows.Forms.TableLayoutSettings>-Eigenschaften lösen jetzt eine <xref:System.ComponentModel.InvalidEnumArgumentException> aus, wenn Sie versuchen, einen falschen Wert zuzuweisen.

## <a name="change-description"></a>Änderungsbeschreibung

In früheren Versionen von .NET haben diese Eigenschaften eine <xref:System.ArgumentOutOfRangeException> ausgelöst, wenn versucht wurde, einen falschen Wert zuzuweisen. Ab .NET 6.0 lösen diese Eigenschaften in solchen Fällen eine <xref:System.ComponentModel.InvalidEnumArgumentException> aus.

## <a name="reason-for-change"></a>Grund für die Änderung

Das Auslösen von <xref:System.ComponentModel.InvalidEnumArgumentException> ist in ähnlichen Situationen mit der vorhandenen Windows Forms-API identisch. Durch das Auslösen dieser Ausnahme wird für Entwickler auch das Debuggen verbessert.

## <a name="version-introduced"></a>Eingeführt in Version

.NET 6.0

## <a name="recommended-action"></a>Empfohlene Maßnahme

- Aktualisieren Sie den Code, um zu verhindern, dass falsche Werte zugewiesen werden.
- Verarbeiten Sie ggf. eine <xref:System.ComponentModel.InvalidEnumArgumentException>, wenn Sie auf diese APIs zugreifen.

## <a name="affected-apis"></a>Betroffene APIs

In der folgenden Tabelle sind die betroffenen Eigenschaften aufgeführt:

| Eigenschaft | Version geändert |
|-|-|-|-|
| <xref:System.Windows.Forms.TableLayoutPanel.CellBorderStyle?displayProperty=fullName> | Vorschauversion 1 |
| <xref:System.Windows.Forms.TableLayoutPanel.GrowStyle?displayProperty=fullName> | Vorschauversion 1 |

<!--

### Affected APIs

- `P:System.Windows.Forms.TableLayoutPanel.CellBorderStyle`
- `P:System.Windows.Forms.TableLayoutPanel.GrowStyle`

### Category

Windows Forms

-->

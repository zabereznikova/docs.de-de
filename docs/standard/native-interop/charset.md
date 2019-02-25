---
title: Zeichensätze und Marshalling – .NET
description: Erfahren Sie, wie die verschiedenen Werte des Zeichensatzes die Vorgehensweise ändern, wie .NET Ihre Daten in nativen Code marshallt.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: 2ff6c485906db481cb5236f83e885ba9fd46450b
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2019
ms.locfileid: "56411376"
---
# <a name="charsets-and-marshalling"></a>Zeichensätze und Marshalling

Die Art und Weise, wie `char`-Werte, `string`-Objekte und `System.Text.StringBuilder`-Objekte gemarshallt werden, hängt vom Wert im Feld `CharSet` in P/Invoke oder der Struktur ab. Sie können den `CharSet` von P/Invoke festlegen, indem Sie beim Deklarieren von P/Invoke das Feld <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> bestimmen. Um den `CharSet` für eine Struktur festzulegen, bestimmen Sie das Feld <xref:System.Runtime.InteropServices.StructLayoutAttribute.CharSet?displayProperty=nameWithType> in Ihrer Strukturdeklaration. Wenn diese Attributfelder nicht festgelegt sind, bestimmt der Sprachcompiler, welcher `CharSet` verwendet wird. C# verwendet standardmäßig den Zeichensatz <xref:System.Runtime.InteropServices.CharSet.Ansi>.

Die folgende Tabelle zeigt eine Zuordnung zwischen den einzelnen Zeichensätzen und wie ein Zeichen oder eine Zeichenkette dargestellt wird, wenn sie mit diesem Zeichensatz gemarshallt wird:

| CharSet | Windows | Unix | Mono unter Unix |
|---------|---------|-------|-------|
| Ansi    | `char` (ANSI)  | `char` (ANSI unter macOS, UTF-8 für Linux) | `char` (UTF-8) |
| Unicode | `wchar_t` (UTF-16) | `char16_t` (UTF-16) | `char16_t` (UTF-16) |
| Auto | `wchar_t` (UTF-16) | `char16_t` (UTF-16) | `char` (UTF-8) |

Stellen Sie sicher, dass Sie wissen, welche Darstellung Ihre native Darstellung erwartet, wenn Sie Ihren Zeichensatz auswählen.

---
title: Zeichensätze und Marshalling – .NET
description: Erfahren Sie, wie die verschiedenen Werte des Zeichensatzes die Vorgehensweise ändern, wie .NET Ihre Daten in nativen Code marshallt.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: c50c58ad639b1efb29c13e5124fe3c32e8af96fc
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063337"
---
# <a name="charsets-and-marshaling"></a>Zeichensätze und Marshalling

Die Art und Weise, wie `char`-Werte, `string`-Objekte und `System.Text.StringBuilder`-Objekte gemarshallt werden, hängt vom Wert im Feld `CharSet` in P/Invoke oder der Struktur ab. Sie können den `CharSet` von P/Invoke festlegen, indem Sie beim Deklarieren von P/Invoke das Feld <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> bestimmen. Um den `CharSet` für eine Struktur festzulegen, bestimmen Sie das Feld <xref:System.Runtime.InteropServices.StructLayoutAttribute.CharSet?displayProperty=nameWithType> in Ihrer Strukturdeklaration. Wenn diese Attributfelder nicht festgelegt sind, bestimmt der Sprachcompiler, welcher `CharSet` verwendet wird. C# und VB verwenden standardmäßig den Zeichensatz <xref:System.Runtime.InteropServices.CharSet.Ansi>.

Die folgende Tabelle zeigt eine Zuordnung zwischen den einzelnen Zeichensätzen und wie ein Zeichen oder eine Zeichenkette dargestellt wird, wenn sie mit diesem Zeichensatz gemarshallt wird:

| `CharSet`-Wert | Windows            | .NET Core 2.2 und früher unter Unix | .NET Core 3.0 und höher und Mono unter Unix |
|-----------------|--------------------|-----------------------------------|------------------------------------------|
| Ansi            | `char` (ANSI)      | `char` (UTF-8)                    | `char` (UTF-8)                           |
| Unicode         | `wchar_t` (UTF-16) | `char16_t` (UTF-16)               | `char16_t` (UTF-16)                      |
| Auto            | `wchar_t` (UTF-16) | `char16_t` (UTF-16)               | `char` (UTF-8)                           |

Stellen Sie sicher, dass Sie wissen, welche Darstellung Ihre native Darstellung erwartet, wenn Sie Ihren Zeichensatz auswählen.

---
title: Zeichensätze und Marshalling – .NET
description: Erfahren Sie, wie die verschiedenen Werte des Zeichensatzes die Vorgehensweise ändern, wie .NET Ihre Daten in nativen Code marshallt.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: a29d53f8e422da1a78e131110972d83987c5464a
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337924"
---
# <a name="charsets-and-marshaling"></a>Zeichensätze und Marshalling

Die Art und Weise, wie `char`-Werte, `string`-Objekte und `System.Text.StringBuilder`-Objekte gemarshallt werden, hängt vom Wert im Feld `CharSet` in P/Invoke oder der Struktur ab. Sie können den `CharSet` von P/Invoke festlegen, indem Sie beim Deklarieren von P/Invoke das Feld <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> bestimmen. Wenn Sie die `CharSet` für einen Typ festlegen möchten, legen Sie das <xref:System.Runtime.InteropServices.StructLayoutAttribute.CharSet?displayProperty=nameWithType> Feld für die Klassen-oder Struktur Deklaration fest. Wenn diese Attributfelder nicht festgelegt sind, bestimmt der Sprachcompiler, welcher `CharSet` verwendet wird. C#und Visual Basic die <xref:System.Runtime.InteropServices.CharSet.Ansi> charset standardmäßig verwenden.

Die folgende Tabelle zeigt eine Zuordnung zwischen den einzelnen Zeichensätzen und wie ein Zeichen oder eine Zeichenkette dargestellt wird, wenn sie mit diesem Zeichensatz gemarshallt wird:

| `CharSet`-Wert | Windows            | .NET Core 2.2 und früher unter Unix | .NET Core 3.0 und höher und Mono unter Unix |
|-----------------|--------------------|-----------------------------------|------------------------------------------|
| Ansi            | `char` (die standardmäßige [Windows-ANSI-Codepage des Systems](/windows/win32/intl/code-pages))      | `char` (UTF-8)                    | `char` (UTF-8)                           |
| Unicode         | `wchar_t` (UTF-16) | `char16_t` (UTF-16)               | `char16_t` (UTF-16)                      |
| Automatisch            | `wchar_t` (UTF-16) | `char16_t` (UTF-16)               | `char` (UTF-8)                           |

Stellen Sie sicher, dass Sie wissen, welche Darstellung Ihre native Darstellung erwartet, wenn Sie Ihren Zeichensatz auswählen.

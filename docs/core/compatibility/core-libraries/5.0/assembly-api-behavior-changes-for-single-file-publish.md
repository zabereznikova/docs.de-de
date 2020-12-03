---
title: 'Breaking Change: Assemblybezogene Behavior Changes für Veröffentlichungsformat mit einzelner Datei'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, durch den mehrere auf den Speicherort der Assemblydatei bezogene APIs Behavior Changes aufweisen, wenn sie in einem Veröffentlichungsformat mit einzelner Datei aufgerufen werden.
ms.date: 11/01/2020
ms.openlocfilehash: d77e30318040c8298065073a41caab56f2ca3875
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759470"
---
# <a name="assembly-related-api-behavior-changes-for-single-file-publishing-format"></a>Assemblybezogene Behavior Changes für Veröffentlichungsformat mit einzelner Datei

Mehrere auf den Speicherort der Assemblydatei bezogene APIs weisen Behavior Changes auf, wenn sie in einem Veröffentlichungsformat mit einzelner Datei aufgerufen werden.

## <a name="change-description"></a>Änderungsbeschreibung

Bei einer Veröffentlichung mit einzelner Datei für .NET 5.0 und höhere Versionen werden Assemblybundles aus dem Arbeitsspeicher geladen anstatt auf den Datenträger extrahiert zu werden. Für Apps, die als einzelne Datei veröffentlicht werden, bedeutet dies, dass bestimmte auf den Speicherort bezogene APIs verschiedene Werte für .NET 5.0 und höhere Versionen zurückgeben als ältere Versionen von .NET. Es gibt folgenden Änderungen:

| API | Vorgängerversionen | .NET 5.0 und höher |
| - | - | - |
| <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> | Gibt extrahierten DLL-Dateipfad zurück | Gibt leere Zeichenfolge für Assemblybundles zurück |
| <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType> | Gibt extrahierten DLL-Dateipfad zurück | Löst eine Ausnahme für Assemblybundles aus |
| <xref:System.Reflection.Assembly.GetFile(System.String)?displayProperty=nameWithType> | Gibt `null` für Assemblybundles zurück | Löst eine Ausnahme für Assemblybundles aus |
| `Environment.GetCommandLineArgs()[0]` | Der Wert ist der Name der Einstiegspunkt-DLL. | Der Wert ist der Name der ausführbaren Hostdatei. |
| <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> | Der Wert ist das temporäre Extraktionsverzeichnis. | Der Wert ist das Verzeichnis, das die ausführbare Hostdatei enthält. |

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="recommended-action"></a>Empfohlene Maßnahme

Vermeiden Sie Abhängigkeiten vom Speicherort der Assemblydatei, wenn die Veröffentlichung als einzelne Datei erfolgt.

## <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.GetFile(System.String)?displayProperty=nameWithType>
- <xref:System.Environment.GetCommandLineArgs?displayProperty=nameWithType>
- <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Reflection.Assembly.Location`
- `P:System.Reflection.Assembly.CodeBase`
- `M:System.Reflection.Assembly.GetFile(System.String)`
- `M:System.Environment.GetCommandLineArgs`
- `P:System.AppContext.BaseDirectory`

-->

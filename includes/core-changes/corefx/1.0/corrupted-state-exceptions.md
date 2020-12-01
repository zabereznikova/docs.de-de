---
ms.openlocfilehash: 394f2daebad7b6af94bee4d7876796e87fe8ab19
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031993"
---
### <a name="handling-corrupted-state-exceptions-is-not-supported"></a>Verarbeiten von Corrupted State Exceptions wird nicht unterstützt

Das Verarbeiten von Corrupted State Exceptions wird in .NET Core nicht unterstützt.

#### <a name="change-description"></a>Änderungsbeschreibung

Zuvor konnten Corrupted State Exceptions durch Ausnahmehandler mit verwaltetem Code abgefangen und verarbeitet werden, indem z. B. eine [try-catch](../../../../docs/csharp/language-reference/keywords/try-catch.md)-Anweisung in C# verwendet wurde.

Ab .NET Core 1.0 können Corrupted State Exceptions nicht mehr von verwaltetem Code verarbeitet werden. Die Common Language Runtime liefert keine Corrupted State Exceptions an verwalteten Code.

#### <a name="version-introduced"></a>Eingeführt in Version

1.0

#### <a name="recommended-action"></a>Empfohlene Aktion

Vermeiden Sie die Notwendigkeit einer Verarbeitung von Corrupted State Exceptions, indem Sie sich mit den Situationen befassen, die zu diesen geführt haben. Wenn es absolut notwendig ist, Corrupted State Exceptions zu verarbeiten, schreiben Sie den Ausnahmehandler in C- oder C++-Code.

#### <a name="category"></a>Kategorie

Core .NET-Bibliotheken

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=fullName>
- [legacyCorruptedStateExceptionsPolicy element](~/docs/framework/configure-apps/file-schema/runtime/legacycorruptedstateexceptionspolicy-element.md)

<!--

#### Affected APIs

- `T:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute`

-->

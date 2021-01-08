---
title: Compilerfehler und -warnungen
description: Beschreibungen und Lösungen für Fehler und Warnungen, die vom F#-Compiler ausgegeben werden
ms.date: 12/21/2019
ms.openlocfilehash: 58430297abe807027afdc52841d67d1233401ff1
ms.sourcegitcommit: e395fabeeea5c705d243d246fa64446839ac85b6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2021
ms.locfileid: "97856119"
---
# <a name="f-compiler-messages"></a>F#-Compilermeldungen

In diesem Abschnitt werden Compilerfehler und -warnungen ausführlich erläutert, die der F#-Compiler für bestimmte Konstrukte ausgibt. Die Standardfehler können wie folgt geändert werden:

- Behandeln bestimmter Warnungen mithilfe der `-warnaserror+`-Compileroption als wären diese Fehler

- Ignorieren bestimmter Warnungen mithilfe der `-nowarn`-Compileroption

Wenn eine bestimmte Warnung oder ein Fehler noch nicht in diesem Abschnitt aufgezeichnet wurde:

- Scrollen Sie zum Ende dieser Seite, und senden Sie uns Feedback, einschließlich Nummer oder Text des Fehlers.
- Fügen Sie diesen alternativ selbst hinzu, indem Sie die Anweisungen in [create-new-fsharp-compiler-message.fsx](https://github.com/dotnet/docs/blob/master/docs/fsharp/language-reference/compiler-messages/util/create-new-fsharp-compiler-message.fsx) befolgen, und öffnen Sie einen Pull Request für dieses Repository.

## <a name="see-also"></a>Siehe auch

- [F#-Compileroptionen](../compiler-options.md)

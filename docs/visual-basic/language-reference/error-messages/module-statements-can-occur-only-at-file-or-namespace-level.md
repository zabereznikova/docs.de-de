---
title: Module-Anweisungen können nur auf Namespace- oder Dateiebene verwendet werden.
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: b946a527d3de3a030ac03691c77afcf440f518ee
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160313"
---
# <a name="bc30617-module-statements-can-occur-only-at-file-or-namespace-level"></a>BC30617: "Module"-Anweisungen können nur auf Datei-oder Namespace Ebene auftreten.

`Module` -Anweisungen müssen am Anfang der Quelldatei unmittelbar nach den `Option` -und- `Imports` Anweisungen, globalen Attributen und Namespace Deklarationen, aber vor allen anderen Deklarationen angezeigt werden.

 **Fehler-ID:** BC30617

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Verschieben Sie die `Module` -Anweisung an den Anfang der Namespacedeklaration oder Quelldatei.

## <a name="see-also"></a>Siehe auch

- [Module-Anweisung](../statements/module-statement.md)

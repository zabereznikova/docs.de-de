---
title: Module-Anweisungen können nur auf Namespace- oder Dateiebene verwendet werden.
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: 91e6c81bb64c259411cbef8a36629b8b320ea584
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873757"
---
# <a name="module-statements-can-occur-only-at-file-or-namespace-level"></a>Module-Anweisungen können nur auf Namespace- oder Dateiebene verwendet werden.

`Module` -Anweisungen müssen am Anfang der Quelldatei unmittelbar nach den `Option` -und- `Imports` Anweisungen, globalen Attributen und Namespace Deklarationen, aber vor allen anderen Deklarationen angezeigt werden.  
  
 **Fehler-ID:** BC30617  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Verschieben Sie die `Module` -Anweisung an den Anfang der Namespacedeklaration oder Quelldatei.  
  
## <a name="see-also"></a>Weitere Informationen

- [Module-Anweisung](../statements/module-statement.md)

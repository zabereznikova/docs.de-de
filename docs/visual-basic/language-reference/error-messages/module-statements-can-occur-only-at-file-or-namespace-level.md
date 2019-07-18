---
title: Module-Anweisungen können nur auf Namespace- oder Dateiebene verwendet werden.
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: fc3c102dbfe7c55e66093421bc11379d48ba000d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592098"
---
# <a name="module-statements-can-occur-only-at-file-or-namespace-level"></a>Module-Anweisungen können nur auf Namespace- oder Dateiebene verwendet werden.
`Module` -Anweisungen müssen am Anfang der Quelldatei angezeigt werden unmittelbar nach `Option` und `Imports` Anweisungen, globalen Attributen und Namespacedeklarationen, aber vor allen anderen Deklarationen.  
  
 **Fehler-ID:** BC30617  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Verschieben Sie die `Module` -Anweisung an den Anfang der Namespacedeklaration oder Quelldatei.  
  
## <a name="see-also"></a>Siehe auch

- [Module-Anweisung](../../../visual-basic/language-reference/statements/module-statement.md)

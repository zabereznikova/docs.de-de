---
title: Eine Anweisung kann keinen Block außerhalb einer "If"-Zeilenanweisung beenden.
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 3fe3faaa3637446bb6ab443ba1d6e1d1004b4d48
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400317"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-if-statement"></a>Eine Anweisung kann keinen Block außerhalb einer "If"-Zeilenanweisung beenden.
Eine einzeilige `If` Anweisung enthält mehrere durch Doppelpunkte getrennte Anweisungen (:), von denen eine eine- `End` Anweisung für einen Kontroll Block außerhalb der einzeiligen ist `If` . Einzeilige `If` Anweisungen verwenden nicht die- `End If` Anweisung.  
  
 **Fehler-ID:** BC32005  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Verschieben Sie die einzeilige `If` Anweisung außerhalb des Kontroll Blocks, der die- `End If` Anweisung enthält.  
  
## <a name="see-also"></a>Weitere Informationen

- [If...Then...Else-Anweisung](../statements/if-then-else-statement.md)

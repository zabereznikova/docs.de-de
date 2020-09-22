---
title: Eine Anweisung kann keinen Block außerhalb einer "If"-Zeilenanweisung beenden.
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 5e75c29e57a9c04c66e6bca79d99bb18c513f667
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870734"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-if-statement"></a>Eine Anweisung kann keinen Block außerhalb einer "If"-Zeilenanweisung beenden.

Eine einzeilige `If` Anweisung enthält mehrere durch Doppelpunkte getrennte Anweisungen (:), von denen eine eine- `End` Anweisung für einen Kontroll Block außerhalb der einzeiligen ist `If` . Einzeilige `If` Anweisungen verwenden nicht die- `End If` Anweisung.  
  
 **Fehler-ID:** BC32005  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Verschieben Sie die einzeilige `If` Anweisung außerhalb des Kontroll Blocks, der die- `End If` Anweisung enthält.  
  
## <a name="see-also"></a>Weitere Informationen

- [If...Then...Else-Anweisung](../statements/if-then-else-statement.md)

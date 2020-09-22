---
title: Let-Prozedur der Eigenschaft ist nicht definiert, und Get-Prozedur hat kein Objekt zurückgegeben.
ms.date: 07/20/2015
f1_keywords:
- vbrID451
ms.assetid: 8542382a-689f-4e1b-abc0-c1e2dadb92f4
ms.openlocfilehash: fbeaa224ea9e095f86c37e571492d83bc98b4397
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871087"
---
# <a name="property-let-procedure-not-defined-and-property-get-procedure-did-not-return-an-object"></a>Let-Prozedur der Eigenschaft ist nicht definiert, und Get-Prozedur hat kein Objekt zurückgegeben.

Bestimmte Eigenschaften, Methoden und Vorgänge können nur auf Objekte angewendet werden `Collection` . Sie haben einen Vorgang oder eine Eigenschaft angegeben, der für Sammlungen exklusiv ist, aber das Objekt ist keine Auflistung.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Überprüfen Sie die Schreibweise des Objekt-oder Eigenschafts namens, oder überprüfen Sie, ob das Objekt ein- `Collection` Objekt ist.  
  
2. Sehen Sie sich die Methode an, die zum `Add` Hinzufügen des Objekts zur Auflistung verwendet wird, um sicherzustellen, dass die Syntax korrekt ist und dass alle Bezeichner richtig geschrieben wurden.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.Collection>

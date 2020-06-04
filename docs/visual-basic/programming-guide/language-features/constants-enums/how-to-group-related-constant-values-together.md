---
title: 'Vorgehensweise: Gruppieren verwandter konstanter Werte'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: d2393af8b0c2b0c2e528f9908a78fbc7f182c8cf
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414439"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a>Gewusst wie: Gruppieren verwandter konstanter Werte (Visual Basic)
Eine Enumeration ist die beste Möglichkeit, Verwandte Konstanten zusammen zu gruppieren. Sie erstellen eine Enumeration mit der- `Enum` Anweisung im Deklarations Abschnitt einer Klasse oder eines Moduls. Weitere Informationen finden Sie unter Gewusst [wie: Deklarieren einer Enumeration](how-to-declare-enumerations.md).  
  
### <a name="to-group-related-constant-values"></a>Gruppieren verwandter konstanter Werte  
  
1. Schreiben Sie eine Deklaration, die eine Code Zugriffsebene, das `Enum` Schlüsselwort und einen gültigen Namen enthält. In diesem Beispiel wird die- `Private` Enumeration erstellt `temperatureValues` .  
  
     [!code-vb[VbEnumsTask#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#21)]  
  
2. Definieren Sie die Konstanten in der-Enumeration. In diesem Beispiel wird die `Public` -Enumeration erstellt, `temperatureValues` und ihre Werte werden zugewiesen.  
  
     [!code-vb[VbEnumsTask#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Enumerationen und Namensqualifikation](enumerations-and-name-qualification.md)
- [Vorgehensweise: Verweisen auf einen Enumerationsmember](how-to-refer-to-an-enumeration-member.md)
- [Situationen für die Verwendung von Enumerationen](when-to-use-an-enumeration.md)
- [Übersicht über Konstanten](constants-overview.md)
- [Konstanten und literale Datentypen](constant-and-literal-data-types.md)
- [Konstanten und Enumerationen](../../../language-reference/constants-and-enumerations.md)

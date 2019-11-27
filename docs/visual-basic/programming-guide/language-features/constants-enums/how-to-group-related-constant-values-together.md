---
title: 'Gewusst wie: Gruppieren verwandter konstanter Werte'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: 151eefee4f69e1db8ba40f91334da8a051b95732
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354031"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a>Gewusst wie: Gruppieren verwandter konstanter Werte (Visual Basic)
Eine Enumeration ist die beste Möglichkeit, Verwandte Konstanten zusammen zu gruppieren. Sie erstellen eine Enumeration mit der `Enum`-Anweisung im Deklarations Abschnitt einer Klasse oder eines Moduls. Weitere Informationen finden Sie unter Gewusst [wie: Deklarieren einer Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).  
  
### <a name="to-group-related-constant-values"></a>Gruppieren verwandter konstanter Werte  
  
1. Schreiben Sie eine Deklaration, die eine Code Zugriffsebene, das `Enum`-Schlüsselwort und einen gültigen Namen enthält. In diesem Beispiel wird die `Private`-Enumeration erstellt, `temperatureValues`.  
  
     [!code-vb[VbEnumsTask#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#21)]  
  
2. Definieren Sie die Konstanten in der-Enumeration. In diesem Beispiel werden die `Public`-Enumeration `temperatureValues` erstellt und deren Werte zugewiesen.  
  
     [!code-vb[VbEnumsTask#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Gewusst wie: Verweisen auf einen Enumerationsmember](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Situationen für die Verwendung von Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [Übersicht über Konstanten](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [Konstanten und literale Datentypen](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md)

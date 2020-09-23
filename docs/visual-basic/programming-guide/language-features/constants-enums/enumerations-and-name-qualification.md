---
title: Enumerationen und Namensqualifikation
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- Imports statement [Visual Basic], namespace declarations
- declaring namespaces [Visual Basic], enumerations
- name collisions
- ambiguous names [Visual Basic], enumerations
- enumerations [Visual Basic], name qualification
- names [Visual Basic], avoiding conflicts
- namespaces [Visual Basic], declaring
- naming conflicts, enumerations
- naming conflicts, qualifying names
- declaring enumerations
- references [Visual Basic], enumeration members
- naming conventions [Visual Basic], naming conflicts
- declarations [Visual Basic], namespaces
ms.assetid: 08ba2738-df52-4140-bc55-f57c871c9b73
ms.openlocfilehash: 6e067d72e557b97f8626b148e173e3d1583f92b8
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91086269"
---
# <a name="enumerations-and-name-qualification-visual-basic"></a>Enumerationen und Namensqualifikation (Visual Basic)

Normalerweise müssen Sie beim Verweisen auf einen Member einer Enumeration den Elementnamen mit dem Enumerationsnamen qualifizieren. Wenn Sie z. b. auf das- `Sunday` Member der- `Days` Enumeration verweisen möchten, verwenden Sie die folgende Syntax:  
  
 [!code-vb[VbEnumsTask#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#18)]  
  
## <a name="using-the-imports-statement"></a>Verwenden der Imports-Anweisung  

 Sie können die Verwendung voll qualifizierter Namen vermeiden, indem Sie `Imports` dem Abschnitt Namespace Deklarationen in Ihrem Code eine-Anweisung hinzufügen, wie im folgenden Beispiel gezeigt:  
  
 [!code-vb[VbEnumsTask#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#22)]  
  
 Eine `Imports` -Anweisung importiert Namespace Namen aus referenzierten Projekten und Assemblys und innerhalb desselben Projekts wie das Modul, in dem die-Anweisung angezeigt wird. Nachdem diese Anweisung hinzugefügt wurde, können Sie ohne Qualifizierung auf Ihre Enumerationsmember verweisen, wie im folgenden Beispiel gezeigt:  
  
 [!code-vb[VbEnumsTask#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#24)]  
  
 Wenn Sie Sätze verwandter Konstanten in Enumerationen organisieren, können Sie dieselben Konstanten Namen in unterschiedlichen Kontexten verwenden. Beispielsweise können Sie in den `Days` Enumerationen und die gleichen Namen für die Wochentag-Konstanten verwenden `WorkDays` . Wenn Sie die- `Imports` Anweisung mit ihren Enumerationen verwenden, müssen Sie darauf achten, mehrdeutige Verweise zu vermeiden. Betrachten Sie das folgende Beispiel:  
  
 [!code-vb[VbEnumsTask#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#22)]  
  
 [!code-vb[VbEnumsTask#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#25)]  
  
 Wenn Sie davon ausgehen, dass `Monday` ein Member der `Days` -Enumeration und der- `Workdays` Enumeration ist, generiert dieser Code einen Compilerfehler. Um mehrdeutige Verweise zu vermeiden, wenn Sie auf eine einzelne Konstante verweisen, qualifizieren Sie den konstanten Namen durch seine Enumeration. Der folgende Code bezieht sich auf die `Saturday` Konstanten in `Days` den `WorkDays` Enumerationen und.  
  
 [!code-vb[VbEnumsTask#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#32)]  
  
## <a name="see-also"></a>Siehe auch

- [Konstanten und Enumerationen](../../../language-reference/constants-and-enumerations.md)
- [Gewusst wie: Deklarieren einer Enumeration](how-to-declare-enumerations.md)
- [Vorgehensweise: Verweisen auf einen Enumerationsmember](how-to-refer-to-an-enumeration-member.md)
- [Gewusst wie: Durchlaufen einer Enumeration in Visual Basic](how-to-iterate-through-an-enumeration.md)
- [Vorgehensweise: Bestimmen der einem Enumerationswert zugeordnete Zeichenfolge](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Situationen für die Verwendung von Enumerationen](when-to-use-an-enumeration.md)
- [Konstanten und literale Datentypen](constant-and-literal-data-types.md)
- [Enum-Anweisung](../../../language-reference/statements/enum-statement.md)
- [Imports-Anweisung (.NET-Namespace und Typ)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Datentypen](../../../language-reference/data-types/index.md)

---
title: Enumerationen und Namensqualifikation (Visual Basic)
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
ms.openlocfilehash: f0a806b040720cf6682f8a72025a0590dd4d91f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61907438"
---
# <a name="enumerations-and-name-qualification-visual-basic"></a>Enumerationen und Namensqualifikation (Visual Basic)
Wenn auf einen Member einer Enumeration zu verweisen, müssen Sie normalerweise den Membernamen, durch den Enumerationsnamen qualifizieren. Beispielsweise zum Verweisen auf die `Sunday` Mitglied Ihrer `Days` Enumeration, verwenden Sie die folgende Syntax:  
  
 [!code-vb[VbEnumsTask#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#18)]  
  
## <a name="using-the-imports-statement"></a>Verwenden der Importanweisung  
 Sie können vermeiden, verwenden vollqualifizierte Namen durch das Hinzufügen einer `Imports` Anweisung, um die Namespace-Deklarationen-Abschnitt des Codes, wie im folgenden Beispiel:  
  
 [!code-vb[VbEnumsTask#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#22)]  
  
 Ein `Imports` -Anweisung importiert Namespacenamen aus referenzierten Projekten und Assemblys, und aus dem gleichen Projekt wie das Modul, in dem die Anweisung angezeigt wird. Sobald diese Anweisung hinzugefügt wird, finden Sie in Ihrer Enumerationsmember ohne Qualifikation verwenden – wie im folgenden Beispiel gezeigt:  
  
 [!code-vb[VbEnumsTask#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#24)]  
  
 Durch das Organisieren von Sätzen verknüpfter Konstanten in Enumerationen, können Sie den gleichen Namen für Aufzählungskonstanten in unterschiedlichen Kontexten. Beispielsweise können Sie die gleichen Namen für den Wochentagskonstanten in der `Days` und `WorkDays` Enumerationen. Bei Verwendung der `Imports` Anweisung für die Enumerationen, Sie müssen darauf achten, mehrdeutige Verweise zu vermeiden. Betrachten Sie das folgende Beispiel:  
  
 [!code-vb[VbEnumsTask#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#22)]  
  
 [!code-vb[VbEnumsTask#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#25)]  
  
 Vorausgesetzt, dass `Monday` ist ein Mitglied sowohl der `Days` Enumeration und die `Workdays` Enumeration, die diesen Code wird ein Compilerfehler generiert. Um mehrdeutige Verweise zu vermeiden, beim Verweisen auf einer einzelnen Konstante, qualifizieren Sie den Namen den Konstanten mit der Auflistung. Der folgende Code bezieht sich auf die `Saturday` Konstanten in der `Days` und `WorkDays` Enumerationen.  
  
 [!code-vb[VbEnumsTask#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#32)]  
  
## <a name="see-also"></a>Siehe auch

- [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md)
- [Vorgehensweise: Deklarieren einer Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Vorgehensweise: Finden Sie in einen Enumerationsmember](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Vorgehensweise: Durchlaufen einer Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [Vorgehensweise: Bestimmen der einem Enumerationswert zugeordneten Zeichenfolge](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Situationen für die Verwendung von Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [Konstanten und literale Datentypen](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [Enum-Anweisung](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [Imports-Anweisung (.NET-Namespace und -Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Datentypen](../../../../visual-basic/language-reference/data-types/index.md)

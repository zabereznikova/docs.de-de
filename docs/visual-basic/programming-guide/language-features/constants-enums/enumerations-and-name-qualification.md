---
title: Enumerationen und Namensqualifikation (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3cb97d6a8f4b7e81f2b759010214e200ec63ff21
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="enumerations-and-name-qualification-visual-basic"></a>Enumerationen und Namensqualifikation (Visual Basic)
Beim Verweisen auf einen Member einer Enumeration müssen Sie normalerweise den Elementnamen mit dem Enumerationsnamen qualifizieren. Z. B. zum Verweisen auf die `Sunday` Mitglied Ihrer `Days` -Enumeration, würden Sie die folgende Syntax verwenden:  
  
 [!code-vb[VbEnumsTask#18](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_1.vb)]  
  
## <a name="using-the-imports-statement"></a>Verwenden die Imports-Anweisung  
 Sie können vermeiden, verwenden vollqualifizierte Namen durch Hinzufügen einer `Imports` Anweisung zum Namespacedeklarationsabschnitt des Codes, wie im folgenden Beispiel:  
  
 [!code-vb[VbEnumsTask#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_2.vb)]  
  
 Ein `Imports` -Anweisung importiert Namespacenamen aus referenzierten Projekten und Assemblys, und aus dem gleichen Projekt wie das Modul, in dem die Anweisung angezeigt wird. Nachdem diese Anweisung hinzugefügt wird, finden Sie in der Enumerationsmember ohne Qualifizierung, wie im folgenden Beispiel gezeigt:  
  
 [!code-vb[VbEnumsTask#24](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_3.vb)]  
  
 Organisieren Sie Sätze von verwandten Konstanten in Enumerationen, können Sie die gleichen Konstantennamen in unterschiedlichen Kontexten verwenden. Sie können z. B. die gleichen Namen für den Wochentagskonstanten in der `Days` und `WorkDays` Enumerationen. Bei Verwendung der `Imports` -Anweisung für die Enumerationen achten mehrdeutige Verweise zu vermeiden. Betrachten Sie das folgende Beispiel:  
  
 [!code-vb[VbEnumsTask#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_2.vb)]  
  
 [!code-vb[VbEnumsTask#25](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_4.vb)]  
  
 Vorausgesetzt, dass `Monday` ist ein Mitglied sowohl der `Days` Enumeration und die `Workdays` -Enumeration, mit diesem Code wird ein Compilerfehler generiert. Um mehrdeutige Verweise zu vermeiden, beim Verweisen auf einer einzelnen Konstante, qualifizieren Sie den Namen den Konstanten mit der Enumeration. Der folgende Code bezieht sich auf die `Saturday` Konstanten in der `Days` und `WorkDays` Enumerationen.  
  
 [!code-vb[VbEnumsTask#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_5.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [Vorgehensweise: Deklarieren einer Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [Gewusst wie: Verweisen auf einen Enumerationsmember](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [Vorgehensweise: Durchlaufen einer Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [Gewusst wie: Bestimmen der einem Enumerationswert zugeordnete Zeichenfolge](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [Situationen für die Verwendung von Enumerationen](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [Konstanten und literale Datentypen](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [Enum-Anweisung](../../../../visual-basic/language-reference/statements/enum-statement.md)  
 [Imports-Anweisung (.NET-Namespace und -Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md)

---
title: Situationen für die Verwendung von Enumerationen (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5ab152687f4f9e4ba6bd032ae7c1352f65af715f
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="when-to-use-an-enumeration-visual-basic"></a>Situationen für die Verwendung von Enumerationen (Visual Basic)
Enumerationen bieten eine einfache Möglichkeit zum Arbeiten mit Gruppen verwandter Konstanten. Eine Enumeration oder `Enum`, ist ein symbolischer Namen für einen Satz von Werten. Enumerationen werden als Datentypen behandelt können, und sie Sätze von Konstanten für die Verwendung mit Variablen und Eigenschaften zu erstellen.  
  
## <a name="when-to-use-an-enumeration"></a>Situationen für die Verwendung von Enumerationen  
 Wenn eine Prozedur eine begrenzte Anzahl von Variablen akzeptiert werden, sollten erwägen Sie, eine Enumeration zu verwenden. Enumerationen stellen für Code besser lesbar, insbesondere dann, wenn Sie aussagekräftige Namen verwendet werden.  
  
 Vorteile der Verwendung von Enumerationen:  
  
-   Fehler durch Transponieren oder falsch eingegebene Zahlen wird reduziert.  
  
-   Vereinfacht die Werte in der Zukunft ändern.  
  
-   Macht Code einfacher zu lesen, was bedeutet, dass es weniger wahrscheinlich ist, dass Fehler einschleichen können.  
  
-   Stellt Aufwärtskompatibilität sicher. Mit Enumerationen ist der Code weniger wahrscheinlich, dass Sie einen Fehler, wenn in der Zukunft jemand die Namen der entsprechenden Werte ändert.  
  
## <a name="naming-enumerations"></a>Benennen von Enumerationen  
 Verwenden Sie eine Benennungskonvention für Enumerationsmember. Wenn in Visual Basic einen Enumerationsmembernamen auftritt, kann eine Ausnahme ausgelöst werden, wenn andere Bibliotheken referenzierten Typ den gleichen Namen enthalten. Verwenden Sie ein eindeutiges Präfix, das die Werte aus Ihrer Anwendung oder Komponente identifiziert.  
  
 Beim Verweisen auf einen Member einer Enumeration, Sie müssen den Membernamen mit dem Enumerationsnamen qualifizieren, da sonst verwenden die `Imports` Anweisung. Weitere Informationen finden Sie unter [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
## <a name="predefined-enumerations"></a>Vordefinierte Enumerationen  
 Visual Basic bietet eine Reihe von vordefinierten Enumerationen, z. B. `FirstDayOfWeek` und `MsgBoxResult`, um Ihren Code zu vereinfachen. Eine Liste dieser finden Sie unter [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Deklarieren einer Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [Gewusst wie: Verweisen auf einen Enumerationsmember](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [Vorgehensweise: Durchlaufen einer Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [Gewusst wie: Bestimmen der einem Enumerationswert zugeordnete Zeichenfolge](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [Enum-Anweisung](../../../../visual-basic/language-reference/statements/enum-statement.md)  
 [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md)

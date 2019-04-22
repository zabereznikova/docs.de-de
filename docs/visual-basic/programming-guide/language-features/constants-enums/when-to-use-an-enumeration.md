---
title: Situationen für die Verwendung von Enumerationen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
ms.openlocfilehash: ff2d8c324aee8bbccef050c020e5392368b05b1c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58825104"
---
# <a name="when-to-use-an-enumeration-visual-basic"></a>Situationen für die Verwendung von Enumerationen (Visual Basic)
Enumerationen bieten eine einfache Möglichkeit zum Arbeiten mit Sätzen verknüpfter Konstanten. Eine Enumeration oder `Enum`, ist ein symbolische Namen für einen Satz von Werten. Enumerationen als Datentyp behandelt werden, und können sie zum Erstellen von Gruppen von Konstanten für die Verwendung mit Variablen und Eigenschaften.  
  
## <a name="when-to-use-an-enumeration"></a>Situationen für die Verwendung von Enumerationen  
 Wenn eine Prozedur eine begrenzte Anzahl von Variablen akzeptiert werden, sollten erwägen Sie, eine Enumeration zu verwenden. Enumerationen stellen für Code besser lesbar, insbesondere dann, wenn Sie aussagekräftige Namen verwendet werden.  
  
 Die Vorteile der Verwendung von Enumerationen:  
  
-   Fehler aufgrund eines Transponieren oder falsch eingegebene Zahlen wird reduziert.  
  
-   Erleichtert die Werte in der Zukunft ändern.  
  
-   Macht Code einfacher zu lesen, was bedeutet, dass es weniger wahrscheinlich ist, dass Fehler einschleichen können.  
  
-   Stellt Aufwärtskompatibilität sicher. Mit Enumerationen ist der Code weniger wahrscheinlich fehlschlägt, wenn in der Zukunft jemand die Namen der entsprechenden Werte ändert.  
  
## <a name="naming-enumerations"></a>Benennen von Enumerationen  
 Verwenden Sie eine Benennungskonvention für Enumerationsmember. Bei Visual Basic einen Enumerationsmembernamen findet, kann eine Ausnahme ausgelöst werden, wenn andere Typbibliotheken auf den gleichen Namen enthalten. Verwenden Sie ein eindeutiges Präfix, das die Werte aus Ihrer Anwendung oder Komponente identifiziert.  
  
 Wenn auf einen Member einer Enumeration verwiesen wird, Sie müssen qualifizieren Sie den Membernamen durch den Enumerationsnamen oder anderweitig verwenden die `Imports` Anweisung. Weitere Informationen finden Sie unter [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
## <a name="predefined-enumerations"></a>Vordefinierte Enumerationen  
 Visual Basic bietet eine Reihe von vordefinierten Enumerationen, z. B. `FirstDayOfWeek` und `MsgBoxResult`, um Ihren Code zu vereinfachen. Eine Liste dieser finden Sie unter [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md).  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Deklarieren einer Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Vorgehensweise: Finden Sie in einen Enumerationsmember](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Vorgehensweise: Durchlaufen einer Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [Vorgehensweise: Bestimmen der einem Enumerationswert zugeordneten Zeichenfolge](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Enum-Anweisung](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md)

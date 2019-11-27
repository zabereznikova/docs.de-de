---
title: Situationen für die Verwendung von Enumerationen
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
ms.openlocfilehash: 5daae8d487ddfe079a54e305e59e32e8ded8f65e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353960"
---
# <a name="when-to-use-an-enumeration-visual-basic"></a>Situationen für die Verwendung von Enumerationen (Visual Basic)
Enumerationen bieten eine einfache Möglichkeit, mit Sätzen verwandter Konstanten zu arbeiten. Eine Enumeration oder `Enum`ist ein symbolischer Name für einen Satz von Werten. Enumerationen werden als Datentypen behandelt, und Sie können Sie zum Erstellen von Konstanten für die Verwendung mit Variablen und Eigenschaften verwenden.  
  
## <a name="when-to-use-an-enumeration"></a>Situationen für die Verwendung von Enumerationen  
 Wenn eine Prozedur einen begrenzten Satz an Variablen akzeptiert, sollten Sie die Verwendung einer Enumeration in Erwägung gezogen. Enumerationen sorgen für klareren und besser lesbaren Code, insbesondere dann, wenn aussagekräftige Namen verwendet werden.  
  
 Zu den Vorteilen der Verwendung von Enumerationen gehören:  
  
- Reduziert Fehler, die durch das übertragen oder falsch formatiping von Zahlen verursacht werden  
  
- Erleichtert das Ändern von Werten in der Zukunft.  
  
- Vereinfacht das Lesen von Code, was bedeutet, dass es weniger wahrscheinlich ist, dass Fehler in das Skript einfließen.  
  
- Gewährleistet die Vorwärtskompatibilität. Mit Enumerationen schlägt der Code weniger wahrscheinlich fehl, wenn Sie in Zukunft die Werte ändern, die den Elementnamen entsprechen.  
  
## <a name="naming-enumerations"></a>Benennen von Enumerationen  
 Verwenden Sie eine Benennungs Konvention für Enumerationsmember. Wenn Visual Basic auf einen enumerationselementnamen stößt, wird möglicherweise eine Ausnahme ausgelöst, wenn andere Typbibliotheken, auf die verwiesen wird, denselben Namen aufweisen. Verwenden Sie ein eindeutiges Präfix, das die Werte aus der Anwendung oder Komponente identifiziert.  
  
 Wenn Sie auf einen Member einer Enumeration verweisen, müssen Sie den Elementnamen mit dem Namen der Enumeration qualifizieren, oder Sie müssen die `Imports`-Anweisung verwenden. Weitere Informationen finden Sie unter [Enumerationen und namens Qualifizierung](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
## <a name="predefined-enumerations"></a>Vordefinierte Enumerationen  
 Visual Basic bietet eine Reihe vordefinierter Enumerationen, z. b. `FirstDayOfWeek` und `MsgBoxResult`, um Ihren Code zu vereinfachen. Eine Liste dieser Informationen finden Sie unter [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md).  
  
## <a name="see-also"></a>Siehe auch

- [Gewusst wie: Deklarieren einer Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Gewusst wie: Verweisen auf einen Enumerationsmember](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Gewusst wie: Durchlaufen einer Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [Gewusst wie: Bestimmen der einem Enumerationswert zugeordnete Zeichenfolge](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Enum-Anweisung](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md)

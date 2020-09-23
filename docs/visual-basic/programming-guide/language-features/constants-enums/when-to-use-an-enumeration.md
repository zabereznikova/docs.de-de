---
title: Situationen für die Verwendung von Enumerationen
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
ms.openlocfilehash: 7b1b269a5d28d89cd491bac88fbefd4547fdc3c3
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91095628"
---
# <a name="when-to-use-an-enumeration-visual-basic"></a>Situationen für die Verwendung von Enumerationen (Visual Basic)

Enumerationen bieten eine einfache Möglichkeit, mit Sätzen verwandter Konstanten zu arbeiten. Eine Enumeration, oder `Enum` , ist ein symbolischer Name für einen Satz von Werten. Enumerationen werden als Datentypen behandelt, und Sie können Sie zum Erstellen von Konstanten für die Verwendung mit Variablen und Eigenschaften verwenden.  
  
## <a name="when-to-use-an-enumeration"></a>Situationen für die Verwendung von Enumerationen  

 Wenn eine Prozedur einen begrenzten Satz an Variablen akzeptiert, sollten Sie die Verwendung einer Enumeration in Erwägung gezogen. Enumerationen sorgen für klareren und besser lesbaren Code, insbesondere dann, wenn aussagekräftige Namen verwendet werden.  
  
 Zu den Vorteilen der Verwendung von Enumerationen gehören:  
  
- Reduziert Fehler, die durch das übertragen oder falsch formatiping von Zahlen verursacht werden  
  
- Erleichtert das Ändern von Werten in der Zukunft.  
  
- Vereinfacht das Lesen von Code, was bedeutet, dass es weniger wahrscheinlich ist, dass Fehler in das Skript einfließen.  
  
- Gewährleistet die Vorwärtskompatibilität. Mit Enumerationen schlägt der Code weniger wahrscheinlich fehl, wenn Sie in Zukunft die Werte ändern, die den Elementnamen entsprechen.  
  
## <a name="naming-enumerations"></a>Benennen von Enumerationen  

 Verwenden Sie eine Benennungs Konvention für Enumerationsmember. Wenn Visual Basic auf einen enumerationselementnamen stößt, wird möglicherweise eine Ausnahme ausgelöst, wenn andere Typbibliotheken, auf die verwiesen wird, denselben Namen aufweisen. Verwenden Sie ein eindeutiges Präfix, das die Werte aus der Anwendung oder Komponente identifiziert.  
  
 Wenn Sie auf einen Member einer Enumeration verweisen, müssen Sie den Elementnamen mit dem Namen der Enumeration qualifizieren oder die `Imports` Anweisung verwenden. Weitere Informationen finden Sie unter [Enumerationen und namens Qualifizierung](enumerations-and-name-qualification.md).  
  
## <a name="predefined-enumerations"></a>Vordefinierte Enumerationen  

 Visual Basic bietet eine Reihe vordefinierter Enumerationen, wie z `FirstDayOfWeek` `MsgBoxResult` . b. und, um Ihren Code zu vereinfachen. Eine Liste dieser Informationen finden Sie unter [Konstanten und Enumerationen](../../../language-reference/constants-and-enumerations.md).  
  
## <a name="see-also"></a>Siehe auch

- [Gewusst wie: Deklarieren einer Enumeration](how-to-declare-enumerations.md)
- [Vorgehensweise: Verweisen auf einen Enumerationsmember](how-to-refer-to-an-enumeration-member.md)
- [Enumerationen und Namensqualifikation](enumerations-and-name-qualification.md)
- [Gewusst wie: Durchlaufen einer Enumeration in Visual Basic](how-to-iterate-through-an-enumeration.md)
- [Vorgehensweise: Bestimmen der einem Enumerationswert zugeordnete Zeichenfolge](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Enum-Anweisung](../../../language-reference/statements/enum-statement.md)
- [Konstanten und Enumerationen](../../../language-reference/constants-and-enumerations.md)

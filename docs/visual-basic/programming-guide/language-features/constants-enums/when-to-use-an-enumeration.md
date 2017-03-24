---
title: Verwendung von Enumerationen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
caps.latest.revision: 12
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f22102a2e1e7eafd7fcf4db1f46af2cc622eba70
ms.lasthandoff: 03/13/2017

---
# <a name="when-to-use-an-enumeration-visual-basic"></a>Situationen für die Verwendung von Enumerationen (Visual Basic)
Enumerationen bieten eine einfache Möglichkeit zum Arbeiten mit Gruppen verwandter Konstanten. Eine Enumeration oder `Enum`, ein symbolischer Namen für einen Satz von Werten ist. Enumerationen werden als Datentypen behandelt, und Sie können diese Konstanten für die Verwendung mit Variablen und Eigenschaften erstellen.  
  
## <a name="when-to-use-an-enumeration"></a>Situationen für die Verwendung von Enumerationen  
 Wenn eine Prozedur eine begrenzte Menge von Variablen annimmt, sollten erwägen Sie, eine Enumeration zu verwenden. Enumerationen stellen für Code besser lesbar, insbesondere wenn aussagekräftige Namen verwendet werden.  
  
 Die Verwendung von Enumerationen hat folgende Vorteile:  
  
-   Fehler aufgrund eines vertauschen oder falsch eingegebene Zahlen wird reduziert.  
  
-   Erleichtert die Werte in der Zukunft ändern.  
  
-   Ist der Code einfacher zu lesen, was bedeutet, dass es weniger wahrscheinlich ist, dass Fehler einschleichen können.  
  
-   Sicherstellung der Vorwärtskompatibilität. Mit Enumerationen ist der Code weniger wahrscheinlich fehlschlägt, wenn jemand die Namen der entsprechenden Werte ändert.  
  
## <a name="naming-enumerations"></a>Benennen von Enumerationen  
 Verwenden Sie eine Namenskonvention für Enumerationsmember. Wenn [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] einen Enumerationsmembernamen trifft möglicherweise eine Ausnahme ausgelöst, falls andere Typbibliotheken, auf die verwiesen wird, denselben Namen enthalten. Verwenden Sie ein eindeutiges Präfix an, das die Werte aus der Anwendung oder Komponente identifiziert.  
  
 In Bezug auf einen Member einer Enumeration Sie müssen den Membernamen mit dem Enumerationsnamen qualifizieren, da sonst verwenden die `Imports` Anweisung. Weitere Informationen finden Sie unter [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
## <a name="predefined-enumerations"></a>Vordefinierte Enumerationen  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Stellt eine Reihe vordefinierter Enumerationen bereit, z. B. `FirstDayOfWeek` und `MsgBoxResul`t, um Ihren Code zu vereinfachen. Eine Liste dieser finden Sie unter [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Deklarieren einer Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [Gewusst wie: Verweisen auf einen Enumerationsmember](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)   
 [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Gewusst wie: Durchlaufen einer Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)   
 [Gewusst wie: Bestimmen der einem Enumerationswert zugeordnete Zeichenfolge](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)   
 [Enum-Anweisung](../../../../visual-basic/language-reference/statements/enum-statement.md)   
 [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md)

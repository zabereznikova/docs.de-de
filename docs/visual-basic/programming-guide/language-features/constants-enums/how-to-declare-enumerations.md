---
title: 'Gewusst wie: Deklarieren einer Enumeration (Visual Basic) | Microsoft-Dokumentation'
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
- declarations, enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
caps.latest.revision: 24
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
ms.openlocfilehash: 8ff8bf2df39bed0597740bcda968283ec854f447
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-declare-enumerations-visual-basic"></a>Gewusst wie: Deklarieren einer Enumeration (Visual Basic)
Sie erstellen eine Enumeration mit den `Enum` -Anweisung im Deklarationsabschnitt einer Klasse oder eines Moduls. Sie können eine Enumeration innerhalb einer Methode nicht deklarieren. Verwenden Sie zum Angeben der entsprechenden Ebene des Zugriffs `Private`, `Protected`, `Friend`, oder `Public`.  
  
 Ein `Enum` Typ hat einen Namen, einen zugrunde liegenden Typ und einen Satz von Feldern, von denen jedes eine Konstante darstellt. Der Name muss ein gültiger [!INCLUDE[vbprvblong](../../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] Qualifizierer. Der zugrunde liegende Typ muss einen ganzzahligen Typ –`Byte`, `Short`, `Long` oder `Integer`. Standardmäßig ist `Integer` festgelegt. Enumerationen sind immer stark typisiert und nicht mit Ganzzahltypen austauschbar.  
  
 Enumerationen können keine Gleitkommawerte haben. Wenn eine Enumeration einen Gleitkommawert zugewiesen ist `Option Strict On`, ein Compilerfehler ausgelöst. Wenn `Option Strict` ist `Off`, der Wert wird automatisch konvertiert, um die `Enum` Typ.  
  
 Informationen zu Namen und Gewusst wie: Verwenden der `Imports` Anweisung, damit Namensqualifikation unnötig, finden Sie unter [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
### <a name="to-declare-an-enumeration"></a>Um eine Enumeration zu deklarieren.  
  
1.  Schreiben Sie eine Deklaration, die eine Ebene, enthält die `Enum` -Schlüsselwort und einen gültigen Namen, wie in den folgenden Beispielen wird jeweils ein anderes deklariert `Enum`.  
  
     [!code-vb[VbEnumsTask&3;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_1.vb)]  
  
2.  Definieren Sie die Konstanten in der Enumeration. Standardmäßig wird die erste Konstante in einer Enumeration mit initialisiert `0`, und alle nachfolgenden Konstanten Wert eins mehr als die vorherigen Konstante initialisiert werden. Z. B. die folgende Enumeration `Days`, enthält eine Konstante mit dem Namen `Sunday` mit dem Wert `0`, eine Konstante mit dem Namen `Monday` mit dem Wert `1`, eine Konstante mit dem Namen `Tuesday` mit dem Wert des `2`und so weiter.  
  
     [!code-vb[VbEnumsTask&4;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_2.vb)]  
  
3.  Sie können Konstanten in einer Enumeration explizit Werte zuweisen, mit der eine Zuweisung. Sie können eine beliebige Ganzzahl auch negative Zahlen zuweisen. Beispielsweise sollten Sie die Konstanten Werte kleiner als&0; (null), um Fehlerzustände darstellen. In der folgenden Enumeration, die Konstante `Invalid` der Wert explizit zugewiesen `–1`, und die Konstante `Sunday` erhält den Wert `0`. Da es sich um die erste Konstante in der Enumeration ist `Saturday` wird auch auf den Wert initialisiert `0`. Der Wert der `Monday` ist `1` (eins höher ist als der Wert der `Sunday`); der Wert der `Tuesday` ist `2`und so weiter.  
  
     [!code-vb[VbEnumsTask&5;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_3.vb)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a>Um eine Enumeration als expliziten Typ zu deklarieren.  
  
-   Geben Sie den Typ der Enumeration mit der `As` -Klausel, wie im folgenden Beispiel gezeigt.  
  
     [!code-vb[VbEnumsTask&6;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_4.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Enumerationen und Namensqualifikation](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Gewusst wie: Verweisen auf einen Enumerationsmember](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)   
 [Gewusst wie: Durchlaufen einer Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)   
 [Gewusst wie: Bestimmen der einem Enumerationswert zugeordnete Zeichenfolge](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)   
 [Verwenden Sie eine Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)   
 [Übersicht über Konstanten](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [Konstanten und Literale Datentypen](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)   
 [Konstanten und Enumerationen](../../../../visual-basic/language-reference/constants-and-enumerations.md)

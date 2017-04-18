---
title: "Gewusst wie: Definieren eines Parameters für eine Prozedur (Visual Basic) | Microsoft-Dokumentation"
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
- procedure parameters, defining data types for
- procedures, parameters
- procedures, defining
- Visual Basic code, procedures
- procedure parameters, defining
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 9fb9ad244499039c1768ff97f071168e0a0842e4
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a>Gewusst wie: Definieren eines Parameters für eine Prozedur (Visual Basic)
Ein *Parameter* kann der aufrufenden Code einen Wert an die Prozedur übergeben werden, wenn er aufgerufen. Sie deklarieren jeden Parameter für eine Prozedur, wie Sie eine Variable deklarieren, die den Namen und den Datentyp angibt. Sie auch angeben, den Mechanismus übergeben, und gibt an, ob der Parameter optional ist.  
  
 Weitere Informationen finden Sie unter [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md).  
  
### <a name="to-define-a-procedure-parameter"></a>Definieren Sie einen Prozedurparameter  
  
1.  Fügen Sie in der Prozedurdeklaration den Parameternamen, die Prozedur die Parameterliste, trennen es von anderen Parametern durch Kommas.  
  
2.  Entscheiden Sie, den Datentyp des Parameters.  
  
3.  Führen Sie den Parameternamen ein `As` -Klausel, um den Datentyp anzugeben.  
  
4.  Entscheiden Sie, die Übergabemechanismus für den Parameter ein. Normalerweise übergeben Sie Parameter als Wert, es sei denn, Sie möchten, dass das Verfahren, um den Wert in den aufrufenden Code ändern können.  
  
5.  Vor den Parameternamen stehen [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oder [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) an die Methode übergeben. Weitere Informationen finden Sie unter [Unterschiede zwischen übergeben von Argumenten nach Wert und als Verweis](./differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
6.  Wenn der Parameter optional ist, vor der Übergabemechanismus mit [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) , und führen Sie den Datentyp des Parameters mit einem Gleichheitszeichen (`=`) und einen Standardwert.  
  
     Im folgende Beispiel wird die Gliederung definiert eine `Sub` -Prozedur mit drei Parametern. Die ersten beiden sind erforderlich, und der dritte ist optional. Die Parameterdeklarationen werden in der Parameterliste durch Kommas getrennt.  
  
     [!code-vb[VbVbcnProcedures&33;](./codesnippet/VisualBasic/how-to-define-a-parameter-for-a-procedure_1.vb)]  
  
     Der erste Parameter nimmt ein `customer` -Objekt, und `updateCustomer` können direkt aktualisieren, die Variable übergeben `c` , da das Argument übergeben wird [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md). Das Verfahren kann die Werte der beiden letzten Argumente nicht ändern, da sie übergeben werden [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).  
  
     Wenn der aufrufende Code keinen Wert für bereitstellt der `level` Parameter [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] wird auf den Standardwert 0.  
  
     Wenn die Überprüfung des Typs wechseln ([Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) ist `Off`, `As` -Klausel ist optional, wenn Sie einen Parameter definieren. Allerdings verwendet einen Parameter einer `As` -Klausel, diese müssen verwenden. Wenn der Schalter für die Typprüfung ist `On`, die `As` -Klausel ist für jede Parameterdefinition erforderlich.  
  
     Die Angabe von Datentypen für alle Programmierelemente wird als bezeichnet *starke Typisierung*. Wenn Sie die Option `Option Strict On`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] erzwingt eine starke Typisierung. Dies wird, aus den folgenden Gründen empfohlen:  
  
    -   Sie können IntelliSense-Unterstützung für die Variablen und Parameter. Dadurch können Sie die Eigenschaften und andere Member zu sehen, wie Sie in Ihrem Code eingeben.  
  
    -   Sie können den Compiler an, zu überprüfen. Auf diese Weise catch-Anweisungen, die zur Laufzeit aufgrund von Fehlern, z. B. Überlauf fehlschlagen können. Es fängt auch Aufrufe von Methoden für Objekte, die diese nicht unterstützen.  
  
    -   Schnellere Ausführung des Codes führt. Ein Grund hierfür ist, die, wenn Sie nicht für ein Programmierelement einen Datentyp angeben der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler weist es den `Object` Typ. Der kompilierte Code möglicherweise Konvertieren zwischen `Object` und anderen Datentypen, die Leistung reduziert wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)   
 [Sub-Prozeduren](./sub-procedures.md)   
 [Function-Prozeduren](./function-procedures.md)   
 [Gewusst wie: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)   
 [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)   
 [Rekursive Prozeduren](./recursive-procedures.md)   
 [Prozedurüberladung](./procedure-overloading.md)   
 [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Objektorientierte Programmierung](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)

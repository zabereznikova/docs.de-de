---
title: "Unterschiede zwischen dem Übergeben eines Arguments als Wert und als Verweis (Visual Basic) | Microsoft-Dokumentation"
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
- ByRef keyword, passing arguments by reference
- Visual Basic code, procedures
- procedures, passing arguments
- ByVal keyword, passing arguments by value
- arguments [Visual Basic], passing by value or by reference
ms.assetid: 5f5c38fe-3e2d-494c-8fff-f4025b55ec93
caps.latest.revision: 14
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
ms.openlocfilehash: 93c515dd8524cde85555a27879baee00185f78e3
ms.lasthandoff: 03/13/2017

---
# <a name="differences-between-passing-an-argument-by-value-and-by-reference-visual-basic"></a>Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis (Visual Basic)
Wenn Sie ein oder mehrere Argumente an eine Prozedur übergeben, entspricht jedes Argument einem zugrunde liegenden Programmierelement im Aufrufcode. Sie können entweder den Wert dieses zugrunde liegenden Elements oder einen Verweis darauf übergeben. Dies wird als bezeichnet die *Mechanismus übergeben*.  
  
## <a name="passing-by-value"></a>Übergeben als Wert  
 Übergeben Sie ein Argument *Wert* durch Angabe der [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) Schlüsselwort für den entsprechenden Parameter in der Prozedurdefinition. Bei Verwendung dieses Mechanismus übergeben [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] kopiert den Wert des zugrunde liegenden Programmierelements in eine lokale Variable in der Prozedur. Der Code der Prozedur keinen Zugriff auf das zugrunde liegende Element in der aufrufende Code keinen.  
  
## <a name="passing-by-reference"></a>Übergeben als Verweis  
 Übergeben Sie ein Argument *als Verweis* durch Angabe der [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) Schlüsselwort für den entsprechenden Parameter in der Prozedurdefinition. Bei Verwendung dieses Mechanismus übergeben [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] übergibt an die Prozedur einen direkten Verweis auf das zugrunde liegende Programmierelement im aufrufenden Code.  
  
## <a name="passing-mechanism-and-element-type"></a>Übergabemechanismus und Elementtyp  
 Die Auswahl der Standardmechanismus zum übergeben entspricht nicht der Klassifizierung des zugrunde liegenden Elementtyps. Übergeben als Wert oder als Verweis bezieht sich auf was [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] für den Prozedurcode bereitstellt. Ein Werttyp oder Verweistyp bezieht sich auf wie ein Programmierelement im Arbeitsspeicher gespeichert werden.  
  
 Allerdings sind die Übergabemechanismus und Elementtyp verknüpft. Der Wert eines Verweistyps ist ein Zeiger auf die Daten an anderer Stelle im Arbeitsspeicher. Dies bedeutet, dass wenn Sie einen Verweistyp nach Wert übergeben, der Code einen Zeiger auf die zugrunde liegenden Daten des Elements, obwohl das zugrunde liegende Element selbst nicht darauf zugreifen können. Wenn das Element eine Arrayvariable, z. B. Code der Prozedur keinen Zugriff auf die Variable selbst, aber Zugriff auf die Array-Elemente.  
  
## <a name="ability-to-modify"></a>Fähigkeit zum Ändern  
 Wenn Sie ein nicht änderbares Element als Argument übergeben, die Prozedur kann nie ändern sie in den aufrufenden Code, übergebenes `ByVal` oder `ByRef`.  
  
 Änderbaren Elementen wird in der folgenden Tabelle die Interaktion zwischen dem Elementtyp und der Mechanismus übergeben.  
  
|Elementtyp|Übergeben`ByVal`|Übergeben`ByRef`|  
|------------------|--------------------|--------------------|  
|Werttyp (enthält nur einen Wert)|Die Variable oder eines seiner Member kann nicht von der Prozedur geändert werden.|Die Prozedur kann die Variable und ihre Member ändern.|  
|Verweistyp (enthält einen Zeiger auf eine Klasse oder Struktur Instanz)|Die Prozedur die Variable nicht ändern, aber Member der Instanz, auf die sie zeigt.|Die Variable und die Member der Instanz, auf der er zeigt, kann die Prozedur ändern.|  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)   
 [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md)   
 [Gewusst wie: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)   
 [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)   
 [Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten](./differences-between-modifiable-and-nonmodifiable-arguments.md)   
 [Gewusst wie: Ändern des Werts eines Prozedurarguments](./how-to-change-the-value-of-a-procedure-argument.md)   
 [Gewusst wie: Schützen eines Prozedurarguments gegen Wertänderungen](./how-to-protect-a-procedure-argument-against-value-changes.md)   
 [Gewusst wie: erzwingen, dass ein Argument als Wert übergeben werden](./how-to-force-an-argument-to-be-passed-by-value.md)   
 [Übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md)   
 [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)

---
title: "Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- ByRef keyword [Visual Basic], passing arguments by reference
- Visual Basic code, procedures
- procedures [Visual Basic], passing arguments
- ByVal keyword [Visual Basic], passing arguments by value
- arguments [Visual Basic], passing by value or by reference
ms.assetid: 5f5c38fe-3e2d-494c-8fff-f4025b55ec93
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3efd4f41184287cdcd3d499712a857bee997c1a4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="differences-between-passing-an-argument-by-value-and-by-reference-visual-basic"></a>Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis (Visual Basic)
Wenn Sie ein oder mehrere Argumente an eine Prozedur übergeben, entspricht jedes Argument einer zugrunde liegenden Programmierelement im aufrufenden Code. Sie können entweder den Wert dieses Elements zugrunde liegenden oder einen Verweis darauf übergeben. Dies bezeichnet man die *Übergabemechanismus*.  
  
## <a name="passing-by-value"></a>Übergeben als Wert  
 Sie übergeben ein Argument *nach Wert* durch Angabe der [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) Schlüsselwort für den entsprechenden Parameter in der Prozedurdefinition ab. Wenn Sie diese Option verwenden Übergabemechanismus [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] kopiert den Wert des zugrunde liegenden Programmierelements in eine lokale Variable in der Prozedur. Der Code die Prozedur besitzt keinen Zugriff auf das zugrunde liegende Element nicht im aufrufenden Code.  
  
## <a name="passing-by-reference"></a>Übergeben als Verweis  
 Sie übergeben ein Argument *Verweisübergabe* durch Angabe der [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) Schlüsselwort für den entsprechenden Parameter in der Prozedurdefinition ab. Wenn Sie diese Option verwenden Übergabemechanismus [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] übergibt die Prozedur einen direkten Verweis auf das zugrunde liegende Programmierelement im aufrufenden Code.  
  
## <a name="passing-mechanism-and-element-type"></a>Übergabemechanismus und Elementtyp.  
 Die Wahl des Übergabemechanismus entspricht nicht der Klassifizierung des zugrunde liegenden Elementtyps. Übergeben als Wert oder als Verweis bezieht sich auf was [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] an den Prozedurcode bereitstellt. Ein Werttyp oder Verweistyp bezieht sich auf wie ein Programmierelement im Arbeitsspeicher gespeichert werden.  
  
 Allerdings sind die Übergabemechanismus und Elementtyp verknüpft. Der Wert eines Verweistyps ist ein Zeiger auf die Daten an anderer Stelle im Arbeitsspeicher. Dies bedeutet, dass wenn Sie einen Verweistyp als Wert übergeben, die Prozedurcode einen Zeiger auf die zugrunde liegenden Daten des Elements, verfügt, obwohl das zugrunde liegende Element selbst nicht darauf zugreifen kann. Wenn das Element eine Arrayvariable, z. B. Code der Prozedur keinen Zugriff auf die Variable selbst, jedoch Zugriff auf die Array-Elemente.  
  
## <a name="ability-to-modify"></a>Fähigkeit zum Ändern  
 Wenn Sie ein nicht veränderbares Element als Argument übergeben, die Prozedur kann nie ändern sie im aufrufenden Code, ob sie übergeben wird `ByVal` oder `ByRef`.  
  
 Für eine änderbare Element wird in der folgenden Tabelle die Interaktion zwischen dem Elementtyp und dem Übergabemechanismus.  
  
|Elementtyp|Übergeben`ByVal`|Übergeben`ByRef`|  
|------------------|--------------------|--------------------|  
|Werttyp (enthält nur einen Wert)|Die Prozedur kann nicht die Variable oder eines seiner Member geändert werden.|Die Prozedur kann die Variable und ihre Member ändern.|  
|Verweistyp (enthält einen Zeiger auf eine Klasse oder Struktur)|Die Prozedur die Variable kann nicht geändert werden, aber es kann Member der Instanz, auf der er zeigt, ändern.|Die Variable und die Member der Instanz, auf der er zeigt, kann die Prozedur ändern.|  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)  
 [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)  
 [Gewusst wie: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)  
 [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)  
 [Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [Gewusst wie: Ändern des Werts eines Prozedurarguments](./how-to-change-the-value-of-a-procedure-argument.md)  
 [Gewusst wie: Schützen eines Prozedurarguments gegen Wertänderungen](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [Gewusst wie: Erzwingen, dass ein Argument als Wert übergeben wird](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [Übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md)  
 [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)

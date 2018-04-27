---
title: Variablen in Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic]
- values [Visual Basic], storing
ms.assetid: 4cfaa06d-4ae3-4307-897b-cf599dc24caa
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5e4397fb90e4fa5a3e68390137b84a375cf35956
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="variables-in-visual-basic"></a>Variablen in Visual Basic
Sie müssen häufig Werte beim Ausführen von Berechnungen mit Visual Basic zu speichern. Sie möchten z.B. mehrere Werte berechnen, sie vergleichen und je nach Ergebnis des Vergleichs unterschiedliche Vorgänge auf diesen ausführen. Sie müssen die Werte beibehalten, wenn Sie sie vergleichen möchten.  
  
## <a name="usage"></a>Verwendung  
 Visual Basic, werden genau wie die meisten Programmiersprachen verwenden, Variablen zum Speichern von Werten. Eine *Variable* besitzt einen Namen (das Wort, das Sie verwenden, wenn Sie sich auf den Wert beziehen, den die Variable enthält). Eine Variable verfügt auch über einen Datentyp (der die Art der Daten bestimmt, die die Variable speichern kann). Eine Variable kann ein Array darstellen, wenn sie einen indizierten Satz von eng verwandten Datenelementen speichern muss.  
  
 Durch den lokalen Typrückschluss können Sie Variablen deklarieren, ohne explizit einen Datentyp angeben zu müssen. Der Compiler leitet stattdessen den Typ der Variablen vom Typ des Initialisiererausdrucks ab. Weitere Informationen finden Sie unter [Local Type Inference (Lokaler Typrückschluss)](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) und [Option Infer Statement (Option Infer-Anweisung)](../../../../visual-basic/language-reference/statements/option-infer-statement.md).  
  
## <a name="assigning-values"></a>Zuweisen von Werten  
 Sie verwenden Zuweisungsanweisungen, um Berechnungen durchzuführen und das Ergebnis einer Variable zuzuweisen, so wie im folgenden Beispiel dargestellt.  
  
 [!code-vb[VbVbalrVariables#1](../../../../visual-basic/programming-guide/language-features/variables/codesnippet/VisualBasic/index_1.vb)]  
  
> [!NOTE]
>  Das Gleichheitszeichen (`=`) ist in diesem Beispiel ein Zuweisungsoperator, kein Gleichheitsoperator. Der Wert wird der `applesSold`-Variablen zugewiesen.  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Verschieben von Daten in und aus einer Variablen](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md).  
  
## <a name="variables-and-properties"></a>Variablen und Eigenschaften  
 Wie eine Variable stellt auch eine *Eigenschaft* einen Wert dar, auf den Sie zugreifen können. Jedoch ist er komplexer als eine Variable. Eine Eigenschaft verwendet Codeblöcke, die steuern, wie der Wert festgelegt und abgerufen wird. Weitere Informationen finden Sie unter [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Problembehandlung bei Variablen](../../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)  
 [Gewusst wie: Verschieben von Daten in und aus einer Variablen](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)  
 [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)  
 [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)

---
title: Variables
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic]
- values [Visual Basic], storing
ms.assetid: 4cfaa06d-4ae3-4307-897b-cf599dc24caa
ms.openlocfilehash: ff617774d7e93ab4238ebc06617cc03fb6bc675a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410386"
---
# <a name="variables-in-visual-basic"></a>Variablen in Visual Basic
Sie müssen häufig Werte speichern, wenn Sie Berechnungen mit Visual Basic durchführen. Sie möchten z.B. mehrere Werte berechnen, sie vergleichen und je nach Ergebnis des Vergleichs unterschiedliche Vorgänge auf diesen ausführen. Sie müssen die Werte beibehalten, wenn Sie sie vergleichen möchten.  
  
## <a name="usage"></a>Verwendung  
 Visual Basic wie die meisten Programmiersprachen verwendet Variablen zum Speichern von Werten. Eine *Variable* besitzt einen Namen (das Wort, das Sie verwenden, wenn Sie sich auf den Wert beziehen, den die Variable enthält). Eine Variable verfügt auch über einen Datentyp (der die Art der Daten bestimmt, die die Variable speichern kann). Eine Variable kann ein Array darstellen, wenn sie einen indizierten Satz von eng verwandten Datenelementen speichern muss.  
  
 Durch den lokalen Typrückschluss können Sie Variablen deklarieren, ohne explizit einen Datentyp angeben zu müssen. Der Compiler leitet stattdessen den Typ der Variablen vom Typ des Initialisiererausdrucks ab. Weitere Informationen finden Sie unter [Local Type Inference (Lokaler Typrückschluss)](local-type-inference.md) und [Option Infer Statement (Option Infer-Anweisung)](../../../language-reference/statements/option-infer-statement.md).  
  
## <a name="assigning-values"></a>Zuweisen von Werten  
 Sie verwenden Zuweisungsanweisungen, um Berechnungen durchzuführen und das Ergebnis einer Variable zuzuweisen, so wie im folgenden Beispiel dargestellt.  
  
 [!code-vb[VbVbalrVariables#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrVariables/VB/Class1.vb#1)]  
  
> [!NOTE]
> Das Gleichheitszeichen (`=`) ist in diesem Beispiel ein Zuweisungsoperator, kein Gleichheitsoperator. Der Wert wird der `applesSold`-Variablen zugewiesen.  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Verschieben von Daten in und aus einer Variablen](how-to-move-data-into-and-out-of-a-variable.md).  
  
## <a name="variables-and-properties"></a>Variablen und Eigenschaften  
 Wie eine Variable stellt auch eine *Eigenschaft* einen Wert dar, auf den Sie zugreifen können. Jedoch ist er komplexer als eine Variable. Eine Eigenschaft verwendet Codeblöcke, die steuern, wie der Wert festgelegt und abgerufen wird. Weitere Informationen finden Sie unter [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](../procedures/differences-between-properties-and-variables.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Variablen Deklaration](variable-declaration.md)
- [Objektvariablen](object-variables.md)
- [Problembehandlung bei Variablen](troubleshooting-variables.md)
- [Vorgehensweise: Verschieben von Daten in eine und aus einer Variablen](how-to-move-data-into-and-out-of-a-variable.md)
- [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](../procedures/differences-between-properties-and-variables.md)
- [Lokaler Typrückschluss](local-type-inference.md)

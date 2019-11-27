---
title: Partitionieren von Daten
ms.date: 07/20/2015
ms.assetid: 69c59379-b66e-422c-b324-5b5c07760ef7
ms.openlocfilehash: 2ab4e27ef6d825b9100fc3c15b7a9554ae49e516
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353155"
---
# <a name="partitioning-data-visual-basic"></a>Partitionierung von Daten (Visual Basic)
Partitionieren in LINQ bezieht sich auf den Vorgang, bei dem eine Eingabesequenz in zwei Abschnitte unterteilt wird, ohne die Elemente dabei neu anzuordnen, und bei dem anschließend einer der Abschnitte zurückzugeben wird.  
  
 Die folgende Abbildung zeigt das Ergebnis von drei verschiedenen Partitionierungsvorgängen einer Zeichensequenz. Der erste Vorgang gibt die ersten drei Elemente in der Sequenz zurück. Der zweite Vorgang überspringt die ersten drei Elemente und gibt die übrigen Elemente zurück. Der dritte Vorgang überspringt die ersten beiden Elemente in der Sequenz und gibt die nächsten drei Elemente zurück.  
  
 ![Abbildung zu drei LINQ-Partitionierungsvorgängen.](./media/partitioning-data/linq-partitioning-operations.png)  
  
 Die Methoden des Standardabfrageoperators, die Sequenzen partitionieren, sind im folgenden Abschnitt aufgeführt.  
  
## <a name="operators"></a>Operatoren  
  
|Name des Operators|Beschreibung|Syntax von Visual Basic-Abfrage Ausdrücken|Weitere Informationen|  
|-------------------|-----------------|------------------------------------------|----------------------|  
|Skip|Überspringt Elemente bis zu einer angegebenen Position in einer Sequenz|`Skip`|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|SkipWhile|Überspringt Elemente, die auf einer Prädikatfunktion basieren, bis ein Element die Bedingung nicht erfüllt|`Skip While`|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|Take|Übernimmt Elemente bis zu einer angegebenen Position in einer Sequenz|`Take`|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|TakeWhile|Übernimmt Elemente, die auf einer Prädikatfunktion basieren, bis ein Element der Bedingung nicht erfüllt|`Take While`|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a>Beispiele für die Abfrageausdruckssyntax  
  
### <a name="skip"></a>Skip  
 Im folgenden Codebeispiel wird die `Skip`-Klausel in Visual Basic verwendet, um die ersten vier Zeichen folgen in einem Array von Zeichen folgen zu überspringen, bevor die restlichen Zeichen folgen im Array zurückgegeben werden.  
  
 [!code-vb[CsLINQPartitioning#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#1)]  
  
### <a name="skipwhile"></a>SkipWhile  
 Im folgenden Codebeispiel wird die `Skip While`-Klausel in Visual Basic verwendet, um die Zeichen folgen in einem Array zu überspringen, während der erste Buchstabe der Zeichenfolge "a" ist. Die verbleibenden Zeichen folgen im Array werden zurückgegeben.  
  
 [!code-vb[CsLINQPartitioning#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#2)]  
  
### <a name="take"></a>Take  
 Im folgenden Codebeispiel wird die `Take`-Klausel in Visual Basic verwendet, um die ersten beiden Zeichen folgen in einem Array von Zeichen folgen zurückzugeben.  
  
 [!code-vb[CsLINQPartitioning#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#3)]  
  
### <a name="takewhile"></a>TakeWhile  
 Im folgenden Codebeispiel wird die `Take While`-Klausel in Visual Basic verwendet, um Zeichen folgen aus einem Array zurückzugeben, während die Länge der Zeichenfolge fünf oder kleiner ist.  
  
 [!code-vb[CsLINQPartitioning#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/CsLINQPartitioning/VB/Partitioning.vb#4)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Linq>
- [Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Skip-Klausel](../../../../visual-basic/language-reference/queries/skip-clause.md)
- [Skip While-Klausel](../../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [Take-Klausel](../../../../visual-basic/language-reference/queries/take-clause.md)
- [Take While-Klausel](../../../../visual-basic/language-reference/queries/take-while-clause.md)

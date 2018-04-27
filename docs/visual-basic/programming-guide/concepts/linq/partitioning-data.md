---
title: Partitionieren von Daten (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 69c59379-b66e-422c-b324-5b5c07760ef7
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 01e4e6d6db07a520b97911de5388b8e42b7e1acc
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="partitioning-data-visual-basic"></a>Partitionieren von Daten (Visual Basic)
Partitionieren in LINQ bezieht sich auf den Vorgang, bei dem eine Eingabesequenz in zwei Abschnitte unterteilt wird, ohne die Elemente dabei neu anzuordnen, und bei dem anschließend einer der Abschnitte zurückzugeben wird.  
  
 Die folgende Abbildung zeigt das Ergebnis von drei verschiedenen Partitionierungsvorgängen einer Zeichensequenz. Der erste Vorgang gibt die ersten drei Elemente in der Sequenz zurück. Der zweite Vorgang überspringt die ersten drei Elemente und gibt die übrigen Elemente zurück. Der dritte Vorgang überspringt die ersten beiden Elemente in der Sequenz und gibt die nächsten drei Elemente zurück.  
  
 ![LINQ-Partitionierungsvorgänge](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")  
  
 Die Methoden des Standardabfrageoperators, die Sequenzen partitionieren, sind im folgenden Abschnitt aufgeführt.  
  
## <a name="operators"></a>Operatoren  
  
|Name des Operators|Beschreibung|Visual Basic-Abfrageausdruckssyntax|Weitere Informationen|  
|-------------------|-----------------|------------------------------------------|----------------------|  
|Skip|Überspringt Elemente bis zu einer angegebenen Position in einer Sequenz|`Skip`|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=nameWithType>|  
|SkipWhile|Überspringt Elemente, die auf einer Prädikatfunktion basieren, bis ein Element die Bedingung nicht erfüllt|`Skip While`|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=nameWithType>|  
|Take|Übernimmt Elemente bis zu einer angegebenen Position in einer Sequenz|`Take`|<xref:System.Linq.Enumerable.Take%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=nameWithType>|  
|TakeWhile|Übernimmt Elemente, die auf einer Prädikatfunktion basieren, bis ein Element der Bedingung nicht erfüllt|`Take While`|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a>Beispiele für die Abfrageausdruckssyntax  
  
### <a name="skip"></a>Skip  
 Im folgenden Codebeispiel wird mit der `Skip` -Klausel in Visual Basic, überspringen die ersten vier Zeichenfolgen in ein Array von Zeichenfolgen vor der Rückgabe der verbleibenden Zeichenfolgen im Array.  
  
 [!code-vb[CsLINQPartitioning#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_1.vb)]  
  
### <a name="skipwhile"></a>SkipWhile  
 Im folgenden Codebeispiel wird mit der `Skip While` -Klausel in Visual Basic, um die Zeichenfolgen in einem Array überspringen, wenn es sich bei der erste Buchstaben der Zeichenfolge ist "a". Die übrigen Zeichenfolgen im Array werden zurückgegeben.  
  
 [!code-vb[CsLINQPartitioning#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_2.vb)]  
  
### <a name="take"></a>Take  
 Im folgenden Codebeispiel wird mit der `Take` -Klausel in Visual Basic, um die ersten zwei Zeichenfolgen in ein Array von Zeichenfolgen zurückzugeben.  
  
 [!code-vb[CsLINQPartitioning#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_3.vb)]  
  
### <a name="takewhile"></a>TakeWhile  
 Im folgenden Codebeispiel wird mit der `Take While` -Klausel in Visual Basic, um Zeichenfolgen aus einem Array zurück, während die Länge der Zeichenfolge fünf oder weniger beträgt.  
  
 [!code-vb[CsLINQPartitioning#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_4.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Linq>  
 [Standard Query Operators Overview (Visual Basic) (Übersicht über Standardabfrageoperatoren (Visual Basic))](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [Skip-Klausel](../../../../visual-basic/language-reference/queries/skip-clause.md)  
 [Skip While-Klausel](../../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [Take-Klausel](../../../../visual-basic/language-reference/queries/take-clause.md)  
 [Take While-Klausel](../../../../visual-basic/language-reference/queries/take-while-clause.md)

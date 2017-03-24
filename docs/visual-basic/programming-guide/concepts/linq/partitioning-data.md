---
title: Partitionieren von Daten (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 69c59379-b66e-422c-b324-5b5c07760ef7
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a746ce3e24812d1df6b6e221cca0364bf2cc7f1c
ms.lasthandoff: 03/13/2017

---
# <a name="partitioning-data-visual-basic"></a>Partitionieren von Daten (Visual Basic)
Partitionieren in LINQ ist für die Ausführung einer Eingabesequenz in zwei Abschnitte unterteilt, ohne die Elemente neu anordnen und anschließend einen der Abschnitte zurückgegeben.  
  
 Die folgende Abbildung zeigt die Ergebnisse von drei verschiedenen Partitionierung Operationen für eine Sequenz von Zeichen. Die erste Operation gibt die ersten drei Elemente in der Sequenz zurück. Die zweite Operation überspringt die ersten drei Elemente und gibt die übrigen Elemente zurück. Die dritte Operation überspringt die ersten beiden Elemente in der Sequenz und gibt die nächsten drei Elemente zurück.  
  
 ![LINQ-Partitionierung Operations](../../../../csharp/programming-guide/concepts/linq/media/linq_partition.png "LINQ_Partition")  
  
 Die Standardabfrageoperator-Methoden, die Sequenzen partitionieren, werden im folgenden Abschnitt aufgelistet.  
  
## <a name="operators"></a>Operatoren  
  
|Name des Operators|Beschreibung|Visual Basic-Abfrageausdruckssyntax|Weitere Informationen|  
|-------------------|-----------------|------------------------------------------|----------------------|  
|Skip|Überspringt Elemente bis zu einer angegebenen Position in einer Sequenz.|`Skip`|<xref:System.Linq.Enumerable.Skip%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Skip%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Skip%2A?displayProperty=fullName></xref:System.Linq.Queryable.Skip%2A?displayProperty=fullName>|  
|SkipWhile|Überspringt die Elemente basierend auf einer Prädikatfunktion, bis ein Element die Bedingung nicht erfüllt.|`Skip While`|<xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=fullName></xref:System.Linq.Enumerable.SkipWhile%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=fullName></xref:System.Linq.Queryable.SkipWhile%2A?displayProperty=fullName>|  
|Take|Übernimmt die Elemente bis zu einer angegebenen Position in einer Sequenz.|`Take`|<xref:System.Linq.Enumerable.Take%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Take%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Take%2A?displayProperty=fullName></xref:System.Linq.Queryable.Take%2A?displayProperty=fullName>|  
|TakeWhile|Übernimmt die Elemente basierend auf einer Prädikatfunktion, bis ein Element die Bedingung nicht erfüllt.|`Take While`|<xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=fullName></xref:System.Linq.Enumerable.TakeWhile%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=fullName></xref:System.Linq.Queryable.TakeWhile%2A?displayProperty=fullName>|  
  
## <a name="query-expression-syntax-examples"></a>Beispiele für die Abfrageausdruckssyntax  
  
### <a name="skip"></a>Skip  
 Im folgenden Codebeispiel wird die `Skip` -Klausel in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] über die ersten vier Zeichenfolgen in einem Array von Zeichenfolgen zu überspringen, bevor die restlichen Zeichenfolgen im Array zurückgegeben.  
  
 [!code-vb[CsLINQPartitioning&#1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_1.vb)]  
  
### <a name="skipwhile"></a>SkipWhile  
 Im folgenden Codebeispiel wird die `Skip While` -Klausel in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] , überspringen die Zeichenfolgen in einem Array, wenn der erste Buchstabe der Zeichenfolge ist "a". Die übrigen Zeichenfolgen im Array werden zurückgegeben.  
  
 [!code-vb[CsLINQPartitioning&#2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_2.vb)]  
  
### <a name="take"></a>Take  
 Im folgenden Codebeispiel wird die `Take` -Klausel in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] die ersten zwei Zeichenfolgen in einem Array von Zeichenfolgen zurückgeben.  
  
 [!code-vb[CsLINQPartitioning&3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_3.vb)]  
  
### <a name="takewhile"></a>TakeWhile  
 Im folgenden Codebeispiel wird die `Take While` -Klausel in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] um Zeichenfolgen aus einem Array zurückzugeben, wenn die Länge der Zeichenfolge fünf oder weniger beträgt.  
  
 [!code-vb[CsLINQPartitioning&4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/partitioning-data_4.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Linq></xref:System.Linq>   
 [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Skip-Klausel](../../../../visual-basic/language-reference/queries/skip-clause.md)   
 [Skip While-Klausel](../../../../visual-basic/language-reference/queries/skip-while-clause.md)   
 [Take-Klausel](../../../../visual-basic/language-reference/queries/take-clause.md)   
 [Take While-Klausel](../../../../visual-basic/language-reference/queries/take-while-clause.md)

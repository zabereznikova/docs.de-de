---
title: 'Gewusst wie: Abfragen von Zeichen in einer Zeichenfolge (LINQ) (Visual Basic) | Microsoft-Dokumentation'
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
ms.assetid: 499ebbe0-746c-4235-9dba-ce722c12b50e
caps.latest.revision: 4
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: dabd63e52707f3078c6cdc41db8c4f0e7dfbf70e
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-query-for-characters-in-a-string-linq-visual-basic"></a>Gewusst wie: Abfragen von Zeichen in einer Zeichenfolge (LINQ) (Visual Basic)
Da die <xref:System.String>-Klasse implementiert die generische <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle kann eine beliebige Zeichenfolge als eine Sequenz von Zeichen abgefragt werden.</xref:System.Collections.Generic.IEnumerable%601> </xref:System.String> Dies ist jedoch nicht die normale Verwendung von LINQ. Verwenden Sie für komplexe Muster Abgleichen von Vorgängen die <xref:System.Text.RegularExpressions.Regex>Klasse.</xref:System.Text.RegularExpressions.Regex>  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel fragt eine Zeichenfolge zum Ermitteln der Anzahl von Ziffern, die sie enthält. Beachten Sie, dass die Abfrage "wiederverwendet wird, nachdem er zum ersten Mal ausgeführt wird. Dies ist möglich, da die Abfrage selbst keine eigentlichen Ergebnisse gespeichert werden.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Erstellen eines Projekts, die auf .NET Framework, Version 3.5 oder höher mit einem Verweis auf System.Core.dll und eine `Imports` -Anweisung für den Namespace "System.Linq".  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ und Zeichenfolgen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)   
 [Gewusst wie: Kombinieren von LINQ-Abfragen mit regulären Ausdrücken (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md)

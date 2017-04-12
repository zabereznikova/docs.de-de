---
title: Ein Ausdruck vom Typ &lt;Typ&gt; kann nicht abgefragt werden | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36593
- vbc36593
dev_langs:
- VB
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
caps.latest.revision: 5
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
ms.openlocfilehash: 1e7e1e2652cf730ef6d14b0579d8a3ee3de67fbb
ms.lasthandoff: 03/13/2017

---
# <a name="expression-of-type-lttypegt-is-not-queryable"></a>Ein Ausdruck vom Typ &lt;Typ&gt; kann nicht abgefragt werden
Ein Ausdruck vom Typ \<Typ > kann nicht abgefragt werden. Sicherstellen Sie, dass einen Assembly und/oder Namespaceimport Import nicht für die LINQ-Anbieter fehlt.  
  
 Abfragbare Typen werden definiert die <xref:System.Linq>, <xref:System.Data.Linq>, und <xref:System.Xml.Linq>Namespaces.</xref:System.Xml.Linq> </xref:System.Data.Linq> </xref:System.Linq> Importieren Sie eine oder mehrere dieser Namespaces zur LINQ-Abfragen auszuführen.  
  
 Die <xref:System.Linq>Namespaces können Sie Abfragen von Objekten wie z. B. Sammlungen und Arrays mithilfe von LINQ.</xref:System.Linq>  
  
 Der <xref:System.Data.Linq>-Namespace ermöglicht es Ihnen, ADO.NET-Datasets und SQL Server-Datenbanken mithilfe von LINQ Abfragen.</xref:System.Data.Linq>  
  
 Die <xref:System.Xml.Linq>Namespaces können Sie XML-Abfrage mithilfe von LINQ und XML-Features in Visual Basic verwenden.</xref:System.Xml.Linq>  
  
 **Fehler-ID:** BC36593  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Hinzufügen einer `Import` -Anweisung für die <xref:System.Linq>, <xref:System.Data.Linq>, oder <xref:System.Xml.Linq>Namespace zur Codedatei.</xref:System.Xml.Linq> </xref:System.Data.Linq> </xref:System.Linq> Sie können auch Namespaces für das Projekt importieren, mit dem **Verweise** Seite im Projekt-Designer (**Mein Projekt**).  
  
2.  Stellen Sie sicher, dass des Typs, den Sie identifiziert haben, wie die Quelle der Abfrage ein abfragbarer Typ ist. D. h. ein Typ, <xref:System.Collections.Generic.IEnumerable%601>oder <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601> implementiert,  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Linq></xref:System.Linq>   
 <xref:System.Data.Linq></xref:System.Data.Linq>   
 <xref:System.Xml.Linq>   
 [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [Verweise und die Imports-Anweisung](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)   
 [Imports-Anweisung (.NET-Namespace und -Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Seite „Verweise“, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)

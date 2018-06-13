---
title: Ein Ausdruck vom Typ &lt;Typ&gt; kann nicht abgefragt werden
ms.date: 07/20/2015
f1_keywords:
- bc36593
- vbc36593
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
ms.openlocfilehash: 9d333abda5e303f8fab6d1f707df7ac77d8e03ce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589008"
---
# <a name="expression-of-type-lttypegt-is-not-queryable"></a>Ein Ausdruck vom Typ &lt;Typ&gt; kann nicht abgefragt werden
Ein Ausdruck vom Typ \<Typ > kann nicht abgefragt werden. Stellen Sie sicher, dass Sie keinen Assembly-Verweis und/oder Namespace Import für LINQ-Anbieter fehlt.  
  
 Abfragbare Typen definiert sind, der <xref:System.Linq>, <xref:System.Data.Linq>, und <xref:System.Xml.Linq> Namespaces. Sie müssen mindestens einen dieser Namespaces zum Ausführen von LINQ-Abfragen importieren.  
  
 Die <xref:System.Linq> Namespace können Sie Abfrageobjekte wie Auflistungen und Arrays mithilfe von LINQ.  
  
 Die <xref:System.Data.Linq> Namespace ermöglicht es Ihnen, ADO.NET-Datasets und SQL Server-Datenbanken mittels LINQ Abfragen.  
  
 Die <xref:System.Xml.Linq> Namespace, die XML-Abfrage können Sie mithilfe von LINQ und XML-Funktionen in Visual Basic verwenden.  
  
 **Fehler-ID:** BC36593  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Hinzufügen einer `Import` -Anweisung für die <xref:System.Linq>, <xref:System.Data.Linq>, oder <xref:System.Xml.Linq> Namespace in die Codedatei. Sie können auch Namespaces für das Projekt importieren, mit der **Verweise** Seite im Projekt-Designer (**Mein Projekt**).  
  
2.  Stellen Sie sicher, dass des Typs, den Sie identifiziert haben, wie die Quelle der Abfrage ein abfragbarer Typ ist. D. h. einen Typ, implementiert <xref:System.Collections.Generic.IEnumerable%601> oder <xref:System.Linq.IQueryable%601>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Linq>  
 <xref:System.Data.Linq>  
 <xref:System.Xml.Linq>  
 [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [Verweise und die Imports-Anweisung](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [Imports-Anweisung (.NET-Namespace und -Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [Seite „Verweise“, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)

---
title: Ein Ausdruck vom Typ <type> kann nicht abgefragt werden
ms.date: 07/20/2015
f1_keywords:
- bc36593
- vbc36593
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
ms.openlocfilehash: 7f74d56b47629ff76f9b935d26278ace8df4c353
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842329"
---
# <a name="expression-of-type-type-is-not-queryable"></a>Ein Ausdruck vom Typ \<Typs > kann nicht abgefragt werden
Ein Ausdruck vom Typ \<Typs > kann nicht abgefragt werden. Stellen Sie sicher, dass eine Assembly und/oder Namespaceimport importieren keine für den LINQ-Anbieter fehlt.  
  
 Abfragbare Typen werden definiert, der <xref:System.Linq>, <xref:System.Data.Linq>, und <xref:System.Xml.Linq> Namespaces. Importieren Sie eine oder mehrere dieser Namespaces zur LINQ-Abfragen auszuführen.  
  
 Die <xref:System.Linq> Namespace können Sie Abfrageobjekte wie z. B. Sammlungen und Arrays mithilfe von LINQ.  
  
 Die <xref:System.Data.Linq> -Namespace ermöglicht Ihnen, ADO.NET Datasets und SQL Server-Datenbanken mithilfe von LINQ abzufragen.  
  
 Die <xref:System.Xml.Linq> Namespace können Sie XML-Abfrage mithilfe von LINQ und XML-Features in Visual Basic verwenden.  
  
 **Fehler-ID:** BC36593  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Hinzufügen einer `Import` -Anweisung für die <xref:System.Linq>, <xref:System.Data.Linq>, oder <xref:System.Xml.Linq> Namespace Ihrer Codedatei. Sie können auch Namespaces für Ihr Projekt importieren, mit der **Verweise** auf der Seite im Projekt-Designer (**Mein Projekt**).  
  
2.  Stellen Sie sicher, dass des Typs, den Sie identifiziert haben, wie die Quelle der Abfrage ein abfragbarer Typ ist. D. h. einen Typ, der implementiert <xref:System.Collections.Generic.IEnumerable%601> oder <xref:System.Linq.IQueryable%601>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Linq>
- <xref:System.Data.Linq>
- <xref:System.Xml.Linq>
- [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md)
- [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)
- [Verweise und die Imports-Anweisung](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [Imports-Anweisung (.NET-Namespace und -Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Seite „Verweise“, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)

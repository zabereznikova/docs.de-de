---
title: Ein Ausdruck vom Typ <type> kann nicht abgefragt werden
ms.date: 07/20/2015
f1_keywords:
- bc36593
- vbc36593
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
ms.openlocfilehash: 78b47601bf0a013d079f638f6dac27511e01aec4
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874218"
---
# <a name="expression-of-type-type-is-not-queryable"></a>Ein Ausdruck vom Typ \<type> kann nicht abgefragt werden

Ein Ausdruck vom Typ kann nicht abgefragt werden \<type> . Stellen Sie sicher, dass für den LINQ-Anbieter kein Assemblyverweis und/oder Namespace Import vorhanden ist.  
  
 Abfragbare Typen werden in den <xref:System.Linq> <xref:System.Data.Linq> <xref:System.Xml.Linq> Namespaces, und definiert. Sie müssen einen oder mehrere dieser Namespaces importieren, um LINQ-Abfragen auszuführen.  
  
 Mit dem- <xref:System.Linq> Namespace können Sie Objekte wie Auflistungen und Arrays mithilfe von LINQ Abfragen.  
  
 Der <xref:System.Data.Linq> -Namespace ermöglicht es Ihnen, ADO.NET-Datasets und SQL Server-Datenbanken mithilfe von LINQ abzufragen.  
  
 Der <xref:System.Xml.Linq> -Namespace ermöglicht Ihnen das Abfragen von XML mithilfe von LINQ und die Verwendung von XML-Funktionen in Visual Basic.  
  
 **Fehler-ID:** BC36593  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Fügen Sie `Import` der Codedatei eine-Anweisung für den- <xref:System.Linq> ,- <xref:System.Data.Linq> oder- <xref:System.Xml.Linq> Namespace hinzu. Sie können Namespaces für Ihr Projekt auch importieren, indem Sie die Seite **Verweise** des Projekt-Designers (**mein Projekt**) verwenden.  
  
2. Stellen Sie sicher, dass der Typ, den Sie als Quelle der Abfrage identifiziert haben, ein abfragbarer Typ ist. Das heißt, ein Typ, der <xref:System.Collections.Generic.IEnumerable%601> oder implementiert <xref:System.Linq.IQueryable%601> .  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Linq>
- <xref:System.Data.Linq>
- <xref:System.Xml.Linq>
- [Einführung in LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [LINQ](../../programming-guide/language-features/linq/index.md)
- [XML](../../programming-guide/language-features/xml/index.md)
- [Verweise und die Imports-Anweisung](../../programming-guide/program-structure/references-and-the-imports-statement.md)
- [Imports-Anweisung (.NET-Namespace und Typ)](../statements/imports-statement-net-namespace-and-type.md)
- [Seite "Verweise", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)

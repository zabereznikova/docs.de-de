---
title: "Expression of type &lt;type&gt; is not queryable | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc36593"
  - "vbc36593"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36593"
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Expression of type &lt;type&gt; is not queryable
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Ein Ausdruck vom Typ "\<Typ\>" kann nicht abgefragt werden.Stellen Sie sicher, dass kein Assemblyverweis und\/oder Namespaceimport für den LINQ\-Anbieter fehlt.  
  
 Abfragbare Typen werden in den Namespaces <xref:System.Linq>, <xref:System.Data.Linq> und <xref:System.Xml.Linq> definiert.  Sie müssen mindestens einen dieser Namespaces importieren, um LINQ\-Abfragen auszuführen.  
  
 Der <xref:System.Linq>\-Namespace ermöglicht es Ihnen, Objekte wie Auflistungen und Arrays mithilfe von LINQ abzufragen.  
  
 Der <xref:System.Data.Linq>\-Namespace ermöglicht es Ihnen, ADO.NET\-Datasets und SQL Server\-Datenbanken mithilfe von LINQ abzufragen.  
  
 Der <xref:System.Xml.Linq>\-Namespace ermöglicht es Ihnen, XML mithilfe von LINQ abzufragen und XML\-Features in Visual Basic zu verwenden.  
  
 **Fehler\-ID:** BC36593  
  
### So beheben Sie diesen Fehler  
  
1.  Fügen Sie der Codedatei die `Import`\-Anweisung für den Namespace <xref:System.Linq>, <xref:System.Data.Linq> oder <xref:System.Xml.Linq> hinzu.  Namespaces für das Projekt können auch über die Seite **Verweise** im Projekt\-Designer \(**Mein Projekt**\) importiert werden.  
  
2.  Stellen Sie sicher, dass der Typ, der als Quelle der Abfrage identifiziert wurde, ein abfragbarer Typ ist.  Es muss sich also um einen Typ handeln, durch den <xref:System.Collections.Generic.IEnumerable%601> oder <xref:System.Linq.IQueryable%601> implementiert wird.  
  
## Siehe auch  
 <xref:System.Linq>   
 <xref:System.Data.Linq>   
 <xref:System.Xml.Linq>   
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)   
 [Imports Statement \(.NET Namespace and Type\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Seite "Verweise", Projekt\-Designer \(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic)
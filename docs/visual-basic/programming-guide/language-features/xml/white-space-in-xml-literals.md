---
title: Leerzeichen in XML-Literalen (Visual Basic) | Microsoft-Dokumentation
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
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
caps.latest.revision: 14
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: b98a88696f24cc0b95401812471d13acea4faa6d
ms.lasthandoff: 03/13/2017

---
# <a name="white-space-in-xml-literals-visual-basic"></a>Leerzeichen in XML-Literalen (Visual Basic)
Die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] -Compiler bindet nur die signifikanten Leerzeichen eines XML-Literals, wenn er erstellt ein [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] Objekt. Bedeutungslose Leerzeichen werden nicht übernommen.  
  
## <a name="significant-and-insignificant-white-space"></a>Signifikante und nicht signifikante Leerraum  
 Leerzeichen in XML-Literalen sind nur in drei Bereichen signifikant:  
  
-   Wenn sie in einem Attributwert befinden.  
  
-   Wenn sie sind Bestandteil der Textinhalt des Elements, und der Text auch andere Zeichen enthält.  
  
-   Wenn sie in einem eingebetteten Ausdruck für den Textinhalt des Elements sind.  
  
 Andernfalls der Compiler behandelt Leerzeichen als nicht signifikant und schließt Sie nicht der [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] -Objekt für das Literal.  
  
 Um nicht signifikanter Leerraum in einem XML-literal einschließen möchten, verwenden Sie einen eingebetteten Ausdruck, der ein Zeichenfolgenliteral mit den Leerzeichen enthält.  
  
> [!NOTE]
>  Wenn die `xml:space` Attribut in einem XML-Elementliteral, erscheint die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] schließt der Compiler das Attribut in der <xref:System.Xml.Linq.XElement>Objekt hinzufügen können, aber dieses Attribut ändert sich nicht darauf aus, wie der Compiler Leerzeichen behandelt.</xref:System.Xml.Linq.XElement>  
  
## <a name="examples"></a>Beispiele  
 Das folgende Beispiel enthält zwei XML-Elemente, äußere und innere. Beide Elemente enthalten Leerzeichen im Textinhalt. Die Leerzeichen im äußeren Element ist unbedeutend, da er nur Leerzeichen und ein XML-Element enthält. Der Leerraum in der inneren Elements ist wichtig, da er Leerzeichen und Text enthält.  
  
 [!code-vb[VbXMLSamples&#29;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]  
  
 Beim Ausführen zeigt dieser Code den folgenden Text an.  
  
```  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)

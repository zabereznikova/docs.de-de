---
title: Leerzeichen in XML-Literalen (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d8587abb98fe33ab2c5a0cef6cea76049a00909e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="white-space-in-xml-literals-visual-basic"></a>Leerzeichen in XML-Literalen (Visual Basic)
Die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Compiler bindet nur die signifikanter Leerraumzeichen aus einem XML-Literal, wenn er erstellt eine [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Objekt. Bedeutungslose Leerzeichen sind nicht integriert.  
  
## <a name="significant-and-insignificant-white-space"></a>Signifikante und nicht signifikante Leerraum  
 Leerzeichen in XML-Literalen sind nur in drei Bereichen signifikant:  
  
-   Wenn sie in einem Attributwert befinden.  
  
-   Wenn sie sind Bestandteil der Textinhalt des Elements und der Text auch andere Zeichen enthält.  
  
-   Wenn sie in einem eingebetteten Ausdruck für den Textinhalt des Elements sind.  
  
 Andernfalls der Compiler behandelt Leerzeichen als nicht signifikant und schließt dann nicht in der [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Objekt für das Literal.  
  
 Verwenden Sie einen eingebetteten Ausdruck, der ein Zeichenfolgenliteral mit den Leerzeichen enthält, für die Einbeziehung der nicht signifikanten Leerraum in einem XML-literal.  
  
> [!NOTE]
>  Wenn die `xml:space` Attribut in einem XML-Elementliteral, erscheint die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] schließt der Compiler das Attribut in der <xref:System.Xml.Linq.XElement> Objekt hinzufügen können, aber dieses Attribut ändert sich nicht darauf aus, wie der Compiler Leerzeichen behandelt.  
  
## <a name="examples"></a>Beispiele  
 Das folgende Beispiel enthält zwei XML-Elemente, äußere und innere. Beide Elemente werden Leerzeichen in ihre Text-Inhalt enthalten. Der Leerraum in der äußeren Elements ist nicht signifikante, da sie nur aus Leerzeichen und ein XML-Element enthält. Der Leerraum in der inneren Elements ist wichtig, weil er Leerzeichen und Text enthält.  
  
 [!code-vb[VbXMLSamples#29](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]  
  
 Wenn ausführen, zeigt dieser Code den folgenden Text an.  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)

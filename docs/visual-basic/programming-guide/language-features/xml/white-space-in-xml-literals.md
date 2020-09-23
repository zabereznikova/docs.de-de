---
title: Leerzeichen in XML-Literalen
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: 5db8f92117e77d96eab34f28758546393e2afca0
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91099098"
---
# <a name="white-space-in-xml-literals-visual-basic"></a>Leerzeichen in XML-Literalen (Visual Basic)

Der Visual Basic-Compiler bindet nur die signifikanten leer Raum Zeichen aus einem XML-Literalzeichen ein, wenn ein-Objekt erstellt wird [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] . Die unbedeutenden Leerzeichen sind nicht eingeschlossen.  
  
## <a name="significant-and-insignificant-white-space"></a>Signifikanter und unbedeutender Leerraum  

 Leerzeichen in XML-Literalen sind nur in drei Bereichen wichtig:  
  
- Wenn Sie einen Attribut Wert haben.  
  
- Wenn Sie Teil des Text Inhalts eines Elements sind und der Text auch andere Zeichen enthält.  
  
- Wenn Sie in einem eingebetteten Ausdruck für den Text Inhalt eines Elements enthalten sind.  
  
 Andernfalls behandelt der Compiler leer Raum Zeichen als unbedeutend und schließt dann nicht in das- [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Objekt für das Literale ein.  
  
 Verwenden Sie einen eingebetteten Ausdruck, der ein Zeichenfolgenliteral mit dem Leerraum enthält, um unbedeutende Leerzeichen in ein XML-Literalformat einzubeziehen  
  
> [!NOTE]
> Wenn das `xml:space` Attribut in einem XML-Elementliterals angezeigt wird, schließt der Visual Basic Compiler das-Attribut in das- <xref:System.Xml.Linq.XElement> Objekt ein, aber durch das Hinzufügen dieses Attributs wird nicht geändert, wie der Compiler Leerraum behandelt.  
  
## <a name="examples"></a>Beispiele  

 Das folgende Beispiel enthält zwei XML-Elemente (Outer und Inner). Beide Elemente enthalten Leerraum in Ihren Text Inhalt. Der Leerraum im äußeren Element ist unerheblich, da er nur Leerraum und ein XML-Element enthält. Der Leerraum im Inneren Element ist wichtig, da er Leerzeichen und Text enthält.  
  
 [!code-vb[VbXMLSamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#29)]  
  
 Wenn Sie ausführen, wird in diesem Code der folgende Text angezeigt.  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen von XML in Visual Basic](creating-xml.md)

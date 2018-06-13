---
title: Namen von deklarierten XML-Elementen und Attributen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals [Visual Basic]
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
ms.openlocfilehash: 9b586936281bfbf2dcace7cf2892bebf305fc842
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650425"
---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a>Namen von deklarierten XML-Elementen und Attributen (Visual Basic)
Dieses Thema enthält Visual Basic-Richtlinien für die Benennung von XML-Elemente und Attribute im XML-Literalen.  In einem XML-literal können Sie einen lokalen Namen oder einen qualifizierten Namen angeben. Ein qualifizierter Name besteht aus einer XML-Namespacepräfix, einen Doppelpunkt und einem lokalen Namen. Weitere Informationen zu XML-Namespacepräfixe, finden Sie unter [XML-Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="rules"></a>Regeln  
 Ein lokaler Namen eines Elements oder Attributs in Visual Basic muss die folgenden Regeln entsprechen.  
  
-   Sie können mit einem Namespace beginnen. Er muss mit einem Buchstaben oder Unterstrich beginnen (`_`).  
  
-   Es darf nur alphabetische Zeichen, Dezimalziffern, Unterstriche, Punkte (.) und Bindestriche (-).  
  
-   Es darf nicht mehr als 1.024 Zeichen lang sein.  
  
-   Doppelpunkte, die im Namen angezeigt werden. Geben Sie Abgrenzung Namespace an. Aus diesem Grund können Sie Doppelpunkte nur zum Angeben eines XML-Namespaces für einen bestimmten Namen aus.  
  
 Darüber hinaus sollten Sie die folgenden Richtlinien entsprechen.  
  
-   XML 1.0-Spezifikation behält sich alle Namen, die mit der Zeichenfolge "Xml", der eine Variante der Schreibweise beginnt. Verwenden Sie daher nicht die Namen für das Element und Attributnamen.  
  
### <a name="name-length-guidelines"></a>Richtlinien zur Länge von Namen  
 Ein Name sollte aus praktischen Gründen so kurz wie möglich sein immer noch eindeutig identifiziert die Art des Elements. Dies verbessert die Lesbarkeit des Codes und reduziert die Größe des Zeile Länge und Quelldatei.  
  
 Ihr Name sollte jedoch nicht so kurz sein, dass es nicht angemessen beschrieben werden, das Element oder wie Sie im Code verwendet. Dies ist wichtig für die Lesbarkeit des Codes. Wenn eine andere Person versucht wird, zu verstehen, oder wenn Sie selbst an ihn sind sehr lange, nachdem Sie ihn geschrieben haben, können die entsprechenden Elementnamen Zeit sparen.  
  
## <a name="case-sensitivity-in-names"></a>Groß-/Kleinschreibung in Namen  
 XML-Elementnamen sind Groß-/Kleinschreibung beachtet. Dies bedeutet, dass bei der Visual Basic-Compiler zwei Namen verglichen werden, die nur die Groß-und Kleinschreibung unterscheiden, werden als unterschiedliche Namen interpretiert. Beispielsweise interpretiert `ABC` und `abc` als Verweise auf verschiedene Elemente.  
  
## <a name="xml-namespaces"></a>XML-Namespaces  
 Wenn ein XML-Elementliteral erstellen, können Sie das XML-Namespacepräfix für den Elementnamen angeben. Weitere Informationen finden Sie unter [XML-Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [XML-Elementliteral](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)

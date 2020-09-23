---
title: Namen von deklarierten XML-Elementen und Attributen
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals [Visual Basic]
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
ms.openlocfilehash: 2142674c3de4c5ac9e806c1328daa3efb697beb9
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085619"
---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a>Namen von deklarierten XML-Elementen und Attributen (Visual Basic)

Dieses Thema enthält Visual Basic Richtlinien für das Benennen von XML-Elementen und-Attributen in XML-Literalen.  In einem XML-Literalwert können Sie einen lokalen Namen oder einen qualifizierten Namen angeben. Ein qualifizierter Name besteht aus einem XML-Namespace Präfix, einem Doppelpunkt und einem lokalen Namen. Weitere Informationen zu XML-Namespace Präfixen finden Sie unter [XML-Elementliterale](../../../language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="rules"></a>Regeln  

 Der lokale Name eines Elements oder Attributs in Visual Basic muss den folgenden Regeln entsprechen.  
  
- Er kann mit einem Namespace beginnen. Er muss mit einem Buchstaben oder einem Unterstrich ( `_` ) beginnen.  
  
- Sie darf nur alphabetische Zeichen, Dezimalziffern, Unterstriche, Punkte (.) und Bindestriche (-) enthalten.  
  
- Er darf nicht mehr als 1.024 Zeichen lang sein.  
  
- Doppelpunkte, die in Namen angezeigt werden, geben die Namespace Abgrenzung an. Daher können Sie nur Doppelpunkte verwenden, um einen XML-Namespace für einen bestimmten Namen anzugeben.  
  
 Außerdem sollten Sie die folgende Richtlinie einhalten.  
  
- Die XML 1,0-Spezifikation reserviert alle Namen, die mit der Zeichenfolge "XML" beginnen, einer beliebigen groß-und Kleinschreibung. Verwenden Sie daher diese Namen nicht für die Element-und Attributnamen.  
  
### <a name="name-length-guidelines"></a>Namens Längen Richtlinien  

 Als praktische Angelegenheit sollte ein Name so kurz wie möglich sein, während er die Art des Elements eindeutig identifiziert. Dadurch wird die Lesbarkeit des Codes verbessert, und die Zeilen-und Quelldatei Größe wird reduziert.  
  
 Der Name sollte jedoch nicht so kurz sein, dass er das Element nicht ordnungsgemäß beschreibt oder wie der Code es verwendet. Dies ist wichtig für die Lesbarkeit des Codes. Wenn ein anderer Benutzer versucht, ihn zu verstehen, oder wenn Sie sich nach dem Schreiben einen langen Zeitraum ansehen, können die entsprechenden Elementnamen Zeit sparen.  
  
## <a name="case-sensitivity-in-names"></a>Groß-/Kleinschreibung in Namen  

 Bei XML-Elementnamen wird Groß-/Kleinschreibung beachtet Dies bedeutet Folgendes: Wenn der Visual Basic Compiler zwei Namen vergleicht, die sich nur in alphabetischer Schreibweise unterscheiden, werden Sie als unterschiedliche Namen interpretiert. Er interpretiert z. b `ABC` `abc` . und als Verweis auf getrennte Elemente.  
  
## <a name="xml-namespaces"></a>XML-Namespaces  

 Beim Erstellen eines XML-Elementliterals können Sie das XML-Namespace Präfix für den Elementnamen angeben. Weitere Informationen finden Sie unter [XML-Elementliterale](../../../language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen von XML in Visual Basic](creating-xml.md)
- [XML-Elementliteral](../../../language-reference/xml-literals/xml-element-literal.md)

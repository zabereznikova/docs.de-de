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
ms.openlocfilehash: 2221f2677183cf360fa82a4d73a679a8b68927d1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761701"
---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a>Namen von deklarierten XML-Elementen und Attributen (Visual Basic)
Dieses Thema enthält die Visual Basic-Richtlinien für die Benennung von XML-Elemente und Attribute im XML-Literale.  In einem XML-literal können Sie einen lokalen Namen oder ein qualifizierter Name angeben. Ein qualifizierter Name besteht aus einer XML-Namespacepräfix, einen Doppelpunkt und einem lokalen Namen. Weitere Informationen zu XML-Namespacepräfixe, finden Sie unter [XML-Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="rules"></a>Regeln  
 Ein lokaler Namen eines Elements oder Attributs in Visual Basic muss die folgenden Regeln entsprechen.  
  
- Sie können mit einem Namespace beginnen. Es muss mit einem Buchstaben oder einem Unterstrich beginnen (`_`).  
  
- Es darf nur Buchstaben, Dezimalziffern, Unterstriche, Punkte (.) und Bindestriche (-).  
  
- Es darf nicht mehr als 1.024 Zeichen lang sein.  
  
- Doppelpunkte, die im Namen angezeigt werden. Geben Sie Namespace demarkation an. Aus diesem Grund können Sie Doppelpunkte, nur für einen XML-Namespace für einen bestimmten Namen zu geben.  
  
 Darüber hinaus sollte die folgenden Richtlinien eingehalten werden.  
  
- Die XML 1.0-Spezifikation reserviert alle Namen, die mit der Zeichenfolge "Xml", der eine Variante der Schreibweise ab. Verwenden Sie daher nicht die Namen für das Element und dem Attributnamen.  
  
### <a name="name-length-guidelines"></a>Richtlinien zur Länge von Namen  
 Ein praktischer Tipp sollte ein Name und die Art des Elements immer noch eindeutig kennzeichnen so kurz wie möglich sein. Dies verbessert die Lesbarkeit des Codes und die Länge und die Quelldatei Größe reduziert.  
  
 Ihr Name sollte jedoch nicht so kurz sein, dass es nicht angemessen beschrieben werden, das Element oder wie Ihr Code verwendet. Dies ist wichtig für die Lesbarkeit des Codes. Wenn eine andere Person versucht, eine klare Vorstellung davon haben, oder wenn Sie sich an sind viel Zeit nach dessen Erstellung, können die entsprechenden Elementnamen Zeit sparen.  
  
## <a name="case-sensitivity-in-names"></a>Groß-/Kleinschreibung in Namen  
 XML-Elementnamen sind Groß-/Kleinschreibung beachtet. Dies bedeutet, dass wenn Visual Basic-Compiler zwei Namen, die nur die Groß-und Kleinschreibung unterscheiden vergleicht, werden als unterschiedliche Namen interpretiert. Z. B. interpretiert `ABC` und `abc` als Verweise auf verschiedene Elemente.  
  
## <a name="xml-namespaces"></a>XML-Namespaces  
 Wenn ein XML-Elementliteral erstellen, können Sie das XML-Namespacepräfix für den Elementnamen angeben. Weitere Informationen finden Sie unter [XML-Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [XML-Elementliteral](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)

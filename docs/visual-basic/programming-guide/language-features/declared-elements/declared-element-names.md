---
title: Declared Element Names
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic], case sensitivity
- names [Visual Basic], Visual Basic rules
- naming conventions [Visual Basic]
- element names [Visual Basic]
- declared elements [Visual Basic], identifiers
- declarations [Visual Basic], elements
- declared elements [Visual Basic], valid names
- '[] escape characters [Visual Basic]'
- names [Visual Basic], elements
- declaration statements [Visual Basic], declared elements
- declaring elements [Visual Basic]
- identifiers [Visual Basic], declared elements
- case sensitivity, declared element names
- escape characters [Visual Basic]
- names [Visual Basic], declared elements
- declared elements [Visual Basic], about declared elements
- escaped names [Visual Basic]
- declared elements [Visual Basic], names
- names [Visual Basic], naming conventions
- identifiers [Visual Basic], elements
ms.assetid: 09d8843b-c0dc-4afe-9dab-87c439a69e66
ms.openlocfilehash: e8620517b934a5f1a97ea25c5a94c8b932bb47b2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345432"
---
# <a name="declared-element-names-visual-basic"></a>Namen deklarierter Elemente (Visual Basic)
Jedes deklarierte Element weist einen Namen auf, der auch als *Bezeichner*bezeichnet wird. Dies ist der Inhalt, den der Code verwendet, um darauf zu verweisen.  
  
## <a name="rules"></a>Regeln  
 Für einen Elementnamen in Visual Basic müssen die folgenden Regeln beachtet werden:  
  
- Er muss mit einem alphabetischen Zeichen oder einem Unterstrich (`_`) beginnen.  
  
- Sie darf nur alphabetische Zeichen, Dezimalziffern und Unterstriche enthalten.  
  
- Er muss mindestens ein alphabetisches Zeichen oder eine Dezimal Ziffer enthalten, wenn er mit einem Unterstrich beginnt.  
  
- Er darf nicht mehr als 1023 Zeichen lang sein.  
  
 Die Längen Beschränkung von 1023 Zeichen gilt auch für die gesamte Zeichenfolge eines voll qualifizierten Namens, z. b. `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.  
  
 Das folgende Beispiel zeigt einige gültige Elementnamen.  
  
 `aB123__45`  
  
 `_567`  
  
 Das folgende Beispiel zeigt einige ungültige Elementnamen. Der erste enthält nur einen Unterstrich, der zweite beginnt mit einer Dezimal Ziffer, das dritte enthält ein ungültiges Zeichen ($).  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
> Element Namen, die mit einem Unterstrich (`_`) beginnen, sind nicht Teil der [Sprachunabhängigkeit und sprachunabhängigen Komponenten](../../../../standard/language-independence-and-language-independent-components.md) (CLS). Daher kann CLS-kompatibler Code keine Komponente verwenden, die solche Namen definiert. Ein Unterstrich an einer beliebigen anderen Position in einem Elementnamen ist jedoch CLS-kompatibel.  
  
### <a name="name-length-guidelines"></a>Namens Längen Richtlinien  
 Als praktische Angelegenheit sollte Ihr Name so kurz wie möglich sein, während er die Art des Elements eindeutig identifiziert. Dadurch wird die Lesbarkeit des Codes verbessert, und die Zeilen-und Quelldatei Größe wird reduziert.  
  
 Auf der anderen Seite sollte Ihr Name nicht so kurz sein, dass er nicht genau beschreibt, was das Element darstellt und wie der Code es verwendet. Dies ist wichtig für die Lesbarkeit des Codes. Wenn eine andere Person versucht, dies zu verstehen, oder wenn Sie sich nach dem verfassen einen langen Zeitraum ansehen, können geeignete Elementnamen einen beträchtlichen Zeitraum sparen.  
  
## <a name="escaped-names"></a>Namens Escapezeichen  
 Im Allgemeinen darf ein Elementname keinem der Schlüsselwörter entsprechen, die von Visual Basic reserviert sind, z. b. `Case` oder `Friend`. Sie können jedoch einen *Namen*mit Escapezeichen definieren, der in eckige Klammern (`[ ]`) eingeschlossen ist. Ein Name mit Escapezeichen kann mit einem beliebigen Visual Basic Schlüsselwort identisch sein, da die Klammern jegliche Mehrdeutigkeit Sie verwenden die Klammern auch, wenn Sie später in Ihrem Code auf den Namen verweisen.  
  
 Im Allgemeinen sollten Sie Namen mit Escapezeichen nur dann verwenden, wenn:  
  
- Der Code wurde von einer früheren Version von Visual Basic migriert, die das Schlüsselwort nicht als Name reserviert hat. noch  
  
- Sie arbeiten mit Code, der in einer anderen Sprache geschrieben ist, in der das angegebene Schlüsselwort nicht reserviert ist.  
  
 Andernfalls sollten Sie das Umbenennen des Elements in Erwägung gezogen, wenn der Name mit einem Schlüsselwort in Konflikt steht. Die integrierte Entwicklungsumgebung (Integrated Development Environment, IDE) bietet eine einfache Möglichkeit, dies zu erreichen. Weitere Informationen finden Sie unter [Refactoring](/visualstudio/ide/refactoring-in-visual-studio).  
  
## <a name="case-sensitivity-in-names"></a>Groß-/Kleinschreibung in Namen  
 Bei Element Namen in Visual Basic wird Groß-/Kleinschreibung nicht beachtet. Dies bedeutet Folgendes: Wenn der Compiler zwei Namen vergleicht, die sich nur in alphabetischer Schreibweise unterscheiden, interpretiert er Sie als denselben Namen. Er geht z. B. davon aus, dass `ABC` und `abc` auf das gleiche deklarierte Element verweisen.  
  
 Allerdings verwendet die Common Language Runtime (CLR) die Groß-/Kleinschreibung unterscheidende Bindung. Wenn Sie also eine Assembly oder DLL erstellen und für andere Assemblys verfügbar machen, wird bei Ihren Namen Groß-und Kleinschreibung unterschieden. Wenn Sie z. B. eine Klasse mit einem Element namens `ABC`definieren, müssen andere Assemblys, die die Klasse über die Common Language Runtime verwenden, auf das Element als `ABC`verweisen. Wenn Sie danach die Klasse erneut kompilieren und den Namen des Elements in `abc`ändern, können die anderen Assemblys, die Ihre Klasse verwenden, nicht mehr auf dieses Element zugreifen. Wenn Sie also eine aktualisierte Version einer Assembly herausgeben, sollten Sie die Groß-/Kleinschreibung öffentlicher Elemente nicht ändern.  
  
## <a name="names-and-locales"></a>Namen und Gebiets Schemas  
 Der Vergleich von Namen ist unabhängig vom Gebiets Schema. Wenn zwei Namen in einem Gebiets Schema vorliegen, entsprechen Sie garantiert allen Gebiets Schemas.  
  
## <a name="see-also"></a>Siehe auch

- [Deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)
- [Merkmale deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Anweisungen](../../../../visual-basic/language-reference/statements/index.md)

---
title: Namen deklarierter Elemente (Visual Basic)
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
ms.openlocfilehash: 5b1f8ccc402f7f5928a33f434664b0f28d108e6d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58814067"
---
# <a name="declared-element-names-visual-basic"></a>Namen deklarierter Elemente (Visual Basic)
Jedem deklariertes Element hat einen Namen, die so genannte ein *Bezeichner*, wird der Code verwendet wird, um darauf zu verweisen.  
  
## <a name="rules"></a>Regeln  
 Ein Elementname in Visual Basic muss die folgenden Regeln beachten:  
  
-   Es muss mit einem Buchstaben oder einem Unterstrich beginnen (`_`).  
  
-   Sie müssen nur alphabetische Zeichen, Dezimalziffern und Unterstriche enthalten.  
  
-   Es muss mindestens ein alphabetisches Zeichen oder eine Dezimalstelle enthalten, wenn er mit einem Unterstrich beginnt.  
  
-   Es darf nicht mehr als 1023 Zeichen lang sein.  
  
 Die maximale Länge des 1023 Zeichen gilt auch für die gesamte Zeichenfolge des vollqualifizierten Namens, z. B. `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.  
  
 Das folgende Beispiel zeigt einige gültige Elementnamen.  
  
 `aB123__45`  
  
 `_567`  
  
 Das folgende Beispiel zeigt einige ungültige Elementnamen. Die erste enthält nur einen Unterstrich, das zweite Beispiel beginnt mit einer Dezimalstelle und das dritte enthält ein ungültiges Zeichen ($).  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
>  Elementnamen, die mit einem Unterstrich beginnen (`_`) ist nicht Teil der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../../standard/language-independence-and-language-independent-components.md) (CLS), damit eine Komponente nicht CLS-kompatiblem Code verwenden kann, die solchen Namen definiert. Allerdings ist ein Unterstrich in einer beliebigen anderen Position in einem Elementnamen CLS-kompatibel.  
  
### <a name="name-length-guidelines"></a>Richtlinien zur Länge von Namen  
 Ein praktischer Tipp sollten Ihren Namen und die Art des Elements immer noch eindeutig kennzeichnen so kurz wie möglich sein. Dies verbessert die Lesbarkeit des Codes und die Länge und die Quelldatei Größe reduziert.  
  
 Andererseits, sollten Ihren Namen nicht so kurz sein, dass es nicht angemessen beschrieben werden, was das Element darstellt und wie Ihr Code verwendet. Dies ist wichtig für die Lesbarkeit des Codes. Wenn eine andere Person versucht, eine klare Vorstellung davon haben, oder wenn Sie sich an sind viel Zeit nach dessen Erstellung, können geeignete Elementnamen viel Zeit speichern.  
  
## <a name="escaped-names"></a>Namen mit Escapezeichen  
 Im Allgemeinen ein Elementname darf nicht übereinstimmen eines reservierten von Visual Basic, wie z. B. Schlüsselwörter `Case` oder `Friend`. Allerdings können Sie definieren eine *mit Escapezeichen versehen namens*, die durch eckige Klammern eingeschlossen wird (`[ ]`). Ein Namen mit Escapezeichen kann alle Visual Basic-Schlüsselwort übereinstimmen, da jegliche Mehrdeutigkeit durch die Klammern. Wenn Sie auf den Namen später in Ihrem Code verweisen, können Sie auch die eckigen Klammern.  
  
 Im Allgemeinen sollten Sie mit Escapezeichen versehene Namen verwenden nur dann, wenn:  
  
-   Ihr Code wurde von einer früheren Version von Visual Basic migriert, die nicht das Schlüsselwort verwendet wird, als Namen reserviert, oder oder  
  
-   Sie arbeiten mit Code in einer anderen Sprache, in dem das angegebene Schlüsselwort nicht reserviert ist.  
  
 Andernfalls sollten Sie das Element umbenennen, wenn der Name mit einem Schlüsselwort in Konflikt steht. Die integrierte Entwicklungsumgebung (IDE) bietet eine einfache Möglichkeit hierzu. Weitere Informationen finden Sie unter [Refactoring](/visualstudio/vb-ide/refactoring-vb).  
  
## <a name="case-sensitivity-in-names"></a>Groß-/Kleinschreibung in Namen  
 Elementnamen in Visual Basic werden Groß-/Kleinschreibung. Dies bedeutet, dass wenn der Compiler zwei Namen, die nur Groß-und Kleinschreibung unterscheiden vergleicht, werden mit demselben Namen interpretiert. Er geht z. B. davon aus, dass `ABC` und `abc` auf das gleiche deklarierte Element verweisen.  
  
 Die common Language Runtime (CLR) wird jedoch die Groß-/Kleinschreibung Bindung verwendet. Wenn Sie also eine Assembly oder DLL erstellen und für andere Assemblys verfügbar machen, wird bei Ihren Namen Groß-und Kleinschreibung unterschieden. Wenn Sie z. B. eine Klasse mit einem Element namens `ABC`definieren, müssen andere Assemblys, die die Klasse über die Common Language Runtime verwenden, auf das Element als `ABC`verweisen. Wenn Sie danach die Klasse erneut kompilieren, und ändern den Namen des Elements zu `abc`, die andere Assemblys, die Ihre Klasse verwenden können nicht mehr auf dieses Element zugreifen. Wenn Sie also eine aktualisierte Version einer Assembly herausgeben, sollten Sie die Groß-/Kleinschreibung öffentlicher Elemente nicht ändern.  
  
## <a name="names-and-locales"></a>Namen und Gebietsschemas  
 Vergleich von Namen wird unabhängig vom Gebietsschema. Wenn zwei Namen in einem Gebietsschema übereinstimmen, werden sie garantiert in allen Gebietsschemas entsprechen.  
  
## <a name="see-also"></a>Siehe auch

- [Deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)
- [Merkmale deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Anweisungen](../../../../visual-basic/language-reference/statements/index.md)

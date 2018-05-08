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
ms.openlocfilehash: 2f48f885b66f99ecc8c6c7e13fea7e75f0e3d24a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="declared-element-names-visual-basic"></a>Namen deklarierter Elemente (Visual Basic)
Jedem deklariertes Element hat einen Namen, so genannte ein *Bezeichner*, wird der Code dazu verwendet wird, um darauf zu verweisen.  
  
## <a name="rules"></a>Regeln  
 Ein Elementname in Visual Basic muss die folgenden Regeln beachten:  
  
-   Er muss mit einem alphabetischen Zeichen oder einem Unterstrich beginnen (`_`).  
  
-   Es darf nur alphabetische Zeichen, Dezimalziffern und Unterstriche enthalten.  
  
-   Es muss mindestens ein alphabetisches Zeichen oder eine Dezimalziffer enthalten, wenn er mit einem Unterstrich beginnt.  
  
-   Es darf nicht mehr als 1023 Zeichen lang sein.  
  
 Die maximale Länge des 1023 Zeichen gilt auch für die gesamte Zeichenfolge des vollqualifizierten Namens, z. B. `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.  
  
 Das folgende Beispiel zeigt einige gültige Elementnamen.  
  
 `aB123__45`  
  
 `_567`  
  
 Das folgende Beispiel zeigt einige ungültige Elementnamen. Die erste Zeile nur einen Unterstrich enthält, das zweite Beispiel beginnt mit einer Dezimalstelle, und die dritte Spalte enthält ein ungültiges Zeichen ($).  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
>  Elementnamen, die mit einem Unterstrich beginnen (`_`) sind nicht Teil der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../../standard/language-independence-and-language-independent-components.md) (CLS), damit eine Komponente nicht CLS-kompatiblem Code verwenden kann, die solche Namen definiert. Allerdings ist ein Unterstrich in einer beliebigen anderen Position im Namen eines Elements CLS-kompatibel.  
  
### <a name="name-length-guidelines"></a>Richtlinien zur Länge von Namen  
 Ihren Namen sollten aus praktischen Gründen so kurz wie möglich werden immer noch eindeutig identifiziert die Art des Elements. Dies verbessert die Lesbarkeit des Codes und reduziert die Größe des Zeile Länge und Quelldatei.  
  
 Andererseits, sollte Ihr Name nicht so kurz sein, dass es nicht angemessen beschrieben werden, was das Element darstellt, und wie Sie im Code verwendet. Dies ist wichtig für die Lesbarkeit des Codes. Wenn eine andere Person versucht wird, zu verstehen, oder wenn Sie selbst an ihn sind sehr lange, nachdem Sie ihn geschrieben haben, können geeignete Elementnamen eine erhebliche Zeit speichern.  
  
## <a name="escaped-names"></a>Namen mit Escapesequenz  
 Im allgemeinen Namen eines Elements darf nicht entsprechen keines wie z. B. von Visual Basic reservierten Schlüsselwörter `Case` oder `Friend`. Allerdings können Sie definieren eine *mit Escapezeichen versehen Namen*, die durch Klammern eingeschlossen wird (`[ ]`). Ein Namen mit Escapezeichen kann alle Visual Basic-Schlüsselwort übereinstimmen, da jegliche Mehrdeutigkeit durch die Klammern. Die Klammern wird auch bei auf den Namen später in Ihrem Code verweisen verwenden.  
  
 Im Allgemeinen sollten Sie Namen mit Escapesequenz verwenden nur, wenn:  
  
-   Code wurde von einer früheren Version von Visual Basic migriert, nicht das Schlüsselwort verwendet wird, als einen Namen reserviert; oder  
  
-   Sie arbeiten mit Code in einer anderen Sprache, in dem das angegebene Schlüsselwort nicht reserviert ist.  
  
 Andernfalls sollten Sie das Element umbenennen, wenn dessen Name mit einem Schlüsselwort einen Konflikt verursacht. Die integrierte Entwicklungsumgebung (IDE) bietet eine einfache Möglichkeit hierzu. Weitere Informationen finden Sie unter [Refactoring](/visualstudio/vb-ide/refactoring-vb).  
  
## <a name="case-sensitivity-in-names"></a>Groß-/Kleinschreibung in Namen  
 Elementnamen in Visual Basic Groß-/Kleinschreibung unterschieden. Dies bedeutet, dass wenn der Compiler zwei Namen verglichen werden, die nur Groß-und Kleinschreibung unterscheiden, werden mit demselben Namen interpretiert. Er geht z. B. davon aus, dass `ABC` und `abc` auf das gleiche deklarierte Element verweisen.  
  
 Allerdings verwendet die common Language Runtime (CLR) Bindung Groß-/Kleinschreibung beachtet. Wenn Sie also eine Assembly oder DLL erstellen und für andere Assemblys verfügbar machen, wird bei Ihren Namen Groß-und Kleinschreibung unterschieden. Wenn Sie z. B. eine Klasse mit einem Element namens `ABC`definieren, müssen andere Assemblys, die die Klasse über die Common Language Runtime verwenden, auf das Element als `ABC`verweisen. Wenn Sie danach die Klasse erneut kompilieren und ändern den Namen des Elements um `abc`, die andere Assemblys, die Ihre Klasse verwenden können nicht mehr auf dieses Element zugreifen. Wenn Sie also eine aktualisierte Version einer Assembly herausgeben, sollten Sie die Groß-/Kleinschreibung öffentlicher Elemente nicht ändern.  
  
## <a name="names-and-locales"></a>Namen und Gebietsschemas  
 Vergleich von Namen wird unabhängig vom Gebietsschema. Wenn zwei Namen in einem Gebietsschema übereinstimmen, werden sie garantiert in allen Gebietsschemas entsprechen.  
  
## <a name="see-also"></a>Siehe auch  
 [Deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)  
 [Merkmale deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Anweisungen](../../../../visual-basic/language-reference/statements/index.md)

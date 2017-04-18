---
title: Deklarierte Elementnamen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- declared elements, case sensitivity
- names, Visual Basic rules
- naming conventions
- element names
- declared elements, identifiers
- declarations, elements
- declared elements, valid names
- '[] escape characters [Visual Basic]'
- names, elements
- declaration statements, declared elements
- declaring elements
- identifiers, declared elements
- case sensitivity, declared element names
- escape characters
- names, declared elements
- declared elements, about declared elements
- escaped names
- declared elements, names
- names, naming conventions
- identifiers, elements
ms.assetid: 09d8843b-c0dc-4afe-9dab-87c439a69e66
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 56ac0684e5176f33aa6f9600f20d9fe3fcf09416
ms.lasthandoff: 03/13/2017

---
# <a name="declared-element-names-visual-basic"></a>Namen deklarierter Elemente (Visual Basic)
Jedes deklarierte Element hat einen Namen, die auch als bezeichnet ein *Bezeichner*, wird der Code dazu verwendet wird, um darauf zu verweisen.  
  
## <a name="rules"></a>Regeln  
 Ein Elementname in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] müssen die folgenden Regeln beachten:  
  
-   Es muss mit einem Buchstaben oder Unterstrich beginnen (`_`).  
  
-   Es darf nur alphabetische Zeichen, Dezimalziffern und Unterstriche enthalten.  
  
-   Es muss mindestens ein alphabetisches Zeichen oder eine Dezimalstelle enthalten, wenn er mit einem Unterstrich beginnt.  
  
-   Sie müssen nicht mehr als 1023 Zeichen lang sein.  
  
 Die maximale Länge des 1023 Zeichen gilt auch für die gesamte Zeichenfolge eines vollqualifizierten Namens, z. B. `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.  
  
 Das folgende Beispiel zeigt einige gültige Elementnamen.  
  
 `aB123__45`  
  
 `_567`  
  
 Das folgende Beispiel zeigt einige ungültige Elementnamen. Die erste enthält nur einen Unterstrich, das zweite Beispiel beginnt mit einer Dezimalstelle und die dritte Spalte enthält ein ungültiges Zeichen ($).  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
>  Elementnamen, die mit einem Unterstrich beginnen (`_`) sind nicht Teil der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](https://msdn.microsoft.com/library/12a7a7h3) (CLS), d. h. CLS-kompatiblen Code eine Komponente verwenden können, die solche Namen definiert. Allerdings ist ein Unterstrich an einer anderen Stelle in einem Elementnamen CLS-kompatibel.  
  
### <a name="name-length-guidelines"></a>Richtlinien zur Länge von Namen  
 Ihr Name sollte aus praktischen Gründen so kurz wie möglich sein und gleichzeitig die Art des Elements eindeutig kennzeichnen. Dies verbessert die Lesbarkeit des Codes und Länge und die Quelldatei die Größe verringert.  
  
 Auf der anderen Seite sollte den Namen Ihres nicht so kurz sein, dass es nicht angemessen beantwortet werden, was das Element darstellt, und wie der Code verwendet. Dies ist wichtig für die Lesbarkeit des Codes. Wenn jemand versucht, zu verstehen, oder wenn Sie sich diese betrachten sehr lange, nachdem Sie ihn geschrieben haben, geeignete Elementnamen verwendet eine beträchtliche Zeit speichern.  
  
## <a name="escaped-names"></a>Namen mit Escapesequenz  
 In der Regel ein Elementname muss mit keinem der reservierten Schlüsselwort [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], wie z. B. `Case` oder `Friend`. Allerdings können Sie definieren ein *mit Escapezeichen versehen Name*, der von geschweiften Klammern eingeschlossen ist (`[ ]`). Ein Name mit Escapezeichen kann keinem [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] -Schlüsselwort, da die Klammern Mehrdeutigkeit. Die Klammern wird auch bei auf den Namen später in Ihrem Code verweisen verwenden.  
  
 Im Allgemeinen verwenden Sie Escapezeichen Namen nur, wenn:  
  
-   Ihr Code wurde von einer früheren Version von migriert [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] , die als ein Dienstname verwendete Schlüsselwort nicht reserviert oder  
  
-   Sie arbeiten mit Code in einer anderen Sprache, in dem das angegebene Schlüsselwort nicht reserviert ist.  
  
 Andernfalls sollten Sie das Element umbenennen, wenn der Name mit einem Schlüsselwort in Konflikt steht. Die integrierte Entwicklungsumgebung (IDE) bietet eine einfache Möglichkeit dazu. Weitere Informationen finden Sie unter [Refactoring](https://docs.microsoft.com/visualstudio/vb-ide/refactoring-vb).  
  
## <a name="case-sensitivity-in-names"></a>Groß-und Kleinschreibung bei Namen  
 Elementnamen [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Groß-und Kleinschreibung unterschieden. Dies bedeutet, dass die beiden Namen-Compiler, die nur Groß-und Kleinschreibung unterscheiden, werden als derselbe Name interpretiert. Er geht z. B. davon aus, dass `ABC` und `abc` auf das gleiche deklarierte Element verweisen.  
  
 Die common Language Runtime (CLR) wird jedoch die Groß-/Kleinschreibung Bindung verwendet. Wenn Sie also eine Assembly oder DLL erstellen und für andere Assemblys verfügbar machen, wird bei Ihren Namen Groß-und Kleinschreibung unterschieden. Wenn Sie z. B. eine Klasse mit einem Element namens `ABC`definieren, müssen andere Assemblys, die die Klasse über die Common Language Runtime verwenden, auf das Element als `ABC`verweisen. Wenn Sie danach die Klasse erneut kompilieren und ändern den Namen des Elements an `abc`, die andere Assemblys, die mithilfe der Klasse können nicht mehr auf dieses Element zugreifen. Wenn Sie also eine aktualisierte Version einer Assembly herausgeben, sollten Sie die Groß-/Kleinschreibung öffentlicher Elemente nicht ändern.  
  
## <a name="names-and-locales"></a>Namen und Gebietsschemas  
 Vergleich der Namen ist vom Gebietsschema unabhängig. Wenn zwei Namen in einem Gebietsschema übereinstimmen, stimmen sie in allen Gebietsschemas überein.  
  
## <a name="see-also"></a>Siehe auch  
 [Deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)   
 [Merkmale deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)   
 [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Anweisungen](../../../../visual-basic/language-reference/statements/index.md)

---
title: "Declared Element Names (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "declared elements, case sensitivity"
  - "names, Visual Basic rules"
  - "naming conventions"
  - "element names"
  - "declared elements, identifiers"
  - "declarations, elements"
  - "declared elements, valid names"
  - "[] escape characters [Visual Basic]"
  - "names, elements"
  - "declaration statements, declared elements"
  - "declaring elements"
  - "identifiers, declared elements"
  - "case sensitivity, declared element names"
  - "escape characters"
  - "names, declared elements"
  - "declared elements, about declared elements"
  - "escaped names"
  - "declared elements, names"
  - "names, naming conventions"
  - "identifiers, elements"
ms.assetid: 09d8843b-c0dc-4afe-9dab-87c439a69e66
caps.latest.revision: 27
caps.handback.revision: 27
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Declared Element Names (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Jedes deklarierte Element hat einen Namen, der auch als *Bezeichner* bezeichnet wird, der im Code dazu verwendet wird, auf dieses Element zu verweisen.  
  
## Regeln  
 Ein Elementname in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] muss den folgenden Regeln entsprechen:  
  
-   Er muss mit einem alphabetischen Zeichen oder einem Unterstrich \(`_`\) beginnen.  
  
-   Er darf nur alphabetische Zeichen, Dezimalstellen und Unterstriche enthalten.  
  
-   Er muss mindestens ein alphabetisches Zeichen oder eine Dezimalstelle enthalten, wenn er mit einem Unterstrich beginnt.  
  
-   Er darf nicht mehr als 1023 Zeichen umfassen.  
  
 Die Längenbegrenzung von 1023 Zeichen gilt auch für die gesamte Zeichenfolge eines voll qualifizierten Namens, z. B. `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.  
  
 Das folgenden Beispiel zeigt einige gültige Elementnamen.  
  
 `aB123__45`  
  
 `_567`  
  
 Das folgenden Beispiel zeigt einige ungültige Elementnamen.  Das erste Beispiel enthält nur einen Unterstrich, das zweite Beispiel beginnt mit einer Dezimalstelle, und das dritte Beispiel enthält ein ungültiges Zeichen \($\).  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
>  Elementnamen, die mit einem Unterstrich \(`_`\) beginnen, sind nicht Teil der CLS \([Sprachenunabhängigkeit und sprachunabhängige Komponenten](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)\); daher können Komponenten, die solche Namen definieren, von CLS\-kompatiblem Code nicht verwendet werden.  An allen anderen Positionen in Elementnamen sind Unterstriche jedoch CLS\-kompatibel.  
  
### Richtlinien zur Länge von Namen  
 Der Name sollte aus praktischen Gründen so kurz wie möglich sein und gleichzeitig die Art des Elements eindeutig kennzeichnen.  Dies verbessert die Lesbarkeit des Codes und reduziert die Zeilenlänge und die Quelldateigröße.  
  
 Andererseits sollte der Name aber nicht so kurz sein, dass nicht eindeutig daraus hervorgehen, was das Element darstellt und wie Ihr Code das Element verwendet.  Dies ist für die Lesbarkeit des Codes wichtig.  Wenn andere Benutzer den Code zu verstehen versuchen oder wenn Sie sich den Code lange nach dessen Erstellung ansehen, sparen Sie und die anderen Benutzer unter Umständen sehr viel Zeit, wenn geeignete Elementnamen verwendet wurden.  
  
## Entwertete Namen  
 Im Allgemeinen darf ein Elementname nicht mit einem von [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] reservierten Schlüsselwort übereinstimmen, z. B. `Case` oder `Friend`.  Sie können jedoch einen *entwerteten Namen* definieren, der in eckige Klammern \(`[ ]`\) eingeschlossen wird.  Ein mit Escapezeichen versehener Name kann einem beliebigen [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Schlüsselwort entsprechen, da die eckigen Klammern Mehrdeutigkeiten ausschließen.  Die eckigen Klammern müssen dann auch später im Code bei einem Verweis auf den Namen verwendet werden.  
  
 Im Allgemeinen sollten Sie entwertete Namen nur in den folgenden Situationen verwenden:  
  
-   Ihr Code wurde von einer vorherigen [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Version migriert, bei der das als Name verwendete Schlüsselwort nicht reserviert war, oder  
  
-   Sie arbeiten mit Code, der in einer anderen Sprache geschrieben wurde. Das angegebene Schlüsselwort ist darin nicht reserviert.  
  
 Andernfalls sollten Sie eine Umbenennung des Elements in Betracht ziehen, wenn sein Name mit einem Schlüsselwort in Konflikt steht.  Die integrierte Entwicklungsumgebung \(IDE\) bietet eine einfache Möglichkeit, dies zu bewerkstelligen.  Weitere Informationen finden Sie unter [Umgestaltung und Dialogfeld "Umbenennen"](../../../../visual-basic/developing-apps/using-ide/refactoring-and-rename-dialog-box.md).  
  
## Groß\- und Kleinschreibung bei Namen  
 In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] wird bei Elementnamen nicht zwischen Groß\- und Kleinschreibung unterschieden.  Dies bedeutet, dass der Compiler bei einem Vergleich zweier Namen, die sich nur durch die Groß\- und Kleinschreibung unterscheiden, beide als ein und denselben Namen interpretiert.  `ABC` und `abc` werden beispielsweise als Verweis auf dasselbe deklarierte Element angesehen.  
  
 Die Common Language Runtime \(CLR\) verwendet jedoch eine Bindung, bei der zwischen Groß\- und Kleinschreibung unterschieden wird.  Wenn Sie eine Assembly oder eine DLL erstellen und diese für andere Assemblys verfügbar machen, wird bei den Namen daher zwischen Groß\-\/Kleinschreibung unterschieden.  Wenn Sie beispielsweise eine Klasse mit einem Element `ABC` definieren und andere Assemblys mithilfe der Common Language Runtime auf diese Klasse zugreifen, müssen Sie auf dieses Element verweisen, indem der Name `ABC` verwendet wird.  Wenn Sie danach die Klasse erneut kompilieren und den Namen des Elements in `abc` ändern, können die anderen Assemblys, die die Klasse verwenden, nicht mehr auf dieses Element zugreifen.  Daher sollten Sie beim Fertigstellen einer aktualisierten Version einer Assembly nicht die Groß\- und Kleinschreibung von public\-Elementen verändern.  
  
## Namen und Gebietsschemas  
 Ein Vergleich der Namen ist vom Gebietsschema unabhängig.  Wenn zwei Namen in einem Gebietsschema übereinstimmen, stimmen sie in allen Gebietsschemas überein.  
  
## Siehe auch  
 [Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)   
 [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)   
 [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Statements](../../../../visual-basic/language-reference/statements/index.md)
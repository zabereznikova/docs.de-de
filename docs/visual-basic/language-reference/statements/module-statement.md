---
title: Module-Anweisung
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- Module
- vb.Module
helpviewer_keywords:
- modules, classes
- modules
- Module statement [Visual Basic]
- modules, declaring
- standard modules
- classes [Visual Basic], vs. modules
- declarations [Visual Basic], modules
ms.assetid: a1243afc-14a5-45df-95d5-51118aeac362
caps.latest.revision: 24
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 51f8fd063449c072a69cdffd9f6ce2a96cc3f68c
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="module-statement"></a>Module-Anweisung
Deklariert den Namen eines Moduls, und führt die Definitionen der Variablen, Eigenschaften, Ereignisse und Prozeduren, die das Modul besteht aus.  
  
## <a name="syntax"></a>Syntax  
  
```vb 
[ <attributelist> ] [ accessmodifier ]  Module name  
    [ statements ]  
End Module  
```  
  
## <a name="parts"></a>Teile  
 `attributelist`  
 Dies ist optional. Finden Sie unter [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `accessmodifier`  
 Dies ist optional. Einer der folgenden Werte ist möglich:  
  
-   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
 Finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 `name`  
 Erforderlich. Der Name dieses Moduls. Finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 `statements`  
 Dies ist optional. Anweisungen, die der Variablen, Eigenschaften, Ereignisse, Prozeduren und geschachtelte Typen dieses Moduls definieren.  
  
 `End Module`  
 Beendet die `Module`-Definition.  
  
## <a name="remarks"></a>Hinweise  
 Ein `Module` -Anweisung definiert einen Referenztyp darstellt, die im gesamten Namespace verfügbar. Ein *Modul* (bezeichnet einen *Standardmodul*) ähnelt einer Klasse, doch einige wichtige Unterschiede. Jedes Modul verfügt über genau eine Instanz und muss nicht erstellt oder einer Variablen zugewiesen werden. Module nicht Vererbung unterstützen, und Schnittstellen implementieren. Beachten Sie, dass ein Modul kein *Typ* in dem Sinne, dass eine Klasse oder Struktur ist – ein Programmierelement haben Sie den Datentyp eines Moduls kann nicht deklariert werden.  
  
 Sie können `Module` nur auf Namespaceebene. Dies bedeutet, dass die *Deklarationskontext* für ein Modul eine Quelldatei oder Namespace sein muss und nicht mit einer Klasse, Struktur, Modul, Schnittstelle, Prozedur oder Block. Ein Modul in ein anderes Modul oder in einen beliebigen Typ können nicht geschachtelt werden. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Ein Modul hat die gleiche Lebensdauer wie das Programm. Da die Member aller werden `Shared`, sie verfügen auch über eine Lebensdauer, die gleich des Programms.  
  
 Module standardmäßig ["Friend"](../../../visual-basic/language-reference/modifiers/friend.md) Zugriff. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen. Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Alle Member eines Moduls sind implizit `Shared`.  
  
## <a name="classes-and-modules"></a>Klassen und Module  
 Diese Elemente haben viele ähnlichkeiten, aber es gibt auch einige wichtige Unterschiede.  
  
-   **Terminologie.** Frühere Versionen von Visual Basic werden zwei Typen von Modulen erkannt: *Klassenmodule* (CLS-Dateien) und *Standardmodulen* (BAS-Dateien). Die aktuelle Version ruft diese *Klassen* und *Module*zugeordnet.  
  
-   **Freigegebene Member.** Sie können steuern, ob ein Member einer Klasse eine freigegebene oder Instanzmember.  
  
-   **Objektorientierung.** Klassen können mit dem objektorientierten Module sind allerdings nicht. Damit nur Klassen als Objekte instanziiert werden können. Weitere Informationen finden Sie unter [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="rules"></a>Regeln  
  
-   **Modifizierer.** Alle Modulmember sind implizit [Shared](../../../visual-basic/language-reference/modifiers/shared.md). Sie können keine der `Shared` -Schlüsselwort, wenn ein Element, und Sie deklarieren den freigegebenen Status aller Mitglieder nicht ändern können.  
  
-   **Vererbung.** Ein Modul kann nicht von einem Typ erben, außer <xref:System.Object>, von dem alle Module erben. Insbesondere kann nicht einem Modul voneinander erben.  
  
     Können Sie keine der [Anweisung erbt](../../../visual-basic/language-reference/statements/inherits-statement.md) auch nicht zum angeben, in der Moduldefinition eines <xref:System.Object>.  
  
-   **Standardeigenschaft.** Sie können keine standardmäßigen Eigenschaften in einem Modul definieren. Weitere Informationen finden Sie unter [Standard](../../../visual-basic/language-reference/modifiers/default.md).  
  
## <a name="behavior"></a>Verhalten  
  
-   **Zugriffsebene.** Innerhalb eines Moduls können Sie jeden Member mit einer eigenen Zugriffsebene deklarieren. Standardzugriff für Module [öffentlichen](../../../visual-basic/language-reference/modifiers/public.md) zuzugreifen, mit Ausnahme von Variablen und Konstanten, die standardmäßig die [Private](../../../visual-basic/language-reference/modifiers/private.md) Zugriff. Wenn ein Modul den Zugriff eines seiner Elemente ist stärker als eingeschränkt, hat das angegebene Modul Zugriffsebene Vorrang vor.  
  
-   **Bereich.** Ein Modul ist der Gültigkeitsbereich des Namespace.  
  
     Der Bereich jedes Elements Modul ist das gesamte Modul. Beachten Sie, die alle Elemente werden *heraufstufung geben*, wodurch ihres Bereichs auf den Namespace, mit dem Modul höher gestuft werden. Weitere Informationen finden Sie unter [Typerweiterung](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).  
  
-   **Qualifizierung.** Sie können mehrere Module in einem Projekt haben, und Sie können Member mit demselben Namen in zwei oder mehrere Module deklarieren. Allerdings müssen Sie alle Verweise auf ein Element mit dem entsprechenden Modulnamen qualifizieren, wenn der Verweis, der außerhalb des Moduls stammt. Weitere Informationen finden Sie unter [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbVbalrStatements#69](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/module-statement_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Namespace-Anweisung](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Typerweiterung](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)

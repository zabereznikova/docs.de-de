---
title: Module-Anweisung (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 5628224a08fe5f12cf2a81b179c4998001174354
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42933908"
---
# <a name="module-statement"></a>Module-Anweisung
Deklariert den Namen eines Moduls, und führt die Definitionen der Variablen, Eigenschaften, Ereignisse und Prozeduren ein, denen das Modul enthält.  
  
## <a name="syntax"></a>Syntax  
  
```vb 
[ <attributelist> ] [ accessmodifier ]  Module name  
    [ statements ]  
End Module  
```  
  
## <a name="parts"></a>Teile  
 `attributelist`  
 Dies ist optional. Finden Sie unter [Liste](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `accessmodifier`  
 Dies ist optional. Einer der folgenden Werte ist möglich:  
  
-   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
 Finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 `name`  
 Erforderlich. Der Name dieses Moduls. Finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 `statements`  
 Dies ist optional. Anweisungen, die definieren, die Variablen, Eigenschaften, Ereignisse, Verfahren und geschachtelte Typen dieses Moduls.  
  
 `End Module`  
 Beendet die `Module`-Definition.  
  
## <a name="remarks"></a>Hinweise  
 Ein `Module` -Anweisung definiert einen Verweistyp handelt, die im gesamten Namespace verfügbar. Ein *Modul* (bezeichnet ein *Standardmodul*) wird der ähnlich wie eine Klasse jedoch einige wichtige Unterschiede. Jedes Modul verfügt über genau eine Instanz, und es muss nicht erstellt oder einer Variablen zugewiesen werden. Module nicht unterstützen die Vererbung und Schnittstellen implementieren. Beachten Sie, dass ein Modul kein *Typ* in dem Sinne, dass eine Klasse oder Struktur ist – ein Programmierelement, damit Sie den Datentyp eines Moduls kann nicht deklariert werden.  
  
 Sie können `Module` nur auf Namespaceebene. Dies bedeutet, dass die *Deklarationskontext* für ein Modul, eine Quelldatei oder der Namespace sein muss, und nicht, eine Klasse, Struktur, Modul, Schnittstelle, Prozedur oder Block möglich. Sie können ein Modul in einem anderen Modul oder in einen beliebigen Typ nicht schachteln. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Ein Modul hat die gleiche Lebensdauer wie Ihr Programm. Da die Member aller werden `Shared`, sie verfügen auch über eine Lebensdauer, die gleich dem des Programms.  
  
 Module standardmäßig [Friend](../../../visual-basic/language-reference/modifiers/friend.md) Zugriff. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen. Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Alle Elemente eines Moduls handelt es sich implizit `Shared`.  
  
## <a name="classes-and-modules"></a>Klassen und Modulen  
 Diese Elemente verfügen über viele ähnlichkeiten, aber es gibt auch einige wichtige Unterschiede.  
  
-   **-Terminologie verwenden.** Zwei Arten von Modulen zur Erkennung von früheren Versionen von Visual Basic: *Klassenmodule* (CLS-Dateien) und *Standardmodulen* (BAS-Dateien). Der aktuellen Version werden diese *Klassen* und *Module*bzw.  
  
-   **Freigegebene Member.** Sie können steuern, ob ein Member einer Klasse eines freigegebenen oder Instanzmember.  
  
-   **Objektorientierung.** Klassen sind objektorientiert, Module jedoch nicht. Damit nur Klassen als Objekte instanziiert werden können. Weitere Informationen finden Sie unter [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="rules"></a>Regeln  
  
-   **Modifizierer.** Alle Member des Moduls handelt es sich implizit [Shared](../../../visual-basic/language-reference/modifiers/shared.md). Sie können keine der `Shared` -Schlüsselwort deklariert einen Member, und Sie den freigegebenen Status aller Mitglieder ändern kann nicht.  
  
-   **Vererbung.** Ein Modul kann nicht von einem Typ erben, außer <xref:System.Object>, von dem alle Module zu erben. Ein Modul kann nicht vor allem von einem anderen erben.  
  
     Sie können keine der [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) auch nicht zum angeben, in der Moduldefinition eines <xref:System.Object>.  
  
-   **Standardeigenschaft.** Sie können keine standardmäßigen Eigenschaften in einem Modul definieren. Weitere Informationen finden Sie unter [Standard](../../../visual-basic/language-reference/modifiers/default.md).  
  
## <a name="behavior"></a>Verhalten  
  
-   **Zugriffsebene.** Innerhalb eines Moduls können Sie jeden Member mit einer eigenen Zugriffsebene deklarieren. Standardzugriff für Module [öffentliche](../../../visual-basic/language-reference/modifiers/public.md) zuzugreifen, mit Ausnahme von Variablen und Konstanten, die standardmäßig [Private](../../../visual-basic/language-reference/modifiers/private.md) Zugriff. Wenn ein Modul mehr als einen seiner Member Zugriff eingeschränktem, hat die Zugriffsebene des angegebenen Moduls Vorrang vor.  
  
-   **Bereich.** Ein Modul ist im Bereich im gesamten Namespace.  
  
     Der Gültigkeitsbereich jedes Modul-Element ist das gesamte Modul. Beachten Sie, die alle Elemente werden *typerweiterung*, wodurch ihres Bereichs, die auf den Namespace, die das Modul höher gestuft werden. Weitere Informationen finden Sie unter [Typerweiterung](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).  
  
-   **Qualifizierung.** Sie haben mehrere Module in einem Projekt, und Sie können Member mit demselben Namen in zwei oder mehrere Module deklarieren. Allerdings müssen Sie alle Verweise auf einen solchen Member mit dem entsprechenden Modulnamen qualifizieren, wenn der Verweis von außerhalb des Moduls ist. Weitere Informationen finden Sie unter [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbVbalrStatements#69](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/module-statement_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Namespace-Anweisung](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Typerweiterung](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)

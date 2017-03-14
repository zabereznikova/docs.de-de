---
title: "Module Statement | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "Module"
  - "vb.Module"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "modules, classes"
  - "modules"
  - "Module statement"
  - "modules, declaring"
  - "standard modules"
  - "classes [Visual Basic], vs. modules"
  - "declarations, modules"
ms.assetid: a1243afc-14a5-45df-95d5-51118aeac362
caps.latest.revision: 24
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 24
---
# Module Statement
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Deklariert den Namen eines Moduls und führt die Definitionen der Variablen, Eigenschaften, Ereignisse und Prozeduren ein, die die Struktur umfasst.  
  
## Syntax  
  
```  
[ <attributelist> ] [ accessmodifier ]  Module name  
    [ statements ]  
End Module  
```  
  
## Teile  
 `attributelist`  
 Optional.  Weitere Informationen finden Sie unter [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `accessmodifier`  
 Optional.  Einer der folgenden Werte ist möglich:  
  
-   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
 Weitere Informationen finden Sie unter [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 `name`  
 Erforderlich.  Name des Moduls.  Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 `statements`  
 Optional.  Anweisungen, die die Variablen, Eigenschaften, Ereignisse, Prozeduren und geschachtelten Typen des Moduls definieren.  
  
 `End Module`  
 Beendet die `Module`\-Definition.  
  
## Hinweise  
 Eine `Module`\-Anweisung definiert einen Verweistyp, der im gesamten Namespace verfügbar ist.  Ein *Modul* \(zuweilen auch als *Standardmodul* bezeichnet\)ähnelt einer Klasse, doch bestehen einige wichtige Unterschiede.  Jedes Modul verfügt über genau eine Instanz und muss weder erstellt noch einer Variablen zugewiesen werden.  Module unterstützen keine Vererbung und implementieren keine Schnittstellen.  Beachten Sie, dass ein Modul kein *Typ* in dem Sinn ist, in dem eine Klasse oder Struktur ein Typ ist – Sie können ein Programmierelement nicht mit einem Datentyp Modul deklarieren.  
  
 `Module` kann nur auf Namespaceebene verwendet werden.  Dies bedeutet, dass der *Deklarationskontext* für ein Modul eine Quelldatei oder ein Namespace sein muss und keine Klasse, keine Struktur, kein Modul, keine Schnittstelle, keine Prozedur und kein Block sein kann.  Sie können Module nicht in anderen Modulen und auch nicht in einem Typ schachteln.  Weitere Informationen finden Sie unter [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Ein Modul verfügt über die gleiche Lebensdauer wie das Programm.  Da alle seine Member `Shared` sind, entspricht deren Lebensdauer ebenfalls der Lebensdauer des Programms.  
  
 Der Standardzugriff für Module ist [Friend](../../../visual-basic/language-reference/modifiers/friend.md).  Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.  Weitere Informationen finden Sie unter [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Alle Member eines Moduls sind implizit `Shared`.  
  
## Klassen und Module  
 Diese Elemente weisen viele Ähnlichkeiten auf, jedoch bestehen auch einige wichtige Unterschiede.  
  
-   **Begriffe.** In älteren Versionen von Visual Basic werden zwei Typen von Modulen erkannt: *Klassenmodule* \(CLS\-Dateien\) und *Standardmodule* \(BAS\-Dateien\).  In der aktuellen Version werden diese als *Klassen* bzw. *Module* bezeichnet.  
  
-   **Freigegebene Member.** Sie können steuern, ob ein Member einer Klasse ein freigegebener Member oder ein Instanzmember ist.  
  
-   **Objektorientierung.** Klassen sind objektorientiert, Module jedoch nicht.  Daher können nur Klassen als Objekte instanziiert werden.  Weitere Informationen finden Sie unter [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## Regeln  
  
-   **Modifizierer.** Alle Modulmember sind implizit [Shared](../../../visual-basic/language-reference/modifiers/shared.md).  Sie können beim Deklarieren eines Members nicht das `Shared`\-Schlüsselwort verwenden, und Sie können den freigegebenen Status von Membern nicht ändern.  
  
-   **Vererbung.** Ein Modul kann von keinem anderen Typ als von <xref:System.Object> erben, von dem alle Module erben.  Insbesondere kann ein Modul nicht von einem anderen Modul erben.  
  
     Sie können die [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) nicht in einer Moduldefinition verwenden, auch nicht zum Angeben von <xref:System.Object>.  
  
-   **Standardeigenschaft.** In einem Modul können keine Standardeigenschaften definiert werden.  Weitere Informationen finden Sie unter [Default](../../../visual-basic/language-reference/modifiers/default.md).  
  
## Verhalten  
  
-   **Zugriffsebene.** In einem Modul können Sie jeden Member mit einer eigenen Zugriffsebene deklarieren.  Der Standardzugriff für Module ist [Public](../../../visual-basic/language-reference/modifiers/public.md), mit Ausnahme von Variablen und Konstanten, deren Standardzugriff [Private](../../../visual-basic/language-reference/modifiers/private.md) ist.  Wenn ein Modul eingeschränkteren Zugriff als einer seiner Member aufweist, hat die angegebene Zugriffsebene des Moduls Vorrang.  
  
-   **Gültigkeitsbereich.** Der Gültigkeitsbereich eines Moduls erstreckt sich auf seinen gesamten Namespace.  
  
     Der Gültigkeitsbereich jedes Modulmembers umfasst das gesamte Modul.  Beachten Sie, dass auf alle Member *Typerweiterung* angewendet wird, sodass ihr Gültigkeitsbereich auf den Namespace erweitert wird, der das Modul enthält.  Weitere Informationen finden Sie unter [Type Promotion](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).  
  
-   **Qualifikation.** In einem Projekt können sich mehrere Module befinden, und Sie können in mehreren Modulen Member mit demselben Namen deklarieren.  Sie müssen jedoch jeden Verweis auf einen solchen Member mit dem entsprechenden Modulnamen qualifizieren, wenn sich der Verweis außerhalb dieses Moduls befindet.  Weitere Informationen finden Sie unter [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## Beispiel  
 [!code-vb[VbVbalrStatements#69](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/module-statement_1.vb)]  
  
## Siehe auch  
 [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md)   
 [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Type Promotion](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
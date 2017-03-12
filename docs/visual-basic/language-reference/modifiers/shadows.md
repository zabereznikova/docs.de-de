---
title: "Shadows (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Shadows"
  - "shadows"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "shadowing"
  - "duplicate names"
  - "scope, shadowing"
  - "Shadows keyword"
  - "names, shadowing"
ms.assetid: 6bf687cd-0544-4797-b51b-911125ec57c6
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Shadows (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Gibt an, dass ein deklariertes Programmierelement ein Element mit derselben Bezeichnung oder eine Gruppe überladener Elemente in einer Basisklasse erneut deklariert und ausblendet.  
  
## Hinweise  
 Hauptzweck des Shadowing \(das auch als *Hide by Name* bezeichnet wird\) ist es, die Definition von Klassenmembern beizubehalten.  Die Basisklasse wird vielleicht in einer Weise geändert, die ein Element mit dem gleichen Namen wie dem bereits definierten Namen zur Folge hat.  In diesem Fall erzwingt der `Shadows`\-Modifizierer, dass Verweise über die Klasse in den von Ihnen definierten Member aufgelöst werden und nicht in das neue Basisklassenelement.  
  
 Sowohl das Shadowing als auch das Überschreiben definieren ein geerbtes Element neu, es gibt jedoch bedeutende Unterschiede zwischen den beiden Vorgehensweisen.  Weitere Informationen finden Sie unter [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
## Regeln  
  
-   **Deklarationskontext.** `Shadows` kann nur auf Klassenebene verwendet werden.  Dies bedeutet, dass der Deklarationskontext für ein `Shadows`\-Element eine Klasse sein muss und es sich nicht um eine Quelldatei, einen Namespace, eine Schnittstelle, ein Modul, eine Struktur oder eine Prozedur handeln kann.  
  
     Sie können in einer einzelnen Deklarationsanweisung nur ein Shadowingelement deklarieren.  
  
-   **Kombinierte Modifizierer.** `Shadows` kann nicht zusammen mit `Overloads`, `Overrides` oder `Static` in derselben Deklaration verwendet werden.  
  
-   **Elementtypen.** Sie können mit jeder Art von deklarierten Elementen ein Shadowing einer anderen Art durchführen.  Wenn Sie mit einer Eigenschaft oder Prozedur ein Shadowing einer anderen Eigenschaft oder Prozedur ausführen, müssen die Parameter und der Rückgabetyp nicht mit jenen der Eigenschaft oder Prozedur der Basisklasse identisch sein.  
  
-   **Zugriff.** Das Element der Basisklasse, für das ein Shadowing ausgeführt wurde, ist normalerweise innerhalb der abgeleiteten Klasse, mit der das Shadowing des Elements ausgeführt wird, nicht verfügbar.  Folgendes ist jedoch zu berücksichtigen.  
  
    -   Wenn über den Code, der auf das Shadowingelement verweist, nicht auf dieses Element zugegriffen werden kann, wird der Verweis in das Element aufgelöst, für das ein Shadowing durchgeführt wurde.  Wenn z. B. ein `Private`\-Element ein Shadowing eines Basisklassenelements durchführt, greift Code ohne Zugriffsberechtigung für das `Private`\-Element stattdessen auf das Basisklassenelement zu.  
  
    -   Wenn Sie ein Element spiegeln, können Sie dennoch mithilfe eines Objekts, das mit dem Typ der Basisklasse deklariert ist, auf das gespiegelte Element zugreifen.  Sie können auch über `MyBase` darauf zugreifen.  
  
 Der `Shadows`\-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Const\-Anweisung](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Declare\-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Delegate\-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Dim\-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Enum\-Anweisung](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Event\-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function\-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface\-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Property\-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub\-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## Siehe auch  
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)   
 [Static](../../../visual-basic/language-reference/modifiers/static.md)   
 [Private](../../../visual-basic/language-reference/modifiers/private.md)   
 [Me, My, MyBase, and MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)   
 [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)   
 [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)   
 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)   
 [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md)   
 [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)   
 [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)   
 [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
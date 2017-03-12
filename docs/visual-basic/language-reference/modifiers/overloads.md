---
title: "Overloads (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Overloads"
  - "Overloads"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Overloads keyword"
  - "hiding by signature"
  - "Shadows keyword"
  - "signature, hiding by"
ms.assetid: 0c6820b8-25b2-4664-bc59-5ca93c99c042
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Overloads (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Gibt an, dass eine Eigenschaft oder Prozedur eine Eigenschaft oder Prozedur bzw. mehrere mit dem gleichen Namen neu deklariert.  
  
## Hinweise  
 Als *Überladung* wird die Bereitstellung von mehreren Definitionen für eine angegebene Eigenschaft oder einen Prozedurnamen im selben Bereich bezeichnet.  Das erneute Deklarieren einer Eigenschaft oder Prozedur mit einer anderen Signatur wird gelegentlich als *Ausblenden nach Signatur* bezeichnet.  
  
## Regeln  
  
-   **Deklarationskontext.** Sie können `Overloads` nur in einer Eigenschaft oder einer Prozedurdeklarationsanweisung.  
  
-   **Kombinierte Modifizierer.** Sie können `Overloads` zusammen mit [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) in derselben Prozedurdeklaration angeben.  
  
-   **Erforderliche Unterschiede.** Die *Signatur* in dieser Deklaration muss sich von der Signatur jeder Eigenschaft oder Prozedur unterscheiden, die sie überlädt.  Die Signatur besteht aus der Eigenschaft oder dem Prozedurnamen und dem Folgenden:  
  
    -   der Anzahl der Parameter  
  
    -   Der Reihenfolge der Parameter  
  
    -   der Datentypen der Parameter  
  
    -   der Anzahl der Typparameter \(für eine generische Prozedur\)  
  
    -   des Rückgabetyps \(nur für eine Konvertierungsoperatorprozedur\)  
  
     Alle Überladungen müssen denselben Namen aufweisen. Jede muss sich jedoch von allen anderen in mindestens einem der vorstehenden Punkte unterscheiden.  Dadurch kann der Compiler unterscheiden, welche Version verwendet werden muss, wenn der Code die Eigenschaft oder Prozedur aufruft.  
  
-   **Nicht zulässige Unterschiede.** Das Ändern von mindestens einem der folgenden Punkte ist für das Überladen einer Eigenschaft oder Prozedur nicht gültig, da sie kein Bestandteil der Signatur sind:  
  
    -   ob ein Wert \(für eine Prozedur\) zurückgegeben wird  
  
    -   der Datentyp des Rückgabewerts \(mit Ausnahme eines Konvertierungsoperators\)  
  
    -   die Namen der Parameter oder Typparameter  
  
    -   die Einschränkungen hinsichtlich der Typparameter \(für eine generische Prozedur\)  
  
    -   Parametermodifiziererschlüsselwörter \(wie `ByRef` oder `Optional`\)  
  
    -   Eigenschaft oder Prozedurmodifiziererschlüsselwörter \(wie `Public` oder `Shared`\)  
  
-   **Optionaler Modifizierer.** Sie müssen den `Overloads`\-Modifizierer nicht verwenden, wenn Sie mehrere überladene Eigenschaften oder Prozeduren in derselben Klasse definieren.  Wenn Sie jedoch `Overloads` in einer der Deklarationen verwenden, müssen Sie sie in allen davon verwenden.  
  
-   **Shadowing und Überladung**. `Overloads` kann auch verwendet werden, um ein vorhandenes Member oder einen Satz von überladenen Membern in einer Basisklasse zu spiegeln  Wenn Sie `Overloads` auf diese Art und Weise verwenden, deklarieren Sie die Eigenschaft oder Methode mit demselben Namen und derselben Parameterliste als Basisklassenmember, und Sie stellen das `Shadows`\-Schlüsselwort nicht bereit.  
  
 Beim Verwenden von `Overrides` fügt der Compiler implizit `Overloads` hinzu, sodass Ihre Bibliotheks\-APIs leichter mit C\# verwendet werden können.  
  
 Der `Overloads`\-Modifizierer kann in den folgenden Kontexten verwendet werden:  
  
 [Function\-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property\-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub\-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## Siehe auch  
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)   
 [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
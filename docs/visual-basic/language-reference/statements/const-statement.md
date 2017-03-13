---
title: "Const Statement (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Const"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Const statement [Visual Basic]"
ms.assetid: 495b318d-b7c5-4198-94f8-0790a541b07a
caps.latest.revision: 28
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 28
---
# Const Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Deklariert und definiert eine oder mehrere Konstanten.  
  
## Syntax  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ]   
Const constantlist  
```  
  
## Teile  
 `attributelist`  
 Optional.  Liste von Attributen, die für alle in dieser Anweisung deklarierten Konstanten zutreffen.  Siehe [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) \(in spitzen Klammern "`<`" und "`>`"\).  
  
 `accessmodifier`  
 Optional.  Geben Sie damit an, welcher Code auf diese Konstanten zugreifen kann.  Kann [Public](../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend` oder [Private](../../../visual-basic/language-reference/modifiers/private.md) sein.  
  
 `Shadows`  
 Optional.  Verwenden Sie dieses Schlüsselwort, um ein Programmierelement in einer Basisklasse neu zu deklarieren und auszublenden.  Siehe [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
 `constantlist`  
 Erforderlich.  Liste der Konstanten, die in dieser Anweisung deklariert werden.  
  
 `constant` `[ ,` `constant` `... ]`  
  
 Jede `constant` hat folgende Syntax und folgende Bestandteile:  
  
 `constantname` `[ As` `datatype` `] =` `initializer`  
  
|Bestandteil|Beschreibung|  
|-----------------|------------------|  
|`constantname`|Erforderlich.  Name der Konstanten.  Weitere Informationen finden Sie unter [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`datatype`|Erforderlich, wenn `Option Strict` den Wert `On` aufweist.  Datentyp der Konstanten.|  
|`initializer`|Erforderlich.  Ausdruck, der zur Kompilierzeit ausgewertet und dieser Konstante zugewiesen wird.|  
  
## Hinweise  
 Wenn sich ein Wert in der Anwendung niemals ändert, können Sie eine benannte Konstante definieren und statt eines Literalwerts verwenden.  Ein Name ist einprägsamer als ein Wert.  Sie können die Konstante einmal definieren und an verschiedenen Stellen im Code verwenden.  Wenn der Wert in einer neueren Version neu definiert werden muss, muss lediglich in der `Const`\-Anweisung eine Änderung durchgeführt werden.  
  
 `Const` kann nur auf Modul\- oder Prozedurebene verwendet werden.  Dies bedeutet, dass der *Deklarationskontext* für eine Variable eine Klasse, eine Struktur, ein Modul, eine Prozedur oder ein Block sein muss und keine Quelldatei, kein Namespace und keine Schnittstelle sein kann.  Weitere Informationen finden Sie unter [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Für lokale Konstanten \(in einer Prozedur\) gilt standardmäßig der öffentliche Zugriff. Für diese Konstanten können keine Zugriffsmodifizierer verwendet werden.  Standardmäßig gilt für Klassen\- und Modulmemberkonstanten \(außerhalb einer Prozedur\) privater Zugriff und für Strukturmemberkonstanten öffentlicher Zugriff.  Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.  
  
## Regeln  
  
-   **Deklarationskontext.** Eine auf Modulebene deklarierte Konstante, die sich außerhalb jeglicher Prozedur befindet, ist eine *Memberkonstante*. Sie ist ein Member der Klasse, der Struktur oder des Moduls, in der bzw. dem sie deklariert ist.  
  
     Eine auf Prozedurebene deklarierte Konstante ist eine *lokale Konstante*. Sie ist nur lokal in der Prozedur oder dem Block gültig, in der\/dem sie deklariert ist.  
  
-   **Attribute.** Sie können Attribute nur auf Memberkonstanten und nicht auf lokale Konstanten anwenden.  Ein Attribut fügt den Metadaten einer Assembly Informationen hinzu. Dies ist für die temporäre Speicherung, z. B. in lokalen Konstanten, nicht sinnvoll.  
  
-   **Modifizierer.** Standardmäßig sind alle Konstanten `Shared`, `Static` und `ReadOnly`.  Beim Deklarieren einer Konstante können Sie keines dieser Schlüsselwörter verwenden.  
  
     Auf Prozedurebene können Sie zum Deklarieren lokaler Konstanten weder `Shadows` noch Zugriffsmodifizierer verwenden.  
  
-   **Mehrere Konstanten.** Sie können mehrere Konstanten in derselben Deklarationsanweisung deklarieren, indem Sie für jede Konstante den Bestandteil `constantname` angeben.  Mehrere Konstanten werden durch Komma voneinander getrennt.  
  
## Datentypregeln  
  
-   **Datentypen.** Die `Const`\-Anweisung kann den Datentyp einer Variablen deklarieren.  Sie können einen beliebigen Datentyp oder den Namen einer Enumeration angeben.  
  
-   **Standardtyp.** Wenn Sie `datatype` nicht angeben, übernimmt die Konstante automatisch den Datentyp von `initializer`.  Wenn Sie sowohl `datatype` als auch `initializer` angeben, muss der Datentyp `initializer` in `datatype` konvertiert werden können.  Wenn weder `datatype` noch `initializer` angegeben werden, wird standardmäßig `Object` als Datentyp verwendet.  
  
-   **Andere Typen.** Sie können für verschiedene Konstanten unterschiedliche Datentypen angeben, indem Sie für jede deklarierte Variable eine eigene `As`\-Klausel verwenden.  Sie können jedoch nicht mit einer gemeinsamen `As`\-Klausel denselben Typ für mehrere Konstanten deklarieren.  
  
-   **Initialisierung.** Sie müssen den Wert der einzelnen Konstanten in `constantlist` initialisieren.  Der `initializer` wird verwendet, um einen Ausdruck bereitzustellen, der der Konstante zugewiesen werden soll.  Bei dem Ausdruck kann es sich um eine beliebige Kombination von Literalen, anderen bereits definierten Konstanten und bereits definierten Enumerationsmembern handeln.  Zur Kombination dieser Elemente können Sie arithmetische und logische Operatoren verwenden.  
  
     Variablen und Funktionen können in `initializer` nicht verwendet werden.  Sie können jedoch Konvertierungsschlüsselwörter wie `CByte` und `CShort` verwenden.  In Kombination mit einem konstanten `String`\- oder `Char`\-Argument, das zur Kompilierungszeit ausgewertet wird, kann auch `AscW` verwendet werden.  
  
## Verhalten  
  
-   **Gültigkeitsbereich.** Auf lokale Konstanten kann nur in ihrer Prozedur oder ihrem Block zugegriffen werden.  Auf Memberkonstanten kann von jeder Stelle in ihrer Klasse, ihrer Struktur oder ihrem Modul zugegriffen werden.  
  
-   **Qualifikation.** Code außerhalb einer Klasse, einer Struktur oder eines Moduls muss den Namen einer Memberkonstanten mit dem Namen der Klasse, der Struktur bzw. des Moduls qualifizieren.  Code außerhalb einer Prozedur oder eines Blocks kann auf keine lokalen Konstanten innerhalb dieser Prozedur bzw. Blocks verweisen.  
  
## Beispiel  
 Im folgenden Beispiel wird mit der `Const`\-Anweisung die Verwendung von Konstanten anstelle von Literalwerten deklariert.  
  
 [!code-vb[VbVbalrStatements#13](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/const-statement_1.vb)]  
  
## Beispiel  
 Wenn Sie eine Konstante mit dem Datentyp `Object` definieren, weist ihr der Visual Basic\-Compiler anstelle von `Object` den Typ `initializer` zu.  Im folgenden Beispiel verfügt die Konstante `naturalLogBase` über den Laufzeittyp `Decimal`.  
  
 [!code-vb[VbVbalrStatements#87](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/const-statement_2.vb)]  
  
 Im vorherigen Beispiel wird die <xref:System.Type.ToString%2A>\-Methode für das vom [GetType Operator](../../../visual-basic/language-reference/operators/gettype-operator.md) zurückgegebene <xref:System.Type>\-Objekt verwendet, weil <xref:System.Type> nicht mit `CStr` in `String` konvertiert werden kann.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>   
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>   
 [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md)   
 [\#Const Directive](../../../visual-basic/language-reference/directives/const-directive.md)   
 [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)   
 [ReDim Statement](../../../visual-basic/language-reference/statements/redim-statement.md)   
 [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Constants and Enumerations](../../../visual-basic/programming-guide/language-features/constants-enums/index.md)   
 [Constants and Enumerations](../../../visual-basic/language-reference/constants-and-enumerations.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
---
title: "Option Compare Statement | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Compare"
  - "vb.OptionCompare"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "case sensitivity, Option Compare statement"
  - "Compare keyword"
  - "binary comparison"
  - "strings [Visual Basic], returning from functions"
  - "binary comparison, Option Compare statement"
  - "strings [Visual Basic], comparing"
  - "string comparison [Visual Basic], Option Compare statement"
  - "Text keyword, Option Compare statement"
  - "Binary keyword, Option Compare statement"
  - "string comparison [Visual Basic], sorting data"
  - "Option Compare statement"
  - "text [Visual Basic], comparing"
ms.assetid: 54e8eeeb-3b0d-4fb9-acce-fbfbd5975f6e
caps.latest.revision: 37
caps.handback.revision: 37
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Option Compare Statement
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Deklariert die Standardvergleichsmethode, die beim Vergleichen von Zeichenfolgendaten verwendet wird.  
  
## Syntax  
  
```  
Option Compare { Binary | Text }  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`Binary`|Dies ist optional.  Resultiert in Zeichenfolgenvergleichen basierend auf einer Sortierreihenfolge, die sich von den internen binären Darstellungen der Zeichen ableitet.<br /><br /> Diese Art von Vergleich ist besonders hilfreich, da die Zeichenfolgen Zeichen enthalten können, die nicht als Text interpretiert werden.  In diesem Fall sollten Sie Vergleiche nicht alphabetischen Äquivalenzen, z. B. Groß\-\/Kleinschreibung vorziehen.|  
|`Text`|Dies ist optional.  Führt zu einem Zeichenfolgenvergleich basierend auf einer schreibungsunabhängigen Textsortierreihenfolge, die durch das Gebietsschema des Systems bestimmt wird.<br /><br /> Diese Art von Vergleich ist nützlich, wenn die Zeichenfolgen nur Textzeichen enthalten und Sie nur anhand alphabetischer Äquivalenzen z. B. Groß\-\/Kleinschreibung oder eng verwandter Buchstaben vergleichen möchten.  Sie könnten zum Beispiel `A` und `a` als gleich ansehen und `Ä` und `ä`, die vor `B` und `b` kommen.|  
  
## Hinweise  
 Wenn sie verwendet wird, muss die `Option Compare`\-Anweisung in einer Datei vor allen anderen Quellcodeanweisungen angeordnet sein.  
  
 Die `Option Compare`\-Anweisung gibt die Zeichenfolgenvergleichsmethode vor \(`Binary` oder `Text`\).  Die Standardmethode zum Textvergleich ist `Binary`.  
  
 Ein `Binary`\-Vergleich vergleicht den numerischen Unicode\-Wert jedes Zeichens in jeder Zeichenfolge.  Ein `Text`\-Vergleich vergleicht alle Unicode\-Zeichen anhand der lexikalische Bedeutung in der aktuellen Kultur.  
  
 In Microsoft Windows wird die Sortierreihenfolge durch die Codepage festgelegt.  Weitere Informationen finden Sie unter [Codepages](/visual-cpp/c-runtime-library/code-pages).  
  
 Im folgenden Beispiel werden Zeichen der Codepage für Westeuropäisch \(ANSI 1252\) mit `Option Compare Binary` sortiert, wodurch eine typische binäre Sortierreihenfolge erzeugt wird.  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 Wenn dieselben Zeichen in derselben Codepage `Option Compare Text` mit sortiert werden, wird die folgende Sortierreihenfolge erzeugt.  
  
 `(A=a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
## Wenn eine Option Compare\-Anweisung nicht vorhanden ist  
 Wenn der Quellcode keine `Option Compare`\-Anweisung enthält, wird die Einstellung **Option Compare** auf der [Seite "Kompilieren", Projekt\-Designer \(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic) wird verwendet.  Wenn Sie den Befehlszeilencompiler verwenden, wird die Einstellung verwendet, die von der [\/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)\-Compileroption festgelegt wird.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
#### Festelegen der Option Compare in der IDE  
  
1.  Wählen Sie im **Projektmappen\-Explorer** ein Projekt aus.  Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  Weitere Informationen finden Sie unter [NIB: Managing Project Properties with the Project Designer](http://msdn.microsoft.com/de-de/983f3c18-832f-4666-afec-74b716ff3e0e).  
  
2.  Klicken Sie die Registerkarte **Kompilieren**.  
  
3.  Legen Sie den Wert im Textfeld **Option Compare** fest.  
  
 Wenn Sie ein Projekt erstellen, wird die **Option Compare**\-Einstellung in der Registerkarte **Kompilieren** auf die **Option Compare**\-Einstellung im Dialogfeld **Optionen** festgelegt.  Um diese Einstellung zu ändern, klicken Sie im Menü **Tools** auf **Optionen**.  Erweitern Sie im Dialogfeld **Optionen Projekte und Lösungen** und klicken Sie dann auf **VB Defaults**.  Die ursprüngliche Standardeinstellung in **VB Defaults** ist **binär**.  
  
#### Festlegen der Option Compare in der Befehlszeile  
  
-   Aktivieren Sie die [\/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)\-Compileroption im **vbc**\-Befehl.  
  
## Beispiel  
 Das folgenden Beispiel verwendet die `Option Compare`\-Anweisung, um den binären Vergleich als die Standardzeichenfolgenvergleichsmethode festzulegen.  Um diesen Code zu verwenden, heben Sie die Auskommentierung der `Option Compare Binary`\-Anweisung auf und positionieren Sie sie am Anfang der Quelldatei.  
  
 [!code-vb[VbVbalrStatements#45](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-compare-statement_1.vb)]  
  
## Beispiel  
 Im folgenden Beispiel wird die `Option Compare`\-Anweisung verwendet, um die Textsortierreihenfolge als die Standardzeichenfolgenvergleichsmethode festzulegen.  Um diesen Code zu verwenden, heben Sie die Auskommentierung der `Option Compare Text`\-Anweisung auf und positionieren Sie sie am Anfang der Quelldatei.  
  
 [!code-vb[VbVbalrStatements#46](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-compare-statement_2.vb)]  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Strings.InStr%2A>   
 <xref:Microsoft.VisualBasic.Strings.InStrRev%2A>   
 <xref:Microsoft.VisualBasic.Strings.Replace%2A>   
 <xref:Microsoft.VisualBasic.Strings.Split%2A>   
 <xref:Microsoft.VisualBasic.Strings.StrComp%2A>   
 [\/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)   
 [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md)   
 [Comparison Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Like Operator](../../../visual-basic/language-reference/operators/like-operator.md)   
 [String\-Funktionen](../../../visual-basic/language-reference/functions/string-functions.md)   
 [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md)   
 [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)
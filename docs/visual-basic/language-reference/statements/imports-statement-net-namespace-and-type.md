---
title: "Imports Statement (.NET Namespace and Type) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Imports"
  - "imports"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "declared element names [Visual Basic], qualification"
  - "imports [Visual Basic]"
  - "Imports statement [Visual Basic]"
  - "aliases [Visual Basic], Imports statement"
  - "container elements [Visual Basic]"
  - "namespaces [Visual Basic], importing"
  - "Imports statement [Visual Basic], syntax"
  - "import aliases [Visual Basic]"
  - "aliases [Visual Basic], import"
  - "declared elements [Visual Basic], container elements"
ms.assetid: 7062f8aa-d890-4232-9eed-92836e13fb6e
caps.latest.revision: 40
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 40
---
# Imports Statement (.NET Namespace and Type)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Ermöglicht Typnamenverweise ohne Namespaceangabe.  
  
## Syntax  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`aliasname`|Optional.  Ein *Importalias* oder Name, mit dem Code auf `namespace` statt auf den vollständigen Qualifizierungspfad verweisen kann.  Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`namespace`|Erforderlich.  Der vollqualifizierte Name des importierten Namespaces.  Kann eine Zeichenfolge mit Namespaces sein, die auf beliebiger Ebenen geschachtelt sind.|  
|`element`|Optional.  Der Name eines im Namespace deklarierten Programmierelements.  Kann ein beliebiges Containerelement sein.|  
  
## Hinweise  
 Die `Imports` \-Anweisung ermöglicht direkte Verweise auf Typen, die in einem bestimmten Namespace enthalten sind.  
  
 Sie können einen einzelnen Namespacenamen oder eine Zeichenfolge mit geschachtelten Namespaces angeben.  Jeder geschachtelte Namespace ist vom Namespace auf der nächsthöheren Ebene durch einen \(`.`\) getrennt, wie im folgenden Beispiel veranschaulicht.  
  
 `Imports System.Collections.Generic`  
  
 Jede Quelldatei kann beliebig viele `Imports`\-Anweisungen enthalten.  Diese müssen nach sämtlichen Option\-Deklarationen, z. B. `Option Strict`, angegeben werden und sämtlichen Deklarationen von Programmierelementen, z. B. `Module`\-Anweisungen oder `Class`\-Anweisungen, vorangestellt werden.  
  
 `Imports` kann nur auf Dateiebene verwendet werden.  Dies bedeutet, dass der Deklarationskontext für den Import eine Quelldatei sein muss und kein Namespace, keine Klasse, keine Struktur, kein Modul, keine Schnittstelle, keine Prozedur und kein Block sein kann.  
  
 Beachten Sie, dass mit der `Imports`\-Anweisung keine Elemente aus anderen Projekten und Assemblys für ein Projekt verfügbar gemacht werden.  Das Importieren ersetzt nicht des Festlegens eines Verweises.  Es macht nur das Qualifizieren von Namen überflüssig, die bereits für das Projekt verfügbar sind.  Weitere Informationen finden Sie unter [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) in "Importieren von enthaltenden Elementen".  
  
> [!NOTE]
>  Sie können implizite `Imports`\-Anweisungen mithilfe der [Seite "Verweise", Projekt\-Designer \(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic) definieren.  Weitere Informationen finden Sie unter [Gewusst wie: Hinzufügen oder Entfernen von importierten Namespaces \(Visual Basic\)](../Topic/How%20to:%20Add%20or%20Remove%20Imported%20Namespaces%20\(Visual%20Basic\).md).  
  
## Importaliase  
 Ein *Import\-Alias* definiert den Alias für einen Namespace oder Typ.  Importaliase sind sinnvoll, wenn Sie Elemente mit identischen Namen verwenden, die in einem oder mehreren Namespaces deklariert sind.  Weitere Informationen und ein Beispiel finden Sie in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) unter "Qualifizieren eines Elementnamens".  
  
 Deklarieren Sie einen Member auf Modulebene nicht mit demselben Namen wie `aliasname`.  Andernfalls verwendet der Visual Basic\-Compiler `aliasname` nur für den deklarierten Member und erkennt den Namen nicht mehr als Importalias.  
  
 Obwohl für die Deklaration eines Importalias eine ähnliche Syntax verwendet wird, wie für den Import eines XML\-Namespacepräfixes, unterscheiden sich die Ergebnisse.  Ein Importalias kann auch als Ausdruck im Code verwendet werden, während ein XML\-Namespacepräfix nur in XML\-Literalen oder in XML\-Achseneigenschaften als Präfix für ein qualifiziertes Element oder einen Attributnamen verwendet werden kann.  
  
### Elementnamen  
 Wenn Sie ein `element` angeben, muss dieses ein *Containerelement* darstellen, d. h. ein Programmierelement, das andere Elemente enthalten kann.  Zu Containerelementen zählen Klassen, Strukturen, Module, Schnittstellen und Enumerationen.  
  
 Der Gültigkeitsbereich der Elemente, die durch eine `Imports`\-Anweisung verfügbar gemacht werden, hängt davon ab, ob Sie `element` angeben.  Wenn Sie nur `namespace` angeben, sind alle eindeutig benannten Member dieses Namespaces und die Member der Containerelemente in diesem Namespace ohne Qualifizierung verfügbar.  Wenn Sie sowohl `namespace` als auch `element` angeben, sind nur die Member dieses Elements ohne Qualifizierung verfügbar.  
  
## Beispiel  
 Im folgenden Beispiel werden alle Ordner im Verzeichnis C:\\ mithilfe der <xref:System.IO.DirectoryInfo>\-Klasse zurückgegeben.  
  
 Der Code enthält keine `Imports`\-Anweisungen am Anfang der Datei.  Daher sind die Verweise `DirectoryInfo`, <xref:System.Text.StringBuilder> und <xref:Microsoft.VisualBasic.ControlChars.CrLf> mit den Namespaces alle vollqualifiziert.  
  
 [!code-vb[VbVbalrStatements#152](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/imports-statement-net-na_1.vb)]  
  
## Beispiel  
 Das folgende Beispiel enthält Anweisungen, die `Imports` für die referenzierten Namespaces.  Daher müssen die Typen nicht mit den Namespaces vollqualifiziert werden.  
  
 [!code-vb[VbVbalrStatements#153](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/imports-statement-net-na_2.vb)]  
  
 [!code-vb[VbVbalrStatements#154](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/imports-statement-net-na_3.vb)]  
  
## Beispiel  
 Das folgende Beispiel enthält `Imports`\-Anweisungen, die Aliase für die referenzierten Namespaces erstellen.  Die Typen werden mit den Aliasen qualifiziert.  
  
 [!code-vb[VbVbalrStatements#155](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/imports-statement-net-na_4.vb)]  
  
 [!code-vb[VbVbalrStatements#156](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/imports-statement-net-na_5.vb)]  
  
## Beispiel  
 Das folgende Beispiel enthält `Imports`\-Anweisungen, die Aliase für die referenzierten Typen erstellen.  Aliase werden verwendet, um die Typen angeben.  
  
 [!code-vb[VbVbalrStatements#157](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/imports-statement-net-na_6.vb)]  
  
 [!code-vb[VbVbalrStatements#158](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/imports-statement-net-na_7.vb)]  
  
## Siehe auch  
 [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md)   
 [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)   
 [Imports Statement \(XML Namespace\)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)   
 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
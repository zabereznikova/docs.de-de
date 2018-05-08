---
title: Imports-Anweisung (.NET-Namespace und Typ)
ms.date: 07/20/2015
f1_keywords:
- vb.Imports
- imports
helpviewer_keywords:
- declared element names [Visual Basic], qualification
- imports [Visual Basic]
- Imports statement [Visual Basic]
- aliases [Visual Basic], Imports statement
- container elements [Visual Basic]
- namespaces [Visual Basic], importing
- Imports statement [Visual Basic], syntax
- import aliases [Visual Basic]
- aliases [Visual Basic], import
- declared elements [Visual Basic], container elements
ms.assetid: 7062f8aa-d890-4232-9eed-92836e13fb6e
ms.openlocfilehash: ef569b0ed6428d24d019e00c500e4d4b91c83d49
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="imports-statement-net-namespace-and-type"></a>Imports-Anweisung (.NET-Namespace und Typ)
Ermöglicht das Typnamen ohne Namespacequalifikation referenziert werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`aliasname`|Dies ist optional. Ein *Importalias* oder Namen, die mit dem Code, um verweisen kann `namespace` anstelle der vollständigen Qualifizierungspfad. Finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`namespace`|Erforderlich. Der vollqualifizierte Name des zu importierenden Namespaces. Eine Zeichenfolge von Namespaces kann auf beliebigen Ebenen geschachtelt werden.|  
|`element`|Dies ist optional. Der Name eines Programmierelements deklarierten im Namespace. Ein Containerelement kann sein.|  
  
## <a name="remarks"></a>Hinweise  
 Die `Imports` -Anweisung ermöglicht es, Typen, die in einem bestimmten Namespace direkt verwiesen wird, enthalten sind.  
  
 Sie können einen einzelnen Namespace-Namen oder eine Zeichenfolge von geschachtelten Namespaces angeben. Jeden geschachtelten Namespace wird vom nächsten höheren Ebene Namespace durch einen Punkt getrennt (`.`), wie im folgende Beispiel veranschaulicht wird.  
  
 `Imports System.Collections.Generic`  
  
 Jeder Quelldatei kann eine beliebige Anzahl von enthalten `Imports` Anweisungen. Diese müssen führen Sie die Option-Deklarationen, z. B. die `Option Strict` -Anweisung, und sie müssen vor stehen Deklarationen von Programmierelementen, z. B. `Module` oder `Class` Anweisungen.  
  
 Sie können `Imports` nur auf Dateiebene. Dies bedeutet, dass der Deklarationskontext für den Import von eine Quelldatei muss und nicht mit Namespace, Klasse, Struktur, Modul, Schnittstelle, Prozedur oder Block.  
  
 Beachten Sie, dass die `Imports` Anweisung nimmt Elemente aus anderen Projekten und Assemblys für Ihr Projekt verfügbar. Importieren von ist nicht das Festlegen eines Verweises stattfinden. Es erübrigt es sich nur um Namen zu qualifizieren, die bereits im Projekt verfügbar sind. Weitere Informationen finden Sie unter "Importieren von enthaltenen Elementen" in [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
> [!NOTE]
>  Sie können implizite definieren `Imports` -Anweisungen mithilfe der [Seite "Verweise", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic). Weitere Informationen finden Sie unter [wie: Hinzufügen oder Entfernen von importierten Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).  
  
## <a name="import-aliases"></a>Importaliase  
 Ein *Importalias* den Alias für einen Namespace oder Typ definiert. Importaliase sind nützlich, wenn Sie mithilfe der Elemente mit dem gleichen Namen, die in einem oder mehreren Namespaces deklariert werden müssen. Weitere Informationen und ein Beispiel finden Sie unter "Qualifizieren eines Elementnamens" in [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
 Sie sollten nicht deklarieren, ein Element auf Modulebene mit dem gleichen Namen wie `aliasname`. Wenn Sie dies tun, Visual Basic-Compiler verwendet `aliasname` nur für den deklarierten Member und nicht länger als ein Importalias erkannt.  
  
 Obwohl die Syntax zum Deklarieren von ein Importalias verwendet wie zum Importieren einer XML-Namespacepräfix verwendet wird, unterscheiden sich die Ergebnisse. Ein Importalias kann als ein Ausdruck in Ihrem Code verwendet werden, während ein XML-Namespacepräfix nur in XML-Literalen oder XML-Achseneigenschaften als Präfix für eine qualifiziertes Element oder Attribut verwendet werden kann.  
  
### <a name="element-names"></a>Elementnamen  
 Wenn Sie angeben `element`, muss darstellen einer *Containerelement*, d. h. ein Programmierelement, das andere Elemente enthalten kann. Containerelemente enthalten Klassen, Strukturen, Modulen, Schnittstellen und Enumerationen.  
  
 Der Bereich der Elemente zur Verfügung gestellt wurden ein `Imports` Anweisung hängt davon ab, ob Sie angeben `element`. Wenn Sie nur angeben, `namespace`, alle eindeutig benannten Member dieses Namespace und Mitglieder der Containerelemente in diesem Namespace, ohne Qualifizierung verfügbar sind. Wenn Sie beide angeben `namespace` und `element`nur die Elemente dieses Elements ohne Qualifizierung verfügbar sind.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel gibt alle Ordner im Verzeichnis C:\ mithilfe der <xref:System.IO.DirectoryInfo> Klasse.  
  
 Der Code hat keine `Imports` Anweisungen am Anfang der Datei. Aus diesem Grund die `DirectoryInfo`, <xref:System.Text.StringBuilder>, und <xref:Microsoft.VisualBasic.ControlChars.CrLf> Verweise mit Namespaces vollständig qualifiziert werden.  
  
 [!code-vb[VbVbalrStatements#152](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel schließt `Imports` Anweisungen für die Namespaces verwiesen wird. Aus diesem Grund müssen die Typen nicht mit den Namespaces vollqualifiziert sein.  
  
 [!code-vb[VbVbalrStatements#153](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_2.vb)]  
  
 [!code-vb[VbVbalrStatements#154](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_3.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel schließt `Imports` -Anweisungen, die Aliase für die referenzierten Namespaces erstellen. Die Typen werden mit den Aliasen qualifiziert.  
  
 [!code-vb[VbVbalrStatements#155](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_4.vb)]  
  
 [!code-vb[VbVbalrStatements#156](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_5.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel schließt `Imports` -Anweisungen, die Aliase für den referenzierten Typen zu erstellen. Aliase werden verwendet, um die Typen anzugeben.  
  
 [!code-vb[VbVbalrStatements#157](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_6.vb)]  
  
 [!code-vb[VbVbalrStatements#158](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_7.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Namespace-Anweisung](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [Verweise und die Imports-Anweisung](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)  
 [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)

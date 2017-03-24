---
title: Imports-Anweisung (.NET Namespace und Typ) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Imports
- imports
dev_langs:
- VB
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
caps.latest.revision: 40
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 393f3e9a264817d8658585267c954d973290530a
ms.lasthandoff: 03/13/2017

---
# <a name="imports-statement-net-namespace-and-type"></a>Imports-Anweisung (.NET-Namespace und Typ)
Ermöglicht Typnamen ohne Kennzeichnung durch einen Namespace verwiesen werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`aliasname`|Optional. Ein *importieren Alias* oder den Namen, die mit dem Code, um verweisen kann `namespace` anstelle der vollständigen Qualifizierungspfad. Finden Sie unter [deklarierten Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`namespace`|Erforderlich. Der vollqualifizierte Name des zu importierenden Namespace. Eine Zeichenfolge mit Namespaces kann auf allen Ebenen geschachtelt werden.|  
|`element`|Optional. Der Name eines Programmierelements deklarierten im Namespace. Containerelement kann sein.|  
  
## <a name="remarks"></a>Hinweise  
 Die `Imports` -Anweisung ermöglicht die Typen, die in einem bestimmten Namespace direkte Verweise auf enthalten sind.  
  
 Sie können einen einzelnen Namespacenamen oder eine Zeichenfolge mit geschachtelten Namespaces angeben. Jeden geschachtelten Namespace ist aus dem nächsten höherer Ebene Namespace durch einen Punkt getrennt (`.`), wie im folgende Beispiel veranschaulicht wird.  
  
 `Imports System.Collections.Generic`  
  
 Jede Quelldatei kann eine beliebige Anzahl von enthalten `Imports` Anweisungen. Diese müssen führen Sie die Option-Deklarationen, wie z. B. die `Option Strict` -Anweisung, und sie müssen Deklarationen von Programmierelementen, wie z. B. voranstellen `Module` oder `Class` Anweisungen.  
  
 Sie können `Imports` nur auf Dateiebene. Dies bedeutet, dass Deklarationskontext für den Import von muss eine Quelldatei und einen Namespace, Klasse, Struktur, Modul, Schnittstelle, Prozedur oder Block nicht möglich.  
  
 Beachten Sie, dass die `Imports` Anweisung macht nicht Elemente aus anderen Projekten und Assemblys im Projekt verfügbar. Importieren erfolgt der Festlegen eines Verweises. Es entfernt nur die Notwendigkeit, qualifizieren Sie Namen, die bereits im Projekt verfügbar sind. Weitere Informationen finden Sie unter "Importieren von enthaltenden Elementen" in [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
> [!NOTE]
>  Sie können implizite definieren `Imports` -Anweisungen mithilfe der [Seite "Verweise", Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic). Weitere Informationen finden Sie unter [Gewusst wie: Hinzufügen oder Entfernen von importierten Namespaces (Visual Basic)](http://msdn.microsoft.com/library/44cebec3-0ea0-47c2-8406-4edeab6a997e).  
  
## <a name="import-aliases"></a>Importaliase  
 Ein *importieren Alias* definiert den Alias für einen Namespace oder Typ. Importaliase sind nützlich, wenn Sie mithilfe der Elemente mit dem gleichen Namen, die in einem oder mehreren Namespaces deklariert werden müssen. Weitere Informationen und ein Beispiel finden Sie unter "Qualifizieren eines Elementnamens" in [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
 Deklarieren Sie nicht Mitglied auf Modulebene mit dem gleichen Namen wie `aliasname`. Wenn Sie dies tun, Visual Basic-Compiler verwendet `aliasname` nur für den deklarierten Member und darf nicht mehr als ein Importalias erkannt.  
  
 Obwohl die Syntax zum Deklarieren eines Importalias für ein XML-Namespacepräfix importieren, verwendet wird, unterscheiden sich die Ergebnisse. Ein Importalias kann als Ausdruck in Ihrem Code verwendet werden, während ein XML-Namespacepräfix nur in XML-Literalen oder XML-Achseneigenschaften als Präfix für ein qualifiziertes Element oder Attributname verwendet werden kann.  
  
### <a name="element-names"></a>Elementnamen  
 Wenn Sie angeben, `element`, muss darstellen einer *Containerelement*, d. h. ein Programmierelement, das andere Elemente enthalten kann. Container-Elemente enthalten Klassen, Strukturen, Module, Schnittstellen und Enumerationen.  
  
 Der Gültigkeitsbereich der Elemente zur Verfügung gestellt wurden ein `Imports` Anweisung, hängt davon ab, ob angegeben `element`. Wenn Sie lediglich angeben `namespace`, alle eindeutig benannten Member dieses Namespaces und Member der Containerelemente in diesem Namespace, ohne Qualifizierung verfügbar sind. Wenn Sie beide angeben `namespace` und `element`, werden nur die Member dieses Elements ohne Qualifizierung verfügbar.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel gibt alle Ordner im Verzeichnis C:\ mithilfe der <xref:System.IO.DirectoryInfo>Klasse.</xref:System.IO.DirectoryInfo>  
  
 Der Code verfügt über keine `Imports` -Anweisungen am Anfang der Datei. Aus diesem Grund die `DirectoryInfo`, <xref:System.Text.StringBuilder>, und <xref:Microsoft.VisualBasic.ControlChars.CrLf>Verweise sind mit den Namespaces alle vollqualifiziert.</xref:Microsoft.VisualBasic.ControlChars.CrLf> </xref:System.Text.StringBuilder>  
  
 [!code-vb[VbVbalrStatements&#152;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel schließt `Imports` Anweisungen für die Namespaces verwiesen wird. Daher müssen die Typen nicht mit den Namespaces vollqualifiziert sein.  
  
 [!code-vb[VbVbalrStatements&#153;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_2.vb)]  
  
 [!code-vb[VbVbalrStatements&#154;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_3.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel schließt `Imports` -Anweisungen, die Aliase für den referenzierten Namespaces erstellen. Die Typen werden mit den Aliasen qualifiziert.  
  
 [!code-vb[VbVbalrStatements&#155;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_4.vb)]  
  
 [!code-vb[VbVbalrStatements&#156;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_5.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel schließt `Imports` -Anweisungen, die Aliase für den referenzierten Typen zu erstellen. Aliase werden verwendet, um die Typen anzugeben.  
  
 [!code-vb[VbVbalrStatements&#157;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_6.vb)]  
  
 [!code-vb[VbVbalrStatements&#158;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/imports-statement-net-namespace-and-type_7.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Namespace-Anweisung](../../../visual-basic/language-reference/statements/namespace-statement.md)   
 [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [Verweise und die Imports-Anweisung](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)   
 [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)   
 [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)

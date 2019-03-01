---
title: Imports-Anweisung - Namespace von .NET und Datentyp (Visual Basic)
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
ms.openlocfilehash: 93b299ffd8d2be1b1fabfd752e75d18ef87714b2
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974379"
---
# <a name="imports-statement-net-namespace-and-type"></a>Imports-Anweisung (.NET-Namespace und Typ)
Ermöglicht das Typnamen ohne namespacenennung verwiesen werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
Imports [ aliasname = ] namespace  
-or-  
Imports [ aliasname = ] namespace.element  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`aliasname`|Dies ist optional. Ein *Importalias* oder Namen, die mit dem Code, um verweisen kann `namespace` anstelle der vollständigen Qualifizierungspfad. Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`namespace`|Erforderlich. Der voll gekennzeichnete Name des Namespace importiert wird. Eine Zeichenfolge von Namespaces kann zu allen Ebenen geschachtelt werden.|  
|`element`|Dies ist optional. Der Namen eines Programmierelements, die in den Namespace deklariert werden. Alle Containerelement kann sein.|  
  
## <a name="remarks"></a>Hinweise  
 Die `Imports` Anweisung aktiviert die Typen, die in einem angegebenen Namespace nicht direkt verwiesen werden, enthalten sind.  
  
 Sie können einen einzelnen Namespace-Namen oder eine Zeichenfolge von geschachtelten Namespaces angeben. Jeden geschachtelten Namespace ist aus dem nächsten höheren Ebene Namespace durch einen Punkt getrennt (`.`), wie im folgende Beispiel veranschaulicht.  
  
 `Imports System.Collections.Generic`  
  
 Jede Quelldatei kann eine beliebige Anzahl von enthalten `Imports` Anweisungen. Diese müssen führen Sie die Option-Deklarationen, z. B. die `Option Strict` -Anweisung, und sie müssen vor stehen Deklarationen von Programmierelementen, z. B. `Module` oder `Class` Anweisungen.  
  
 Sie können `Imports` nur auf Dateiebene. Dies bedeutet, dass der Deklarationskontext für den Import von muss eine Quelldatei und Namespace, Klasse, Struktur, Modul, Schnittstelle, Prozedur oder Block nicht möglich.  
  
 Beachten Sie, dass die `Imports` Anweisung macht nicht Elemente aus anderen Projekten und Assemblys für Ihr Projekt verfügbar. Importieren von nimmt nicht an die Stelle der Festlegen eines Verweises. Es wird lediglich entfernt die Notwendigkeit, qualifizieren Sie Namen, die bereits für Ihr Projekt verfügbar sind. Weitere Informationen finden Sie unter "Importieren von enthaltenen Elementen" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
> [!NOTE]
>  Sie können implizite definieren `Imports` Anweisungen durch Verwenden der [Seite "Verweise", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic). Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen oder Entfernen von importierten Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).  
  
## <a name="import-aliases"></a>Importaliase  
 Ein *Importalias* definiert den Alias für einen Namespace oder Typ. Importaliase sind nützlich, wenn Sie Elemente verwenden, mit dem gleichen Namen, die in einem oder mehreren Namespaces deklariert werden müssen. Weitere Informationen und ein Beispiel finden Sie unter "Qualifizieren eines Elementnamens" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
 Deklarieren Sie nicht Mitglied auf Modulebene mit dem gleichen Namen wie `aliasname`. Visual Basic-Compiler wird verwendet, wenn Sie dies tun, `aliasname` nur für den deklarierten Member und nicht mehr als ein Importalias erkannt.  
  
 Obwohl die Syntax für einen Importalias deklarieren, zum Importieren einer XML-Namespacepräfix verwendet wird, unterscheiden sich die Ergebnisse. Ein Importalias kann als ein Ausdruck in Ihrem Code verwendet werden, während ein XML-Namespacepräfix in XML-Literalen oder XML-Achseneigenschaften nur als Präfix für ein qualifiziertes Element oder Attributname verwendet werden kann.  
  
### <a name="element-names"></a>Elementnamen  
 Wenn Sie angeben `element`, muss darstellen einer *Containerelement*, d. h. ein Programmierelement, das andere Elemente enthalten kann. Container-Elemente enthalten Klassen, Strukturen, Module, Schnittstellen und Enumerationen.  
  
 Der Bereich der Elemente zur Verfügung gestellt wurden ein `Imports` Anweisung hängt davon ab, ob Sie angeben `element`. Wenn Sie nur angeben `namespace`, alle eindeutig benannte Member dieses Namespace und Mitglieder der Container-Elemente innerhalb dieses Namespace sind ohne Qualifizierung verfügbar. Wenn Sie beide angeben `namespace` und `element`, nur die Elemente des Elements ohne Qualifizierung verfügbar sind.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel gibt alle Ordner im Verzeichnis C:\ mit der <xref:System.IO.DirectoryInfo> Klasse.  
  
 Der Code weist keine `Imports` Anweisungen am Anfang der Datei. Aus diesem Grund die `DirectoryInfo`, <xref:System.Text.StringBuilder>, und <xref:Microsoft.VisualBasic.ControlChars.CrLf> Verweise mit den Namespaces alle vollständig qualifiziert werden.  
  
 [!code-vb[VbVbalrStatements#152](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#152)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel schließt `Imports` Anweisungen für die Namespaces auf die verwiesen wird. Aus diesem Grund müssen die Typen nicht mit den Namespaces vollqualifiziert sein.  
  
 [!code-vb[VbVbalrStatements#153](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#153)]  
  
 [!code-vb[VbVbalrStatements#154](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#154)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel schließt `Imports` -Anweisungen, die Aliase für den referenzierten Namespace zu erstellen. Die Typen werden mit den Aliasen qualifiziert.  
  
 [!code-vb[VbVbalrStatements#155](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#155)]  
  
 [!code-vb[VbVbalrStatements#156](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#156)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel schließt `Imports` -Anweisungen, die Aliase für den referenzierten Typen erstellen. Aliase werden verwendet, um die Typen anzugeben.  
  
 [!code-vb[VbVbalrStatements#157](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#157)]  
  
 [!code-vb[VbVbalrStatements#158](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#158)]  
  
## <a name="see-also"></a>Siehe auch
- [Namespace-Anweisung](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [Verweise und die Imports-Anweisung](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
- [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)

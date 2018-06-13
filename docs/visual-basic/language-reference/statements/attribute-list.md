---
title: Attributliste (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
ms.openlocfilehash: 35d031722a5eddd6adce5e32df62b86c500d305b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604069"
---
# <a name="attribute-list-visual-basic"></a>Attributliste (Visual Basic)
Gibt die Attribute, die auf eine deklarierte Programmierelement angewendet werden. Mehrere Attribute werden durch Kommas getrennt. Nachfolgend ist die Syntax für ein Attribut.  
  
## <a name="syntax"></a>Syntax  
  
```  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a>Teile  
 `attributemodifier`  
 Erforderlich für Attribute, die am Anfang einer Quelldatei angewendet. Kann [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) oder [Modul](../../../visual-basic/language-reference/modifiers/module-keyword.md).  
  
 `attributename`  
 Erforderlich. Der Name des Attributs.  
  
 `attributearguments`  
 Dies ist optional. Liste der Positionsargumente für dieses Attribut. Mehrere Argumente werden durch Kommas getrennt.  
  
 `attributeinitializer`  
 Dies ist optional. Liste der Variablen oder Eigenschaft-Initialisierer für dieses Attribut. Mehrere Initialisierer werden durch Kommas getrennt.  
  
## <a name="remarks"></a>Hinweise  
 Sie können ein oder mehrere Attribute auf fast alle Programmierelement (Typen, Prozeduren, Eigenschaften und So weiter) anwenden. Attribute, die in den Metadaten der Assembly angezeigt werden, und können Sie kommentieren von Code oder gibt an, wie ein bestimmtes Programmierelement verwenden. Vom Visual Basic und .NET Framework definierten Attribute angewendet werden, und Sie können eigene Attribute definieren.  

 Weitere Informationen dazu, wann zum Verwenden von Attributen finden Sie unter [Übersicht über Attribute](../../../visual-basic/programming-guide/concepts/attributes/index.md). Informationen über Attributnamen finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="rules"></a>Regeln  
  
-   **Platzierung.** Sie können Attribute, die meisten deklarierten Programmierelementen anwenden. Zum Anwenden von einem oder mehreren Attributen, die Sie setzen eine *Attributblock* am Anfang der Deklaration des Elements. Jeder Eintrag in der Attributliste gibt ein Attribut, die Sie anwenden möchten und die Modifizierer und die Argumente, die Sie für diesen Aufruf des Attributs verwenden.  
  
-   **Spitzen Klammern.** Wenn Sie eine Liste der Attribute angeben, müssen Sie es in spitzen Klammern einschließen ("`<`"und"`>`").  
  
-   **Teil der Deklaration.** Das Attribut muss Teil der Deklaration des Elements, keine separate Anweisung sein. Sie können die Zeilenfortsetzungszeichenfolge (" `_`") der deklarationsanweisung auf mehrere Quellcodezeilen zu erweitern.  
  
-   **Modifizierer.** Ein Attributmodifizierer (`Assembly` oder `Module`) ist erforderlich für jedes Attribut auf ein Programmierelement am Anfang einer Quelldatei angewendet. Attributmodifizierer dürfen nicht auf Attribute, die auf Elemente, die nicht am Anfang einer Quelldatei angewendet.  
  
-   **Argumente.** Alle Variablen oder Eigenschaft-Initialisierer müssen alle Positionsargumente für ein Attribut vorangestellt werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel wendet die <xref:System.Runtime.InteropServices.DllImportAttribute> -Attribut auf eine rumpfdefinition einer `Function` Prozedur.  
  
 [!code-vb[VbVbalrStatements#1](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/attribute-list_1.vb)]  
  
 <xref:System.Runtime.InteropServices.DllImportAttribute> Gibt an, dass die attributierte Prozedur einen Einstiegspunkt in eine nicht verwaltete Dynamic Link Library (DLL) darstellt. Das Attribut stellt den Namen der DLL als positionelle Argumente und den anderen Informationen als Variable Initialisierer.  
  
## <a name="see-also"></a>Siehe auch  
 [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md)  
 [Module \<<schlüsselwort>](../../../visual-basic/language-reference/modifiers/module-keyword.md)  
 [Übersicht über Attribute](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)

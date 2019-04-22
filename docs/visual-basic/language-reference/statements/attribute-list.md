---
title: Attributliste (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
ms.openlocfilehash: 2399ec1342280df101e2818399e0f41f10d9606d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58818416"
---
# <a name="attribute-list-visual-basic"></a>Attributliste (Visual Basic)
Gibt die Attribute, die auf ein deklariertes Programmierelement ein Element angewendet werden. Mehrere Attribute werden durch Kommas getrennt. Es folgt die Syntax für ein Attribut.  
  
## <a name="syntax"></a>Syntax  
  
```  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a>Teile  
|||
|---|---|
|`attributemodifier`|Erforderlich für die Attribute, die am Anfang einer Quelldatei angewendet. Kann [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) oder [Modul](../../../visual-basic/language-reference/modifiers/module-keyword.md).|
|`attributename`| Erforderlich. Der Name des Attributs.|
|`attributearguments`|Dies ist optional. Die Liste positioneller Argumente für dieses Attribut. Mehrere Argumente werden durch Kommas getrennt.|
|`attributeinitializer`|Dies ist optional. Liste der Variablen oder Eigenschaft-Initialisierer für dieses Attribut. Mehrere Initialisierer werden durch Kommas getrennt.|
  
## <a name="remarks"></a>Hinweise  
 Sie können eine oder mehrere Attribute auf fast jedem Programmierelement (Typen, Prozeduren, Eigenschaften und So weiter) anwenden. Attribute, die in den Metadaten der Assembly angezeigt werden, und können Sie Ihren Code zu kommentieren oder angeben, wie ein bestimmtes Programmierelement zu verwenden. Von Visual Basic und .NET Framework definierten Attribute angewendet werden, und Sie können eigene Attribute definieren.  

 Weitere Informationen dazu, wann Sie Attribute verwenden, finden Sie unter [Übersicht über Attribute](../../../visual-basic/programming-guide/concepts/attributes/index.md). Weitere Informationen zu den Attributnamen, finden Sie unter [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="rules"></a>Regeln  
  
-   **Platzierung.** Sie können Attribute auf die meisten deklarierte Programmierelemente anwenden. Um ein oder mehrere Attribute zu übernehmen, Sie platzieren einen *Attributblock* am Anfang der Elementdeklaration. Jeder Eintrag in der Attributliste gibt ein Attribut, die Sie anwenden möchten, und die Modifizierer und Argumente, die Sie für diesen Aufruf des Attributs verwenden.  
  
-   **Spitzen Klammern.** Wenn Sie eine Liste der Attribute angeben, müssen Sie es in spitzen Klammern einschließen ("`<`"und"`>`").  
  
-   **Teil der Deklaration.** Das Attribut muss Teil der Elementdeklaration, nicht auf einer separaten Anweisung sein. Können Sie die Zeilenfortsetzungszeichenfolge (" `_`") zum Erweitern der deklarationsanweisung auf mehrere Quellcodezeilen.  
  
-   **Modifizierer.** Ein Attributmodifizierer (`Assembly` oder `Module`) muss für jedes Attribut angewendet wird, auf ein Programmierelement am Anfang einer Quelldatei. Attributmodifizierer dürfen keine für Attribute, die auf Elemente, die nicht am Anfang einer Quelldatei angewendet.  
  
-   **Argumente.** Alle Positionsargumente für ein Attribut müssen jede Variable oder eine Eigenschaft-Initialisierer vorangestellt sein.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die <xref:System.Runtime.InteropServices.DllImportAttribute> -Attribut auf eine rumpfdefinition einer `Function` Verfahren.  
  
 [!code-vb[VbVbalrStatements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#1)]  
  
 <xref:System.Runtime.InteropServices.DllImportAttribute> Gibt an, dass die attributierte Prozedur einen Einstiegspunkt in eine nicht verwaltete Dynamic Link Library (DLL) darstellt. Das Attribut stellt den Namen der DLL als ein Positionsargument und die anderen Informationen als Variableninitialisierern bereit.  
  
## <a name="see-also"></a>Siehe auch

- [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md)
- [Module \<<schlüsselwort>](../../../visual-basic/language-reference/modifiers/module-keyword.md)
- [Übersicht über Attribute](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [Vorgehensweise: Umbrechen und Zusammenfassen von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)

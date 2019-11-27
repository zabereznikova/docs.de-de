---
title: Attributliste
ms.date: 07/20/2015
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
ms.openlocfilehash: f9332f52622551bb6b944242f71bd80f439982e9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354064"
---
# <a name="attribute-list-visual-basic"></a>Attributliste (Visual Basic)
Gibt die Attribute an, die auf ein deklariertes Programmier Element angewendet werden sollen. Mehrere Attribute werden durch Kommas getrennt. Im folgenden finden Sie die Syntax für ein Attribut.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
[ attributemodifier ] attributename [ ( attributearguments | attributeinitializer ) ]  
```  
  
## <a name="parts"></a>-Komponenten  
|||
|---|---|
|`attributemodifier`|Erforderlich für Attribute, die am Anfang einer Quelldatei angewendet werden. Kann eine [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) oder ein [Modul](../../../visual-basic/language-reference/modifiers/module-keyword.md)sein.|
|`attributename`| Erforderlich Der Name des Attributs.|
|`attributearguments`|Optional. Liste der positionellen Argumente für dieses Attribut. Mehrere Argumente werden durch Kommas getrennt.|
|`attributeinitializer`|Optional. Liste der Variablen-oder Eigenschafteninitialisierer für dieses Attribut. Mehrere Initialisierer werden durch Kommas getrennt.|
  
## <a name="remarks"></a>Hinweise  
 Sie können ein oder mehrere Attribute auf fast alle Programmier Elemente anwenden (Typen, Prozeduren, Eigenschaften usw.). Attribute werden in den Metadaten der Assembly angezeigt, und Sie können Ihnen helfen, Ihren Code zu kommentieren oder anzugeben, wie ein bestimmtes Programmier Element verwendet werden soll. Sie können Attribute anwenden, die durch Visual Basic und die .NET Framework definiert sind, und Sie können eigene Attribute definieren.  

 Weitere Informationen dazu, wann Attribute verwendet werden sollten, finden Sie unter [Übersicht über Attribute](../../../visual-basic/programming-guide/concepts/attributes/index.md). Weitere Informationen zu Attributnamen finden Sie unter [deklarierte Element Namen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="rules"></a>Regeln  
  
- **Praktika.** Sie können Attribute auf die meisten deklarierten Programmier Elemente anwenden. Zum Anwenden eines oder mehrerer Attribute platzieren Sie einen *Attribut Block* am Anfang der Element Deklaration. Jeder Eintrag in der Attribut Liste gibt ein Attribut an, das Sie anwenden möchten, sowie den Modifizierer und die Argumente, die Sie für diesen Aufruf des Attributs verwenden.  
  
- **Spitze Klammern.** Wenn Sie eine Attribut Liste angeben, müssen Sie Sie in spitzen Klammern ("`<`" und "`>`") einschließen.  
  
- **Teil der Deklaration.** Das Attribut muss Teil der Element Deklaration und keine separate Anweisung sein. Sie können die Zeilen Fortsetzungs Sequenz ("`_`") verwenden, um die Deklarations Anweisung auf mehrere Quell Codezeilen zu erweitern.  
  
- **Modifizierer.** Ein Attributmodifizierer (`Assembly` oder `Module`) ist für jedes Attribut erforderlich, das auf ein Programmier Element am Anfang einer Quelldatei angewendet wird. Attributmodifiziererer sind für Attribute, die auf Elemente angewendet werden, die sich nicht am Anfang einer Quelldatei befinden, nicht zulässig.  
  
- **Argumentation.** Alle positionellen Argumente für ein Attribut müssen allen Variablen-oder eigenschafteninitialisierern vorangestellt sein.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird das <xref:System.Runtime.InteropServices.DllImportAttribute>-Attribut auf eine Skeleton-Definition einer `Function` Prozedur angewendet.  
  
 [!code-vb[VbVbalrStatements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#1)]  
  
 <xref:System.Runtime.InteropServices.DllImportAttribute> gibt an, dass die attributierte Prozedur einen Einstiegspunkt in einer nicht verwalteten DLL (Dynamic-Link Library) darstellt. Das Attribut stellt den DLL-Namen als Positions Argument und die anderen Informationen als Variableninitialisierer bereit.  
  
## <a name="see-also"></a>Siehe auch

- [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md)
- [Module \<<schlüsselwort>](../../../visual-basic/language-reference/modifiers/module-keyword.md)
- [Übersicht über Attribute](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)

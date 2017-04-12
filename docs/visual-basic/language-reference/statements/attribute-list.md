---
title: Attributliste (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- attribute list
- attributes [Visual Basic], applying
ms.assetid: 5880073a-68a4-4b6b-8a07-ace32959a4e2
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: e360794ad217784e2358967bfbcc03959cd043b1
ms.lasthandoff: 03/13/2017

---
# <a name="attribute-list-visual-basic"></a>Attributliste (Visual Basic)
Gibt die Attribute, die auf ein deklariertes Programmierelement angewendet werden. Mehrere Attribute werden durch Kommas getrennt. Folgendes ist die Syntax für ein Attribut.  
  
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
 Optional. Liste der Positionsargumente für dieses Attribut. Mehrere Argumente werden durch Kommas getrennt.  
  
 `attributeinitializer`  
 Optional. Liste der Variablen oder Eigenschaft-Initialisierer für dieses Attribut. Mehrere Initialisierer werden durch Kommas getrennt.  
  
## <a name="remarks"></a>Hinweise  
 Sie können ein oder mehrere Attribute auf beinahe jedes Programmierelement (Typen, Prozeduren, Eigenschaften usw.) anwenden. Attribute werden in den Metadaten der Assembly, und können Sie Ihren Code versehen oder angeben, wie bestimmten Programmierelements verwenden. Von Visual Basic und .NET Framework definierten Attribute angewendet werden, und Sie können eigene Attribute definieren.  

 Weitere Hinweise zum Verwenden von Attributen finden Sie unter [Attributes Overview](../../../visual-basic/programming-guide/concepts/attributes/index.md). Informationen über Attributnamen finden Sie unter [Elementnamen deklariert](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="rules"></a>Regeln  
  
-   **Platzierung.** Sie können Attribute auf die meisten deklarierten Programmierelemente anwenden. Um ein oder mehrere Attribute anzuwenden, platzieren Sie ein *Attributblock* am Anfang der Elementdeklaration. Jeder Eintrag in der Attributliste gibt ein Attribut aus, die Sie anwenden möchten und die Modifizierer und die Argumente für diesen Aufruf des Attributs verwendete.  
  
-   **Spitze Klammern.** Wenn Sie eine Attributliste angeben, müssen Sie es in spitze Klammern einschließen ("`<`"und"`>`").  
  
-   **Teil der Deklaration.** Das Attribut muss Teil der Elementdeklaration keine separate Anweisung sein. Können Sie die Zeilenfortsetzungszeichenfolge (" `_`") die deklarationsanweisung auf mehrere Zeilen von Quellcode zu erweitern.  
  
-   **Modifizierer.** Ein Attributmodifizierer (`Assembly` oder `Module`) ist erforderlich für jedes Attribut auf ein Programmierelement am Anfang einer Quelldatei angewendet. Attributmodifizierer dürfen nicht auf Attribute, die auf Elemente, die nicht am Anfang einer Quelldatei angewendet.  
  
-   **Argumente.** Alle Variablen oder Eigenschaft-Initialisierer müssen alle positionelle Argumente für ein Attribut vorangestellt werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird das <xref:System.Runtime.InteropServices.DllImportAttribute>-Attribut auf eine Skelettdefinition einer `Function` Prozedur.</xref:System.Runtime.InteropServices.DllImportAttribute>  
  
 [!code-vb[VbVbalrStatements&#1;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/attribute-list_1.vb)]  
  
 <xref:System.Runtime.InteropServices.DllImportAttribute>Gibt an, dass die attributierte Prozedur einen Einstiegspunkt in eine nicht verwaltete Dynamic Link Library (DLL) darstellt.</xref:System.Runtime.InteropServices.DllImportAttribute> Das Attribut stellt den Namen der DLL als positionelle Argumente und andere Informationen als Variable Initialisierer bereit.  
  
## <a name="see-also"></a>Siehe auch  
 [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md)   
 [Modul \<Schlüsselwort >](../../../visual-basic/language-reference/modifiers/module-keyword.md)   
 [Übersicht über Attribute](../../../visual-basic/programming-guide/concepts/attributes/index.md)   
 [Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)

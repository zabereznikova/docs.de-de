---
title: Der Wert vom Typ "Typ1" kann nicht zu "Typ2" konvertiert werden
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: c8480c6fab2bff931950ebc21d0a8affe3c41c66
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58827145"
---
# <a name="value-of-type-type1-cannot-be-converted-to-type2"></a>Der Wert vom Typ "Typ1" kann nicht zu "Typ2" konvertiert werden
Wert vom Typ "Typ1" kann nicht in 'Typ2' konvertiert werden. Sie können die Value-Eigenschaft den Zeichenfolgenwert des ersten Elements der abzurufenden "\<ParentElement >'.  
  
 Es wurde versucht, ein XML-Literal implizit in einen bestimmten Typ umzuwandeln. Das XML-Literal kann nicht implizit in den angegebenen Typ umgewandelt werden.  
  
 **Fehler-ID:** BC31194  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Verwenden Sie die `Value` -Eigenschaft des XML-Literals, um auf dessen Wert als `String`zu verweisen. Verwenden Sie die `CType` -Funktion, eine weitere Typkonvertierungsfunktion, oder die <xref:System.Convert> -Klasse, um den Wert in den angegebenen Typ umzuwandeln.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Convert>
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md)
- [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)

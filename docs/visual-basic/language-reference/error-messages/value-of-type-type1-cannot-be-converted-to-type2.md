---
title: Der Wert vom Typ "Typ1" kann nicht zu "Typ2" konvertiert werden
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: 8c80429db618e1bcadce1a58a6514d625f0b3cf1
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870232"
---
# <a name="value-of-type-type1-cannot-be-converted-to-type2"></a>Der Wert vom Typ "Typ1" kann nicht zu "Typ2" konvertiert werden

Der Wert vom Typ ' Typ1 ' kann nicht in ' Typ2 ' konvertiert werden. Sie können die Value-Eigenschaft verwenden, um den Zeichen folgen Wert des ersten Elements von "" zu erhalten \<parentElement> .  
  
 Es wurde versucht, ein XML-Literal implizit in einen bestimmten Typ umzuwandeln. Das XML-Literal kann nicht implizit in den angegebenen Typ umgewandelt werden.  
  
 **Fehler-ID:** BC31194  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Verwenden Sie die `Value` -Eigenschaft des XML-Literals, um auf dessen Wert als `String`zu verweisen. Verwenden Sie die `CType` -Funktion, eine weitere Typkonvertierungsfunktion, oder die <xref:System.Convert> -Klasse, um den Wert in den angegebenen Typ umzuwandeln.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Convert>
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [XML-Literale](../xml-literals/index.md)
- [XML](../../programming-guide/language-features/xml/index.md)

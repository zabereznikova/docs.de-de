---
title: Der Ausdruck weist den Typ '<typename>' auf, einen eingeschränkten Typ, der nicht verwendet werden kann, um auf von 'Object' oder 'ValueType' geerbte Member zuzugreifen
ms.date: 07/20/2015
f1_keywords:
- bc31393
- vbc31393
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
ms.openlocfilehash: 017a2458562068727674bd3fd9cda8c33d989e8b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59314619"
---
# <a name="expression-has-the-type-typename-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-object-or-valuetype"></a>Ausdruck weist den Typ "\<Typname >', einen eingeschränkten Typ, kann nicht verwendet werden, um von 'Object' oder 'ValueType' geerbte Member zuzugreifen
Ein Ausdruck ergibt einen Typ, der von der common Language Runtime (CLR) geschachtelt werden kann, aber greift auf ein Element, das Boxing erforderlich.  
  
 *Boxing* bezieht sich auf die Verarbeitung, die zum Konvertieren eines Typs in `Object` oder gelegentlich in <xref:System.ValueType>erforderlich ist. Die common Language Runtime kann nicht bestimmte Typen, z. B. Feld <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, und <xref:System.TypedReference>.  
  
 Dieser Ausdruck versucht, mithilfe der eingeschränkten Typs zum Aufrufen einer Methode geerbt von <xref:System.Object> oder <xref:System.ValueType>, z. B. <xref:System.Object.GetHashCode%2A> oder <xref:System.Object.ToString%2A>. Um diese Methode zugreifen zu können, hat Visual Basic eine implizites Boxing-Konvertierung versucht, die diesen Fehler verursacht.  
  
 **Fehler-ID:** BC31393  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Suchen Sie den Ausdruck, der den angegebenen Typ ergibt.  
  
2. Suchen Sie den Teil der Anweisung, die versucht, die zum Aufrufen der Methode geerbt von <xref:System.Object> oder <xref:System.ValueType>.  
  
3. Schreiben Sie Anweisung um den Methodenaufruf zu vermeiden.  
  
## <a name="see-also"></a>Siehe auch

- [Implizite und explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)

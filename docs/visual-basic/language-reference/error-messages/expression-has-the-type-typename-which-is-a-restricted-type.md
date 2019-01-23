---
title: Ausdruck weist den Typ &#39; &lt;Typename&gt; &#39; , einen eingeschränkten Typ, kann nicht verwendet werden, um über geerbte Member zuzugreifen &#39;Objekt&#39; oder &#39;ValueType&#39;
ms.date: 07/20/2015
f1_keywords:
- bc31393
- vbc31393
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
ms.openlocfilehash: d44b9a29f0848508d8cd814e857d9b01819ce7ab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54535956"
---
# <a name="expression-has-the-type-39lttypenamegt39-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-39object39-or-39valuetype39"></a>Ausdruck weist den Typ &#39; &lt;Typename&gt; &#39; , einen eingeschränkten Typ, kann nicht verwendet werden, um über geerbte Member zuzugreifen &#39;Objekt&#39; oder &#39;ValueType&#39;
Ein Ausdruck ergibt einen Typ, der von der common Language Runtime (CLR) geschachtelt werden kann, aber greift auf ein Element, das Boxing erforderlich.  
  
 *Boxing* bezieht sich auf die Verarbeitung, die zum Konvertieren eines Typs in `Object` oder gelegentlich in <xref:System.ValueType>erforderlich ist. Die common Language Runtime kann nicht bestimmte Typen, z. B. Feld <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, und <xref:System.TypedReference>.  
  
 Dieser Ausdruck versucht, mithilfe der eingeschränkten Typs zum Aufrufen einer Methode geerbt von <xref:System.Object> oder <xref:System.ValueType>, z. B. <xref:System.Object.GetHashCode%2A> oder <xref:System.Object.ToString%2A>. Um diese Methode zugreifen zu können, hat Visual Basic eine implizites Boxing-Konvertierung versucht, die diesen Fehler verursacht.  
  
 **Fehler-ID:** BC31393  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Suchen Sie den Ausdruck, der den angegebenen Typ ergibt.  
  
2.  Suchen Sie den Teil der Anweisung, die versucht, die zum Aufrufen der Methode geerbt von <xref:System.Object> oder <xref:System.ValueType>.  
  
3.  Schreiben Sie Anweisung um den Methodenaufruf zu vermeiden.  
  
## <a name="see-also"></a>Siehe auch
- [Implizite und explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)

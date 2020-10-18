---
title: Der Ausdruck weist den Typ '<typename>' auf, einen eingeschränkten Typ, der nicht verwendet werden kann, um auf von 'Object' oder 'ValueType' geerbte Member zuzugreifen
ms.date: 07/20/2015
f1_keywords:
- bc31393
- vbc31393
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
ms.openlocfilehash: 3e19c0d71ee47ac61e9704f0fcd2637f01aa0896
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163050"
---
# <a name="bc31393-expression-has-the-type-typename-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-object-or-valuetype"></a>BC31393: der Ausdruck weist den Typ ' \<typename> ' auf, bei dem es sich um einen eingeschränkten Typ handelt, der nicht für den Zugriff auf von ' Object ' oder ' ValueType ' geerbte Member verwendet

Ein Ausdruck wird zu einem Typ ausgewertet, der nicht vom Common Language Runtime (CLR) gekapselt werden kann, aber auf einen Member zugreift, der Boxing erfordert.

 *Boxing* bezieht sich auf die Verarbeitung, die zum Konvertieren eines Typs in `Object` oder gelegentlich in <xref:System.ValueType>erforderlich ist. Der Common Language Runtime kann bestimmte Strukturtypen nicht einfeldern, <xref:System.ArgIterator> z <xref:System.RuntimeArgumentHandle> . b <xref:System.TypedReference> ., und.

 Dieser Ausdruck versucht, den eingeschränkten Typ zu verwenden, um eine Methode aufzurufen, die von <xref:System.Object> oder geerbt <xref:System.ValueType> wird, z <xref:System.Object.GetHashCode%2A> . b <xref:System.Object.ToString%2A> . oder. Für den Zugriff auf diese Methode hat Visual Basic versucht, eine implizite Boxing-Konvertierung auszuführen, die diesen Fehler verursacht.

 **Fehler-ID:** BC31393

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Suchen Sie den Ausdruck, der den angegebenen Typ ergibt.

2. Suchen Sie den Teil der Anweisung, der versucht, die Methode aufzurufen, die von oder geerbt wurde <xref:System.Object> <xref:System.ValueType> .

3. Schreiben Sie die Anweisung neu, um den Methodenaufrufe zu vermeiden.

## <a name="see-also"></a>Siehe auch

- [Implizite und explizite Konvertierungen](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)

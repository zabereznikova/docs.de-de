---
title: Verwaltete Klassen, die von einer COM-Klasse abgeleitet werden, können nicht als spät gebunden aufgerufen werden.
ms.date: 07/20/2015
f1_keywords:
- vbrLateboundCallToInheritedComClass
ms.assetid: 7bc16e84-8d29-4f8e-bc4f-002c65c71099
ms.openlocfilehash: 401cb5d7194cbef616c87d59e5b1ed7f923fe6f9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402121"
---
# <a name="managed-classes-derived-from-a-com-class-cannot-be-called-late-bound"></a>Verwaltete Klassen, die von einer COM-Klasse abgeleitet werden, können nicht als spät gebunden aufgerufen werden.

Sie haben versucht, eine verwaltete Klasse, die von einer COM-Klasse abgeleitet wird, als spät gebunden aufzurufen; solche Aufrufe werden nicht unterstützt.

## <a name="to-correct-the-problem"></a>So beheben Sie das Problem

Ändern Sie den Aufruf in früh gebunden.

## <a name="see-also"></a>Weitere Informationen

- [Fehlertypen](../programming-guide/language-features/error-types.md)

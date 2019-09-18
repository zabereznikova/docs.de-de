---
title: Verwaltete Klassen, die von einer COM-Klasse abgeleitet werden, können nicht als spät gebunden aufgerufen werden.
ms.date: 07/20/2015
f1_keywords:
- vbrLateboundCallToInheritedComClass
ms.assetid: 7bc16e84-8d29-4f8e-bc4f-002c65c71099
ms.openlocfilehash: c18f2b6e1751d39ceb81c190f70ee161ca716bc8
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054183"
---
# <a name="managed-classes-derived-from-a-com-class-cannot-be-called-late-bound"></a>Verwaltete Klassen, die von einer COM-Klasse abgeleitet werden, können nicht als spät gebunden aufgerufen werden.

Sie haben versucht, eine verwaltete Klasse, die von einer COM-Klasse abgeleitet wird, als spät gebunden aufzurufen; solche Aufrufe werden nicht unterstützt.

## <a name="to-correct-the-problem"></a>So beheben Sie das Problem

Ändern Sie den Aufruf in früh gebunden.

## <a name="see-also"></a>Siehe auch

- [Fehlertypen](../../visual-basic/programming-guide/language-features/error-types.md)

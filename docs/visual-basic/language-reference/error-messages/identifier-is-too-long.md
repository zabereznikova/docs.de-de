---
title: Der Bezeichner ist zu lang.
ms.date: 07/20/2015
f1_keywords:
- bc30033
- vbc30033
helpviewer_keywords:
- BC30033
ms.assetid: 3d07f6d0-9a2f-49ca-94e8-1e354932e855
ms.openlocfilehash: eafcb2fdf706e12fa606a442ad577c88ed5a7427
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162855"
---
# <a name="bc30033-identifier-is-too-long"></a>BC30033: der Bezeichner ist zu lang.

Der Name oder Bezeichner jedes Programmier Elements ist auf 1023 Zeichen beschränkt. Außerdem darf ein voll qualifizierter Name nicht länger als 1023 Zeichen sein. Dies bedeutet, dass die gesamte `<namespace>.<...>.<namespace>.<class>.<element>` Bezeichnerzeichenfolge () nicht mehr als 1023 Zeichen lang sein darf, einschließlich der Member-Access Operator ( `.` )-Zeichen.

 **Fehler-ID:** BC30033

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Reduzieren Sie die Länge des Bezeichners.

## <a name="see-also"></a>Siehe auch

- [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)

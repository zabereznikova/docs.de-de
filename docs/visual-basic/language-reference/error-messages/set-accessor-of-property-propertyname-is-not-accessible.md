---
title: Auf den Set-Accessor der <propertyname>-Eigenschaft kann nicht zugegriffen werden.
ms.date: 07/20/2015
f1_keywords:
- vbc31102
- bc31102
helpviewer_keywords:
- BC31102
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
ms.openlocfilehash: 3cf828eb5f11090a74a65388e2b89a191046a456
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162244"
---
# <a name="bc31102-set-accessor-of-property-propertyname-is-not-accessible"></a>BC31102: auf den Set-Accessor der Eigenschaft "" kann nicht zugegriffen werden. \<propertyname>

Eine-Anweisung versucht, den Wert einer Eigenschaft zu speichern, wenn Sie keinen Zugriff auf die Prozedur der Eigenschaft hat `Set` .

 Wenn die [Set-Anweisung](../statements/set-statement.md) mit einer restriktiveren Zugriffsebene als die- [Eigenschafts Anweisung](../statements/property-statement.md)gekennzeichnet ist, kann der Versuch, den Eigenschafts Wert festzulegen, in den folgenden Fällen fehlschlagen:

- Die `Set` -Anweisung ist als [Privat](../modifiers/private.md) gekennzeichnet, und der Aufruf Code befindet sich außerhalb der Klasse oder Struktur, in der die Eigenschaft definiert ist.

- Die `Set` -Anweisung ist als [geschützt](../modifiers/protected.md) markiert, und der Aufruf Code ist nicht in der Klasse oder Struktur, in der die Eigenschaft definiert ist, oder in einer abgeleiteten Klasse.

- Die `Set` -Anweisung ist als [Friend](../modifiers/friend.md) gekennzeichnet, und der Aufruf Code befindet sich nicht in derselben Assembly, in der die-Eigenschaft definiert ist.

 **Fehler-ID:** BC31102

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Wenn Sie die Kontrolle über den Quellcode haben, der die Eigenschaft definiert, sollten Sie die `Set` Prozedur mit der gleichen Zugriffsebene wie die Eigenschaft selbst deklarieren.

- Wenn Sie nicht über die Kontrolle über den Quellcode verfügen, der die Eigenschaft definiert, oder Sie die `Set` Prozedur Zugriffsebene über die Eigenschaft selbst einschränken müssen, versuchen Sie, die Anweisung zu verschieben, die den Eigenschafts Wert auf einen Code Bereich festlegt, der einen besseren Zugriff auf die Eigenschaft hat.

## <a name="see-also"></a>Siehe auch

- [Eigenschaftenprozeduren](../../programming-guide/language-features/procedures/property-procedures.md)
- [Vorgehensweise: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](../../programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)

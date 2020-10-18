---
title: Auf den Get-Accessor der <propertyname>-Eigenschaft kann nicht zugegriffen werden.
ms.date: 07/20/2015
f1_keywords:
- vbc31103
- bc31103
helpviewer_keywords:
- BC31103
ms.assetid: 3c346c32-7669-4b04-841d-7a9df9cb703e
ms.openlocfilehash: bd6830e16ba3d1f76c61519b4456832a2efec716
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162907"
---
# <a name="bc31103-get-accessor-of-property-propertyname-is-not-accessible"></a>BC31103: auf den Get-Accessor der Eigenschaft "" kann nicht zugegriffen werden. \<propertyname>

Eine-Anweisung versucht, den Wert einer Eigenschaft abzurufen, wenn Sie keinen Zugriff auf die Prozedur der Eigenschaft hat `Get` .

 Wenn die [Get-Anweisung](../statements/get-statement.md) mit einer restriktiveren Zugriffsebene als die- [Eigenschafts Anweisung](../statements/property-statement.md)gekennzeichnet ist, kann der Versuch, den Eigenschafts Wert zu lesen, in den folgenden Fällen fehlschlagen:

- Die `Get` -Anweisung ist als [Privat](../modifiers/private.md) gekennzeichnet, und der Aufruf Code befindet sich außerhalb der Klasse oder Struktur, in der die Eigenschaft definiert ist.

- Die `Get` -Anweisung ist als [geschützt](../modifiers/protected.md) markiert, und der Aufruf Code ist nicht in der Klasse oder Struktur, in der die Eigenschaft definiert ist, oder in einer abgeleiteten Klasse.

- Die `Get` -Anweisung ist als [Friend](../modifiers/friend.md) gekennzeichnet, und der Aufruf Code befindet sich nicht in derselben Assembly, in der die-Eigenschaft definiert ist.

 **Fehler-ID:** BC31103

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Wenn Sie die Kontrolle über den Quellcode haben, der die Eigenschaft definiert, sollten Sie die `Get` Prozedur mit der gleichen Zugriffsebene wie die Eigenschaft selbst deklarieren.

- Wenn Sie nicht über die Kontrolle über den Quellcode verfügen, der die Eigenschaft definiert, oder wenn Sie die `Get` Prozedur Zugriffsebene mehr als die Eigenschaft selbst einschränken müssen, versuchen Sie, die Anweisung zu verschieben, die den Eigenschafts Wert liest, in einen Code Bereich, der einen besseren Zugriff auf die Eigenschaft hat.

## <a name="see-also"></a>Siehe auch

- [Eigenschaftenprozeduren](../../programming-guide/language-features/procedures/property-procedures.md)
- [Vorgehensweise: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](../../programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)

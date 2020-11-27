---
description: '#C#-Referenz: Nullable'
title: '#C#-Referenz: Nullable'
ms.date: 11/18/2020
f1_keywords:
- '#nullable'
helpviewer_keywords:
- '#nullable directive [C#]'
ms.openlocfilehash: 4c114a09f29769fcc824bcdabdc1d523e33f199d
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099446"
---
# <a name="nullable-c-reference"></a>C#-Referenz: #nullable

Die Präprozessoranweisung `#nullable` legt den *Nullable-Anmerkungskontext* und den *Nullable-Warnungskontext* fest. Die Anweisung steuert, ob Nullable-Anmerkungen wirksam sind und ob Warnungen zur NULL-Zulässigkeit angegeben werden. Jeder Kontext ist entweder *deaktiviert* oder *aktiviert*.

Beide Kontexte können auf Projektebene (außerhalb des C#-Quellcodes) festgelegt werden. Die `#nullable`-Anweisung steuert die Anmerkungs- und Warnungskontexte und hat Vorrang vor anderen Einstellungen auf Projektebene. Eine Anweisung legt die von ihr gesteuerten Kontexte fest, bis sie von einer anderen Anweisung überschrieben wird oder bis zum Ende der Quelldatei.

Die Auswirkungen der Anweisungen lauten wie folgt:

- `#nullable disable`: Diese Anweisung legt die Nullable-Anmerkungskontexte und -Warnungskontexte auf *deaktiviert* fest.
- `#nullable enable`: Diese Anweisung legt die Nullable-Anmerkungskontexte und -Warnungskontexte auf *aktiviert* fest.
- `#nullable restore`: Diese Anweisung stellt die Nullable-Anmerkungskontexte und -Warnungskontexte der Projekteinstellungen wieder her.
- `#nullable disable annotations`: Diese Anweisung legt den Nullable-Anmerkungskontext auf *deaktiviert* fest.
- `#nullable enable annotations`: Diese Anweisung legt den Nullable-Anmerkungskontext auf *aktiviert* fest.
- `#nullable restore annotations`: Diese Anweisung stellt den Nullable-Anmerkungskontext der Projekteinstellungen wieder her.
- `#nullable disable warnings`: Diese Anweisung legt den Nullable-Warnungskontext auf *deaktiviert* fest.
- `#nullable enable warnings`: Diese Anweisung legt den Nullable-Warnungskontext auf *aktiviert* fest.
- `#nullable restore warnings`: Diese Anweisung stellt den Nullable-Warnungskontext der Projekteinstellungen wieder her.

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Präprozessoranweisungen](./index.md)

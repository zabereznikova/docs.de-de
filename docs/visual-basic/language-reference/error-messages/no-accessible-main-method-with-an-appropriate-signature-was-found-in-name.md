---
title: Es wurde keine zugreifbare Main-Methode mit entsprechender Signatur in "<name>" gefunden.
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 6958e778701066760aa74e3b4d566800b7527b76
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871475"
---
# <a name="no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a>Es wurde keine zugreifbare Main-Methode mit entsprechender Signatur in "\<name>" gefunden.

Für Befehlszeilen Anwendungen muss definiert sein `Sub Main` . `Main` muss als deklariert werden `Public Shared` , als ob Sie in einer Klasse definiert ist, oder wie, `Public` Wenn Sie in einem Modul definiert ist.  
  
 **Fehler-ID:** BC30737  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Definieren `Public Sub Main` Sie eine Prozedur für das Projekt. Deklarieren Sie Sie nur dann als `Shared` if und only, wenn Sie Sie in einer Klasse definieren.  
  
## <a name="see-also"></a>Weitere Informationen

- [Struktur von Visual Basic-Programmen](../../programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [Vorgehensweisen](../../programming-guide/language-features/procedures/index.md)

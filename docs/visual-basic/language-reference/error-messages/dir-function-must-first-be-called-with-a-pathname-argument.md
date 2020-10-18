---
title: Die 'Dir'-Funktion muss zuerst mit einem 'PathName'-Argument aufgerufen werden.
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: 7f8191b0ef5452fcf6f3a20c3e0f28ca84ef9c4a
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163427"
---
# <a name="dir-function-must-first-be-called-with-a-pathname-argument"></a>Die 'Dir'-Funktion muss zuerst mit einem 'PathName'-Argument aufgerufen werden.

Ein anfänglicher-Rückruf für die- `Dir` Funktion schließt das-Argument nicht ein `PathName` . Der erste Aufruf von `Dir` muss einen enthalten `PathName` , aber nachfolgende Aufrufe von `Dir` müssen keine Parameter enthalten, um das nächste Element abzurufen.

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Geben Sie `PathName` im Funktions aufrufein Argument an.

## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>

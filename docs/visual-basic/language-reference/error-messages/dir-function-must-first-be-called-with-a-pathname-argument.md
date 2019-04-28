---
title: Die 'Dir'-Funktion muss zuerst mit einem 'PathName'-Argument aufgerufen werden.
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: d255b8dddd098835764f72b8a166eaa08b0353df
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803453"
---
# <a name="dir-function-must-first-be-called-with-a-pathname-argument"></a>Die 'Dir'-Funktion muss zuerst mit einem 'PathName'-Argument aufgerufen werden.
Einen anfänglichen Aufruf der `Dir` Funktion schließt nicht die `PathName` Argument. Der erste Aufruf `Dir` müssen eine `PathName`, aber nachfolgende Aufrufe von `Dir` müssen keine Parameter zum Abrufen des nächsten Elements enthalten.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Geben Sie einen `PathName` Argument im Funktionsaufruf.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>

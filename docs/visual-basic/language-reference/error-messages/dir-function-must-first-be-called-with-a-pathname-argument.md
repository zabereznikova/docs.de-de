---
title: '&#39;Dir&#39; Funktion muss zuerst aufgerufen werden, mit einem &#39;PathName&#39; Argument'
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: 3a271d7c2c2f7b98bae8f3f6fa9b67b65e3548f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="39dir39-function-must-first-be-called-with-a-39pathname39-argument"></a>&#39;Dir&#39; Funktion muss zuerst aufgerufen werden, mit einem &#39;PathName&#39; Argument
Einem ersten Aufruf der `Dir` Funktion schließt nicht die `PathName` Argument. Der erste Aufruf von `Dir` umfasst eine `PathName`, aber nachfolgende Aufrufe `Dir` müssen nicht enthalten Parameter, um das nächste Element abzurufen.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Geben Sie einen `PathName` Argument im Funktionsaufruf.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>

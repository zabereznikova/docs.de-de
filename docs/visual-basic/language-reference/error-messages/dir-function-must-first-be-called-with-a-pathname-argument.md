---
title: Die 'Dir'-Funktion muss zuerst mit einem 'PathName'-Argument aufgerufen werden.
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: 828c715d9aaceef17d030113e7eda302f025ca9d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55282589"
---
# <a name="dir-function-must-first-be-called-with-a-pathname-argument"></a>Die 'Dir'-Funktion muss zuerst mit einem 'PathName'-Argument aufgerufen werden.
Einen anfänglichen Aufruf der `Dir` Funktion schließt nicht die `PathName` Argument. Der erste Aufruf `Dir` müssen eine `PathName`, aber nachfolgende Aufrufe von `Dir` müssen keine Parameter zum Abrufen des nächsten Elements enthalten.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Geben Sie einen `PathName` Argument im Funktionsaufruf.  
  
## <a name="see-also"></a>Siehe auch
- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>

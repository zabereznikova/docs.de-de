---
title: Automatisierungsfehler
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 790b171b8d4022bd6d8b038c4221f24805ae42f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="automation-error"></a>Automatisierungsfehler
Beim Ausführen einer Methode oder Abrufen oder Festlegen einer Eigenschaft einer Objektvariable ist ein Fehler aufgetreten. Der Fehler wurde von der Anwendung gemeldet, mit der das Objekt erstellt wurde.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie die Eigenschaften des `Err`-Objekts, um die Ursache und die Art des Fehlers zu ermitteln.  
  
2.  Verwenden Sie die Anweisung `On Error Resume Next` unmittelbar vor der Zugriffsanweisung, und prüfen Sie dann unmittelbar nach der Zugriffsanweisung auf Fehler hin.  
  
## <a name="see-also"></a>Siehe auch  
 [Fehlertypen](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [Sprechen Sie mit uns](/visualstudio/ide/talk-to-us)

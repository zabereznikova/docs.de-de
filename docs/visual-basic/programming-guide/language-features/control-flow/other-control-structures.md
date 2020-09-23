---
title: Weitere Steuerungsstrukturen
ms.date: 07/20/2015
helpviewer_keywords:
- statements [Visual Basic], control flow
- control structures [Visual Basic]
ms.assetid: 24b811f7-98ba-40ec-8dd3-4d528cfa4574
ms.openlocfilehash: 8e7ca699e532ac7cfbe7918d850e7a28d1b27bcf
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058611"
---
# <a name="other-control-structures-visual-basic"></a>Weitere Steuerungsstrukturen (Visual Basic)

Visual Basic bietet Steuerungsstrukturen, die Ihnen helfen, eine Ressource freizugeben, oder die Häufigkeit, mit der ein Objekt Verweis wiederholt werden muss.  
  
## <a name="usingend-using-construction"></a>Wird verwendet... Ende der Erstellung  

 Bei der `Using...End Using` Erstellung wird ein Anweisungsblock erstellt, in dem Sie eine Ressource, z. b. eine SQL-Verbindung, verwenden können. Optional können Sie die Ressource mit der- `Using` Anweisung abrufen. Wenn Sie den- `Using` Block beenden, gibt Visual Basic die Ressource automatisch frei, sodass Sie für anderen zu verwendenden Code verfügbar ist. Die Ressource muss lokal und verwerfbar sein. Weitere Informationen finden Sie unter [using-Anweisung](../../../language-reference/statements/using-statement.md).  
  
## <a name="withend-with-construction"></a>Mit... Mit Konstruktion beenden  

 Mit der- `With...End With` Konstruktion können Sie einen Objekt Verweis einmal angeben und dann eine Reihe von-Anweisungen ausführen, die auf seine Member zugreifen. Dadurch können Sie Ihren Code vereinfachen und die Leistung verbessern, da Visual Basic den Verweis für jede Anweisung, die darauf zugreift, nicht erneut einrichten muss. Weitere Informationen finden Sie unter [with... End with-Anweisung](../../../language-reference/statements/with-end-with-statement.md).  
  
## <a name="see-also"></a>Siehe auch

- [Ablaufsteuerung](index.md)
- [Entscheidungsstrukturen](decision-structures.md)
- [Schleifenstrukturen](loop-structures.md)
- [Geschachtelte Steuerungsstrukturen](nested-control-structures.md)
- [Using-Anweisung](../../../language-reference/statements/using-statement.md)
- [With...End With-Anweisung](../../../language-reference/statements/with-end-with-statement.md)

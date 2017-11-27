---
title: '&#39; &lt;Eventname&gt;&#39; ist ein Ereignis und kann nicht direkt aufgerufen werden'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords: BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bb987c957a28aa37c40ad975b945c20da4690f6e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="39lteventnamegt39-is-an-event-and-cannot-be-called-directly"></a>&#39; &lt;Eventname&gt;&#39; ist ein Ereignis und kann nicht direkt aufgerufen werden
"<`eventname`>' ist ein Ereignis und kann daher nicht direkt aufgerufen werden. Verwenden einer `RaiseEvent` Anweisung, um ein Ereignis auszulösen.  
  
 Ein Prozeduraufruf gibt ein Ereignis für den Namen der Prozedur. Ein Ereignishandler ist eine Prozedur, aber das Ereignis selbst ist ein signaling Gerät, die ausgelöst und behandelt werden muss.  
  
 **Fehler-ID:** BC32022  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Verwenden einer `RaiseEvent` Anweisung signalisieren eines Ereignisses und das Aufrufen der Prozedur oder Prozeduren, die sie behandeln.  
  
## <a name="see-also"></a>Siehe auch  
 [RaiseEvent-Anweisung](../../../visual-basic/language-reference/statements/raiseevent-statement.md)

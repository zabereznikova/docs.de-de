---
title: "Zu viele Clients für DLL-Anwendung | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID47
ms.assetid: 4b87780b-67ad-4c96-9253-db954a751dad
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1abc9ce574de00db42a33cde478ca80be74e61ff
ms.lasthandoff: 03/13/2017

---
# <a name="too-many-dll-application-clients"></a>Zu viele Clients für die DLL-Anwendung
Die Dynamic Link Library (DLL) für [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Zugriff kann nur eine begrenzte Anzahl von Server-Anwendung aufnehmen. Die Anwendung und anderen Clientanwendungen, die [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Hosts (von denen einige möglicherweise zugegriffen, indem der Anwendung) alle versuchen, Zugriff auf die [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] DLL zur gleichen Zeit.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Reduzieren Sie die Anzahl der geöffneten Programme, die Zugriff auf [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [Fehlertypen](../../visual-basic/programming-guide/language-features/error-types.md)

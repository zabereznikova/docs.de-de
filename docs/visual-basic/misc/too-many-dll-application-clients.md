---
title: "Zu viele Clients für die DLL-Anwendung"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID47
ms.assetid: 4b87780b-67ad-4c96-9253-db954a751dad
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d4b9278134e937ac8bf4626237954432d727ac0d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="too-many-dll-application-clients"></a>Zu viele Clients für die DLL-Anwendung
Die Dynamic Link Library (DLL) für [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] kann nur einer begrenzten Anzahl von Hostanwendungen Zugriff gewähren. Ihre Anwendung und andere Clientanwendungen, die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] - Hosts sind (von denen auf einige möglicherweise von Ihrer Anwendung zugegriffen wird), versuchen gleichzeitig, auf die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] -DLL zuzugreifen.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Reduzieren Sie die Anzahl der geöffneten Anwendungen, die auf [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]zugreifen.  
  
## <a name="see-also"></a>Siehe auch  
 [Fehlertypen](../../visual-basic/programming-guide/language-features/error-types.md)

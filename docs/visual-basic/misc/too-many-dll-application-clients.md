---
title: "Zu viele Clients für die DLL-Anwendung"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID47
ms.assetid: 4b87780b-67ad-4c96-9253-db954a751dad
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d4b9278134e937ac8bf4626237954432d727ac0d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="too-many-dll-application-clients"></a><span data-ttu-id="36a0a-102">Zu viele Clients für die DLL-Anwendung</span><span class="sxs-lookup"><span data-stu-id="36a0a-102">Too many DLL application clients</span></span>
<span data-ttu-id="36a0a-103">Die Dynamic Link Library (DLL) für [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] kann nur einer begrenzten Anzahl von Hostanwendungen Zugriff gewähren.</span><span class="sxs-lookup"><span data-stu-id="36a0a-103">The dynamic-link library (DLL) for [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] can only accommodate access by a limited number of host applications.</span></span> <span data-ttu-id="36a0a-104">Ihre Anwendung und andere Clientanwendungen, die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] - Hosts sind (von denen auf einige möglicherweise von Ihrer Anwendung zugegriffen wird), versuchen gleichzeitig, auf die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] -DLL zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="36a0a-104">Your application and other applications that are [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] hosts (some of which may be accessed by your application) are all attempting to access the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] DLL at the same time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="36a0a-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="36a0a-105">To correct this error</span></span>  
  
-   <span data-ttu-id="36a0a-106">Reduzieren Sie die Anzahl der geöffneten Anwendungen, die auf [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]zugreifen.</span><span class="sxs-lookup"><span data-stu-id="36a0a-106">Reduce the number of open applications accessing [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36a0a-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36a0a-107">See Also</span></span>  
 [<span data-ttu-id="36a0a-108">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="36a0a-108">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)

---
title: Zu viele Clients für die DLL-Anwendung
ms.date: 07/20/2015
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
ms.openlocfilehash: 78b3291531c2097fb4124486f6fbac40e2d13b8e
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="too-many-dll-application-clients"></a><span data-ttu-id="5a88c-102">Zu viele Clients für die DLL-Anwendung</span><span class="sxs-lookup"><span data-stu-id="5a88c-102">Too many DLL application clients</span></span>
<span data-ttu-id="5a88c-103">Die Dynamic Link Library (DLL) für Visual Basic kann nur den Zugriff durch eine begrenzte Anzahl von hostanwendungen aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="5a88c-103">The dynamic-link library (DLL) for Visual Basic can only accommodate access by a limited number of host applications.</span></span> <span data-ttu-id="5a88c-104">Ihre Anwendung und andere Clientanwendungen, die Visual Basic-Hosts sind (von denen einige von der Anwendung zugegriffen werden kann), versuchen gleichzeitig auf die Visual Basic-DLL.</span><span class="sxs-lookup"><span data-stu-id="5a88c-104">Your application and other applications that are Visual Basic hosts (some of which may be accessed by your application) are all attempting to access the Visual Basic DLL at the same time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5a88c-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="5a88c-105">To correct this error</span></span>  
  
-   <span data-ttu-id="5a88c-106">Reduzieren Sie die Anzahl der geöffneten Anwendungen, die Zugriff auf Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5a88c-106">Reduce the number of open applications accessing Visual Basic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a88c-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5a88c-107">See Also</span></span>  
 [<span data-ttu-id="5a88c-108">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="5a88c-108">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)

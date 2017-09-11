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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 18781161d1208e7e8d01f99eb9d655803d249e6e
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="too-many-dll-application-clients"></a><span data-ttu-id="01457-102">Zu viele Clients für die DLL-Anwendung</span><span class="sxs-lookup"><span data-stu-id="01457-102">Too many DLL application clients</span></span>
<span data-ttu-id="01457-103">Die Dynamic Link Library (DLL) für [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Zugriff kann nur eine begrenzte Anzahl von Server-Anwendung aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="01457-103">The dynamic-link library (DLL) for [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] can only accommodate access by a limited number of host applications.</span></span> <span data-ttu-id="01457-104">Die Anwendung und anderen Clientanwendungen, die [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Hosts (von denen einige möglicherweise zugegriffen, indem der Anwendung) alle versuchen, Zugriff auf die [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] DLL zur gleichen Zeit.</span><span class="sxs-lookup"><span data-stu-id="01457-104">Your application and other applications that are [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] hosts (some of which may be accessed by your application) are all attempting to access the [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] DLL at the same time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="01457-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="01457-105">To correct this error</span></span>  
  
-   <span data-ttu-id="01457-106">Reduzieren Sie die Anzahl der geöffneten Programme, die Zugriff auf [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="01457-106">Reduce the number of open applications accessing [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01457-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01457-107">See Also</span></span>  
 [<span data-ttu-id="01457-108">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="01457-108">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)

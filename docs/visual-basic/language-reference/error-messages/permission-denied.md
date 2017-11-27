---
title: Berechtigung verweigert (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID70
ms.assetid: 71f46756-f522-4814-aab4-492bf9924245
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c5d7965ebd42cb3e56d66966d035be9ba3d3957c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="permission-denied-visual-basic"></a><span data-ttu-id="b6e52-102">Berechtigung verweigert (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b6e52-102">Permission denied (Visual Basic)</span></span>
<span data-ttu-id="b6e52-103">Es wurde in einem schreibgeschützten Datenträger zu schreiben oder auf eine gesperrte Datei zuzugreifen versucht.</span><span class="sxs-lookup"><span data-stu-id="b6e52-103">An attempt was made to write to a write-protected disk or to access a locked file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b6e52-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="b6e52-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="b6e52-105">Um eine Datei schreibgeschützt öffnen, ändern Sie das Schreibschutzattribut der Datei.</span><span class="sxs-lookup"><span data-stu-id="b6e52-105">To open a write-protected file, change the write-protection attribute of the file.</span></span>  
  
2.  <span data-ttu-id="b6e52-106">Stellen Sie sicher, dass die Datei nicht von einem anderen Prozess gesperrt hat, und warten Sie zum Öffnen der Datei, bis die andere Prozess, diesen freigibt.</span><span class="sxs-lookup"><span data-stu-id="b6e52-106">Make sure that another process has not locked the file, and wait to open the file until the other process releases it.</span></span>  
  
3.  <span data-ttu-id="b6e52-107">Für den Zugriff auf die Registrierung, überprüfen Sie, dass Ihre Benutzerberechtigungen dieser Typ von Registrierungszugriff umfassen.</span><span class="sxs-lookup"><span data-stu-id="b6e52-107">To access the registry, check that your user permissions include this type of registry access.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6e52-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6e52-108">See Also</span></span>  
 [<span data-ttu-id="b6e52-109">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="b6e52-109">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)

---
title: Automatisierungsfehler
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 790b171b8d4022bd6d8b038c4221f24805ae42f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="automation-error"></a><span data-ttu-id="7d6c4-102">Automatisierungsfehler</span><span class="sxs-lookup"><span data-stu-id="7d6c4-102">Automation error</span></span>
<span data-ttu-id="7d6c4-103">Beim Ausführen einer Methode oder Abrufen oder Festlegen einer Eigenschaft einer Objektvariable ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7d6c4-103">An error occurred while executing a method or getting or setting a property of an object variable.</span></span> <span data-ttu-id="7d6c4-104">Der Fehler wurde von der Anwendung gemeldet, mit der das Objekt erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7d6c4-104">The error was reported by the application that created the object.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7d6c4-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="7d6c4-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="7d6c4-106">Überprüfen Sie die Eigenschaften des `Err`-Objekts, um die Ursache und die Art des Fehlers zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="7d6c4-106">Check the properties of the `Err` object to determine the source and nature of the error.</span></span>  
  
2.  <span data-ttu-id="7d6c4-107">Verwenden Sie die Anweisung `On Error Resume Next` unmittelbar vor der Zugriffsanweisung, und prüfen Sie dann unmittelbar nach der Zugriffsanweisung auf Fehler hin.</span><span class="sxs-lookup"><span data-stu-id="7d6c4-107">Use the `On Error Resume Next` statement immediately before the accessing statement, and then check for errors immediately after the accessing statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d6c4-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d6c4-108">See Also</span></span>  
 [<span data-ttu-id="7d6c4-109">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="7d6c4-109">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [<span data-ttu-id="7d6c4-110">Sprechen Sie mit uns</span><span class="sxs-lookup"><span data-stu-id="7d6c4-110">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)

---
title: Automatisierungsfehler | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID440
dev_langs:
- VB
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b48ada07663889db633a43fabb577d5129c5cbb3
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="automation-error"></a><span data-ttu-id="cf643-102">Automatisierungsfehler</span><span class="sxs-lookup"><span data-stu-id="cf643-102">Automation error</span></span>
<span data-ttu-id="cf643-103">Beim Ausführen einer Methode oder Abrufen oder Festlegen einer Eigenschaft einer Objektvariable ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="cf643-103">An error occurred while executing a method or getting or setting a property of an object variable.</span></span> <span data-ttu-id="cf643-104">Der Fehler wurde von der Anwendung gemeldet, mit der das Objekt erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="cf643-104">The error was reported by the application that created the object.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cf643-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="cf643-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="cf643-106">Überprüfen Sie die Eigenschaften des `Err`-Objekts, um die Ursache und die Art des Fehlers zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="cf643-106">Check the properties of the `Err` object to determine the source and nature of the error.</span></span>  
  
2.  <span data-ttu-id="cf643-107">Verwenden Sie die Anweisung `On Error Resume Next` unmittelbar vor der Zugriffsanweisung, und prüfen Sie dann unmittelbar nach der Zugriffsanweisung auf Fehler hin.</span><span class="sxs-lookup"><span data-stu-id="cf643-107">Use the `On Error Resume Next` statement immediately before the accessing statement, and then check for errors immediately after the accessing statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf643-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf643-108">See Also</span></span>  
 <span data-ttu-id="cf643-109">[Error Types (Fehlertypen)](../../../visual-basic/programming-guide/language-features/error-types.md) </span><span class="sxs-lookup"><span data-stu-id="cf643-109">[Error Types](../../../visual-basic/programming-guide/language-features/error-types.md) </span></span>  
<span data-ttu-id="cf643-110"> [Sprechen Sie mit uns](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span><span class="sxs-lookup"><span data-stu-id="cf643-110"> [Talk to Us](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span></span>

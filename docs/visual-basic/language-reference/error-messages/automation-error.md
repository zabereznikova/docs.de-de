---
title: Automatisierungsfehler
ms.date: 07/20/2015
f1_keywords:
- vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
ms.openlocfilehash: 8370f744b916ce4a797c808ed58c5fc9580e6278
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59304310"
---
# <a name="automation-error"></a><span data-ttu-id="62abb-102">Automatisierungsfehler</span><span class="sxs-lookup"><span data-stu-id="62abb-102">Automation error</span></span>
<span data-ttu-id="62abb-103">Beim Ausführen einer Methode oder Abrufen oder Festlegen einer Eigenschaft einer Objektvariable ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="62abb-103">An error occurred while executing a method or getting or setting a property of an object variable.</span></span> <span data-ttu-id="62abb-104">Der Fehler wurde von der Anwendung gemeldet, mit der das Objekt erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="62abb-104">The error was reported by the application that created the object.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="62abb-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="62abb-105">To correct this error</span></span>  
  
1. <span data-ttu-id="62abb-106">Überprüfen Sie die Eigenschaften des `Err`-Objekts, um die Ursache und die Art des Fehlers zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="62abb-106">Check the properties of the `Err` object to determine the source and nature of the error.</span></span>  
  
2. <span data-ttu-id="62abb-107">Verwenden Sie die Anweisung `On Error Resume Next` unmittelbar vor der Zugriffsanweisung, und prüfen Sie dann unmittelbar nach der Zugriffsanweisung auf Fehler hin.</span><span class="sxs-lookup"><span data-stu-id="62abb-107">Use the `On Error Resume Next` statement immediately before the accessing statement, and then check for errors immediately after the accessing statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62abb-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62abb-108">See also</span></span>

- [<span data-ttu-id="62abb-109">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="62abb-109">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="62abb-110">Sprechen Sie mit uns</span><span class="sxs-lookup"><span data-stu-id="62abb-110">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)

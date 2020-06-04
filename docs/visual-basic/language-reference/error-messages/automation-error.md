---
title: Automatisierungsfehler
ms.date: 07/20/2015
f1_keywords:
- vbrID440
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
ms.openlocfilehash: d62ba57db8bffefb2cfebed705251d87fe285602
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409893"
---
# <a name="automation-error"></a><span data-ttu-id="fdbd1-102">Automatisierungsfehler</span><span class="sxs-lookup"><span data-stu-id="fdbd1-102">Automation error</span></span>

<span data-ttu-id="fdbd1-103">Beim Ausführen einer Methode oder Abrufen oder Festlegen einer Eigenschaft einer Objektvariable ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="fdbd1-103">An error occurred while executing a method or getting or setting a property of an object variable.</span></span> <span data-ttu-id="fdbd1-104">Der Fehler wurde von der Anwendung gemeldet, mit der das Objekt erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="fdbd1-104">The error was reported by the application that created the object.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fdbd1-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="fdbd1-105">To correct this error</span></span>  
  
1. <span data-ttu-id="fdbd1-106">Überprüfen Sie die Eigenschaften des `Err`-Objekts, um die Ursache und die Art des Fehlers zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="fdbd1-106">Check the properties of the `Err` object to determine the source and nature of the error.</span></span>  
  
2. <span data-ttu-id="fdbd1-107">Verwenden Sie die Anweisung `On Error Resume Next` unmittelbar vor der Zugriffsanweisung, und prüfen Sie dann unmittelbar nach der Zugriffsanweisung auf Fehler hin.</span><span class="sxs-lookup"><span data-stu-id="fdbd1-107">Use the `On Error Resume Next` statement immediately before the accessing statement, and then check for errors immediately after the accessing statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdbd1-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fdbd1-108">See also</span></span>

- [<span data-ttu-id="fdbd1-109">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="fdbd1-109">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
- [<span data-ttu-id="fdbd1-110">Sprechen Sie mit uns</span><span class="sxs-lookup"><span data-stu-id="fdbd1-110">Talk to Us</span></span>](/visualstudio/ide/feedback-options)

---
title: 'Vorgehensweise: Verweisen auf die aktuelle Instanz eines Objekts'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: 64d21fe4aaf6fd34bf880373a7ab3067fb67820e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077058"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a><span data-ttu-id="54896-102">Gewusst wie: Verweisen auf die aktuelle Instanz eines Objekts (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54896-102">How to: Refer to the Current Instance of an Object (Visual Basic)</span></span>

<span data-ttu-id="54896-103">Die *aktuelle Instanz* eines-Objekts ist die Instanz, in der der Code gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="54896-103">The *current instance* of an object is the instance in which the code is currently executing.</span></span>  
  
 <span data-ttu-id="54896-104">Verwenden Sie das- `Me` Schlüsselwort, um auf die aktuelle-Instanz zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="54896-104">You use the `Me` keyword to refer to the current instance.</span></span>  
  
### <a name="to-refer-to-the-current-instance"></a><span data-ttu-id="54896-105">So verweisen Sie auf die aktuelle Instanz</span><span class="sxs-lookup"><span data-stu-id="54896-105">To refer to the current instance</span></span>  
  
- <span data-ttu-id="54896-106">Verwenden `Me` Sie das Schlüsselwort, in dem Sie normalerweise den Namen einer Objektvariablen verwenden.</span><span class="sxs-lookup"><span data-stu-id="54896-106">Use the `Me` keyword where you would normally use the name of an object variable.</span></span>  
  
    ```vb  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     <span data-ttu-id="54896-107">Obwohl `Me` sich wie eine Objekt Variable verhält, können Sie Sie nicht deklarieren oder ihr andere zuweisen.</span><span class="sxs-lookup"><span data-stu-id="54896-107">Although `Me` behaves like an object variable, you cannot declare it or assign anything to it.</span></span> <span data-ttu-id="54896-108">`Me` verweist immer auf die aktuelle-Instanz.</span><span class="sxs-lookup"><span data-stu-id="54896-108">`Me` always refers to the current instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54896-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="54896-109">See also</span></span>

- [<span data-ttu-id="54896-110">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="54896-110">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="54896-111">Zuweisung von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="54896-111">Object Variable Assignment</span></span>](object-variable-assignment.md)
- [<span data-ttu-id="54896-112">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="54896-112">Me, My, MyBase, and MyClass</span></span>](../../program-structure/me-my-mybase-and-myclass.md)

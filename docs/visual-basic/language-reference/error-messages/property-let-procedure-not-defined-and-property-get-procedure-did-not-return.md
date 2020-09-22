---
title: Let-Prozedur der Eigenschaft ist nicht definiert, und Get-Prozedur hat kein Objekt zurückgegeben.
ms.date: 07/20/2015
f1_keywords:
- vbrID451
ms.assetid: 8542382a-689f-4e1b-abc0-c1e2dadb92f4
ms.openlocfilehash: fbeaa224ea9e095f86c37e571492d83bc98b4397
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871087"
---
# <a name="property-let-procedure-not-defined-and-property-get-procedure-did-not-return-an-object"></a><span data-ttu-id="7127d-102">Let-Prozedur der Eigenschaft ist nicht definiert, und Get-Prozedur hat kein Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7127d-102">Property let procedure not defined and property get procedure did not return an object</span></span>

<span data-ttu-id="7127d-103">Bestimmte Eigenschaften, Methoden und Vorgänge können nur auf Objekte angewendet werden `Collection` .</span><span class="sxs-lookup"><span data-stu-id="7127d-103">Certain properties, methods, and operations can only apply to `Collection` objects.</span></span> <span data-ttu-id="7127d-104">Sie haben einen Vorgang oder eine Eigenschaft angegeben, der für Sammlungen exklusiv ist, aber das Objekt ist keine Auflistung.</span><span class="sxs-lookup"><span data-stu-id="7127d-104">You specified an operation or property that is exclusive to collections, but the object is not a collection.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7127d-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="7127d-105">To correct this error</span></span>  
  
1. <span data-ttu-id="7127d-106">Überprüfen Sie die Schreibweise des Objekt-oder Eigenschafts namens, oder überprüfen Sie, ob das Objekt ein- `Collection` Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="7127d-106">Check the spelling of the object or property name, or verify that the object is a `Collection` object.</span></span>  
  
2. <span data-ttu-id="7127d-107">Sehen Sie sich die Methode an, die zum `Add` Hinzufügen des Objekts zur Auflistung verwendet wird, um sicherzustellen, dass die Syntax korrekt ist und dass alle Bezeichner richtig geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="7127d-107">Look at the `Add` method used to add the object to the collection to be sure the syntax is correct and that any identifiers were spelled correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7127d-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7127d-108">See also</span></span>

- <xref:Microsoft.VisualBasic.Collection>
